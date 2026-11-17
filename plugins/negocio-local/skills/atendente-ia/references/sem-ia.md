# Atendimento sem IA (WhatsApp Business)

Este é um caminho completo. O Claude escreve os textos; o dono atende pelo WhatsApp Business no celular do negócio. Não custa nada de ferramenta.

O que o Claude entrega a partir do `atendente/prompt.md` e da ficha:

1. Saudação.
2. Mensagem de ausência.
3. Respostas rápidas (atalhos que o dono chama digitando "/").
4. Roteiro de atendimento para o dono.
5. Etiquetas sugeridas para organizar os contatos.

O kit vai para `publicar/` e a skill `presenca-nas-redes` explica como levar ao celular e o que só se configura no app. Confira os nomes das opções no app: eles mudam.

## O que é com o dono

Colar cada texto, preencher os campos entre colchetes (chave Pix, endereço de retirada, agenda), responder cada cliente e confirmar pedidos. Campos como a chave Pix só o dono preenche; o Claude deixa `[chave Pix]` e não pede nem guarda o dado.

## Saudação (modelo inventado: Doceria Aurora)

```
Oi! Aqui é a Doceria Aurora. Já te mando o cardápio. Me diz o que você quer e se é para retirada ou entrega.
```

Saudação e ausência são mensagens automáticas do app. Aqui quem responde depois é o dono; não prometa um prazo de resposta que ele não vai cumprir.

## Mensagem de ausência (modelo)

```
Oi! Agora estamos fechados. Atendemos todos os dias, das 10h às 20h. Deixe seu pedido aqui que a gente responde assim que abrir.
```

## Respostas rápidas (7 para começar)

| Atalho | Para quê | Texto-modelo |
|---|---|---|
| /cardapio | Mandar itens e preços | "Nosso cardápio de hoje: [itens e preços da ficha]. Quer pedir?" |
| /horario | Horário | "Atendemos todos os dias, das 10h às 20h." |
| /entrega | Entrega e frete | "Entregamos nos bairros [lista]. O frete fica em torno de [faixa], e eu confirmo o valor certinho." |
| /pagamento | Forma de pagamento | "Aceitamos [formas]. Para Pix, eu te mando a chave quando confirmar o pedido: [chave Pix]." |
| /retirada | Retirada | "A retirada é combinada por aqui. Me diz o horário que prefere." |
| /pedido | Resumo do pedido | "Teu pedido: [itens] = R$ [total]. [Entrega para X, frete em torno de R$ Y | Retirada às HH]." |
| /obrigado | Encerrar | "Obrigada pelo pedido! Qualquer coisa é só chamar." |

Preços, bairros e faixas vêm só da ficha. Item que a ficha não tem fica como pergunta ao dono.

## Roteiro do dono (uma página)

1. Respondeu em até alguns minutos no horário de atendimento? Cliente que espera esfria.
2. Primeira mensagem: saudação e uma pergunta.
3. Confirme itens e total antes de falar de entrega.
4. Retirada ou entrega? Anote horário, e endereço se for entrega.
5. Se o dono quiser medir de onde vêm as vendas, pergunte como o cliente conheceu o negócio e anote. É sugestão: só entra no roteiro com o ok dele.
6. Mande o resumo com `/pedido` e confirme o pagamento você mesmo.
7. Etiquete o contato (por exemplo: novo, pediu, pago, entregue).
8. Cliente que disse "depois eu vejo": responda uma vez e não insista.
9. Reclamação, alergia e dúvida de ingrediente: responda você, com calma, sem decorar frase pronta.

## Etiquetas sugeridas

Novo contato, Pediu, Aguardando pagamento, Pago, Entregue, Pós-venda. O app tem limite de etiquetas e nomes próprios: o dono confere na tela.

## O que fica de fora, e o que dizer ao dono

Sem IA, o atendimento só acontece quando o dono está olhando o celular. Mensagem fora do horário só recebe a ausência. Se o dono quiser testar a IA depois, o prompt já está pronto (`com-ozap.md`).
