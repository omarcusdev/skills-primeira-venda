# Estrutura do projeto

As skills criam e usam esta estrutura na pasta do negócio. Para agência, uma pasta por cliente, sem arquivos compartilhados entre elas. Todos os caminhos são relativos à pasta do negócio: abra o Claude Code dentro da pasta do cliente. Se a sessão estiver numa pasta com vários clientes, pergunte qual é o cliente e use `<cliente>/negocio/ficha.md` em todos os caminhos, ou peça para abrir a sessão na pasta dele.

```
<negocio>/
├── negocio/ficha.md          fatos do negócio (fonte única: telefone do negócio, preços, horários, entrega, pagamento, tom, o que nunca dizer)
├── negocio/estado.md         quadro tem / falta / está ruim, com a coluna "como sei", e a ordem de trabalho
├── negocio/decisoes.md       cada decisão e cada ok por item, com data e quem aprovou
├── pesquisa/                 relatórios por frente, com seção "Verificação"
├── plano/plano.md, plano/teste.md
├── marca/marca.json, marca.md, logo.svg, perfil.png, rotulos/
├── midia/originais/          nunca alterada
├── midia/tratadas/
├── midia/inventario.md       com a coluna "autorização de imagem"
├── conteudo/<semana>/        peças, legendas.md, revisao.md
├── publicar/                 kit numerado para o humano colar (LEIA-PRIMEIRO.md)
├── anuncios/conta.md, anuncios/rodada-N/{plano.md,passo-a-passo.md,resultado.md}
├── atendente/prompt.md, testes.md, erros.md
├── gestao/brief.md, gestao/diario/AAAA-MM-DD.md, gestao/toques.md
├── vendas/caderno.csv
└── ferramentas/              código que o Claude escreveu a partir das references, e o venv
```

Cada skill cria só as pastas de que precisa. `montar-negocio` cria `negocio/` com os três arquivos: ficha, estado e decisões.

## Quem escreve o quê

| Pasta ou arquivo | Skill que escreve |
|---|---|
| `negocio/*` | `montar-negocio` (e cada skill atualiza o estado no fim da etapa) |
| `pesquisa/`, `plano/` | `pesquisa-e-plano` |
| `marca/` | `marca` |
| `midia/`, `conteudo/` | `conteudo` |
| `publicar/` | `presenca-nas-redes` |
| `anuncios/` | `anuncios` |
| `atendente/` | `atendente-ia` |
| `gestao/`, `vendas/` | `acompanhar-vendas` |
| `ferramentas/` | qualquer skill que use código opcional, sempre com ok antes de instalar |

## Proteger os dados de clientes

Para o dono, uma frase só: "não mande as pastas `vendas/` e `gestao/` por e-mail ou nuvem compartilhada". Não fale de git nem de `.gitignore` com quem não pediu.

### `.gitignore`, só se a pasta já for um repositório git

Confira com uma ferramenta antes: `git rev-parse --is-inside-work-tree` responde `true`, ou existe a pasta `.git`. Nunca diga que a pasta usa git sem ter conferido. Se for repositório, sugira acrescentar as linhas abaixo e grave só com o ok. `vendas/`, `gestao/` e `atendente/erros.md` guardam dado e trechos de conversa de cliente. `midia/autorizacoes/` guarda nome e assinatura de cliente. `midia/quadros/` guarda quadros de vídeo com rosto. `midia/originais/` guarda foto sem tratamento e peso. `.env` guarda chave.

```
vendas/
gestao/
atendente/erros.md
midia/originais/
midia/autorizacoes/
midia/quadros/
ferramentas/.venv/
.env
```

O diário e os toques ficam locais. Não vão para e-mail, nuvem compartilhada nem repositório on-line: têm dado de cliente do negócio.

## Regras de conservação

- `midia/originais/` nunca é alterada: o Claude trabalha em cópias.
- `negocio/ficha.md` é a única fonte de telefone, preço e horário. Peça e legenda leem dali, nunca de memória do chat.
- Nenhuma chave, senha ou código em arquivo do projeto, exceto a chave paga opcional em `.env`, que nunca é enviado nem compartilhado.
