# Histórias reais

O que costuma funcionar sem anúncio é a história verdadeira do negócio, com o rosto e a voz do dono. Texto genérico escrito por IA ("Venha conhecer nosso espaço!") soa igual a todos e costuma passar batido. Por isso esta skill **não inventa** história, cliente, número, frase nem abertura de vídeo. Ela pergunta, anota com as palavras do dono e organiza.

## Perguntas para achar histórias

Faça em blocos de até 3, um bloco por mensagem. Pare quando houver de 5 a 10 histórias.

**O dia a dia**
1. O que acontece todo dia que o cliente não vê? (abrir a loja, preparar a massa, lavar as toalhas, testar o carro)
2. Qual parte do trabalho dá mais orgulho de mostrar?
3. Qual pedido ou serviço é mais bonito de ver pronto?

**Os clientes (sem nome, sem foto sem autorização)**
4. Qual pergunta todo cliente faz?
5. Qual erro o cliente comete antes de chegar até você? (cortar o cabelo em casa, deixar a revisão para depois, guardar o bolo na geladeira errado)
6. Teve um pedido diferente ou difícil que deu certo?

**O dono**
7. Por que você abriu o negócio?
8. O que você faz diferente de quem faz a mesma coisa?
9. Qual dica você dá de graça para todo mundo?

Resposta de uma palavra vale. O Claude pergunta de novo, com um exemplo, só uma vez.

## Formatos que costumam funcionar

| Formato | Exemplo (inventado) | Por quê |
|---|---|---|
| Antes e depois | o cabelo chegando e saindo; o carro com o barulho e sem | mostra o resultado nos primeiros segundos |
| Pronto na mão | o bolo sendo cortado; o pet saindo do banho | o produto de verdade é o que se compra |
| Bastidor | abrindo a loja às 7h; a massa crescendo | gente gosta de ver como se faz |
| Dica do ofício | "não guarde o pão na geladeira, faça assim" | dica útil é salva e mandada a alguém |
| Pergunta de cliente | "todo mundo me pergunta quanto tempo dura a escova" | responde quem está na dúvida |
| Série com nome fixo | "Clientes que todo salão conhece #1, #2, #3" | situação que todo mundo reconhece; o nome fixo ajuda a lembrar |
| Pedido do dia | a agenda de hoje, a fornada de hoje (sem nome de cliente) | prova recente e real |

Post que só dá recado ("Bom dia!", data comemorativa sem história, "Estamos abertos") costuma ter pouco alcance. Se o dono quiser um, que venha com uma história junto.

## A abertura do vídeo

- O que aparece nos primeiros 2 ou 3 segundos decide se a pessoa continua. Abra com ação: o produto pronto, o antes e depois, o problema do cliente já sendo resolvido.
- Uma frase curta na tela desde o primeiro quadro, com as palavras do dono. Se o dono já disse uma frase boa, sugira variações dela (ordem, uma palavra trocada), não uma ideia nova.
- Nada de número inventado ("90% das pessoas...") nem promessa ("cabelo novo em 1 dia").
- Vídeo curto. Corte repetição e pausa, mas não corte a fala animada do dono: a energia dele é o que segura.

## Reaproveitar o que já funcionou

- O vídeo que trouxe conversa pode voltar com outra abertura semanas depois. Mude a imagem também (comece em outro momento, troque a ordem, tire ou ponha um trecho): repostar a mesma montagem só com outro texto tende a ficar sem alcance.
- O mesmo vídeo serve no Status, nos reels, no TikTok e como foto no Perfil do Google.

## Modelo de `organico/historias.md`

```markdown
# Banco de histórias (palavras do dono)

| # | História | Formato | Precisa gravar? | Autorização de imagem | Usada em |
|---|---|---|---|---|---|
| H1 | "Todo sábado às 7h eu já tô lavando as toalhas" | bastidor | sim: 3 tomadas | não precisa (só o dono) | |
| H2 | "Todo mundo pergunta se a escova dura uma semana" | pergunta de cliente | não: o dono fala para a câmera | não precisa | |
```

A coluna "Usada em" recebe o código da peça (`F01`, `R02`) quando `conteudo` fizer a peça. Cliente na imagem: a autorização segue `../../conteudo/references/autorizacao-de-imagem.md`.
