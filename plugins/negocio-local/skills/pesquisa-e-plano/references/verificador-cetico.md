# Verificador cético

Um agente por frente grande, rodando depois da pesquisa. Na versão leve, todas as 3 frentes; na completa, as que movem dinheiro e regra: custos, regras e formalização, logística, marketing, operação, concorrência. Sem subagentes, o próprio Claude faz a verificação em um segundo passo, reabrindo as fontes.

Por quê: o pesquisador costuma acertar o tom e errar o número. No caso de origem do plugin, cerca de 1 em 5 afirmações checadas estava errada (amostra de um caso; não conte isso ao dono). Ao dono, diga só "conferi as fontes" e o que ficou sem confirmar.

## O que verificar primeiro

Afirmações que mudam uma decisão: preço de insumo, custo, margem, tarifa, taxa, prazo legal, exigência de regra, número de concorrente. Opinião e tendência geral ficam para depois.

## Passos

1. Liste as afirmações checáveis do arquivo, uma por linha, com a fonte citada.
2. Reabra cada fonte e confira se ela diz mesmo aquilo.
3. Busque uma segunda fonte. Fonte primária (órgão oficial, tabela do fornecedor, página do próprio vendedor) vale mais que blog.
4. Dê o veredito:
   - **confirmado**: a fonte diz isso, e há segunda fonte ou fonte primária;
   - **corrigido**: o valor estava errado; escreva o certo e a fonte;
   - **desatualizado**: era verdade, mudou; escreva o novo valor e a data;
   - **não verificável**: sem fonte aberta, página bloqueada, só trecho de busca. Na dúvida, não confirma.
5. Edite o arquivo no lugar. Marque "(verificado em <data>)" ou "(não verificado)" ao lado de cada número e refaça as contas que dependiam do valor corrigido (margem, ponto de equilíbrio).
6. Anexe a seção de contagens.

Bloqueio de site (erro 403, captcha, pedido de login) vira "não verificável". Não contorne.

## Prompt do verificador

```
Você é um verificador cético. Leia pesquisa/<arquivo>.md.
Para cada afirmação com número, preço, regra ou nome de concorrente:
reabra a fonte citada, busque uma segunda fonte e dê um veredito:
confirmado, corrigido, desatualizado ou não verificável. Na dúvida, não confirme.
Edite o arquivo no lugar: corrija o valor, marque (verificado em <data>) ou (não verificado)
e refaça as contas que dependiam do valor corrigido.
Use só busca na web e páginas públicas. Não contorne bloqueio.
No fim, anexe a seção "## Verificação" no formato abaixo.
Limite de buscas: <N>. Se a cota acabar, pare e liste o que ficou sem verificar.
```

## Formato da seção "Verificação"

```
## Verificação
Verificado em: <data>
Checadas: <n> | Confirmadas: <n> | Corrigidas: <n> | Desatualizadas: <n> | Não verificáveis: <n>

Correções
- <afirmação original> -> <valor certo> (<fonte>, <data>)

Não verificáveis
- <afirmação> (motivo: página bloqueada | só trecho | sem segunda fonte)
```

Some as contagens de todas as frentes no `plano.md`. Se houver muitos "não verificáveis" numa frente, diga isso no resumo: aquela parte do plano é estimativa.
