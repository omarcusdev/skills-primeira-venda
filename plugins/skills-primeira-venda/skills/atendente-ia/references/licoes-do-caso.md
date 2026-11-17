# O que aprendemos

> **Para você, Claude; não é para narrar ao dono.** Estas lições servem para você decidir o que checar. Ao dono, dê o conselho em voz neutra ("acontece de…", "um erro comum é…", "vale fazer X antes, porque…"), sem contar a história de outro negócio e sem usar número daqui como se fosse do dono. Só cite a origem se o dono perguntar de onde vem o conselho, e aí com a amostra dita.

Estas lições vêm do caso de origem do plugin, uma doceria pequena, um único negócio e uma amostra pequena. São o que aconteceu lá, não uma média nem uma promessa. Os números são contagens, sem valores do negócio.

## Prompt

- **Frases fixas literais funcionam melhor que descrição.** O resumo do pedido e a frase de passagem, escritos como o cliente vai ler, saíram quase iguais em toda conversa. "Faça um resumo" variava a cada vez.
- **Proibir a palavra exata elimina o vocabulário interno que vazava.** "Equipe", "atendente" e "transferir" apareciam para o cliente até entrarem numa lista de proibidas.
- **Cada correção virou uma regra com o gatilho na linguagem do cliente.** Por exemplo, a lista de frases que adiam ("agora não posso") e a exceção "ainda não cheguei em casa", que não é adiamento.
- **Erros reais que viram checklist:** cumprimentar de novo, mandar várias perguntas numa mensagem, repetir a mesma pergunta, prometer estoque, dar o endereço da casa, frete fora da tabela, chamar o dono à toa. A lista completa está em `erros-comuns-e-correcoes.md`.
- **Dado pequeno cabe no prompt.** O cardápio era curto e ficou no prompt; catálogo grande iria para uma base de conhecimento.

## Colocar no ar

- **Conectar o número sem agente e com a IA desligada,** e ligar só depois do teste, com alguém olhando e o desligar pronto. A decisão de onde a IA roda (num servidor, e não numa sessão do Claude no computador do usuário) pesou: o computador dorme, o servidor não.
- **Bloquear família, amigos e o próprio dono antes de ligar.** Sair do modo de teste que só responde a números permitidos é um passo explícito.
- **Testar com simulador e depois com um número real de teste,** nunca com cliente.

## Passar o bastão

- **Todo atendente que passa a vez precisa de quatro coisas:** aviso ao dono com o pedido completo, silêncio da IA enquanto o dono atua, um jeito de devolver o chat à IA e notificação que toque no celular. No caso, tudo isso se configurou no painel e foi testado de ponta a ponta antes de abrir.
- **Depois de chamar o dono, a IA ficou calada.** Por isso a última mensagem dela ao cliente tinha de trazer o resumo completo.

## Mídia e cardápio

- **Testar o envio de mídia antes de ligar.** No caso, a IA narrou o envio ("vou te mandar a foto") e esqueceu a pergunta de fechamento em 11 de 12 testes, até uma correção na plataforma; depois, 4 de 4 testes limpos. Isso não se corrigiu no prompt.
- **5 de 8 conversas pararam depois do cardápio em texto.** O cardápio com foto ajuda a continuar a conversa. Amostra minúscula: trate como pista, não como regra.

## Limites do que sabemos

- Não medimos a taxa de conversão de conversa em pedido do atendente, nem quanto ele faturou.
- Os tempos exatos de resposta da IA por conversa não foram consolidados.
- A estimativa de frete por bairro, feita por regressão com cotações reais, tinha só uma cotação: não vale como regra. Use tabela do dono, sempre "em torno de".
