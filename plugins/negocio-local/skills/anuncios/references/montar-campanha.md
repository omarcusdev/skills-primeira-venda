# Montar a campanha

Os nomes de menu e os campos da Meta mudam. O que está aqui é a ideia e a ordem; confira na tela do usuário.

## Duas opções

### Opção A: impulsionar um post pelo app

É o caminho de menor atrito para quem nunca abriu o Gerenciador: o dono escolhe um post bom no Instagram ou na Página, toca em impulsionar, define destino (mensagem no WhatsApp), público, verba e dias.

O que perde: o rastreio por anúncio (fica mais difícil dizer qual criativo vendeu) e o controle fino de horário. Serve para a primeira rodada de uma conta nova, ou de um perfil recente.

Pelo celular: no app do Instagram, abra o post e toque em "Impulsionar"; no app do Facebook, abra a Página, o post e "Impulsionar publicação". Os nomes mudam; confira na tela com o dono.

A skill ainda faz o resto: a conta de `conta-antes-de-gastar.md`, a mensagem pronta com código, o resumo do ok e a leitura. O toque em "impulsionar" e o pagamento são do dono.

### Opção B: campanha no Gerenciador

Dá o controle por anúncio e a programação de horário. Em conta sem histórico, o humano clica em tudo e o Claude guia. Em conta que já rodou, veja `subir-pelo-navegador.md`.

## O que escolher na opção B

- **Objetivo:** campanha de mensagens, com destino WhatsApp. Por exemplo: engajamento, mensagens, WhatsApp (os nomes mudam).
- **Posicionamentos:** os automáticos servem para começar. Confira como a peça aparece em feed e em story antes do ok.
- **Local:** um raio pequeno em volta do negócio (por exemplo, 2 km), pessoas que moram ou estiveram ali. Marque o ponto no mapa e confira no mapa se o pino caiu no bairro certo. Se o público estimado ficar pequeno demais, aumente o raio e diga ao dono.
- **Idade:** 18+. Sem interesses e sem gênero na primeira rodada, para a Meta ter espaço de achar quem responde.
- **Orçamento diário ou total:** programar horário exige orçamento total, e a grade aceita só hora cheia (se o atendimento vai até 19h30, escolha 19h ou 20h e diga o motivo). O conjunto com orçamento diário não troca de tipo: duplique o conjunto. Orçamento total com data de fim muito curta entrega devagar em público pequeno. Orçamento total longo vira rajada depois de uma parada. Prefira blocos de 3 a 4 dias.
- **Horário:** só no horário em que alguém atende. Se a IA atende, diga ao dono que o cliente que precisar dele (frete, foto, encomenda) vai esperar. Confira, depois, em que horas chegaram as conversas e em que horas saíram as vendas: acontece de a janela escolhida terminar antes do horário em que as vendas saem.
- **Desligue** as melhorias e variações geradas por IA da Meta: imagem, animação, música, mídia flexível, melhoria de texto. Elas podem mostrar uma cena que não é o produto real. Algumas aparecem de novo num aviso ao publicar: recuse de novo.

## Mensagem pronta com código por anúncio

A mensagem pronta é o texto que já vem escrito no WhatsApp do cliente quando ele toca no botão. Faça uma por anúncio, cada uma com um código curto no fim, por exemplo "Oi! Vi o anúncio e quero marcar um horário (B2)". O cliente pode apagar o código: o que chegar sem ele entra como "origem não anotada".

Dois cuidados:

- Uma mensagem muito curta ("Quero ver o cardápio") torna o tráfego fácil de reconhecer, mas leva o cliente a pedir só o cardápio e parar. Prefira uma mensagem que já diga o que ele quer fazer (pedir para hoje, marcar um horário). Isso é hipótese, ainda não testada.
- Em editor da Meta, a mensagem pronta fica num modelo salvo. Ao duplicar um anúncio, confira que o modelo certo foi escolhido de novo, senão volta o modelo sugerido.

## Um criativo por anúncio

- Um anúncio por criativo, não várias frases ou imagens dentro do mesmo anúncio. Com verba pequena a Meta não separa o resultado de cada uma, e o teste vira um só.
- Mesmo com anúncios separados, a Meta concentra o gasto no que parece melhor. Comparar com pouco gasto não diz muito. Por isso o corte é por conversas e vendas, não por quem gastou mais.
- Material real primeiro: vídeo curto gravado pelo dono, mostrando o produto ou o serviço de verdade. Arte gráfica só depois, e sem prometer o que a ficha não sustenta. Veja a skill `conteudo`.
- Reel e story: a parte de baixo da tela fica coberta por legenda e botão do anúncio. Não desenhe o botão "chama no WhatsApp" lá embaixo, e deixe o texto na área segura.
- Preço e oferta do criativo vêm só de `negocio/ficha.md`.

## Quantos dias até ter o que ler

Conversas por dia = verba diária no Gerenciador ÷ custo por conversa esperado. Dias para cerca de 10 conversas por grupo = 10 × número de grupos ÷ conversas por dia.

Exemplo inventado: verba R$ 24 por dia, custo esperado por conversa R$ 8: 3 conversas por dia. Com 3 criativos: 10 × 3 ÷ 3 = 10 dias. Se a rodada dura 4 dias, não dá: proponha um criativo só (10 ÷ 3, cerca de 4 dias) ou aceite que a leitura será "não conclusiva".

## Critério escrito antes (modelo)

```
Rodada N
- Verba (Gerenciador) e estimativa no cartão com imposto: ______
- Período e horário (quem atende nele): ______
- Raio e público: ______
- Criativos: A (código), B (código) ...
- Corte: pausar o anúncio com R$ ______ gastos (uns R$ ______ no cartão) e nenhuma conversa, com ok.
- Leitura: com cerca de 10 conversas por grupo; decidir por venda.
- Passa / ajusta / para: ______
```

## Checklist do resumo para o ok

Mostre, numa lista numerada, para o dono responder "sim 1, 3":

1. Conta e portfólio (nome na tela).
2. Valor no Gerenciador e estimativa no cartão com imposto.
3. Período, horário e orçamento (diário ou total).
4. Criativos (a peça e o texto exatos, ou o post escolhido).
5. Público e raio, com o ponto do mapa conferido.
6. Mensagem pronta de cada anúncio, com o código.
7. Número de destino do WhatsApp, lido na tela.
8. Melhorias automáticas: desligadas.

Item sem "sim" não segue. Grave os oks em `negocio/decisoes.md`. Todo valor do resumo, inclusive o de pausa e de corte, vai com a estimativa no cartão ao lado.

## Passo a passo para o dono

Sem Claude in Chrome, grave o passo a passo em `anuncios/rodada-N/passo-a-passo.md`, com os campos e os valores. Se o dono só usa celular, escreva pelo app (opção A). No chat, mande só os próximos 3 passos, na ordem, e diga quanto tempo leva. Depois que ele fizer, mande os 3 seguintes.
