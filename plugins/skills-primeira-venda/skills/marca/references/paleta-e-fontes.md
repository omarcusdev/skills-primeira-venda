# Paleta e fontes

## Como tirar as cores do produto

1. Peça fotos do que já existe: embalagem, adesivo, papel, uniforme, fachada, o produto em si.
2. Escolha de 3 a 4 cores que já aparecem nesses objetos. Por exemplo: do adesivo, do papel da embalagem e de um detalhe do próprio produto.
3. Complete com 2 neutros: um fundo claro e um escuro para texto. O escuro nunca é preto puro; um marrom ou azul muito escuro cansa menos.
4. Monte 6 a 8 cores. Cada uma leva nome, hexadecimal, origem e uso.
5. **Se você não conseguiu ver a foto** e definiu a cor pela descrição do dono, diga isso na tabela e peça para ele comparar com o objeto real. Deixe essa comparação como pendência na ficha até o dono confirmar.

Exemplo inventado ("Doceria Aurora"):

| Nome | Hex | Origem | Uso | Contraste sobre o fundo |
|---|---|---|---|---|
| fundo | #FBF6F1 | papel creme da embalagem | fundo padrão | base |
| texto | #3B2420 | chocolate escuro | títulos e corpo | 13,4:1 |
| texto suave | #7B625B | cacau claro | legendas | 5,2:1 |
| destaque | #C81E3A | detalhe vermelho do produto | preço, 1 palavra por peça | 5,3:1 |
| apoio | #B9745A | papel cobre | linhas e faixas, nunca texto pequeno | 3,4:1 |

Os valores do exemplo são ilustrativos. Calcule os seus.

## Contraste (alvo WCAG AA)

Texto normal precisa de razão de contraste de pelo menos 4,5:1. Texto grande (a partir de cerca de 24 px, ou 19 px em negrito) aceita 3:1.

Luminância relativa de uma cor sRGB:

1. Para cada canal R, G, B, divida por 255 e chame de `c`.
2. Se `c <= 0,03928`, o canal é `c / 12,92`. Senão, `((c + 0,055) / 1,055) ^ 2,4`.
3. `L = 0,2126 * R + 0,7152 * G + 0,0722 * B`.

Razão: `(L_claro + 0,05) / (L_escuro + 0,05)`.

O Claude calcula por código ou à mão, para cada par texto e fundo da tabela, e escreve a razão ao lado. Cor que não passa não é usada para texto pequeno.

## Proporção de uso

Ponto de partida: cerca de 70% fundo claro, 20% cor escura de texto, 10% cores de destaque. Uma cor de destaque por peça costuma bastar.

## Fontes

Três papéis: **destaque** (só o nome e o slogan, estilo manuscrito ou display), **título** e **corpo** (legível em etiqueta pequena).

- Procure em fontes de licença livre (por exemplo, as que a Google Fonts publica sob a licença OFL). O dono baixa o arquivo `.ttf`; o Claude não baixa nada sem dizer de onde.
- Anote em `marca/marca.md`: nome da fonte, onde foi baixada e a licença. Guarde o arquivo de licença junto, em `marca/fontes/`.
- Compare de 4 a 6 candidatas para o destaque antes de escolher. Mostre o nome do negócio escrito em cada uma.
- Escolha uma só família de destaque. Corpo e título combinam melhor quando são de famílias diferentes e de peso contrastante.
- Para etiqueta de 5 cm, o corpo precisa continuar legível. Teste imprimindo em tamanho real, ou na tela a 100%.
- Fonte variável (um arquivo com vários pesos) serve na tela, mas o código opcional de `logo-por-codigo.md` usa só o peso padrão do arquivo. Para outro peso, use um arquivo estático daquele peso.
- No logo e nos rótulos, converta o texto em contorno (veja `logo-por-codigo.md`). Assim a gráfica e o celular do cliente não precisam ter a fonte instalada.

## Exemplos por estilo (sugestões, confira a licença atual de cada uma)

- Manuscrita amigável para o nome: Satisfy, Pacifico, Cookie.
- Título com personalidade: Fraunces, Playfair Display, DM Serif Display.
- Corpo neutro: DM Sans, Inter, Nunito Sans.

Estas são só exemplos. O dono pode preferir outras.
