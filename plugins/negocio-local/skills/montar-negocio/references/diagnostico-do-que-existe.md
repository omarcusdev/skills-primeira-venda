# Diagnóstico do que já existe (entrada "completar")

Objetivo: preencher `negocio/estado.md` com o que **tem**, o que **falta** e o que **está ruim**, dizendo **como o Claude sabe** de cada linha. Depois, propor só o que falta.

## Regra de ouro

Nunca marque "tem" sem ter visto ou recebido print. O que o dono só disse que existe fica com a situação **"dito, falta ver"** e, na coluna "como sei", "dito pelo dono". O que ninguém conferiu fica "não verificado". Nenhuma das duas vale como "tem" para decidir a ordem de trabalho: confirme antes de pular a etapa.

Valores da coluna "como sei":

- **visto no navegador**: o Claude leu a página pública, com o usuário olhando.
- **print do dono**: o dono mandou a imagem.
- **dito pelo dono**: está na conversa, sem prova.
- **não verificado**: ninguém olhou.

## Como ler o que é público

- Com Claude in Chrome: abra a página pública do negócio (perfil do Instagram, Página, catálogo do WhatsApp), leia, uma página por vez, com o usuário olhando. Não percorra perfis em sequência e não use o navegador para seguir, curtir ou responder.
- Sem Claude in Chrome: peça os links e leia o que a busca ou a página pública devolver. O que não carregar vira "não verificado" ou pedido de print.
- Se a ferramenta de navegador não responde na primeira tentativa, passe para links e prints sem insistir.

## Checklist por canal

### Público (o Claude lê)

**Instagram**
- É conta profissional? Tem categoria?
- Bio: diz o que vende, onde atende e como pedir?
- Link na bio: existe e abre?
- Destaques: existem, têm capa coerente?
- Últimas postagens: quantas, com que frequência, qual qualidade de foto?
- Está ligado à Página? (aparece o botão de contato e o nome da Página)

**Página do Facebook**
- Categoria, descrição, foto de perfil e capa.
- Botão de WhatsApp (e se o número do botão é o do negócio).
- Quem administra? (O Claude não vê isso sem login: peça print.)

**WhatsApp Business, parte pública**
- Perfil: nome, categoria, descrição, horário, endereço público (só se o dono quer).
- Catálogo: quantos itens, com foto e preço?

**Fotos e identidade**
- Qualidade das fotos (nítidas, bem iluminadas, enviadas por câmera ou comprimidas por mensageiro).
- Dado pessoal visível em foto: telefone pessoal em adesivo, nome de terceiro, rosto de cliente, logo de outro comércio.
- Há autorização de imagem para rosto ou pet de cliente?

### Pede print ou login (o dono mostra)

**WhatsApp Business, parte do app**
- Mensagem de saudação.
- Mensagem de ausência e horário de atendimento.
- Respostas rápidas.
- Etiquetas.
- Forma de pagamento configurada.

**Anúncios**
- Existe conta de anúncios separada? Em qual portfólio de negócios ela nasceu, e de quem é o portfólio?
- Existe forma de pagamento cadastrada? (O print cobre o final do cartão.)
- Campanhas antigas: objetivo, gasto e resultado.

**Número**
- O número do negócio é só do negócio, ou é o pessoal do dono? Está num celular onde o WhatsApp Business roda?

## Lista de prints para pedir

Peça só os que o levantamento precisa, um por linha, cada um com o caminho no app. Quando os três canais forem relevantes, peça de cada um: Instagram, WhatsApp Business e Página do Facebook. No máximo 5 prints por mensagem, os mais importantes primeiro. Os nomes de menu mudam com a versão do app; se o dono não achar, ele diz e o Claude ajuda a localizar. Se o dono não conseguir mandar print, ele descreve a tela: a linha fica "dito, falta ver".

| # | Print | Onde tocar |
|---|---|---|
| 1 | Perfil do Instagram | app do Instagram > sua foto, embaixo à direita > a parte de cima do perfil (foto, nome, bio, link, destaques) |
| 2 | Tipo de conta do Instagram | no perfil, se aparece o botão "Painel profissional", a conta é profissional; senão, menu (três linhas) > procure "Tipo de conta" |
| 3 | Perfil do WhatsApp Business | WhatsApp Business > menu (três pontos no Android, Configurações no iPhone) > Ferramentas para o negócio > Perfil comercial |
| 4 | Catálogo | mesmo caminho > Catálogo |
| 5 | Página do Facebook | app do Facebook > menu (três linhas) > sua Página > a tela inicial dela (nome, foto, botão de WhatsApp) |
| 6 | Saudação | WhatsApp Business > menu (três pontos no Android, Configurações no iPhone) > Ferramentas para o negócio > Mensagem de saudação |
| 7 | Ausência e horário | mesmo caminho > Mensagem de ausência; e o horário em Perfil do negócio |
| 8 | Respostas rápidas | mesmo caminho > Respostas rápidas (a lista toda) |
| 9 | Etiquetas | mesmo caminho > Etiquetas |
| 10 | Forma de pagamento | Gerenciador de Anúncios > Faturamento e pagamentos (cubra o final do cartão e o nome) |
| 11 | Campanhas antigas | Gerenciador de Anúncios > Campanhas, com o período e as colunas de gasto e resultados |
| 12 | Quem administra a Página | Página > Configurações > Acesso à Página (ou o nome que a tela tiver) |

Antes de mandar, o dono cobre o final do cartão, o nome de terceiros e qualquer código.

## Modelo de `negocio/estado.md`

```markdown
# Estado do negócio

Atualizado em: AAAA-MM-DD.

| Canal | Item | Situação | Por quê | Como sei |
|---|---|---|---|---|
| Número | número só do negócio | falta | usa o pessoal do dono | dito pelo dono |
| Instagram | conta profissional | tem | aparece categoria no perfil | visto no navegador |
| Instagram | destaques | dito, falta ver | dono diz que tem 2 destaques | dito pelo dono |
| Instagram | link na bio | está ruim | link abre página que não existe | visto no navegador |
| WhatsApp Business | saudação | não verificado | print ainda não chegou | não verificado |
| Página | botão de WhatsApp | falta | a Página não tem botão | print do dono |
| Anúncios | conta separada | não verificado | dono não sabe dizer | dito pelo dono |
| Fotos | autorização de imagem | falta | 2 fotos com rosto de cliente, sem registro | print do dono |

## Ordem de trabalho (só o que falta, está ruim ou falta ver)
| # | Passo | Quem faz | Custo em dinheiro |
|---|---|---|---|
```

Situação aceita: `tem` (só com visto ou print), `dito, falta ver`, `falta`, `está ruim`, `não verificado`. As linhas "dito, falta ver" e "não verificado" entram no resumo para o dono confirmar antes de pular a etapa.

## O que fazer com o resultado

1. Mostre o quadro ao dono em poucas linhas: o que tem, o que falta, o que está ruim e o que falta ver. O quadro inteiro fica no arquivo.
2. Não refaça o que existe e funciona sem perguntar. Se algo está ruim, diga por quê e proponha o conserto como item para o dono aprovar.
3. Leve só o que falta para `references/ordem-de-montagem.md`.
