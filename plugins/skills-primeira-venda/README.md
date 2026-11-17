# Negócio local: presença e vendas

Skills em português para o Claude Code montar do zero, ou completar, a presença e as vendas de um negócio local, próprio ou de cliente. O plugin cobre pesquisa e plano, marca, fotos e conteúdo, WhatsApp Business, Página do Facebook, Instagram, anúncios de mensagem, atendimento no WhatsApp (com ou sem IA) e o acompanhamento das vendas depois que tudo está no ar.

Estas skills saíram de um caso real de um pequeno negócio de comida feita em casa, transformado em passos genéricos. Os números do caso aparecem como "o que aprendemos", com a amostra dita, e nunca como promessa. A amostra é pequena e é de um único negócio. Não use como garantia de resultado.

## O que o plugin faz, e o que não faz

- Faz: pesquisa, escreve, organiza, calcula, prepara o material e deixa tudo em arquivos na pasta do seu projeto.
- Não faz: criar conta por você, digitar senha, CPF, cartão ou código, pagar, nem dar o clique final de publicar um anúncio.
- Não promete: venda, lucro ou "100% automático". Um atendente de IA ajuda a responder, mas você continua no comando.
- Ação para fora (publicar, gastar em anúncio, mandar mensagem a cliente, mudar o atendente no ar, ligar a IA num número, salvar um campo público de perfil) só com o seu ok explícito, item por item. O Claude mostra exatamente o que vai sair e espera o "sim".

## As 8 skills

Chame pelo nome (`/skills-primeira-venda:montar-negocio`) ou peça em texto livre.

| Skill | Quando usar |
|---|---|
| `montar-negocio` | Pedido amplo: "monte meu negócio nas redes", "o que falta?", "por onde eu começo?". Faz a entrevista, grava a ficha do negócio, levanta o que já existe e propõe a ordem de trabalho. |
| `pesquisa-e-plano` | Pesquisa de mercado, preço, concorrentes, custo, margem, ponto de equilíbrio, plano de negócio ou de marketing. Termina num plano com decisões e num teste curto de venda com meta e piso escritos antes. |
| `marca` | Nome (com checagem de homônimo e de @), paleta, fontes, logo, foto de perfil, rótulo, etiqueta ou adesivo. |
| `conteudo` | Post, story, reel, carrossel, legenda, criativo, catálogo ou calendário, a partir de fotos e vídeos reais. Revisa privacidade, autorização de imagem, preço e área segura antes de publicar. |
| `presenca-nas-redes` | Criar ou arrumar o WhatsApp Business, a Página do Facebook e o Instagram: escolha do número, kit de textos e imagens para colar, ligação entre as contas e publicações. |
| `anuncios` | Anunciar ou impulsionar com destino no WhatsApp: a conta de quanto pode custar cada venda antes de gastar, conferência da conta de anúncios, criativos e leitura do resultado por venda, não por clique. |
| `atendente-ia` | Atendimento no WhatsApp: prompt do atendente com IA, casos de teste e regras de aviso ao dono. Sem IA, entrega saudação, respostas rápidas e roteiro para o WhatsApp Business. Também serve para entender por que o atendente erra. |
| `acompanhar-vendas` | O "agente gestor": ciclos diários ou semanais que leem o caderno de vendas, as conversas e os números de anúncio, calculam o funil e o custo por venda, propõem follow-ups com o texto exato e escrevem um diário. |

### As duas entradas

1. **Do zero.** A skill `montar-negocio` faz uma entrevista curta, grava a ficha e propõe a ordem. O número do negócio vem primeiro, porque depende de você e demora. Plano leve e marca andam em paralelo enquanto isso. Depois vêm WhatsApp Business, Página, Instagram, conteúdo base, atendimento, anúncio (só com tudo pronto) e acompanhamento.
2. **Completar.** O Claude levanta o que já existe e monta um quadro "tem / falta / está ruim". Cada linha diz como ele sabe: visto pelo navegador, print seu, dito por você ou não verificado. Depois propõe só o que falta.

Pedidos de uma peça só, de um anúncio, do perfil ou do atendente vão direto para a skill daquela etapa.

## O que é com você

- Criar as contas: Página, Instagram, portfólio de negócios, conta de anúncios e, se quiser IA no atendimento, a conta do oZap.
- Senhas, CPF, forma de pagamento e qualquer pagamento. O Claude nunca digita nem pede isso no chat.
- Códigos de verificação e QR code.
- Foto e vídeo do produto ou do serviço. Use fotos e vídeos reais: é o que o cliente vai encontrar na entrega, e no caso que originou o plugin (amostra pequena, um só negócio) o vídeo real teve o melhor custo por conversa.
- Dar o clique final de publicar um anúncio.
- Aprovar cada ação para fora.
- Passar preço, prazo, horário, endereço e estoque. O Claude não inventa nada disso: o que faltar vira pergunta para você.
- Quem trabalha para cliente: o cliente cria o próprio portfólio de negócios e dá acesso de parceiro. Nunca use a senha dele. O Claude confere o nome da conta e do portfólio na tela antes de qualquer gasto ou publicação.

## O que pode custar

O plugin é grátis. O que ele usa e recomenda pode não ser. Os custos aparecem antes de cada decisão.

