# Rótulos e etiquetas

Use só se o negócio vende produto embalado (comida, cosmético, vela, artesanato). Para serviço, esta parte não se aplica.

## Antes de gerar

1. **O número do negócio existe?** Se não, a peça leva `{telefone}` e não vai para a gráfica. Telefone pessoal impresso num adesivo aparece em toda foto e recorte, e o conserto é refazer o adesivo.
2. **Quem confirma os dados do produto é o dono:** ingredientes, alergênicos, peso, validade, conservação. O Claude não preenche isso de cabeça nem copia de produto parecido.
3. Pergunte qual é o suporte: adesivo redondo, etiqueta retangular, selo de caixa. Pergunte o tamanho em mm, ou meça com o dono.

## Tamanho, sangria e resolução

- Trabalhe em **mm reais**. Pixels a 600 dpi: `px = mm / 25,4 * 600`. Um adesivo de 50 mm tem cerca de 1181 px.
- **Sangria** de 2 a 3 mm além do corte, com o fundo até a borda da sangria. Mantenha texto e logo pelo menos 3 mm para dentro do corte.
- Adesivo redondo: a arte é quadrada (com sangria), e o conteúdo importante cabe num círculo um pouco menor que o adesivo.
- Gere SVG para a gráfica (vetor, com texto em contorno) e PNG em 600 dpi para conferir na tela.
- Peça sempre uma prova (uma unidade) antes de imprimir em quantidade.

## Campos de uma etiqueta de comida (ponto de partida)

- nome do produto e marca, com o logo;
- tamanho ou peso, com caixinhas de marcar quando a mesma etiqueta serve a mais de um item (por exemplo, médio e grande);
- "Consumir em até __/__", **em branco**, para o dono preencher à mão;
- conservação (por exemplo, "mantenha refrigerado");
- ingredientes, na ordem que o dono confirmou;
- **alergênicos em destaque:** caixa alta, negrito e contraste alto, perto da lista de ingredientes;
- contato do negócio (`{telefone}` até existir) e @.

## Alergênicos e a faixa RASCUNHO

- Enquanto o dono não confirmar a lista de ingredientes e de alergênicos, a etiqueta sai com uma faixa diagonal ou horizontal escrita **RASCUNHO**, bem visível. A faixa só some quando o dono diz, por escrito, que confirmou.
- Registre a confirmação em `negocio/decisoes.md`.
- Exemplo: a etiqueta de um item sai com a faixa até a receita confirmar trigo, ovos e soja.

## Regra de rotulagem: confira na fonte oficial

A exigência varia com o tipo de produto, o tamanho da embalagem e a venda ser caseira, de pequeno produtor ou industrial. Para alimento embalado, uma referência é a norma da Anvisa sobre alergênicos (RDC 26/2015: caixa alta, negrito, contraste, com altura mínima de letra em embalagem pequena). **Confira a regra atual, para o seu produto, na fonte oficial** (Anvisa, vigilância sanitária local, ou outro órgão do seu ramo). Este material não é parecer jurídico nem sanitário.

## Entrega

- `marca/rotulos/<peça>.svg` e `.png`.
- Uma linha por peça em `negocio/decisoes.md`: tamanho, versão, o que falta confirmar.
- Mostre cada peça ao dono, em tamanho real na tela, antes do ok. Imprimir e pagar é com ele.
