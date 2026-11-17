# Medição e veredito

Meça venda, não clique. Todo número leva o denominador e a amostra.

## 1. Funil

| Etapa | De onde vem |
|---|---|
| Conversas | oZap (`list_chats`) ou o que o dono colou; anúncio: print do Gerenciador |
| Pedidos ou horários marcados | conversas e caderno |
| Vendas | `vendas/caderno.csv` |
| Origem | código na mensagem pronta primeiro; origem gravada pela plataforma como apoio; "não anotada" quando não há |

Conversão conversa para venda = vendas / conversas do mesmo grupo e do mesmo período. Escreva as duas contas, não só a taxa: "2 vendas em 12 conversas (17%)".

## 2. Custo por venda

Do anúncio:

```
custo por venda = (gasto no Gerenciador x (1 + imposto)) / vendas vindas do anúncio
```

- O imposto vem na fatura, por cima do valor do Gerenciador. No caso saiu cerca de 15% a mais; confira na sua fatura e use o seu número.
- Conversas de anúncio sem venda contam no custo. Venda de conhecido não entra na conta do anúncio.
- Compare com o custo máximo por venda de `anuncios/conta.md`, se existir.

Quantas compras pagariam o anúncio (recompra) é **conta, não medição**:

```
compras para empatar = custo por venda / sobra por compra
```

Marque no relatório: "conta feita com a sobra estimada do plano; recompra ainda não medida". No caso, a conta mostrou que a primeira compra não pagava o anúncio; se a recompra pagaria, ninguém tinha medido.

## 3. Amostra

- Com menos de cerca de 10 conversas por grupo, escreva "não é conclusivo". Vale para anúncio A contra B, toque com foto contra sem foto, horário contra horário.
- Dia ou meio dia com gasto concentrado numa rajada não vale como dado de criativo.
- Janela dita pela duração ("num recorte de 3 dias"), não só pela data.

## 4. Antes de culpar o anúncio

Dia com R$ 0 de gasto e anúncio "ativo": olhe a cobrança (saldo devedor, cartão recusado) e o sino de notificações do Gerenciador antes de concluir qualquer coisa. Depois que a cobrança volta, a plataforma pode gastar de uma vez o que ficou acumulado. Quitar saldo é do humano.

## 5. Veredito do teste

O critério foi escrito em `plano/teste.md` antes de começar: meta semanal, piso, número de clientes novos de fora do círculo de conhecidos, origem de cada venda. O veredito segue só esse critério.

```markdown
## Veredito (AAAA-MM-DD)
- Meta: X. Piso: Y. Resultado: Z (de N semanas).
- Clientes novos de fora do círculo: n. Origem das vendas: ...
- Amostra: <conversas por grupo>. Conclusivo? sim/não.
- Veredito: PASSA / AJUSTA / PARA.
- Por quê (em 3 linhas, com os números):
- O que muda, se ajusta: <1 a 3 mudanças com métrica>.
- Decisão do dono: <o que decidiu e quando>.
```

Use exatamente as definições de Passa, Ajusta e Para gravadas em `plano/teste.md`. Se o `teste.md` não tiver, use as de `pesquisa-e-plano/references/teste-de-venda.md`. Não crie critério novo aqui.

- Diga também o que ainda não foi medido.
- Se o veredito for Ajusta, proponha no máximo 3 mudanças, cada uma com métrica.
- Se for Para, proponha o que fazer com o dinheiro e o tempo que sobraram.

O plano é hipótese; o teste mede. No caso, uma semana fechou abaixo da meta do plano, e isso também é resultado. O gestor propõe o veredito. Quem decide é o dono.
