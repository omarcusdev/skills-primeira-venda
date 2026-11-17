# WhatsApp Business

Exemplos inventados: "Doceria Aurora" (produto) e "Salão Exemplo" (serviço). Troque pelos dados da ficha. Nada de preço, prazo ou estoque que não esteja na ficha.

## O que dá pelo computador e o que só pelo celular

Os termos do WhatsApp restringem o uso por meio automatizado. Mesmo campo a campo e com o dono olhando, há risco de o número ser restringido, e é justamente o número do negócio. O padrão é o dono colar os textos do kit no app. O Claude só preenche pelo WhatsApp Web se o dono pedir depois deste aviso. Diga o aviso antes de começar.

| Item | Onde |
|---|---|
| Descrição do perfil, foto, categoria | WhatsApp Web (com ok por campo) ou app |
| Catálogo (itens, fotos, preço, descrição) | WhatsApp Web (com ok por campo) ou app |
| Respostas rápidas | WhatsApp Web (com ok por campo) ou app |
| Etiquetas | app (confira se o Web oferece) |
| Mensagem de saudação | só no app |
| Mensagem de ausência | só no app |
| Horário de funcionamento | só no app |
| Nome do perfil (inclusive acento) | só no app; trocar o nome pode passar por revisão da Meta |

O dono instala o app e registra o número. Ler o QR de "Aparelhos conectados" para abrir o WhatsApp Web é do dono. Só se o dono pedir, depois do aviso acima, e com Claude in Chrome nessa aba e ele olhando, o Claude pode preencher os campos da tabela marcados como Web, um por vez, com ok. **Nunca enviar mensagem a cliente pelo WhatsApp Web automatizado.**

## Armadilhas do caso

1. A digitação pelo navegador às vezes come letras. Releia cada texto depois de salvar.
2. O dono cadastrou o nome sem acento. Nome e acento se corrigem no app.
3. O horário pode vir como "aberta 24 horas" (padrão). Ajuste no app.
4. A categoria vem genérica ("Compras e varejo"). Troque por uma específica do negócio.
5. Foto de produto com adesivo, embalagem ou fachada mostrando número antigo não entra no perfil nem no catálogo. Confira todas as imagens contra o número da ficha.
6. Endereço em branco por padrão se o negócio funciona em casa. Só entra com ok do dono.
7. Catálogo novo fica "em análise" pela Meta. No caso, a aprovação saiu em horas. Confira no app.
8. Atualizar item de catálogo (frase de entrega, produto novo) pode exigir o celular. Deixe como tarefa do dono se o Web não permitir.

## Modelos

**Descrição do perfil (até 3 linhas):**
```
Doces feitos em casa. Brigadeiro, brownie e bolo no pote.
Pedidos pelo WhatsApp, retirada ou entrega.
Atendimento de segunda a sábado, das [hora] às [hora].
```

**Mensagem de saudação:**
```
Oi! Aqui é a Doceria Aurora. Me diga o que você quer pedir e para quando. Já te respondo.
```
Se mais tarde o atendimento for com IA, a saudação diz que é o atendimento virtual do negócio (veja `atendente-ia`). Sem IA, não afirme "atendimento virtual".

**Mensagem de ausência:**
```
Oi! Agora estamos fora do horário. Voltamos [dia] às [hora]. Deixe seu pedido aqui que respondemos assim que abrirmos.
```

**Respostas rápidas (atalho, texto).** Campos entre `[colchetes]` só o dono preenche:

| Atalho | Texto |
|---|---|
| `/precos` | `Nossos preços: [lista da ficha]. Qual você quer?` |
| `/pedido` | `Para fechar o pedido, me diga: o que, quantos, para qual dia e se é retirada ou entrega.` |
| `/pagamento` | `Aceitamos Pix. Chave: [chave Pix]. Titular: [nome do titular]. Me mande o comprovante.` |
| `/entrega` | `Entrega: [regra da ficha]. Retirada: [ponto de referência].` |
| `/horario` | `Atendemos [dias e horário da ficha].` |
| `/indisponivel` | `Esse item acabou por hoje. Posso te oferecer [alternativa da ficha]?` |
| `/obrigado` | `Obrigado pelo pedido! Qualquer dúvida é só chamar.` |

Se faltar chave Pix, titular ou ponto de referência, o Claude não inventa: deixa a resposta rápida pendente e pergunta ao dono. Não pode ficar com `[campo]` sem preencher no ar.

Para serviço com horário marcado (salão, pet shop), troque `/pedido` por `/agendar` (serviço, dia, horário preferido) e `/precos` pela tabela de serviços.

**Item de catálogo:**
```
Nome: Caixa com 6 brigadeiros
Preço: [valor da ficha]
Descrição: [ingredientes e alergênicos conforme a ficha]. Retirada no local ou entrega, com frete à parte.
Foto: publicar/1-whatsapp-business/catalogo-1.png
```
Ingredientes e alergênicos só os que o dono confirmou. Item novo entra no kit antes de entrar no catálogo.

## Etiquetas e contatos

- Etiquetas sugeridas: "Novo cliente", "Pedido pendente", "Pago", "Pós-venda".
- Peça ao dono para salvar cada cliente que pediu na agenda do celular do negócio, com a origem no nome (por exemplo, "Ana (Instagram)"). O status só é visto por quem tem o número salvo, dos dois lados.
- Lista de contatos pessoais e de família não entra em etiqueta de cliente.

## Status do WhatsApp

Canal de presença que não é rede social. O dono posta à mão, por exemplo uma pronta-entrega do dia com o que tem de verdade. O Claude pode preparar a imagem e o texto no kit; quem publica é o dono. Não é automatizado.
