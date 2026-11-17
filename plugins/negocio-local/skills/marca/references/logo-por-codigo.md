# Logo, perfil e `marca.json` por código

Leia ao gerar logo, versão clara, foto de perfil ou qualquer peça que dependa do nome. Tudo nasce de `marca/marca.json`.

## 1. O arquivo único `marca/marca.json`

Modelo (exemplo inventado). O telefone do negócio mora em `negocio/ficha.md`, que é a fonte única. O campo `telefone` do `marca.json` é só uma cópia, para os geradores de peça lerem num lugar só. Até o número existir, fica `{telefone}`.

```json
{
  "nome": "Doceria Aurora",
  "slogan": "feito com carinho",
  "arroba": "@doceria.aurora",
  "telefone": "{telefone}",
  "cores": {
    "fundo": "#FBF6F1",
    "texto": "#3B2420",
    "destaque": "#C81E3A",
    "apoio": "#B9745A",
    "fundo_perfil": "#CFE3F4"
  },
  "fontes": {
    "destaque": "ferramentas/fontes/Destaque-Regular.ttf",
    "titulo": "ferramentas/fontes/Titulo-SemiBold.ttf",
    "corpo": "ferramentas/fontes/Corpo-Regular.ttf"
  }
}
```

Regras:

- Todo gerador (logo, perfil, rótulo, peça de conteúdo) **lê este arquivo**. Ninguém copia o nome para outro lugar.
- **Telefone:** quando o número do negócio chegar à ficha, atualize `telefone` no `marca.json` no mesmo passo e **regenere logo, rótulos e peças**. Sem isso, as peças saem com `{telefone}` ou com o número antigo. Se a ficha e o `marca.json` divergirem, vale a ficha.
- Trocar o nome = mudar `nome` e `arroba`, **fazer backup da pasta `marca/` e `conteudo/`**, regenerar tudo e **olhar cada peça**. Nome mais largo quebra layout.
- `marca/marca.md` é gerado a partir deste arquivo (cores, fontes, regras de uso). Não mantenha o `.md` e o `.json` à mão em paralelo: no caso, o documento de marca ficou com texto de uma versão antiga do nome.

## 2. Caminho padrão: SVG e página de prova, sem instalar nada

O Claude escreve dois arquivos:

- `marca/logo.svg`, com `<text>` e as fontes escolhidas. Modelo mínimo:

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 900 260">
  <rect width="100%" height="100%" fill="#FBF6F1"/>
  <text x="450" y="150" text-anchor="middle"
        font-family="'Nome da Fonte', cursive" font-size="120" fill="#3B2420">Doceria Aurora</text>
  <text x="450" y="205" text-anchor="middle"
        font-family="'Fonte do Corpo', sans-serif" font-size="32" fill="#7B625B">feito com carinho</text>
