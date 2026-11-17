# IA de imagem (opcional, paga)

É opcional e só entra se o usuário já tem uma chave de um serviço de edição de imagem e pede o uso. Os provedores aparecem aqui só como exemplo (por exemplo, o serviço de imagens da OpenAI ou o do Google). O usuário usa a chave dele, na conta dele. Sem isso, o caminho é foto real tratada, ou pedir foto nova ao dono.

## Quando usar

- **Trocar o fundo** de uma foto boa do produto (um fundo estampado, com logo de outra marca ou bagunçado, por uma parede lisa ou uma bancada neutra), mantendo o enquadramento.
- **Montar uma foto quadrada de catálogo** a partir de recortes de fotos reais do produto, num fundo neutro.
- **Aproximar e desfocar o fundo** de uma foto que já é nítida.

## Quando não usar

- **Para consertar foto ruim.** A IA melhora fundo e enquadramento, mas amplifica o defeito de uma foto de partida ruim e não cria nitidez nova. Imagem refeita a partir de um print borrado tende a perder para a foto real.
- **Para criar produto, pessoa, rosto, pet ou cena que não existe.** Produto de anúncio é sempre foto ou vídeo real. Pessoa gerada por IA não entra.
- **Para mostrar um tamanho, um sabor ou um acabamento que o produto não tem.** A IA não corrige falta de informação: se o tamanho médio e o grande têm a mesma foto, só uma foto real dos dois lado a lado resolve.
- **Para fazer o produto parecer melhor do que é.** O produto na imagem é o produto que se entrega. O art. 37 do Código de Defesa do Consumidor trata de publicidade enganosa; confira o texto atual e, na dúvida, fale com um profissional.

## Antes de gastar

1. Pergunte: o usuário tem a chave? Criou com **limite de gasto** no painel do provedor? Se não, explique como pôr um limite e espere.
2. A chave fica no `.env` do projeto, que o próprio usuário preenche. Crie só um `.env.exemplo` com o nome da variável (por exemplo `CHAVE_IMAGEM=`). O `.env` não vai para e-mail nem nuvem compartilhada; só se a pasta já for um repositório git (conferido, veja `montar-negocio/references/falar-com-o-dono.md`), confirme que `.env` está no `.gitignore`. Nunca peça a chave no chat. Nunca imprima a chave, nem em log. Se o usuário colar uma chave no chat, diga para revogá-la no painel e criar outra.
3. Mostre o plano: quantas imagens, de qual foto, com que prompt, e o **custo estimado**. Como referência, uma imagem de edição num modelo de ponta já saiu a cerca de US$ 0,06, estimado pelos tokens de saída, e mais com várias imagens de referência. O preço muda, então confira na página do provedor. Mostre a conta (imagens x preço) e o total.
4. Comece com **uma** imagem. O usuário olha e compara com o produto real. Só depois do ok o lote roda.
5. O resultado vai para `midia/ia/`, nunca por cima da original. Marque no inventário e no plano que a peça usa IA. As plataformas podem pedir um rótulo de conteúdo feito ou editado com IA; confira as regras do aplicativo antes de publicar.

## Regras fixas para todo prompt

Anexe este bloco a todo pedido de edição (em inglês, porque funcionou melhor nos modelos de imagem; ajuste o texto de cada pedido):

```text
Keep every product exactly as it is in the reference photos: shape, size, color,
toppings, packaging, labels. Do not add, remove, duplicate or restyle any item.
No text, no logos, no brand names, no watermarks (except marks that already
exist on the real packaging). Photorealistic, soft natural light, an honest
small-business product photo, not a render.
```

Dicas de pedido:

- "Use only the products from the references; ignore hands, people and any background from them."
- Diga a quantidade exata ("exactly two", "only one").
- Troca de fundo: "Replace only the background with a plain light wall and a light wooden counter. Keep framing and the product unchanged."
- Se uma referência mostra telefone, nome ou logo de terceiros, não a use ou recorte antes (veja `tratamento-de-fotos.md`).

## Esqueleto do script (opcional)

Se o usuário quer rodar por script, escreva `ferramentas/editar_imagem.py` com as chamadas atuais da documentação do provedor, que mudam. O esqueleto de exemplo, para o serviço de imagens da OpenAI (instalação, com o ambiente criado como em `tratamento-de-fotos.md`: `ferramentas/.venv/bin/pip install openai` no macOS e Linux, `ferramentas\.venv\Scripts\pip install openai` no Windows):

```python
#!/usr/bin/env python3
"""Edita uma imagem a partir de uma foto real. A chave vem do .env; nunca é impressa."""
import base64
import os
import sys
from pathlib import Path

from openai import OpenAI

REGRAS_FIXAS = Path(__file__).with_name("regras-fixas.txt").read_text()


def carregar_env(caminho=".env"):
    for linha in Path(caminho).read_text().splitlines():
        if "=" in linha and not linha.lstrip().startswith("#"):
            nome, valor = linha.split("=", 1)
            os.environ.setdefault(nome.strip(), valor.strip())


def editar(entrada, saida, pedido):
    if Path(saida).exists():
        print(f"já existe, pulando: {saida}")
        return
    cliente = OpenAI(api_key=os.environ["CHAVE_IMAGEM"])
    with open(entrada, "rb") as arquivo:
        resposta = cliente.images.edit(
            model=os.environ["MODELO_IMAGEM"],  # nome do modelo: confira na lista atual do provedor
            image=arquivo,
            prompt=f"{pedido}\n\n{REGRAS_FIXAS}",
        )
    Path(saida).write_bytes(base64.b64decode(resposta.data[0].b64_json))
    print(f"gravado: {saida}")


if __name__ == "__main__":
    carregar_env()
    editar(sys.argv[1], sys.argv[2], sys.argv[3])
```

Grave o bloco "Regras fixas" em `ferramentas/regras-fixas.txt`. O nome do modelo e o formato da resposta mudam: confira a documentação atual antes de rodar. O script pula arquivo que já existe, para não pagar duas vezes pelo mesmo pedido.

## Depois de gerar

Abra a imagem e compare com o produto real:

- O produto está idêntico (forma, cor, cobertura, quantidade)?
- Surgiu texto, logo, mão ou objeto que não existia?
- O fundo ficou plausível e sem borda estranha em volta do produto?

Imagens de edição costumam sair pequenas (algo como 1024 a 1536 px de lado). Em tela cheia de story (1080x1920) elas ficam moles: use como imagem de apoio, de feed ou de catálogo, não como o anúncio principal.

Se uma delas falhar em qualquer item, descarte. Não tente "consertar" a imagem com outro pedido por cima.
