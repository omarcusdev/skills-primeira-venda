# Ciclos e permissões

## 1. Padrão: ciclo à mão

Você abre o projeto no Claude Code e diz o ciclo:

- "faz o ciclo de hoje" (leitura geral e follow-ups do dia);
- "faz o ciclo da manhã", "da tarde" ou "do fechamento";
- "faz o ciclo da semana" (funil da semana contra a meta e o mínimo da semana).

Funciona sempre, em qualquer máquina. A continuidade vem do `gestao/brief.md` e do último diário.

Ritmo sugerido para quem começa: sem oZap, um ciclo por dia ou por semana. Com o oZap lendo as conversas, até 3 por dia (manhã, tarde, fechamento) se houver movimento. Mais do que isso gasta cota e raramente muda a decisão.

O fechamento é o único ciclo que precisa de números de anúncio: o dono traz print do Gerenciador (gasto, exibições, cliques e conversas por anúncio) ou lê com o Claude in Chrome, com ok, fora do loop.

## 2. Dentro de uma sessão aberta: `/loop`

`/loop` repete um prompt em intervalos. Serve para ler e escrever o diário sem você pedir toda vez. `/loop` só existe no Claude Code. Fora dele, diga ao dono "peça o ciclo quando abrir o computador", sem dizer qual app ele usa, e não diga "a skill" nem "as instruções do projeto". Limites, ditos antes:

- só roda com a sessão aberta e a máquina ligada;
- some quando a sessão fecha ou a máquina reinicia;
- lembretes recorrentes da sessão expiram (em 7 dias, quando isto foi escrito). O comportamento pode mudar: confira na documentação do Claude Code antes de prometer um intervalo ao dono;
- agentes de fundo morrem com a sessão.

Se o loop sumir, nada se perde: o diário e o brief estão em arquivo. Recomece pelo ciclo à mão.

### Permissões mínimas do loop

O ciclo em loop **só lê o projeto e escreve em `gestao/`**. Ele não lê só `gestao/`, porque precisa de `plano/teste.md`, `vendas/caderno.csv` e `negocio/ficha.md`. Libere só isso, nas permissões do projeto (`.claude/settings.json`), e mostre o arquivo ao dono antes de salvar. Exemplo; confira os nomes exatos das tools em `/mcp` e `/permissions`:

```json
{
  "permissions": {
    "allow": [
      "Read(./**)",
      "Write(gestao/**)",
      "Edit(gestao/**)",
      "mcp__plugin_ozap_ozap__list_chats",
      "mcp__plugin_ozap_ozap__get_messages"
    ]
  }
}
```

Sem oZap, tire as duas últimas linhas. Nunca libere leitura fora da pasta deste negócio (agência: as pastas dos outros clientes ficam de fora). Dentro do loop:

- **nunca** use bypass de permissões nem "aceitar tudo". Se o Claude pedir permissão para algo fora disso, o ciclo para e espera o dono;
- o caderno (`vendas/caderno.csv`) não é atualizado pelo loop: as vendas novas ficam como "linhas propostas" no diário, e você as lança no passo à mão;
- o Claude in Chrome fica desconectado e a aba do Gerenciador de Anúncios, fechada;
- `send_message` e qualquer outra tool de escrita do oZap ficam de fora da lista;
- envio e qualquer mudança acontecem num passo à parte, com o usuário presente.

## 3. Rotina na nuvem: fora desta versão

Uma rotina agendada na nuvem não tem garantia de acesso ao MCP do oZap instalado localmente, e o diário e o caderno, que têm dados de cliente, teriam de subir para um repositório. Por isso o padrão é o ciclo à mão.

## 4. Em qualquer modo

Nada é enviado sem o ok do humano naquele item. O ciclo termina com o relatório curto e o diário gravado.
