# Caderno de vendas

O caderno é o que permite medir. Sem ele, só se sabe quanto o anúncio gastou, não quanto vendeu. Fica em `vendas/caderno.csv`, no projeto do usuário, e não vai para e-mail nem nuvem compartilhada.

## 1. Como as vendas chegam ao caderno

**Padrão:** o dono conta ou cola a venda para o Claude, no próprio ciclo. Pode ser em texto solto: "hoje 2 corte e 1 barba, 3 de conhecido e 1 do anúncio". O Claude lança, pergunta só o que falta (valor, origem) e mostra as linhas antes de gravar.

**Venda dita por áudio:** o Claude não promete transcrever áudio. Peça o texto, ou a transcrição que o usuário já tenha (a do próprio celular, por exemplo). Sem isso, diga que a venda ficou fora do caderno até haver texto.

**Opção avançada: grupo de WhatsApp.** O dono manda as vendas num grupo, e o oZap, com o número dentro do grupo, lê as mensagens (o `get_messages` do oZap devolve a transcrição dos áudios no campo `transcription`). Tem custos e limites:
- só funciona se o número conectado ao oZap estiver no grupo; a conexão por QR lê grupo; a conexão pela API oficial, quando sair (hoje em aprovação na Meta), não lê grupo;
- a IA desse número precisa estar pausada no grupo, senão ela responde lá. Pausar a IA é uma ação: ok do dono;
- as vendas também aparecem em outros lugares (no WhatsApp do negócio, no celular pessoal do dono). O Claude reconcilia e lança só o que não está no caderno;
- LGPD: um grupo com clientes ou terceiros dentro não deve ser lido.

Se o dono não quer o grupo, nada se perde: o padrão basta.

## 2. Colunas

```csv
id,data,tipo,itens,valor,origem,cliente_novo,fonte,ref_mensagem,obs
```

| Coluna | O que é |
|---|---|
| `id` | Único e repetível: `<fonte>-<ref_mensagem>-venda`, ou `manual-AAAAMMDD-NN` se foi dita ao Claude. Ler de novo não duplica. |
| `data` | Data da venda (AAAA-MM-DD). |
| `tipo` | `venda` ou `compra` (gasto de insumo). Compras entram só se o dono quiser medir margem. |
| `itens` | O que foi vendido, em texto curto. |
| `valor` | Valor em reais, como o dono disse. Nada estimado pelo Claude. |
| `origem` | Uma da lista da seção 3. |
| `cliente_novo` | `sim`, `nao` ou vazio se não souber. |
| `fonte` | `ditado`, `grupo`, `conversa`, `colado`. |
| `ref_mensagem` | Id da mensagem, se houver. |
| `obs` | Livre. Sem telefone, sem endereço. |

Cliente: use só o primeiro nome ou um id em `obs`, nunca o telefone completo.

## 3. Origens padrão

`conhecido` (círculo de pessoas próximas), `status`, `instagram`, `google` (Perfil da Empresa no Google ou Maps), `grupo` (grupo do bairro), `parceiro` (indicação de um negócio vizinho), `anuncio`, `indicacao`, `passou_na_porta`, `outro`, `nao_anotada`. Os códigos de canal de `vender-sem-anuncio` (G1, S1, I1, B1, P1, Q1) caem nessas origens.

`nao_anotada` é uma resposta honesta. Prefira ela a chutar. É comum boa parte das vendas ficar sem origem, porque quem vende não pergunta de onde o cliente veio, e a origem gravada pela plataforma às vezes falta ou só guarda a primeira. Diga isso no relatório sempre que `nao_anotada` for grande.

Para o anúncio, o caminho principal é o código: cada anúncio e cada link de WhatsApp leva uma mensagem pronta com um código diferente (por exemplo "Oi! Vi o anúncio A1"). O código aparece na primeira mensagem do cliente e liga a conversa à venda.

## 4. Regras

- O Claude não inventa venda. Só lança o que o dono disse, colou ou o oZap leu.
- O dono não é cobrado por venda não anotada. Quem trabalha no negócio e se sente vigiado para de anotar. Pergunte só quando o negócio precisa para agir.
- Se uma venda aparece na conversa e não está no caderno, proponha a linha no diário; o dono confirma.
- Pergunta do dono do projeto ("como estamos hoje?") se responde só com o dado que já existe. Se falta, diga que falta; não pergunte a quem trabalha no negócio.
