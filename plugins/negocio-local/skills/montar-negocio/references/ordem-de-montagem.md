# Ordem de montagem

A ordem recomendada e o porquê de cada dependência. Corte para o que falta (`negocio/estado.md`). Mostre ao usuário a ordem já cortada, com quem faz cada passo e o custo em dinheiro.

## Em uma linha

Número do negócio primeiro (começa já). Plano leve e marca andam em paralelo enquanto o número não chega. Depois WhatsApp Business, Página, Instagram, conteúdo base, atendimento (com ou sem IA), anúncio (só com tudo pronto) e acompanhamento.

## Os passos

| # | Passo | Skill | Quem faz | Custo em dinheiro | Depende de |
|---|---|---|---|---|---|
| 1 | Número só do negócio (chip ou eSIM) e registro no WhatsApp Business | `presenca-nas-redes` (guia) | **humano** (CPF, pagamento, celular) | chip ou eSIM e a recarga da operadora; o valor depende da operadora | nada. **Começa já**: demora e depende de gente |
| 2 | Plano leve: custos, concorrência, canais de venda, teste curto de venda | `pesquisa-e-plano` | Claude pesquisa; dono passa preços e decide | só a cota do Claude; a versão completa gasta mais e a skill avisa antes | ficha |
| 3 | Marca: nome, paleta, fontes, logo, foto de perfil | `marca` | Claude propõe; dono escolhe o nome | nada por padrão; impressão de rótulo ou adesivo é custo da gráfica | ficha; as peças com telefone esperam o passo 1 (usam `{telefone}`) |
| 4 | Inventário das fotos e vídeos, lista de tomadas | `conteudo` | Claude inventaria; **dono filma e fotografa** | nada | ficha |
| 5 | WhatsApp Business: perfil, saudação, ausência, respostas rápidas, catálogo | `presenca-nas-redes` | **dono** configura no app com o kit do Claude | nada além do passo 1 | passo 1 |
| 6 | Página do Facebook | `presenca-nas-redes` | **dono** cria; Claude entrega o kit | nada | perfil pessoal real do dono como administrador; marca |
| 7 | Ligar o WhatsApp à Página | `presenca-nas-redes` | **dono** confirma o login | nada | passos 5 e 6 |
| 8 | Instagram profissional, ligado à Página | `presenca-nas-redes` | **dono** cria e digita os códigos | nada | passo 1 (o código pode chegar pelo número) e passo 6 |
| 9 | Conteúdo base: alguns posts e o cardápio ou tabela com foto | `conteudo`, `presenca-nas-redes` | Claude prepara; dono aprova item por item; em conta nova, **o dono publica pelo app** | nada; chave paga de imagem ou voz só se o dono quiser | passos 3, 4 e 8 |
| 10 | Atendimento, com ou sem IA | `atendente-ia` | Claude escreve; dono aprova e decide ligar | sem IA, nada. Com IA, a skill diz as condições e o plano pago depois do período de teste antes de o dono decidir | passos 1 e 5 |
| 11 | Anúncio de mensagem para o WhatsApp | `anuncios` | **dono** cria a conta, paga e dá o clique final | verba **mais o imposto** sobre o gasto (no caso, 12% a 15% acima do valor do Gerenciador no cartão; confira na sua fatura) | passos 6 a 10, e a conta da skill `anuncios` dizendo se compensa |
| 12 | Acompanhamento das vendas em ciclos | `acompanhar-vendas` | Claude lê e propõe; dono aprova cada envio | nada além do que já foi escolhido | atendimento rodando e o teste de `pesquisa-e-plano` |

## Por que esta ordem

- **O número vem primeiro.** Chip ou eSIM, CPF e o registro num celular dependem do dono e demoram. Enquanto ele não chega, o Claude trabalha no plano e na marca, que não dependem dele.
- **Número antes da marca impressa.** No caso real, quando o número novo chegou foi preciso refazer criativos, adesivo e etiquetas. E o telefone pessoal impresso num adesivo vazou em toda foto e recorte; a correção foi um adesivo novo. Por isso, até o número existir, as peças usam `{telefone}` e nada com telefone vai para a gráfica.
- **O Instagram espera o número.** O código de verificação pode chegar pelo WhatsApp do número informado. Pedidos de código muito seguidos travam o envio; nesse caso o cadastro por e-mail é o caminho. Quem decide e digita é o dono.
- **A Página precisa de um perfil pessoal real** como administrador. Sem ele, `anuncios` para e explica: não há como contornar.
- **A campanha de WhatsApp precisa de** Página, Instagram ligado, WhatsApp ligado à Página, alguns posts e atendimento pronto. O teste final: alguém de fora manda a mensagem pronta do anúncio e recebe resposta. Se faltar um desses, o anúncio não sai e a skill diz o que falta.
- **Quem chega do anúncio precisa de resposta.** No caso, a primeira pessoa que veio do anúncio ficou sem resposta por causa de um filtro de teste do atendimento e não voltou.
- **Anúncio é o último a ser ligado**, e só depois da conta de quanto pode custar cada venda, com o imposto. A skill `anuncios` diz com franqueza se a primeira compra cobre o anúncio.

## O que pode esperar

Formalização, rótulo definitivo e outras burocracias podem esperar o teste de venda mostrar se o negócio vende, se o dono decidir assim. Registre em `negocio/decisoes.md` que foi decisão dele, com a data. Saúde, segurança e regras de rotulagem do produto não se adiam sem o dono saber: diga o que é obrigatório e confira na fonte oficial.

## Como apresentar a ordem

Uma lista numerada curta, só dos passos que faltam, cada um com "quem faz" e "custo". Peça o ok da ordem inteira numa resposta ("sim" ou os números que ele quer cortar). Esse ok não vale para as ações para fora: cada uma volta a pedir o seu, item por item.

Exemplo de fechamento da apresentação, para um salão que só tem fotos de celular:

```
Ordem proposta (já cortada para o que falta):
1. Número do salão (você, hoje; custo: chip ou eSIM e recarga)
2. Plano leve de preço e concorrência (eu; custo: só a cota do Claude)
3. Marca: nome e logo (eu proponho, você escolhe; sem custo)
4. Lista de tomadas para você gravar o antes e depois (você; sem custo)
5. WhatsApp Business, quando o número chegar (você, com o kit que eu preparo; sem custo)
...
Anúncio e IA no atendimento ficam para o fim, e eu digo o custo de cada um antes de você decidir.
Responda "sim" ou os números que quer cortar.
```

## Lições do caso (amostra pequena, uma doceria)

- Votar uma vez, depois executar. O dono reclamou de páginas de votação repetidas; a votação padrão é uma lista numerada no chat, gravada em `negocio/decisoes.md`.
- O plano de 90 dias virou um teste de 4 semanas com meta, piso e veredito escrito antes. Prove que vende antes de gastar com o resto.
- Guarde votos e decisões em arquivo local: a página de votação do caso sumiu dias depois.