</svg>
```

- `ferramentas/marca/prova.html`, **a página que o dono olha para aprovar**. Ela carrega as fontes escolhidas do Google Fonts por `<link>` e mostra o logo e a foto de perfil. Precisa de internet:

```html
<!doctype html>
<meta charset="utf-8">
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Nome+da+Fonte&family=Fonte+do+Corpo&display=block">
<style>
  body{margin:0;background:#FBF6F1;font-family:'Fonte do Corpo',sans-serif}
  .nome{font-family:'Nome da Fonte',cursive;color:#3B2420}
  .perfil{width:1080px;height:1080px;background:#CFE3F4;display:flex;align-items:center;justify-content:center}
  .perfil .nome{font-size:150px}
</style>
<div class="perfil"><span class="nome">Doceria Aurora</span></div>
```

Por que a prova é em HTML: o `logo.svg` aberto sozinho só mostra a fonte certa em quem a tem instalada. Sem ela, o navegador troca por uma fonte comum e o dono aprovaria um logo diferente do real. Diga isso ao dono: o `logo.svg` com `<text>` **não é o arquivo final**. Para a gráfica e para usar em qualquer lugar, converta em contorno (item 3) ou exporte de um editor gráfico com "texto em curvas". Fonte que não está no Google Fonts: peça o arquivo `.ttf` e use `@font-face` apontando para ele, ou vá direto ao item 3.

Foto de perfil: quadrada, 1080 x 1080. As redes cortam em círculo, então o conteúdo fica no miolo (cerca de 60% da largura) e o fundo vai até a borda. Teste a 110 px: o nome tem de continuar legível. Se não ler, use só as iniciais ou um símbolo simples.

**Instagram e WhatsApp não aceitam SVG.** Quem usa `marca/perfil.png` (a skill `presenca-nas-redes`) precisa do PNG. Gere-o pelo item 4 a partir da `prova.html`, ou pelo caminho manual lá descrito.

## 3. Opcional: texto em contorno por Python

Vale a pena quando o dono vai imprimir ou usar o logo fora do navegador. **Antes de instalar qualquer coisa, mostre os comandos e espere o ok.** Python vai num ambiente isolado dentro de `ferramentas/`.

Instalação (só depois do ok):

- **Windows** (instale o Python em python.org, marcando "Add to PATH"):
  `py -m venv ferramentas\.venv` e depois `ferramentas\.venv\Scripts\pip install fonttools uharfbuzz`
- **macOS** (Python 3 pelo instalador do python.org ou pelo gerenciador que você já usa):
  `python3 -m venv ferramentas/.venv && ferramentas/.venv/bin/pip install fonttools uharfbuzz`
- **Linux:**
  `python3 -m venv ferramentas/.venv && ferramentas/.venv/bin/pip install fonttools uharfbuzz`

Coloque os arquivos `.ttf` das fontes em `ferramentas/fontes/` (e a licença em `marca/fontes/`). Fontes `.ttf` estáticas; o código usa o peso padrão do arquivo.

Arquivo `ferramentas/marca/contorno.py` (o Claude escreve no projeto, na hora):

```python
"""Converte texto em contorno SVG, com kerning e ligaduras, e devolve a caixa real do desenho."""
import sys
import uharfbuzz as hb
from fontTools.ttLib import TTFont
from fontTools.pens.svgPathPen import SVGPathPen
from fontTools.pens.boundsPen import BoundsPen
from fontTools.pens.transformPen import TransformPen


def texto_em_contorno(caminho_fonte, texto, tamanho_px):
    """Devolve (d, (x_min, y_min, x_max, y_max)) com y para baixo, como no SVG."""
    with open(caminho_fonte, "rb") as arquivo:
        dados = arquivo.read()
    fonte_hb = hb.Font(hb.Face(dados))
    buffer = hb.Buffer()
    buffer.add_str(texto)
    buffer.guess_segment_properties()
    hb.shape(fonte_hb, buffer, {"kern": True, "liga": True})

    fonte = TTFont(caminho_fonte)
    glifos = fonte.getGlyphSet()
    nomes = fonte.getGlyphOrder()
    escala = tamanho_px / fonte["head"].unitsPerEm

    caneta = SVGPathPen(glifos)
    limites = BoundsPen(glifos)
    x = 0
    for info, pos in zip(buffer.glyph_infos, buffer.glyph_positions):
        matriz = (escala, 0, 0, -escala, (x + pos.x_offset) * escala, -pos.y_offset * escala)
        glifos[nomes[info.codepoint]].draw(TransformPen(caneta, matriz))
        glifos[nomes[info.codepoint]].draw(TransformPen(limites, matriz))
        x += pos.x_advance
    return caneta.getCommands(), limites.bounds


if __name__ == "__main__":
    caminho_fonte, texto, tamanho = sys.argv[1], sys.argv[2], float(sys.argv[3])
    d, caixa = texto_em_contorno(caminho_fonte, texto, tamanho)
    x_min, y_min, x_max, y_max = caixa
    print(f'<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 {x_max-x_min:.1f} {y_max-y_min:.1f}">'
          f'<path transform="translate({-x_min:.1f} {-y_min:.1f})" d="{d}" fill="#000"/></svg>')
```

Arquivo `ferramentas/marca/gerar_marca.py`, que lê o `marca.json` e gera `logo.svg`, `logo-claro.svg` e `perfil.svg`:

```python
"""Lê marca/marca.json e gera logo.svg, logo-claro.svg e perfil.svg com o texto em contorno.
Uso (da raiz do projeto): ferramentas/.venv/bin/python ferramentas/marca/gerar_marca.py
"""
import json
from pathlib import Path

from contorno import texto_em_contorno

RAIZ = Path(__file__).resolve().parents[2]
MARCA = json.loads((RAIZ / "marca" / "marca.json").read_text(encoding="utf-8"))
CORES = MARCA["cores"]


def desenho_do_nome(tamanho_px, cor):
    d, (x_min, y_min, x_max, y_max) = texto_em_contorno(
        str(RAIZ / MARCA["fontes"]["destaque"]), MARCA["nome"], tamanho_px
    )
    largura, altura = x_max - x_min, y_max - y_min
    caminho = f'<path transform="translate({-x_min:.2f} {-y_min:.2f})" d="{d}" fill="{cor}"/>'
    return caminho, largura, altura


def logo(cor_texto, fundo=None):
    margem = 40
    caminho, largura, altura = desenho_do_nome(200, cor_texto)
    total_l, total_a = largura + 2 * margem, altura + 2 * margem
    base = f'<rect width="100%" height="100%" fill="{fundo}"/>' if fundo else ""
    return (
        f'<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 {total_l:.0f} {total_a:.0f}">'
        f'{base}<g transform="translate({margem} {margem})">{caminho}</g></svg>'
    )


def perfil():
    lado = 1080
    # O nome tem de caber no miolo: as redes cortam a foto em círculo.
    caminho, largura, altura = desenho_do_nome(100, CORES["texto"])
    escala = (lado * 0.62) / largura
    x = (lado - largura * escala) / 2
    y = (lado - altura * escala) / 2
    return (
        f'<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 {lado} {lado}">'
        f'<rect width="{lado}" height="{lado}" fill="{CORES["fundo_perfil"]}"/>'
        f'<g transform="translate({x:.1f} {y:.1f}) scale({escala:.4f})">{caminho}</g></svg>'
    )


saida = RAIZ / "marca"
(saida / "logo.svg").write_text(logo(CORES["texto"]), encoding="utf-8")
(saida / "logo-claro.svg").write_text(logo(CORES["fundo"], CORES["texto"]), encoding="utf-8")
(saida / "perfil.svg").write_text(perfil(), encoding="utf-8")
print("Gerados: logo.svg, logo-claro.svg, perfil.svg")
```

Rodar, da raiz do projeto:

- Windows: `ferramentas\.venv\Scripts\python ferramentas\marca\gerar_marca.py`
- macOS e Linux: `ferramentas/.venv/bin/python ferramentas/marca/gerar_marca.py`

Notas do código:

- `uharfbuzz` aplica kerning e ligaduras. `fonttools` transforma cada glifo em `<path>`.
- A caixa (`bounds`) vem do desenho real, e não da métrica da fonte. Por isso o nome fica centrado de verdade, mesmo em fonte manuscrita com laços que passam da linha.
- Nome longo: o perfil reduz a escala para caber em 62% da largura. Se ficar pequeno demais a 110 px, parta o nome em duas linhas (rode o gerador duas vezes e empilhe) ou use só as iniciais.
- O exemplo usa um único nome em uma linha. O slogan e um símbolo entram do mesmo jeito: mais um `texto_em_contorno` e um `<path>` simples.

## 4. PNG da foto de perfil: navegador sem cabeça ou à mão

O PNG sai do navegador que já está na máquina. Use a `ferramentas/marca/prova.html` do item 2 (fontes pelo Google Fonts) ou, se você gerou `perfil.svg` pelo item 3, uma página que só mostra o SVG, que não depende de fonte instalada:

```html
<!doctype html>
<meta charset="utf-8">
<style>html,body{margin:0;background:transparent}img{display:block;width:1080px;height:1080px}</style>
<img src="../../marca/perfil.svg">
```

Comando (ajuste o caminho do navegador; `--virtual-time-budget` dá tempo de as fontes carregarem):

- **macOS:** `"/Applications/Google Chrome.app/Contents/MacOS/Google Chrome" --headless --screenshot=marca/perfil.png --window-size=1080,1080 --force-device-scale-factor=1 --virtual-time-budget=5000 ferramentas/marca/prova.html`
- **Windows, Chrome:** `"C:\Program Files\Google\Chrome\Application\chrome.exe" --headless --screenshot=marca\perfil.png --window-size=1080,1080 --force-device-scale-factor=1 --virtual-time-budget=5000 ferramentas\marca\prova.html`
- **Windows, Edge** (já vem instalado): `"C:\Program Files (x86)\Microsoft\Edge\Application\msedge.exe" --headless --screenshot=marca\perfil.png --window-size=1080,1080 --force-device-scale-factor=1 --virtual-time-budget=5000 ferramentas\marca\prova.html`
- **Linux:** `google-chrome --headless --screenshot=marca/perfil.png --window-size=1080,1080 --force-device-scale-factor=1 --virtual-time-budget=5000 ferramentas/marca/prova.html` (ou `chromium`)

Confira o tamanho do PNG: se vier com barras ou cortado, ajuste `--window-size`. Se não funcionar de primeira, não insista. Caminho manual, sem instalar nada:

1. O dono abre `ferramentas/marca/prova.html` no navegador.
2. Tira um print da área da foto de perfil.
3. Recorta em quadrado (1080 x 1080 se der) no editor do celular ou do computador e salva como `marca/perfil.png`.

Para pré-visualizar o círculo, abra o PNG e confira os cantos cortados.

## 5. Regras de uso do logo (vão para `marca/marca.md`)

- **Respiro mínimo:** pelo menos a altura de uma letra minúscula redonda do nome, em volta do logo.
- **Tamanho mínimo:** cerca de 120 px na tela e 25 mm no impresso. Abaixo disso, use só a foto de perfil ou o símbolo.
- Nada de deformar, esticar, sombra, contorno ou degradê sobre o logo.
- **Versão clara** (logo branco ou creme) só sobre fundo escuro da paleta.
- Sobre foto, só em área calma. Se a foto for movimentada, ponha o logo numa faixa na cor de fundo.
- Nunca junto ou fundido com o logo de outra marca. Respeite a lista de "marcas que não podem aparecer" da ficha.
- Estilo de foto, tom de voz e uso de emoji (no máximo 1 por peça) também entram no `marca.md`, tirados da ficha. Nada de inventar frase de efeito: o slogan sai do dono.

## 6. Conferência antes do ok

1. Abra `ferramentas/marca/prova.html` (caminho padrão) ou `logo.svg`, `logo-claro.svg` e `perfil.svg` com o texto em contorno (item 3) no navegador e olhe.
   Confirme que existe `marca/perfil.png`.
2. Reduza a foto de perfil a 110 px e confirme que o nome lê.
3. Confira o contraste de cada par de cor usado.
4. Mostre ao dono. Só depois do ok dele a marca vai para a Página, o Instagram ou o WhatsApp Business (quem sobe é a skill `presenca-nas-redes`).
