# Entrevista e ficha

A ficha (`negocio/ficha.md`) é a fonte única dos fatos do negócio. Toda skill lê dela. Se um fato mudar, muda aqui primeiro.

## Como conduzir

- No máximo 10 perguntas, em 3 ou 4 blocos. Espere a resposta de um bloco antes do próximo.
- Anote o que o dono disser com as palavras dele. O que ele não souber vira pendência, nunca chute.
- Pergunte cedo as duas coisas que no caso real custaram caro: **marcas vizinhas ou parentes que não podem aparecer** e **a região**. A regra "não citar a marca do vizinho" chegou depois de cerca de 30 peças prontas e derrubou 8. E sem a região, a pesquisa de mercado saiu genérica.
- O telefone do negócio só entra na ficha quando existir. Até lá, as peças usam o marcador `{telefone}`.
- Telefone pessoal, e-mail pessoal e endereço da casa não entram na ficha como dado público. Se o dono passar, marque "uso interno, nunca em peça".

## As perguntas

**Bloco 1: o que é o negócio**
1. O que vende ou que serviço presta? Quais são os 3 a 5 itens principais?
2. Quais os preços de hoje? (Se não houver tabela, o dono diz de cabeça e a ficha marca "dito pelo dono".)
3. Quem atende e em que horário? Quem responde as mensagens?

**Bloco 2: como o cliente chega e paga**
4. Como o cliente pede ou marca hoje (WhatsApp, ligação, na porta, aplicativo)?
5. Entrega, retirada ou atendimento no local? Se entrega, como se cobra o frete?
6. Formas de pagamento aceitas.

**Bloco 3: lugar, tom e o que já existe**
7. Cidade e região. É para a pesquisa e nunca vai para peça pública sem ok.
8. Tom de voz: como o dono falaria com o cliente? (Formal, de vizinho, divertido.) O que o negócio nunca diria?
9. O que já existe: embalagem, adesivo, uniforme, fachada, fotos, perfis, número de WhatsApp.

**Bloco 4: limites**
10. Quanto pode gastar (por mês, e em anúncio) e em quanto tempo quer ver resultado? E quais marcas vizinhas, parentes ou pessoas não podem aparecer?

Se o dono já respondeu algo no pedido inicial, não repita a pergunta.

## Modelo de `negocio/ficha.md`

```markdown
# Ficha: <nome do negócio ou "sem nome ainda">

Atualizada em: AAAA-MM-DD. Fonte de cada dado: dito pelo dono, print, visto no navegador.

## O negócio
- O que vende ou presta:
- Itens principais:
- Quem atende e horário:

## Preços (fonte: dito pelo dono, em AAAA-MM-DD)
| Item | Preço |
|---|---|

## Pedido, entrega e pagamento
- Como o cliente pede ou marca hoje:
- Entrega, retirada ou no local:
- Frete:
- Formas de pagamento:

## Contato público
- Telefone do negócio: {telefone}   (só quando existir)
- Instagram / Página:

## Região (só para pesquisa; nunca em peça pública sem ok)
- Cidade e bairro:

## Tom
- Como falamos:
- O que nunca dizemos:

## O que já existe
- Embalagem, adesivo, fotos, perfis:

## Limites
- Marcas vizinhas ou pessoas que não podem aparecer:
- Verba e prazo:

## Atendimento com IA (só se usar o oZapOnline, depois de conectar)
- connection_id:
- Últimos 4 dígitos do número do negócio:

## Uso interno (nunca em peça pública)
- Telefone pessoal, e-mail pessoal, endereço da casa:

## Pendências
- [ ] pergunta ainda sem resposta
```

## Modelo de `negocio/decisoes.md`

Uma linha por decisão ou por ok de item. Formato único, para todas as skills: `data | tipo | item | o que | quem aprovou | o que aconteceu`. Tipo é `decisão`, `ok` ou `autorização`. A última coluna fica vazia até acontecer (por exemplo, "publicado pelo usuário no app"). Ordem de cima para baixo, a mais nova no fim. Modelo:

```markdown
# Decisões e oks

AAAA-MM-DD | decisão | ordem | ordem de montagem aprovada | usuário |
AAAA-MM-DD | decisão | burocracia | formalização e rótulo definitivo ficam para depois do teste de venda | dono |
AAAA-MM-DD | ok | item 2 do lote de posts | post "vitrine da semana" | usuário | publicado pelo usuário no app
AAAA-MM-DD | autorização | dados dos clientes | dono autoriza o tratamento dos dados dos clientes dele (agência) | dono, por escrito |
```

Se o dono decidir contra a recomendação do Claude, registre a decisão dele e a divergência. Execute o que o dono decidiu.

## Exemplos inventados (para o Claude se guiar, nunca para copiar)

**Salão Brisa (salão de beleza).** Serviços: corte, escova, coloração, manicure. Preços: corte feminino, escova e coloração com valor "a partir de", dito pelo dono. Atende de terça a sábado, duas profissionais. Cliente marca por WhatsApp e por ligação. No local, aceita Pix, débito e crédito. Tom: simpático, de vizinha. Nunca diz: "promoção imperdível", preço que não está na tabela. Existe: avental com o nome, fotos de antes e depois feitas no celular (só 2 com autorização de rosto). Telefone do negócio: `{telefone}` até a linha existir.

**Pet Folha (pet shop).** Serviços: banho, tosa, venda de ração a granel. Horário: segunda a sábado. Cliente chama por WhatsApp e leva o animal; há busca e entrega por uma taxa fixa, dita pelo dono. Pagamento: Pix e cartão. Tom: carinhoso, sem diminutivo exagerado. Nunca diz: prazo de entrega sem confirmar a agenda. Limite: não pode aparecer foto de animal sem autorização do tutor.

**Lanchonete Esquina Azul (lanchonete).** Cardápio fechado de 12 itens, preços em tabela. Abre de quinta a domingo à noite. Pede por WhatsApp; entrega no bairro com taxa por faixa, retirada no balcão. Pagamento na entrega: Pix, dinheiro, cartão. Tom: rápido e direto. Nunca diz: que tem item que acabou sem o dono confirmar. Verba: pequena, para um teste de 3 semanas.

**Doceria Aurora (doceria caseira).** Cinco produtos, pronta-entrega e encomenda. Retirada combinada com o cliente; frete pelo aplicativo de entrega, pago pelo cliente. Pagamento por Pix. Marcas vizinhas que não aparecem: as de outros comércios da mesma rua. Pendência: ingredientes e alergênicos de cada item, só o dono confirma.
