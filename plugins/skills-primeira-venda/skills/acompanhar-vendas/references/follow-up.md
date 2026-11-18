# Follow-up

Follow-up é uma mensagem a quem já escreveu ao negócio e parou no meio. É uma ação para fora: só sai com o ok do dono naquele item.

## 1. Regras

| Regra | Valor |
|---|---|
| Quem recebe | Só quem escreveu ao negócio. Nunca conversa fria, nunca lista comprada, nunca envio em massa. |
| Quantos | Um toque por cliente. Quem disse não ou "agora não" não recebe outro. Segundo toque só com um fato novo e útil, como exceção que o dono aprova, e escrito no registro. |
| Quando | Só dentro do horário de atendimento da ficha. Fora dele, o toque espera. |
| Tom | O da ficha. Curto, sem pressão, sem escassez falsa, no máximo 1 emoji. |
| Promessa | Nada de estoque, prazo ou preço que não esteja na ficha ("ainda tem", "já separo o seu"). |
| Saída | Todo toque de recompra tem uma saída, escrita na voz do negócio ("se não quiser mais receber, é só falar"), nunca na voz do Claude. |
| O que comprou | Cada toque de recompra cita o que o cliente comprou, como está no caderno. |
| Emissor | Um só. Se o dono responde à mão, o gestor para de propor para aquele cliente. |
| Antes de enviar | Releia a conversa. Se o cliente respondeu, o dono atendeu ou outro toque já saiu, não envie e avise. |

Um número ligado por QR code pode ser restringido pelo WhatsApp se mandar mensagem a quem não escreveu ou em volume fora do padrão. Por isso as regras acima não são só educação.

## 2. Quem não recebe

- quem disse não, ou pediu para não ser incomodado;
- quem o dono já atendeu à mão (olhe a conversa e o painel);
- quem pediu algo que o negócio não faz;
- quem não é cliente: amigo, família, fornecedor, outro robô, número pessoal do dono, quem só reagiu com emoji;
- quem disse que ele mesmo chama depois;
- quem já recebeu um toque (consulte `gestao/toques.md`).

## 3. Textos-modelo (inventados; adapte ao tom da ficha)

Use o primeiro nome do cliente e só fatos da ficha.

**Primeiro toque (viu o cardápio, não pediu):**
> Oi, {nome}! Ficou com vontade de algum item do cardápio da Doceria Aurora? Me diz qual e eu anoto pra você.

**Resposta travada (o cliente perguntou algo e ninguém respondeu):** responda direto à pergunta, com o fato da ficha, e faça uma pergunta só.
> Oi, {nome}, desculpa a demora! A entrega no seu bairro sai {valor da tabela}. Prefere retirar ou receber em casa?

**Reabertura depois de "agora não":** só se houver um fato novo e útil.
> Oi, {nome}! Passando pra avisar que agora a gente também {fato novo}. Se fizer sentido, me chama aqui.

**Recompra, sete dias depois da compra:** curto, sem promoção inventada, com saída.
> Oi, {nome}! Como foi o {o que comprou} da semana passada? Se quiser repetir, é só falar. Se não quiser mais receber, é só falar também.

**Pedido em aberto (o cliente adiou):** não mande toque se ele disse que chama. Se o dono quiser, proponha esperar e anote a data no diário.

Exemplos de outros negócios: no salão, "Oi, {nome}! Faz {x} semanas do seu último corte. Quer que eu veja um horário essa semana?". No pet shop, "Oi, {nome}! O banho do {nome do pet} já está pra vencer? Tenho horário na {dia}.", só se o horário existir na agenda.

## 4. Antes de propor, olhe o que já se aprendeu

- Toque só de texto pode converter pouco; o que reabre a conversa costuma ser a resposta a uma pergunta travada ou um fato novo, não o "oi, tudo bem?".
- Foto junto do toque é hipótese: teste com amostra maior antes de dizer que funciona (veja `medicao-e-veredito.md`).
- Quando o cliente travou depois do cardápio em texto, o cardápio com foto pode ajudar o atendimento; isso é do `atendente-ia`.

## 5. Como propor e como enviar

1. Antes de escrever o motivo de um toque, procure o nome do cliente no caderno inteiro, não só no período do ciclo. Monte a tabela no diário e em `gestao/toques.md`: cliente (primeiro nome ou id), quando, texto exato, motivo, dado que sustenta.
2. Mostre como lista numerada. O dono responde "sim 1, 3". Texto alterado pelo dono vale como novo item: mostre de novo antes de enviar.
3. **Com oZap:** um envio por vez, em sequência, nunca em paralelo, só o texto aprovado, sem mudar nada. Releia a conversa antes de cada um. Depois, confira no chat que a mensagem apareceu. Veja `com-ozap.md`.
4. **Sem oZap:** o dono copia o texto e envia do próprio celular, no WhatsApp ou no WhatsApp Business. Ele avisa o gestor ("mandei 1 e 3") e o gestor registra em `gestao/toques.md`. O Claude nunca automatiza o WhatsApp Web.
5. Registre cada toque, enviado ou não, em `gestao/toques.md`.
6. Meça: no ciclo seguinte, anote quem respondeu e quem comprou depois, com as horas entre o toque e a venda.

## 6. Se o dono recusar o toque automático

Recusar é normal. É comum o dono preferir aprovar texto por texto, e isso fica barato quando cada item vem com o texto pronto, o motivo e o dado. Não tente convencer: registre a decisão em `negocio/decisoes.md`.
