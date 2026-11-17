# Custo e margem

Contas de apoio para o plano. Todos os números dos exemplos são inventados. Use os do dono, e marque o que não for dele como "(estimativa)".

## 1. Hora de trabalho

Quanto vale a hora do dono? É escolha dele. Um ponto de partida é o salário mínimo vigente dividido por 220 horas por mês (confirme o valor do ano em fonte oficial). Se o dono não quiser se pagar agora, calcule as duas margens: **antes da hora** e **depois da hora**. Mostre as duas.

## 2. Custo unitário

```
custo antes da hora = insumos + embalagem + gás ou energia por unidade (+ comissão, se houver)
custo da hora       = hora do dono x tempo gasto por unidade
sobra antes da hora = preço - custo antes da hora
sobra depois da hora = sobra antes da hora - custo da hora
margem = sobra / preço
```

Rendimento real (quantas unidades saem de uma embalagem de insumo) deve vir do dono, não de tabela. É onde mais se erra.

### Exemplo (Doceria Aurora, bolo no pote)

| Item | Valor |
|---|---|
| Preço | R$ 12,00 |
| Insumos | R$ 3,50 |
| Embalagem | R$ 1,20 |
| Gás por unidade | R$ 0,40 |
| Custo antes da hora | R$ 5,10 |
| Sobra antes da hora | R$ 6,90 (57,5%) |
| Tempo por unidade | 12 min; com a hora a R$ 8,00 = R$ 1,60 |
| Sobra depois da hora | R$ 5,30 (44,2%) |

## 3. Piso de margem

Regra sugerida: só vender o que deixa uma margem mínima **depois** da hora. O piso é do dono (ao dono: "a sobra mínima que vale o trabalho"). Um ponto de partida é 25% depois da hora, para ele ajustar; não é norma de mercado. Produto abaixo do piso: suba o preço, mude a receita ou o tamanho, ou corte do cardápio. Verifique primeiro o produto de menor margem, porque é onde um erro de custo vira prejuízo.

## 4. Ponto de equilíbrio

```
custos fixos por semana = (aluguel, plano de telefone, taxas, impostos fixos, ferramentas) / semanas do mês
equilíbrio (unidades por semana) = custos fixos por semana / sobra por unidade
```

Dê a conta com a sobra antes e depois da hora. Arredonde para cima.

### Exemplo (Salão Exemplo, escova)

Aluguel de cadeira de R$ 600,00 por mês. Escova a R$ 70,00, produtos R$ 6,00, 45 minutos com a hora a R$ 20,00 (R$ 15,00 por atendimento). Sobra antes da hora R$ 64,00; depois, R$ 49,00 (70%). Equilíbrio do aluguel: 600 / 64 = 9,4, ou seja, 10 escovas no mês (antes da hora).

## 5. Quanto um anúncio pode custar por venda

Só a conta. O gasto real e o ok são da skill `anuncios`.

```
gasto no cartão = valor no Gerenciador x (1 + imposto)
custo por venda = (gasto no cartão por conversa) / (taxa de conversa que vira venda)
a primeira compra paga o anúncio se: sobra por pedido >= custo por venda
compras para pagar = custo por venda / sobra por pedido, arredondado para cima
```

Imposto: a Meta cobra imposto por cima do valor do anúncio. Use o percentual da fatura do usuário; até ele conferir, 14% é suposição (a mesma da skill `anuncios`), e diga que é.

### Exemplo (Lanchonete Teste)

Ticket R$ 38,00, sobra R$ 14,00 por pedido. Conversa a R$ 5,00 no Gerenciador, com 14% de imposto (suposição), vira R$ 5,70. Se 20% das conversas viram venda, o custo por venda é 5,70 / 0,20 = R$ 28,50. A sobra (R$ 14,00) não cobre: o cliente precisa comprar 3 vezes (28,50 / 14,00 = 2,04, arredonde para cima) para o anúncio se pagar.

Seja franco com o dono: a recompra é hipótese até medir, e é comum a primeira compra não pagar o anúncio. A taxa de conversa do exemplo é inventada; a real pode sair bem abaixo do que o plano supõe.

### Serviço

Troque "pedido" por "atendimento" e "recompra" por "retorno em N semanas". O custo máximo por cliente novo é a sobra de uma visita multiplicada pelo número de visitas esperadas, e o número de visitas é hipótese até o teste mostrar.

## 6. Cenários

Monte três: conservador, base e otimista, cada um com as premissas à vista (unidades por semana, preço, perda). Marque cada premissa como medido, fonte ou estimativa. O teste de venda mede a base; o piso vem do conservador.
