# Ordem de montagem

A ordem recomendada e o porquê de cada dependência. Corte para o que falta (`negocio/estado.md`). Grave a ordem já cortada em `negocio/estado.md`, com quem faz cada passo e o custo em dinheiro, e mostre ao dono só o resumo (veja "Como apresentar a ordem").

## Em uma linha

Número do negócio primeiro (começa já). Plano curto e marca andam em paralelo, ao mesmo tempo, enquanto o número não chega. Depois WhatsApp Business, Página, Instagram, conteúdo base, atendimento (com ou sem IA), o caminho sem anúncio (Perfil no Google, Status, quem já comprou), anúncio (opcional, só com tudo pronto) e acompanhamento.

## Os passos

| # | Passo | Skill | Quem faz | Custo em dinheiro | Depende de |
|---|---|---|---|---|---|
| 1 | Número só do negócio (chip comum ou eSIM, o chip digital) e registro no WhatsApp Business | `presenca-nas-redes` (guia) | **humano** (CPF, pagamento, celular) | chip ou eSIM e a recarga da operadora; o valor depende da operadora | nada. **Começa já**: demora e depende de gente |
| 2 | Plano curto: custos, concorrência, canais de venda, teste curto de venda | `pesquisa-e-plano` | Claude pesquisa; dono passa preços e decide | nada em dinheiro (usa o plano do Claude do dono); a versão completa usa bem mais e a skill avisa antes | ficha |
| 3 | Marca: nome, paleta, fontes, logo, foto de perfil | `marca` | Claude propõe; dono escolhe o nome | nada por padrão; impressão de rótulo ou adesivo é custo da gráfica | ficha; as peças com telefone esperam o passo 1 (usam `{telefone}`) |
| 4 | Inventário das fotos e vídeos, lista de tomadas | `conteudo` | Claude inventaria; **dono filma e fotografa** | nada | ficha |
| 5 | WhatsApp Business: perfil, saudação, ausência, respostas rápidas, catálogo | `presenca-nas-redes` | **dono** configura no app com o kit do Claude | nada além do passo 1 | passo 1 |
| 6 | Página do Facebook | `presenca-nas-redes` | **dono** cria; Claude entrega o kit | nada | perfil pessoal real do dono como administrador; marca |
| 7 | Ligar o WhatsApp à Página | `presenca-nas-redes` | **dono** confirma o login | nada | passos 5 e 6 |
| 8 | Instagram profissional, ligado à Página | `presenca-nas-redes` | **dono** cria e digita os códigos | nada | passo 1 (o código pode chegar pelo número) e passo 6 |
| 9 | Conteúdo base: alguns posts e o cardápio ou tabela com foto | `conteudo`, `presenca-nas-redes` | Claude prepara; dono aprova item por item; em conta nova, **o dono publica pelo app** | nada; chave paga de imagem ou voz só se o dono quiser | passos 3, 4 e 8 |
| 10 | Atendimento, com ou sem IA | `atendente-ia` | Claude escreve; dono aprova e decide ligar | sem IA, nada. Com IA, a skill diz as condições e o plano pago depois do período de teste antes de o dono decidir | passos 1 e 5 |
| 11 | Caminho sem anúncio: 2 ou 3 canais (Perfil da Empresa no Google, Status, quem já comprou, Instagram com vídeo real), rotina semanal e placar de onde veio cada conversa | `vender-sem-anuncio` | Claude planeja e escreve; **dono** cria o perfil do Google, publica e manda cada mensagem | nada em dinheiro | ficha e passo 1; os posts dependem do passo 9 |
| 12 | Anúncio de mensagem para o WhatsApp (opcional) | `anuncios` | **dono** cria a conta, paga e dá o clique final | verba **mais o imposto** que a Meta cobra por cima do valor do anúncio (o dono confere o percentual na fatura) | passos 6 a 10, de preferência um post do passo 11 que já trouxe conversas, e a conta da skill `anuncios` dizendo se compensa |
| 13 | Acompanhamento das vendas em ciclos | `acompanhar-vendas` | Claude lê e propõe; dono aprova cada envio | nada além do que já foi escolhido | atendimento rodando e o teste de `pesquisa-e-plano` |

## Por que esta ordem

