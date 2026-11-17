# Passar para o dono

Todo atendente que passa a vez para uma pessoa precisa de quatro coisas. Sem elas, o pedido se perde ou a IA atropela o dono.

1. **Aviso ao dono, com o contexto completo** (o pedido inteiro, não só "tem cliente esperando").
2. **Silêncio da IA naquela conversa** enquanto o dono atua.
3. **Um jeito de devolver a conversa à IA.**
4. **Notificação que realmente toca no celular do dono.**

E um teste de ponta a ponta antes de ligar: o aviso chegou ao celular do dono?

## Os 3 tipos de aviso

| Tipo | Quando | O que o aviso traz |
|---|---|---|
| PEDIDO NOVO | O pedido está completo | Itens, total, retirada ou entrega, endereço, horário, como conheceu. O prompt exige que o motivo repita o resumo inteiro. |
| CLIENTE PRECISA DE VOCÊ | Reclamação, alergia, desconto, encomenda grande, pedido para outro dia | O que o cliente disse, com as palavras dele, e o que a IA já respondeu |
| NÃO SOUBE RESPONDER | Pergunta fora do que o prompt sabe | A pergunta literal |

Modelo de texto do aviso (o dono recebe no WhatsApp pessoal dele):

```
PEDIDO NOVO
Cliente: [primeiro nome]
Pedido: [itens] = R$ [total]
[Entrega: rua, número, bairro | Retirada às HH]
Como conheceu: [origem]
```

## Depois do aviso

- No caso real, a IA ficou calada por 12 horas naquela conversa depois do aviso, para não atropelar o dono quando ele assumisse. Confira o tempo no seu painel; pode ser diferente.
- Se o dono escrever no chat, a IA cala (no caso, por 24 horas) com a opção de intervenção humana ligada.
- Para devolver a conversa à IA, o dono usa o botão de reativar a IA daquele chat no painel. Pelo MCP, hoje, não dá para destravar a pausa que o aviso cria, e a leitura das conversas pode não mostrar que a IA está pausada: olhe o painel.
- Enviar uma mensagem pelo MCP não pausa a IA na conversa. Se o Claude for responder um cliente e a IA precisar ficar parada naquele chat, proponha a pausa (`pause_chat`) como item e espere o ok do dono.

## O que é configurado onde

No oZapOnline, estas configurações são do painel e não existem como tool no MCP:

- o texto e o número do aviso ao dono;
- a notificação no celular (a opção que faz o WhatsApp Business do dono tocar quando chega mensagem de cliente);
- a pausa quando o dono escreve;
- o "reativar IA" do chat.

Mande o usuário configurar lá, uma opção por vez, e peça que ele diga o que a tela mostra, para o Claude conferir com `get_playbook`, se a credencial tiver. O passo a passo exato muda com o painel: confira o manual da ferramenta em vez de copiar telas daqui.

A notificação no celular tem um efeito colateral: a IA deixa de aparecer "digitando…" e não marca tique azul automático. Diga isso ao dono antes de ligar.

## Teste de ponta a ponta (obrigatório antes de ligar)

1. Faça um pedido completo de um número de teste.
2. Confirme com o dono: chegou o aviso no celular dele, com o pedido inteiro?
3. O celular tocou, ou só apareceu uma notificação silenciosa?
4. O dono escreve no chat de teste: a IA ficou calada?
5. O dono reativa a IA: ela volta a responder?

Se qualquer passo falhar, não ligue a IA para clientes.

## Sem IA

O dono vê tudo no WhatsApp Business. O aviso é a própria notificação do app. O roteiro de `sem-ia.md` cuida do resto.
