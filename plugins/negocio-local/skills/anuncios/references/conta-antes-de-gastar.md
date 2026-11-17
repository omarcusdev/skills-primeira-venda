# Conta antes de gastar

Duas coisas vêm antes de qualquer campanha: a base da conta (quem é dono de quê) e a conta de dinheiro (quanto pode custar cada venda). Sem as duas, não há o que aprovar.

## Passo 0: a base da conta

Confirme cada ponto com o usuário e anote em `anuncios/conta.md`.

1. **Perfil pessoal real no Facebook.** A Página precisa de um perfil pessoal como administrador. Ele deve ter a verificação em duas etapas ligada (quem liga é o dono do perfil). Se o perfil foi criado agora, avise: conta nova tem mais chance de cair em revisão. Nesse caso, comece pelo impulsionar um post pelo app (opção A em `montar-campanha.md`) e deixe o Gerenciador para depois.
2. **Portfólio de negócios criado pelo próprio humano.** O Claude não cria portfólio. Dê o passo a passo e peça que o usuário diga o nome que aparece na tela.
3. **Forma de pagamento escolhida pelo humano.** As opções mudam por conta e por país. Não afirme quais existem: peça que o usuário olhe as que o Gerenciador oferece a ele e escolha. Anote quem paga. O Claude nunca pede nem digita dado de cartão.
4. **Conta de anúncios criada pelo humano,** separada de outros negócios do mesmo dono, se houver. Depois de criada, a conta não sai do portfólio onde nasceu: confira o portfólio antes de criar. Ao criar, confira moeda (BRL) e fuso (no caso, a conta nasceu com um fuso do outro lado do mundo e foi preciso corrigir).

**Se não há perfil pessoal, pare.** Explique que a Página, e portanto o anúncio, depende dele. Não sugira perfil falso nem nenhum jeito de contornar. Só um perfil de uma pessoa real serve.

## Trabalhando para cliente (agência, freelancer)

- O cliente cria o próprio portfólio de negócios e dá acesso de parceiro à agência. A agência nunca usa a senha do cliente.
- A conta de anúncios nasce no portfólio do cliente, não no da agência.
- Antes de qualquer gasto ou publicação, o Claude confere na tela o nome da conta e do portfólio e escreve os dois no resumo que pede o ok. Abrir o Gerenciador pode cair na conta errada: no caso, abriu primeiro a conta de outro negócio.
- Guarde em `negocio/decisoes.md` a autorização por escrito do dono para tratar os dados dos clientes dele.

## A conta de dinheiro

Imposto: o cartão sai com um acréscimo sobre o valor que o Gerenciador mostra. No caso ficou na casa de 12% a 15%. Use 14% como suposição e peça ao usuário para conferir na fatura. Abaixo, `imp` = 1,14.

### Variante produto

Pergunte ou peça ao dono (nada de chute; o que faltar fica como pendência):

- ticket médio do pedido;
- sobra por pedido: preço menos insumo, embalagem, gás e energia, taxa de pagamento e entrega paga pelo dono. Diga se a hora de trabalho do dono entrou ou não;
- custo por conversa esperado: use uma faixa de referência marcada "(estimativa)" ou diga que não há dado;
- conversão esperada de conversa em venda: idem, "(estimativa)".

Contas:

- custo por venda no Gerenciador = custo por conversa ÷ conversão;
- custo por venda no cartão = custo por venda no Gerenciador × `imp`;
- a primeira compra paga o anúncio se o custo por venda no cartão for menor que a sobra por pedido;
- compras para pagar = custo por venda no cartão ÷ sobra por pedido, arredondado para cima. Isso é conta, não medição: depende de o cliente voltar, e isso só se mede depois;
- custo máximo por venda = a sobra por pedido (empate na primeira compra) ou a sobra vezes as compras que o dono já vê de um cliente no período (só se houver histórico dele).

Exemplo inventado, lanchonete: ticket R$ 40, sobra R$ 16 por pedido. Custo por conversa esperado R$ 8, conversão esperada 25% (estimativa). Venda no Gerenciador: R$ 32. No cartão: R$ 36,48. Como 36,48 é maior que 16, a primeira compra não paga. Compras para pagar: 36,48 ÷ 16 = 2,28, ou seja, 3. Diga isso ao dono assim, sem enfeitar. Se a conversão real for metade da esperada, a conta dobra.

### Variante serviço (horário marcado e retorno)

Pergunte ao dono:

- valor do atendimento;
- sobra por atendimento (o que fica depois de material, comissão e taxa);
- quantas visitas um cliente novo costuma fazer em 90 dias, pelo histórico dele (sem histórico, use 1);
- conversão esperada de conversa em horário marcado, e de horário marcado em cliente que comparece (as duas "(estimativa)").

Contas:

- custo máximo por cliente novo = sobra por atendimento × visitas esperadas em 90 dias;
- custo por cliente novo no cartão = (custo por conversa ÷ conversão de conversa em cliente que comparece) × `imp`;
- o anúncio compensa na conta se o custo no cartão ficar abaixo do custo máximo.

Exemplo inventado, barbearia: corte R$ 50, sobra R$ 35. O dono diz que um cliente volta 3 vezes em 90 dias. Custo máximo por cliente novo: R$ 105. Custo por conversa esperado R$ 9, conversão em cliente que comparece 20% (estimativa): R$ 45 no Gerenciador, R$ 51,30 no cartão. Está abaixo de R$ 105 se a volta de 3 visitas se confirmar; se o cliente novo vier uma vez só, o máximo cai para R$ 35 e o anúncio não se paga. Escreva as duas leituras.

### Ponto de equilíbrio e a verba de teste

Verba de teste = o que o dono aceita perder sem aperto. Escreva a frase: "esta verba pode não voltar". Em negócio de ticket baixo, considere antes de anunciar o que sai de graça: indicação, status do WhatsApp, cliente que já conhece. No caso, a maior parte das vendas da semana veio de conhecidos, que custam zero.

Os valores mínimos de orçamento da Meta e a "fase de aprendizado" (um número de eventos por semana, citado por blogs) não foram verificados na documentação oficial. Não os afirme; peça ao usuário para ler o que o Gerenciador mostra na tela.

## Modelo de `anuncios/conta.md`

```
# Conta de anúncios
- Perfil pessoal administrador: sim / não (duas etapas: sim / não)
- Portfólio de negócios (nome na tela): ______  criado por: ______
- Conta de anúncios (nome na tela): ______  moeda: BRL  fuso: ______
- Forma de pagamento escolhida por: ______ (não anotar dado de cartão)
- Quem paga e quita saldo: ______
- Trabalhando para cliente: sim / não. Acesso de parceiro: sim / não.
  Autorização do dono para dados dos clientes: arquivo ______

# A conta
- Variante: produto / serviço
- Ticket ou valor do atendimento: ______   Sobra: ______ (hora do dono inclusa? sim / não)
- Custo por conversa esperado: ______ (fonte ou estimativa)
- Conversão esperada: ______ (fonte ou estimativa)
- Imposto suposto: 14% (conferir na fatura)
- Custo por venda ou por cliente novo, no cartão: ______
- A primeira compra paga? sim / não. Compras ou visitas para pagar: ______ (conta, não medição)
- Verba de teste e frase de risco: ______
```
