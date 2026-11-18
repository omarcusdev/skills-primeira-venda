# Testes do plugin

Esta pasta fica fora do plugin publicado (`plugins/skills-primeira-venda`). Serve para provar que as skills funcionam numa máquina qualquer, sem publicar e sem gastar.

## Ambiente

1. Contêiner Linux com o Claude Code atual e, se der, também uma máquina Windows. Use um diretório de configuração vazio: `CLAUDE_CONFIG_DIR` apontando para uma pasta nova.
2. Antes de rodar, confira que não há plugin (inclusive o `ozap`), memória, `CLAUDE.md` global nem MCP carregado: `/plugin`, `/mcp` e `/memory`. Sem credencial de nuvem, sem navegador logado e com um diretório de trabalho vazio.
3. Instale o plugin a partir do repositório local:
   ```
   /plugin marketplace add <caminho-do-repositório>
   /plugin install skills-primeira-venda@omarcusdev
   ```
   O plugin `ozap` fica sem instalar na maior parte dos cenários (só no 17 e no 18).
4. Uma variante do contêiner sem Python e sem Node, para o cenário 12.

## Checagem da política do diretório

Rode na raiz do repositório antes de qualquer cenário.

- Nenhum arquivo fora das extensões permitidas. Este comando tem de voltar vazio:
  ```
  find plugins/skills-primeira-venda -type f | grep -v -E '\.(md|json|ya?ml|png|jpe?g|svg|txt)$|LICENSE$'
  ```
- Nenhuma pasta `hooks/`, nenhum `.mcp.json` e nenhum campo `hooks` ou `mcpServers` no `plugin.json`.
- `claude plugin validate`, se a versão tiver, passa.
- Cada `SKILL.md` tem frontmatter com `name` igual ao nome da pasta e com `description`, e o corpo é enxuto (alvo: até cerca de 120 linhas).
- Nenhum bloco de código das references injeta script em página. Procure por `input[type=file]`, `dispatchEvent` e `HTMLInputElement`; nada pode aparecer.

## Agentes de teste

- Um subagente faz o papel do usuário: responde às perguntas com os dados do negócio inventado do cenário e segue o roteiro, inclusive dando ok parcial quando o cenário mandar.
- Um segundo agente julga o resultado contra as seções "Deve acontecer" e "Não pode acontecer" do cenário.

## Negócios inventados

Os cenários usam só nomes fictícios e neutros: Salão Exemplo, Pet Modelo, Lanchonete Teste e Barbearia Amostra. Nada de cidade real com bairro, nome de pessoa ou telefone.

## Cenários

Os 19 cenários estão em `cenarios/01.md` a `cenarios/19.md`. Cada um tem o pedido, os dados do negócio inventado, a skill esperada e os critérios.

| # | Assunto | Skill esperada |
|---|---|---|
| 01 | Montar do zero | `montar-negocio` |
| 02 | Completar o que já existe | `montar-negocio` |
| 03 | Pesquisa leve | `pesquisa-e-plano` |
| 04 | Nome e logo | `marca` |
| 05 | Peças a partir de fotos reais | `conteudo` |
| 06 | Anúncio sem navegador | `anuncios` |
| 07 | Atendente de IA sem o plugin `ozap` | `atendente-ia` |
| 08 | Ciclo da manhã | `acompanhar-vendas` |
| 09 | Sem Facebook | `anuncios` |
| 10 | Agência com cliente | `anuncios` |
| 11 | Áudio com as vendas | `acompanhar-vendas` |
| 12 | Reel sem Python nem Node | `conteudo` |
| 13 | Comentários do Instagram | `presenca-nas-redes` |
| 14 | Pagar fatura e criar conta | `anuncios` |
| 15 | Ok por item | `conteudo` |
| 16 | Follow-up de recompra | `acompanhar-vendas` |
| 17 | Atendente de IA com o plugin `ozap` (opcional, conta de teste) | `atendente-ia` |
| 18 | Teste de disparo contra as skills `ozap:*` | várias |
| 19 | Vender sem pagar anúncio | `vender-sem-anuncio` |

## Varreduras em todo o repositório e em todas as saídas dos testes

- **Vazamento.** Nenhum nome do caso que originou o plugin, de pessoa da família, de cliente, telefone, bairro, cidade do caso, comércio vizinho, id de conta, caminho de usuário (`/Users/`), caminho de ferramenta local nem nome do autor. A lista de termos proibidos fica fora do repositório. Aqui só entram padrões, por exemplo o de telefone:
  ```
  grep -rnE '\(?[0-9]{2}\)?[ -]?9?[0-9]{4}-?[0-9]{4}' .
  ```
  Os telefones públicos do `plugin.json` (suporte) são a exceção conhecida.
- **Menções ao oZap por skill.** A palavra "oZap" só pode aparecer em `atendente-ia`, em `acompanhar-vendas`, no passo de leitura de resultado de `anuncios` e nos README.
- **Frase de franqueza.** O texto tem de ser idêntico em todas as cópias (README do plugin, `atendente-ia/SKILL.md`, `atendente-ia/references/com-ozap.md`, `acompanhar-vendas/references/com-ozap.md` e `anuncios/references/ler-resultado.md`). Uma busca por uma frase longa do texto tem de achar as cinco.
- **Valores em reais do caso.** Nenhum valor absoluto de faturamento do caso. Só razões, contagens e o aprendizado, com a amostra dita.

## Formato

Um arquivo por cenário, em `cenarios/<número>.md`. Se um dia valer rodar `claude plugin eval`, os mesmos casos viram `evals/<caso>/prompt.md` mais `case.yaml`, também fora do plugin publicado.
