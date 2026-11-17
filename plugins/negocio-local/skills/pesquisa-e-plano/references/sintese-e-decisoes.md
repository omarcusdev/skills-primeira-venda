# Síntese e decisões

## Crítico de completude (versão completa)

Depois das frentes, um agente (ou um segundo passo do Claude) lê todos os relatórios e lista até 6 lacunas por importância: o que o dono precisa saber para decidir e ninguém pesquisou. Pesquise só as 4 primeiras. Diga ao usuário quais ficaram de fora e por quê. Na versão leve, o crítico vira uma linha no fim do plano: "o que este plano não cobre".

```
Você é um crítico de completude. Leia pesquisa/*.md e negocio/ficha.md.
Liste até 6 lacunas que impedem uma decisão do dono, da mais para a menos importante.
Para cada uma: a pergunta, por que importa e se dá para pesquisar na web ou só o dono responde.
Não pesquise. Não invente.
```

## `plano/plano.md` (modelo)

```
# Plano: <nome do negócio>
Gerado em: <data> | Tamanho: leve | completa

## Resumo
5 a 8 linhas. O que o negócio faz, o que a pesquisa achou, o que recomendamos e o que falta saber.

## Números-chave
| Número | Valor | Base (medido | fonte | estimativa) |

## Onde os relatórios discordam e qual valor adotamos
| Assunto | O que cada relatório disse | Valor adotado | Por quê |

## Decisões
(formato abaixo; de 5 a 15 na leve, até cerca de 30 na completa)

## Premissas
| id | Premissa | Base: medido | fonte | estimativa |

## Riscos
| Risco | Probabilidade | Impacto | O que fazer |

## Pendências para o dono
| id | Pergunta | Por que importa | Quem responde |

## Verificação (soma das frentes)
Checadas, confirmadas, corrigidas, desatualizadas, não verificáveis.

## O que este plano não cobre
```

### Onde os relatórios discordam

A síntese é obrigada a expor as contradições entre frentes (custo, preço, entrega, imposto, validade, verba) e a dizer qual valor adotou e por quê. Se dois relatórios divergem e não dá para decidir, adote o mais conservador e marque "(estimativa)".

### Premissas

Toda premissa leva a base: **medido** (veio do dono ou do negócio rodando), **fonte** (link e data) ou **estimativa** (com a conta). Premissa "estimativa" que mexe no resultado vira item do teste: o teste existe para medi-la.

## Formato de decisão (A/B/C)

```
### D01 Título curto da decisão
Área: preço | produto | logística | regras | marketing | conteúdo | parceria | operação | finanças
Urgência: agora | em 30 dias | em 90 dias
Depende de: <D02, se houver>

Pergunta: <o que o dono precisa decidir>
Contexto: <2 a 4 linhas com os fatos>

A) <opção> — custo: <valor ou esforço> — recomendada
B) <opção> — custo: <...>
C) <opção> — custo: <...>

Por que a recomendada: <1 a 2 linhas>
Fontes: <links>
```

Regras:

1. **Exatamente uma** opção recomendada por decisão.
2. Todo custo em dinheiro, tempo ou os dois. Se for gasto com anúncio, some o imposto da plataforma (confira na sua fatura) e diga que o gasto real só sai com o ok da skill `anuncios`.
3. Decisão que é só do dono (marca, preço final, o que cortar) aparece como pergunta, não como fato.
4. Decisão com regra legal: escreva a opção de formalizar e a de esperar, o que cada uma arrisca e "confira com a fonte oficial da sua cidade". A skill não dá parecer jurídico.
5. Corte o que não muda nada. Decisão que ninguém vai tomar agora é ruído.

## Apresentar ao dono (uma rodada)

1. Mande as decisões numa **lista numerada no chat**, cada uma com as opções e a recomendada. Peça resposta por item, por exemplo "1 A, 2 B, 3 recomendada".
2. Grave cada escolha em `negocio/decisoes.md`: id, escolha, data, quem decidiu.
3. Se o dono votar contra a recomendada, **execute o voto dele** e registre a divergência ("o plano recomendava A; o dono escolheu B"). No caso de origem, o dono escolheu o contrário do plano numa decisão sobre imagem, e a execução seguiu o voto dele.
4. Guarde as respostas em arquivo local. Página de votação não é armazenamento durável: no caso, as páginas de votação sumiram dias depois.
5. Votação só uma vez. Depois da decisão, execute e relate fatos. O dono se irritou com páginas de votação repetidas.
6. Burocracia que o dono quer adiar até o teste mostrar se vende (formalização, rótulo definitivo, vigilância): registre em `decisoes.md` com "adiado por escolha do dono". Diga em uma linha que adiar não elimina a obrigação, e quando ela deve voltar à pauta (por exemplo, "quando passar no veredito").