- **O número vem primeiro.** Chip ou eSIM, CPF e o registro num celular dependem do dono e demoram. Enquanto ele não chega, o Claude trabalha no plano e na marca ao mesmo tempo, porque nenhum dos dois depende do número.
- **Número antes da marca impressa.** Trocar o número depois obriga a refazer criativos, adesivo e etiquetas, e telefone pessoal impresso num adesivo aparece em toda foto e recorte. Por isso, até o número existir, as peças usam `{telefone}` e nada com telefone vai para a gráfica.
- **O Instagram espera o número.** O código de verificação pode chegar pelo WhatsApp do número informado. Pedidos de código muito seguidos travam o envio; nesse caso o cadastro por e-mail é o caminho. Quem decide e digita é o dono.
- **A Página precisa de um perfil pessoal real** como administrador. Sem ele, `anuncios` para e explica: não há como contornar.
- **A campanha de WhatsApp precisa de** Página, Instagram ligado, WhatsApp ligado à Página, alguns posts e atendimento pronto. O teste final: alguém de fora manda a mensagem pronta do anúncio e recebe resposta. Se faltar um desses, o anúncio não sai e a skill diz o que falta.
- **Quem chega do anúncio precisa de resposta.** Um erro comum: um filtro de teste do atendimento deixa sem resposta a primeira pessoa que vem do anúncio, e ela não volta.
- **O caminho sem anúncio vem antes do anúncio.** Não custa dinheiro e mostra qual post ou vídeo já traz conversa; esse é o melhor candidato a virar anúncio. O Perfil no Google pode começar assim que houver ficha e número, sem esperar o Instagram.
- **Anúncio é opcional e o último a ser ligado**, e só depois da conta de quanto pode custar cada venda, com o imposto. A skill `anuncios` diz com franqueza se a primeira compra cobre o anúncio.

## O que pode esperar

Formalização, rótulo definitivo e outras burocracias podem esperar o teste de venda mostrar se o negócio vende, se o dono decidir assim. Registre em `negocio/decisoes.md` que foi decisão dele, com a data. Saúde, segurança e regras de rotulagem do produto não se adiam sem o dono saber: diga o que é obrigatório e confira na fonte oficial.

## Como apresentar a ordem

A ordem inteira, com "quem faz" e "custo" em cada passo, vai para `negocio/estado.md`, na seção "Ordem de trabalho". No chat, só o resumo, em poucas linhas e sem bloco de código:

- o que começa hoje, com quem faz e o custo;
- a frase de que o plano e a marca andam em paralelo enquanto o número não chega;
- o resto em uma ou duas linhas, com o custo em dinheiro de cada parte;
- um pedido de ok só: o da ordem ("sim" ou o que ele quer cortar).

Esse ok não vale para as ações para fora: cada uma volta a pedir o seu, item por item.

Exemplo de resumo, para um salão que só tem fotos de celular:

> Gravei a ordem completa em `negocio/estado.md`. O resumo:
>
> **Começa hoje, ao mesmo tempo:**
> 1. Número só do salão: você compra o chip. Custo: o chip e a recarga, no valor da operadora. Vem primeiro porque demora.
> 2. Enquanto o número não chega, eu faço em paralelo um plano curto de preços e concorrência e a marca (nome e logo). Sem custo em dinheiro.
>
> **Depois que o número chegar:** WhatsApp Business, Página, Instagram e os primeiros posts. Você cria as contas com os textos que eu preparo. Sem custo.
>
> **Antes de pagar qualquer anúncio:** o caminho sem anúncio (Perfil no Google, Status e quem já comprou), com uma rotina que cabe na sua semana. Sem custo.
>
> **No fim, se você quiser:** anúncio (a verba mais o imposto que a Meta cobra por cima) e IA no atendimento (ferramenta paga depois de um teste grátis). Eu digo o custo de cada um antes.
>
> Posso seguir nessa ordem? Responda "sim" ou diga o que quer cortar.

## Cuidados ao conduzir

- Votar uma vez, depois executar. Votação repetida cansa o dono; a votação padrão é uma lista numerada curta no chat, com 1 ou 2 decisões por mensagem, gravada em `negocio/decisoes.md`.
- Um plano longo pode virar um teste curto, de 3 a 4 semanas, com meta, mínimo da semana e resultado esperado escritos antes. Provar que vende vem antes de gastar com o resto.
- Guarde votos e decisões em arquivo local: página de votação pode sumir em poucos dias.
