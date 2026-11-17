# Peças por código (opcional)

Para quem quer gerar posts, stories e capas a partir de um modelo, sem editor gráfico. O padrão sem instalar nada continua sendo o editor do celular e o editor gráfico que o dono já usa. Neste caminho o Claude escreve os arquivos no projeto do usuário e gera as imagens.

Duas opções, da mais simples para a mais completa:

1. **HTML e navegador sem cabeça:** um arquivo HTML por peça, e o navegador tira a foto. Não precisa de Node.
2. **Remotion:** peças e vídeos em React. Precisa de Node. Faz sentido para vídeo animado.

Em qualquer uma, as cores, as fontes, o nome e o `{telefone}` vêm de `marca/marca.json`, e o preço vem de `negocio/ficha.md`. Trocar o nome da marca é mudar uma linha e gerar de novo. Depois de trocar, olhe todas as peças: um nome mais largo pode quebrar uma.

## Opção 1: HTML e navegador sem cabeça

Escreva `conteudo/<semana>/F01.html`. Exemplo de post de feed 4:5 (os valores entre chaves vêm da marca e da ficha, o Claude os preenche na hora):

```html
<!doctype html>
<html lang="pt-BR">
<head>
<meta charset="utf-8">
<style>
  :root { --fundo: {fundo}; --texto: {texto}; --destaque: {destaque}; }
  html, body { margin: 0; }
  .peca { width: 1080px; height: 1350px; background: var(--fundo); color: var(--texto);
          font-family: "{fonte_corpo}", sans-serif; position: relative; overflow: hidden; }
  .foto { width: 100%; height: 900px; object-fit: cover; display: block; }
  .titulo { font-family: "{fonte_titulo}", serif; font-size: 72px; margin: 40px 60px 0; }
  .preco { font-size: 64px; color: var(--destaque); margin: 16px 60px 0; font-weight: 700; }
  .pedido { font-size: 44px; margin: 16px 60px 0; }
</style>
</head>
<body>
  <div class="peca">
    <img class="foto" src="../../midia/tratadas/IMG_0412-4x5.jpg" alt="{descrição curta da foto}">
    <div class="titulo">{nome do produto}</div>
    <div class="preco">{preço da ficha}</div>
    <div class="pedido">Peça pelo WhatsApp</div>
  </div>
</body>
</html>
```

Cuidados:

- A foto é sempre a real tratada. Não deforme (`object-fit: cover` corta, não estica).
- Fontes de licença livre, instaladas no computador ou carregadas de um arquivo local. A fonte que não carrega vira uma fonte comum e muda o visual: confira a imagem gerada.
- Margens da área segura (`formatos-e-area-segura.md`).
- Uma peça por arquivo, com o tamanho exato no CSS.

Gerar a imagem com o Chrome ou o Chromium sem cabeça (um navegador que o usuário já tem; se não tem, o caminho é o editor do celular):

- macOS: `"/Applications/Google Chrome.app/Contents/MacOS/Google Chrome" --headless=new --hide-scrollbars --window-size=1080,1350 --screenshot=conteudo/semana-01/F01.png conteudo/semana-01/F01.html`
- Windows (prompt): `"C:\Program Files\Google\Chrome\Application\chrome.exe" --headless=new --hide-scrollbars --window-size=1080,1350 --screenshot=conteudo\semana-01\F01.png conteudo\semana-01\F01.html`
- Linux: `google-chrome --headless=new --hide-scrollbars --window-size=1080,1350 --screenshot=conteudo/semana-01/F01.png conteudo/semana-01/F01.html` (ou `chromium`)

Se a imagem sair com uma faixa branca embaixo, a janela ficou menor que a peça: aumente a altura de `--window-size` e recorte. Abra o PNG e confira o tamanho.

Para a revisão, gere uma segunda versão com as faixas da área segura desenhadas, só para conferência, e nunca a publique.

## Opção 2: Remotion

O Remotion é gratuito para uso individual e para empresas pequenas. Empresa maior precisa de licença paga. Diga isso ao usuário antes e mande conferir as condições atuais em remotion.dev. Se houver dúvida, fique com a opção 1.

Instalar (mostre o comando e peça o ok):

- Node.js: Windows `winget install OpenJS.NodeJS.LTS`, macOS `brew install node`, Linux pelo gerenciador de pacotes ou pelo site oficial.
- Projeto: `npx create-video@latest` na pasta `ferramentas/`, ou o modelo em branco.

Estrutura sugerida:

- `src/kit.tsx`: o kit da marca. Lê cores, fontes, nome e `{telefone}` de um módulo gerado a partir do `marca.json`, e os preços de um módulo gerado a partir da ficha.
- `src/pecas/F01.tsx`, `src/pecas/R01.tsx` etc.: um arquivo por peça. Um agente ou uma pessoa mexe numa peça sem quebrar as outras.
- `src/Root.tsx`: registra cada peça como `Composition`.

Esqueleto de uma peça estática de feed e de um registro:

```tsx
import {AbsoluteFill, Composition, Img, staticFile} from 'remotion';
import {marca} from './kit';

export const F01 = () => (
  <AbsoluteFill style={{backgroundColor: marca.cores.fundo, fontFamily: marca.fontes.corpo}}>
    <Img src={staticFile('fotos/IMG_0412-4x5.jpg')} style={{width: '100%', height: 900, objectFit: 'cover'}} />
    <div style={{fontFamily: marca.fontes.titulo, fontSize: 72, margin: '40px 60px 0', color: marca.cores.texto}}>
      Bolo de cenoura
    </div>
    <div style={{fontSize: 64, margin: '16px 60px 0', color: marca.cores.destaque, fontWeight: 700}}>
      {marca.precos.boloDeCenoura}
    </div>
  </AbsoluteFill>
);

export const Root = () => (
  <Composition id="F01" component={F01} durationInFrames={1} fps={30} width={1080} height={1350} />
);
```

O `src/index.ts` do projeto chama `registerRoot(Root)`. Cada peça nova vira outra `Composition` dentro do `Root` (em um fragmento `<>...</>`). Os arquivos de foto ficam em `public/fotos/`, cópias de `midia/tratadas/`.

Gerar a imagem e o vídeo:

```bash
npx remotion still src/index.ts F01 saida/F01.png
npx remotion render src/index.ts R01 saida/R01.mp4 --crf=21
```

Regras do caso que valem aqui:

- Animação sempre pelo quadro atual (`useCurrentFrame`), não por transição CSS.
- Vídeo real entra pelo componente de vídeo do Remotion, em cima do arquivo tratado.
- Reel sem som: texto na tela, preço e como pedir. Voz só com chave e pedido do usuário (`legendas-e-tom.md`).
- Confira o tamanho do arquivo final (abaixo de 10 MB). Se passar, suba o `--crf` (21, 24, 27).
- Se a foto real não existe ainda, a peça sai com a faixa "RASCUNHO" e não vai para o lote de aprovação.

## O que o Claude não faz aqui

- Código que rode em página de terceiros, nem para publicar. O que sai daqui são arquivos locais.
- Peça com telefone antes de o número do negócio existir: use `{telefone}` e deixe a peça como rascunho.
