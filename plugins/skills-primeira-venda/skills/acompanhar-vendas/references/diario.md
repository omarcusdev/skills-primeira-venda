# Diário e registro de toques

O diário é a memória do gestor. Um arquivo por ciclo em `gestao/diario/AAAA-MM-DD.md` (se houver mais de um no dia, acrescente `-manha`, `-tarde`, `-fechamento`). O registro de toques é um arquivo só, `gestao/toques.md`, e é a única fonte de "quem recebeu o quê".

Dados de cliente minimizados: primeiro nome ou id da conversa, nunca telefone completo. A pasta `gestao/` não vai para e-mail nem nuvem compartilhada.

## Modelo do diário

```markdown
# Diário AAAA-MM-DD (<tipo do ciclo>)

## 1. Funil (período: desde <último ciclo>)
| Etapa | Qtd | Observação |
|---|---|---|
| Conversas novas | | quantas de anúncio, de link, de conhecido, sem origem |
| Pedidos ou horários marcados | | |
| Vendas fechadas | | |
| Custo por venda (com imposto) | | só se houver gasto no período |
Meta da semana: X. Mínimo da semana: Y. Estamos em: Z.
Amostra: <n> conversas por grupo. Com menos de ~10, não é conclusivo.

## 2. Toques propostos (nada enviado sem ok)
| Cliente | Quando | Texto exato | Motivo | Ok? |
|---|---|---|---|---|

## 3. Toques enviados neste ciclo
| Cliente | Hora | Texto | Resultado do envio |
|---|---|---|---|

## 4. Pesquisa (só web pública)
- <achado> (link, data de leitura, confiança: li na página / vi em resumo)

## 5. Sugestões (máx. 3)
### Sugestão 1 [precisa ok] ou [posso fazer]
- Dado que sustenta:
- Custo:
- Ganho esperado (hipótese, não promessa):
- Métrica de sucesso e quando medir:
- Quem executa:

## 6. Decisões do dono
- <o que aprovou, recusou ou adiou, e quando>

## 7. Linhas propostas para o caderno
(vendas que apareceram nas conversas e ainda não estão no caderno)

## 8. Para o próximo ciclo
- O que medir:
- Toques aguardando resposta:
```

## Modelo do registro de toques

```markdown
# Toques

| Cliente (id) | Tipo | Enviado em | Por quem | Texto (resumo) | Resposta | Venda depois? |
|---|---|---|---|---|---|---|
| ana-01 | 1º toque | | dono | cardápio sem pedido | sem resposta | |
```

Regras do registro:

- uma linha por toque; o cliente que já recebeu um toque não recebe outro (veja `follow-up.md`);
- antes de propor um toque novo, o gestor consulta este arquivo;
- antes de escrever o motivo de um toque, procure o nome do cliente no caderno inteiro, não só no período do ciclo (uma compra antiga muda o motivo);
- registre também "não enviado" e o motivo (cliente respondeu antes, dono atendeu, fora do horário).
- Quando o toque tiver foto, marque na coluna Tipo ("1º toque com foto"), para medir depois se responde mais que o de texto. Com amostra pequena, diga que não dá para concluir.
