# Erros comuns e a regra que cada um vira

Tabela genérica, escrita para qualquer negócio. Use como checklist de revisão antes de ligar e como ponto de partida quando um erro aparecer.

## O método

1. Anote o erro em `atendente/erros.md`: o que aconteceu, a conversa de exemplo (sem telefone e sem sobrenome) e a regra nova.
2. A regra nasce com o gatilho na linguagem do cliente e a resposta exata que a IA deve dar.
3. Mostre o trecho novo ao dono e espere o ok antes de gravar no atendente que está no ar.
4. Rode de novo o caso que falhou e todo o `testes.md`: regra nova pode quebrar regra antiga.
5. Se o prompt piorou, volte à versão anterior (com o oZap, `ozap:revisar-atendente` mostra o histórico).

Modelo de linha em `atendente/erros.md`:

```markdown
| Erro | Conversa de exemplo | Regra nova | Testado em |
|---|---|---|---|
| Cumprimentou de novo na 2ª mensagem | Cliente: "quanto é o X-Burguer?" / IA: "Oi de novo!..." | "Cumprimente só na primeira mensagem da conversa." | caso 1 e 2 |
```

## Tom e forma

| Erro observado | Regra |
|---|---|
| Cumprimenta de novo a cada mensagem ("oi de novo") | "Cumprimente só na primeira mensagem" e a proibição escrita |
| Erra a forma regional de falar | Regra literal com 2 ou 3 exemplos certos tirados da ficha |
| Responde várias perguntas ou manda várias mensagens | "Uma mensagem, até 3 linhas, uma pergunta" |
| Diz "equipe", "atendente" ou "transferir" | Proibir as palavras e dar a frase fixa de passagem |

## Condução do pedido

| Erro observado | Regra |
|---|---|
| Repete "retirada ou entrega?" quando o cliente muda de assunto | "Não repita a mesma pergunta; responda o que o cliente trouxe e retome uma vez" |
| Encerra com "quando quiser" depois de um agradecimento | Fazer uma pergunta de escolha com preços de exemplo e parar se não responder |
| Insiste em pedir endereço de quem disse "agora não posso" | Lista de frases de adiamento; responde uma vez e só agradece depois |
| Trata "ainda não cheguei em casa" como adiamento | Exceção explícita: não é adiamento, é informação de horário |
| Chama o dono por pergunta que dava para resolver (caixa de presente, "tele" quer dizer entrega) | Listar o que a IA resolve sozinha e o sinônimo de entrega que o cliente usa |
| Caixa mista sem as quantidades de cada item | Perguntar quantos de cada e escrever assim no resumo |
| Deixa "onde fica?" sem resposta quando vem junto com pedido de cardápio | Regra de responder as duas coisas na mesma mensagem, mantendo uma pergunta só |

## Limites e privacidade

| Erro observado | Regra |
|---|---|
| Dá o endereço, a rua ou o bairro da casa do dono | Resposta com zona de entrega; "nunca diga que não pode passar o endereço", diga que o dono passa ao confirmar |
| Cita o comércio vizinho como referência | Proibir |
| Confirma estoque ("sim, temos") | "Vou confirmar com o dono se tem agora e já te digo" |
| Frete fechado ou fora da tabela | "Em torno de", tabela, e "o dono te passa o valor" para o resto |
| Promete horário de entrega | Proibir; "o dono confirma o horário" |
| Diz que fez algo que não fez ("já te mandei") | Proibir; só afirmar o que está no histórico |

## Passagem para o dono

| Erro observado | Regra |
|---|---|
| Depois de chamar o dono, responde só "já avisei" sem o resumo do pedido | Exigir o resumo completo na mesma mensagem, mesmo depois de chamar o dono: a IA vai ficar calada em seguida |
| O aviso ao dono chega sem o pedido | O motivo do aviso repete o resumo inteiro (veja `passar-para-o-dono.md`) |

## Erros de operação (não se corrigem no prompt)

- **Narra o envio da foto** ("vou te mandar a foto") e esquece a pergunta de fechamento. Isso pode ser defeito da plataforma, não do prompt. Teste o envio de mídia antes de ligar e, se acontecer, avise o suporte da ferramenta em vez de empilhar regras.
- **Texto junto de uma chamada de ferramenta some ou vaza raciocínio** em alguns modelos. Se uma resposta aparecer cortada ou com texto interno, anote a conversa e avise o suporte.
- **Filtro de teste ligado com o atendimento aberto ao público:** quem vem do anúncio ou do boca a boca fica sem resposta. Confira o modo de teste antes de divulgar o número.
- **Timestamps vêm em UTC** nas ferramentas de leitura; converta para o fuso do negócio antes de dizer "respondeu em X minutos".
