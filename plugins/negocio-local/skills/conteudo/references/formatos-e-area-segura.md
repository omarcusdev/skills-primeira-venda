# Formatos e área segura

As plataformas mudam tamanhos e limites de tempo. Os números abaixo são os que funcionaram num caso real e são um ponto de partida. Antes de publicar, confira na tela de publicação do aplicativo.

## Tamanhos

| Peça | Tamanho em pixels | Proporção | Observação |
|---|---|---|---|
| Post de feed | 1080 x 1350 | 4:5 | Ocupa mais tela que o quadrado |
| Post quadrado | 1080 x 1080 | 1:1 | Serve também para catálogo |
| Carrossel | 1080 x 1350 | 4:5 | Todas as páginas do mesmo tamanho |
| Story | 1080 x 1920 | 9:16 | Imagem ou vídeo curto |
| Reel | 1080 x 1920 | 9:16 | 30 quadros por segundo |
| Capa de destaque | 1080 x 1920 | 9:16 | O ícone fica no centro, num círculo |
| Imagem de catálogo | 1080 x 1080 | 1:1 | Produto inteiro, fundo limpo |
| Criativo de anúncio em vídeo | 1080 x 1920 | 9:16 | No caso, de 6 a 15 s, legível sem som |

## Duração e peso

- No caso, os reels ficaram entre 12 e 25 segundos, os stories em até 15 segundos e os anúncios em vídeo entre 6 e 15 segundos. Os limites de cada plataforma mudam: confira no aplicativo.
- Cada arquivo abaixo de **10 MB**. Foi o limite do envio pelo navegador no caso, e é um bom teto para qualquer envio. Receita de compressão em `video-do-celular.md`.
- Vídeo de anúncio legível **sem som**: preço e como pedir em texto na tela.

## Área segura

A interface do aplicativo cobre o topo (perfil, nome, barra) e a base (legenda, botões, campo de resposta) das peças verticais. Texto e rosto nessas faixas ficam escondidos.

Para 1080 x 1920:

- **Topo:** nada importante acima de 250 px.
- **Base:** nada importante abaixo de 1580 px (os 340 px de baixo ficam livres).
- **Lados:** margem de pelo menos 60 px.
- **Corpo de texto:** pelo menos uns 44 px de altura. O preço pode ser bem maior.

Para o feed de 1080 x 1350: margem de 60 px nos quatro lados. A grade do perfil pode cortar as bordas da peça numa miniatura, então deixe o assunto no centro. Confira no aplicativo.

Se o dono pediu a "aba Reels" ou outra área, confira a posição real no aplicativo e ajuste as margens. Vale mais a simulação com a interface do que o número.

## Como conferir

1. Use as margens acima ao montar a peça, e não depois.
2. Gere uma versão de teste com uma folha de guia: uma imagem que escurece as faixas proibidas. Se a peça é feita por HTML, desenhe duas faixas semitransparentes no topo e na base só na versão de conferência (`pecas-por-codigo.md`).
3. Olhe a peça com a folha de guia. Texto que entra nas faixas escuras sobe ou desce.

## Texto na imagem

- Contraste forte entre o texto e o fundo (alvo: razão de contraste 4,5:1 ou mais para texto pequeno).
- Poucas palavras. Um preço, um nome, uma chamada.
- Português correto, com acento. Preço no formato brasileiro (R$ e vírgula nos centavos), sempre igual ao da ficha.
- Uma cor de destaque por peça, no máximo.
