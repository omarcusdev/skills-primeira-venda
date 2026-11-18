# De onde veio cada conversa

Sem saber de onde veio a conversa, não dá para saber qual canal manter. O jeito mais simples tem duas partes: um código por canal no texto do link do WhatsApp e uma pergunta ao cliente novo.

## 1. Um código por canal

O link do WhatsApp (`wa.me`) aceita um texto já escrito. Ponha um código diferente em cada lugar onde o link aparece. A primeira mensagem do cliente chega com o código.

```text
https://wa.me/{telefone}?text=Oi!%20Vi%20no%20Google%20(G1)%20e%20quero%20saber%20mais
```

- `{telefone}` é o número do negócio, só dígitos, com país e DDD, tirado de `negocio/ficha.md`. Sem número, o link fica como rascunho.
- Códigos sugeridos:

| Canal | Código | Onde o link fica |
|---|---|---|
| Perfil no Google | G1 | no campo de site, agendamento ou pedido, se o perfil aceitar link; se não, conte pelo desempenho do perfil e pela pergunta |
| Status | S1 | não precisa de link: a resposta ao Status chega mostrando o Status |
| Instagram, link na bio | I1 | link na bio (`presenca-nas-redes`) |
| Post ou reel | o código da peça (F01, R02) | `conteudo` já põe um código por peça |
| Grupo do bairro | B1 | na mensagem que o dono posta no grupo |
| Vizinho parceiro | P1, P2 | no cartão ou QR code que fica no balcão do vizinho |
| Porta e balcão | Q1 | no QR code do cartaz |

- Código curto, de uma letra e um número. Grave o mapa canal, código e link em `organico/plano.md`.
- O cliente pode apagar o texto antes de mandar. Por isso o código não pega tudo; a pergunta ajuda.

## 2. A pergunta ao cliente novo

Uma vez, no começo do atendimento: "Como você nos achou?". O dono anota a resposta junto da venda. Se o atendimento for por um atendente com IA, a pergunta só entra nas instruções dele se o dono pedir (veja `atendente-ia`).

## 3. O placar: `organico/placar.md`

Uma linha por canal, por semana (as linhas abaixo são um exemplo inventado). As vendas vêm do caderno de vendas de `acompanhar-vendas` (`vendas/caderno.csv`, coluna `origem`); se o caderno não existe, o dono conta.

```markdown
# Placar sem anúncio

| Semana | Canal | Conversas | Vendas | Rotina cumprida? | Observação |
|---|---|---|---|---|---|
| 2026-11-17 | Google (G1) | 2 | 1 | sim | 1 avaliação nova |
| 2026-11-17 | Status (S1) | 4 | 2 | 3 de 3 | o vídeo do bolo cortado teve 3 respostas |
| 2026-11-17 | sem origem | 3 | 1 | | |
```

- Conte só o que o dono disse, colou ou mostrou em print. Nada estimado.
- "Sem origem" é uma resposta honesta. É comum boa parte das conversas ficar sem origem. Diga isso quando a linha for grande, sem cobrar o dono.
- Curtidas e visualizações podem entrar na observação, mas a decisão é por conversa e venda.

## 4. Como ler e decidir

- Com poucas semanas e poucas conversas, diga que ainda não dá para saber. Decidir por uma conversa a mais ou a menos é sorte.
- Depois de cerca de 4 semanas de rotina cumprida: o canal que trouxe conversas fica; o que não trouxe nenhuma pode sair ou trocar de jeito (outra história, outro horário).
- Se uma peça trouxe conversas várias vezes, ela é a candidata a anúncio, se o dono quiser anunciar (`anuncios`). Anúncio continua opcional.
- Rotina não cumprida não mede o canal: ajuste a rotina antes de cortar o canal.