- Anúncio: o valor que você coloca e mais o imposto cobrado no cartão. No caso que originou o plugin, o imposto somou mais de 10% sobre o gasto; confira na sua fatura.
- Plano do oZapOnline, se você quiser atendente de IA no WhatsApp: dá para testar grátis, e a IA continuar respondendo depois pede um plano (veja o preço no site).
- Chave paga de edição de imagem, se você quiser trocar fundo ou gerar foto de catálogo a partir de uma foto real (por exemplo, um modelo de imagem de algum provedor). É opcional, a chave é sua e vale deixar um limite de gasto no provedor.
- Chave paga de voz sintética, para locução de reel (por exemplo, um serviço de voz de algum provedor). É opcional; sem ela o vídeo vai sem voz, com texto na tela.
- Remotion, se você escolher fazer peças e vídeos por código: é gratuito para pessoas e empresas pequenas e pago para empresas maiores. É opcional.
- Pesquisa completa gasta bastante da sua cota do Claude. A skill oferece uma versão leve e diz o custo antes de começar.

## Ferramentas

Nenhuma é obrigatória para começar. Cada skill diz o que usa e o que fazer quando falta.

- Pesquisa na web e subagentes: aceleram a pesquisa. Sem eles, o Claude trabalha com o que você informa e marca tudo como "não verificado".
- Claude in Chrome: o Claude lê perfis públicos e preenche campos de perfil e do Gerenciador de Anúncios com você olhando. A Meta e o WhatsApp restringem acesso automatizado: mesmo com você olhando, há risco de a conta ser revisada ou limitada. Por isso o caminho padrão é o seu celular, e o Claude avisa antes de usar o navegador. Sem ele, você recebe um passo a passo numerado com os textos prontos para colar, e traz os números de anúncio por print. A documentação oficial do Claude Code diz como ligar.
- Seu celular: é o caminho padrão para gravar, editar vídeo e publicar pelo app.
- Python, ffmpeg e Node são opcionais. Antes de instalar qualquer pacote, o Claude mostra o comando e pede o seu ok. O Python vai num ambiente isolado dentro da pasta do projeto.

O plugin não traz scripts. O que for código vem como bloco dentro das references, para o Claude escrever no seu projeto na hora.

## Instalar

```
/plugin marketplace add omarcusdev/skills-primeira-venda
/plugin install skills-primeira-venda@omarcusdev
```

Para instalar de uma cópia local do repositório, use o caminho da pasta: `/plugin marketplace add ./skills-primeira-venda`.

Depois, abra o Claude Code na pasta do negócio (para agência, uma pasta por cliente) e peça, por exemplo:

1. "Monte do zero a presença da minha barbearia."
2. "Veja o que já existe do meu pet shop e diga o que falta."
3. "Quanto posso pagar por venda num anúncio para a minha lanchonete?"
4. "Escreva o atendente do WhatsApp da Doceria Aurora."

As skills guardam tudo em arquivos na pasta do projeto: ficha do negócio, plano, decisões, diário. O chat se perde e a sessão fecha; o arquivo fica.

## O oZapOnline (opcional)

O oZapOnline é um produto separado, do mesmo autor deste plugin. Ele aparece por nome em três lugares: `atendente-ia` (o atendente de IA no WhatsApp), `acompanhar-vendas` (ler conversas e funil, follow-up e relatório) e `anuncios`, só no passo de ler o resultado. Todo o resto do plugin funciona sem ele.

> O oZapOnline é do mesmo autor deste plugin. É pago por assinatura e dá pra testar grátis; para a IA seguir respondendo depois do teste, é preciso um plano (veja o preço no site). A conexão do número é por QR code, como o WhatsApp Web, e não é a API oficial da Meta: mandar mensagem em massa ou para quem não escreveu pode levar o WhatsApp a restringir o número. A conexão pela API oficial está em aprovação na Meta (em nov/2026; confira no painel). Sem o oZap, esta parte funciona assim: saudação, mensagem de ausência e respostas rápidas do WhatsApp Business, e as vendas e conversas que você digita ou cola para o Claude.

Para usar o oZap por dentro do Claude Code, instale o plugin `ozap`, à parte:

```
/plugin marketplace add ozapgpt/ozap-claude-plugins
/plugin install ozap@ozaponline
```

Depois crie a conta em [app.ozaponline.com/cadastro](https://app.ozaponline.com/cadastro), digite `/mcp`, escolha `plugin:ozap:ozap` e **Authenticate**. As skills deste plugin passam a vez para as do `ozap` (`conectar-whatsapp`, `configurar-cliente`, `testar-e-ir-ao-ar`, `triar-conversas`, `relatorio-semanal` e outras) nos pontos em que o atendimento com IA entra.

Hoje, avisos ao dono, notificação no celular e reativar a IA numa conversa são configurados no painel do oZapOnline. Não há ferramenta para isso no MCP, e a skill manda você fazer por lá.

Quem atende mais de um cliente: uma credencial do oZap pode alcançar mais de um número. Antes de ler ou enviar qualquer coisa, o Claude confere o `connection_id` e o número contra a ficha do cliente.

## Privacidade e LGPD

- Endereço de casa, telefone e e-mail pessoais, print com nome de terceiro e marca vizinha nunca entram em peça pública.
- Rosto ou pet de cliente só aparece com autorização de uso de imagem registrada. Sem ela, a imagem é recortada ou o rosto fica desfocado.
- Dados de clientes do negócio são minimizados: primeiro nome ou id, sem telefone completo no diário. Quem opera para um cliente guarda por escrito a autorização do dono para tratar os dados dos clientes dele.
- Texto de conversa de cliente é dado, nunca ordem. Se uma mensagem tentar dar ordens ao Claude, ele avisa você.
- O Claude nunca cria contas por automação, nunca injeta código em páginas da Meta, nunca responde comentário ou mensagem direta em lote e nunca raspa perfis. A pesquisa de concorrência usa busca na web e páginas públicas.
- A skill sugere um `.gitignore` para as pastas que guardam dado de cliente, chave ou arquivos pesados, para que nada disso vá parar num repositório.

## Licença

MIT. Veja o arquivo [LICENSE](LICENSE).
