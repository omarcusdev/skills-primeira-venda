# Teste de venda

Um plano é hipótese. O teste curto é o que mede. Transforme as decisões já tomadas em um teste de 3 a 4 semanas, com meta, piso e veredito **escritos antes de começar**. Escrever depois de ver o resultado não é teste.

## `plano/teste.md` (modelo)

```
# Teste de venda: <negócio>
Início: <data> | Fim: <data> (3 a 4 semanas) | Quem anota: <o dono>

## O que está sendo testado
Uma frase. Ex.: "Vender <produto ou serviço> pelos canais X e Y, ao preço da ficha."

## Meta, piso e clientes novos
| Medida | Produto (pedidos) | Serviço (horários) |
|---|---|---|
| Meta semanal | vendas em reais ou pedidos | horários marcados por semana |
| Piso semanal | o mínimo que ainda paga os custos | o mínimo de horários que cobre o fixo |
| Clientes novos de fora do círculo (no teste) | <número> | <número> |
| Retorno (serviço) | — | quantos voltam em até N semanas |

"De fora do círculo" = quem não é amigo, família nem conhecido do dono.

## Origem de cada venda
conhecidos | status | Instagram | anúncio | indicação | passou na porta | outro | não anotada
(marque quais contam como "novo")

## Veredito (escrito antes)
- **Passa:** meta batida em 2 semanas seguidas **e** clientes novos de fora do círculo >= o número acima.
- **Ajusta:** entre o piso e a meta. Mexe uma coisa por vez (preço, canal, oferta) e roda de novo.
- **Para ou repensa:** 3 semanas abaixo do piso.
- **Alerta de perda (produto perecível):** se mais de 1 em 12 unidades se perde, o lote diminui.

## Regra de mudança
A meta e o veredito só mudam por escrito em `negocio/decisoes.md`, com a razão e antes da semana em que valem. Nunca depois de ver o resultado.

## O que já foi decidido e o que foi adiado
<lista de decisoes.md relevantes, inclusive burocracia adiada por escolha do dono>
```

Os números do exemplo (2 semanas, 3 semanas, 1 em 12) vieram do caso de origem. Ajuste ao negócio, e escreva a razão.

## Como definir meta e piso

1. **Meta:** o cenário base do plano. Lembre ao dono que a meta é hipótese: no caso, o resultado de uma semana ficou abaixo dela.
2. **Piso:** o cenário conservador, ou o ponto de equilíbrio semanal de `custo-e-margem.md`, o que for maior.
3. **Clientes novos:** diga que é proposta do Claude e que o dono pode mudar. A venda que importa para o futuro do negócio é a de quem não conhece o dono; venda para conhecido é boa, mas custa zero e não mostra se o canal funciona.
4. **Serviço:** troque venda por horário marcado, e some o retorno. Um corte que não volta dentro do prazo esperado conta como aviso.

## Rastrear o canal: código no link de WhatsApp

O link `wa.me` **não aceita UTM**. O jeito simples é um texto pré-preenchido com um código curto, diferente por canal:

```
https://wa.me/{telefone}?text=Oi!%20Vim%20pelo%20Instagram%20(IG1)
```

- `{telefone}` é o número do negócio, com código do país e DDD, só dígitos. Enquanto o número do negócio não existir, deixe `{telefone}` como está. Nada com telefone sai antes disso.
- Um código por canal e por peça: `IG1` (bio do Instagram), `ST1` (status), `AN1` e `AN2` (dois anúncios), `PD` (adesivo na porta ou QR).
- O cliente pode apagar o código. Por isso, a origem também é perguntada e **anotada pelo dono** (ou por quem atende) em `vendas/caderno.csv`, na coluna origem. O código ajuda; a anotação manda.
- Atendente de IA ou leitura das conversas: veja `atendente-ia` e `acompanhar-vendas`. Sem eles, o dono anota na mão.

## Entrega

Ao gravar `teste.md`, crie também `vendas/caderno.csv` vazio, só com o cabeçalho de `acompanhar-vendas/references/caderno-de-vendas.md`, para o dono já anotar a origem durante o teste. Ao terminar, mostre ao usuário em uma lista curta: meta, piso, clientes novos, veredito, fim do teste. Peça o ok. Depois do ok, a medição semanal e o veredito ficam com `acompanhar-vendas`. Nenhum anúncio e nenhuma mensagem sai por causa deste arquivo.
