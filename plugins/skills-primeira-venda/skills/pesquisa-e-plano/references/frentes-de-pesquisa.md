# Frentes de pesquisa

Cada frente é uma pergunta grande, com um arquivo de saída `pesquisa/NN-frente.md`. Use a lista abaixo como menu: nem todo negócio precisa de todas.

## Leve (padrão): 3 frentes

| Frente | O que entrega |
|---|---|
| 1. Custos e preço | custo unitário (insumos, embalagem, energia ou gás, hora de trabalho), faixa de preço praticada na região, margem. Contas em `custo-e-margem.md` |
| 2. Concorrência | de 8 a 15 vendedores da região ou do canal (preço, oferta, como vendem, o que repetem), só de fonte pública |
| 3. Canais de venda | onde o cliente deste negócio encontra e pede (conhecidos, WhatsApp, Instagram, aplicativo de entrega, passar na porta, parceria), com custo e esforço de cada |

## Completa: até 9 frentes

Some às 3 acima:

| Frente | O que entrega |
|---|---|
| Mercado | tamanho e perfil da demanda na região, tendências, sazonalidade, renda por região quando houver dado público (por exemplo, dados do Censo) |
| Regras e formalização | o que a atividade exige (cadastro como MEI ou outro, vigilância sanitária, rotulagem, alvará, regra do condomínio ou do imóvel). Varia por cidade e muda: cada item sai com a fonte oficial e a marca "confira" |
| Logística | retirada, entrega própria, motoboy, aplicativo; custo por rota e quantas entregas enchem uma rota. Tarifa de aplicativo não se acha na web: o dono simula no celular |
| Marketing | quais canais valem para a verba e o tempo do dono, o que a plataforma exige (sem tratar isto como plano de anúncio: o gasto é da skill `anuncios`) |
| Operação | rotina de produção ou atendimento, lote, desperdício, validade, agenda, picos |
| Conteúdo | o que dá para mostrar (produto, bastidor, serviço sendo feito), formatos e frequência que o dono aguenta |
| Parcerias | quem fica perto do negócio e pode trocar divulgação, sem comissão escondida. Antes, pergunte ao dono se alguma marca vizinha ou parente não pode ser citada |

Fora das frentes, depois delas: **preço e finanças** (lê todos os relatórios e fecha tabela de preço, margens, ponto de equilíbrio e cenários) e o **crítico de completude** (ver `sintese-e-decisoes.md`).

Para serviço (salão, barbearia, oficina), troque "lote e validade" por agenda, tempo por atendimento, retorno do cliente e comissão ou aluguel de cadeira.

## Bloco CONTEXTO (copie para cada pesquisador)

Preencha os campos com a ficha. Não inclua nada do que o dono não autorizou.

```
CONTEXTO
Negócio: <o que vende ou que serviço presta>
Região (só para a pesquisa): <cidade e bairro>
Preços e custos que o dono informou: <tabela>
Verba e prazo do dono: <valores>
O dono recebe decisões assim: opções A/B/C, exatamente uma recomendada, com o motivo e o custo de cada.

REGRAS
- Todo número leva fonte (link) e data, ou a marca (estimativa) com a conta à mostra.
- Texto genérico é proibido. Português do Brasil. Prefira fonte primária e do ano corrente.
- Não invente concorrente, preço, tarifa nem lei. Se não achar, escreva "não encontrei".
- Só busca na web e páginas públicas. Não entre em conta, não raspe perfil, não contorne bloqueio.
- Não cite nomes nem números vindos de prints de conversa do dono.
- Termine com: lacunas (o que não deu para saber) e perguntas para o dono.
```

## Orçamento de buscas

Os números abaixo são **ponto de partida**, não limite do Claude. Ajuste à cota que o usuário disser.

| Tamanho | Por frente | Verificação | Reserva |
|---|---|---|---|
| Leve | cerca de 10 buscas | cerca de 5 por frente | 20% do total, para lacuna ou refazer |
| Completa | cerca de 8 a 10 buscas; concorrência cerca de 20 | cerca de 5 a 6 por frente verificada | 20% do total |

Regras:

1. Some o total antes de lançar e mostre ao usuário.
2. Lance as frentes em lotes de 3 quando a cota for curta; não 9 de uma vez.
3. Se a cota acabar, pare. Grave o que existe, marque a frente como "incompleta" no topo do arquivo e liste o que falta. Uma frente incompleta dita é melhor que uma completa inventada.
4. Resultado de busca que só mostra trecho (sem abrir a página) vale como pista, não como fato: marque "pista, não verificado". Faixa de preço montada com pistas não serve de base para dizer que o preço do dono está caro ou barato; para comparar, abra a fonte ou pergunte ao dono.
5. Ao dono, não conte o método (frentes, número de buscas, fontes reabertas). Diga o que está confirmado e o que é só pista.
