# Perfil da Empresa no Google

A ficha do negócio que aparece na busca do Google e no Maps. É grátis. Nenhuma outra skill do plugin cobre este canal: o kit sai daqui.

**Telas mudam.** Os nomes dos botões abaixo podem ter mudado. Confira o texto da tela antes de tocar. Ajuda oficial para o dono: support.google.com/business.

## Quem faz o quê

- **O dono:** cria a conta do Google (de preferência uma só do negócio), cria o perfil, faz a verificação, cola os textos, sobe as fotos, publica e responde avaliações.
- **O Claude:** monta o kit em `organico/google/` (textos de cada campo, lista de fotos, respostas a avaliações) e o passo a passo. Com Claude in Chrome, o dono logado e o perfil já verificado, pode preencher um campo público por vez, com o ok daquele campo, e reler o que ficou salvo, como em `presenca-nas-redes`. Nunca cria o perfil, nunca faz a verificação, nunca responde avaliação pelo navegador.

## Antes de começar

1. Procure o nome do negócio no Google Maps. Às vezes o perfil já existe, criado por alguém. Se existir, o caminho é pedir a posse dele no próprio perfil ("Reivindicar" ou "Você é o proprietário?"), e não criar outro. Perfil duplicado atrapalha os dois.
2. Defina com o dono: o cliente vai até o negócio, ou o negócio vai até o cliente (ou entrega)? Isso decide o endereço.

## O kit: `organico/google/campos.md`

Um bloco por campo, com o texto pronto para colar. Tudo vem de `negocio/ficha.md`; o que faltar vira pergunta.

| Campo | Como preencher |
|---|---|
| Nome | O nome que está na fachada, no cartão e no Instagram. Sem acrescentar cidade, bairro ou "melhor de" no nome: o Google proíbe e pode suspender o perfil. |
| Categoria principal | A que descreve o negócio em poucas palavras (por exemplo "Barbearia", "Pet shop", "Confeitaria"). Escolha da lista do Google. Categorias extras, só se forem verdade. |
| Endereço ou área | Atende no endereço: ponha o endereço. Atende em casa ou só entrega: escolha atender por região (área de atendimento) e **esconda o endereço**. Endereço de casa nunca fica público. |
| Horário | O da ficha. Feriados mudam: o dono atualiza no perfil. |
| Telefone | O número do negócio, nunca o pessoal. |
| Site | Se o negócio tem site, o site. Se não tem, deixe em branco. Instagram e Facebook vão no campo de redes sociais, se o painel mostrar esse campo. |
| Descrição | Até 750 caracteres: o que faz, para quem, onde atende, como pedir ou agendar. Sem link, sem promoção, sem "o melhor da cidade". |
| Produtos ou serviços | Os da ficha, com o preço da ficha. Sem preço inventado. |
| Fotos | Reais: fachada (se há), dentro do negócio, produto ou serviço pronto, o dono trabalhando. Logo e foto de perfil vêm de `marca/`. Rosto de cliente só com autorização (veja `conteudo`). |

## Verificação

O Google escolhe o jeito de verificar: pode ser vídeo do lugar, ligação, mensagem, e-mail ou carta. Pode levar dias. Quem faz é o dono. Se a verificação for recusada, o dono segue o que a tela pede ou a ajuda oficial; o Claude não tenta contornar.

## Avaliações

- **Pedir:** o painel do perfil tem um link (ou QR code) para pedir avaliação. O dono copia e manda a quem já comprou, uma mensagem por pessoa. Texto em `mensagens-prontas.md`.
- **Pedir a todos:** o Google proíbe pedir só a quem gostou e proíbe dar desconto, brinde ou qualquer coisa em troca. Avaliação escrita pelo dono, por parente ou por funcionário também é proibida.
- **Responder:** todas, as boas e as ruins, com calma e sem dado do cliente (nada de "a senhora pediu tal coisa no dia tal"). Avaliação ruim: agradecer, dizer o que vai mudar se for o caso, chamar para conversar no WhatsApp do negócio. O Claude escreve; o dono responde.
- Avaliação falsa ou ofensiva: o dono pode denunciar pelo próprio perfil. Não prometa que o Google vai tirar.

## Manter em dia (rotina)

- **Toda semana, uns 15 minutos:** responder as avaliações novas; subir 1 ou 2 fotos reais da semana.
- **Quando mudar algo:** horário, feriado, preço, serviço novo. Perfil desatualizado (fechado quando diz aberto) gera avaliação ruim.
- **De vez em quando:** uma atualização (post do perfil) com foto e texto curto, a partir de uma história de `organico/historias.md`. A peça vem de `conteudo`.
- **Uma vez por mês:** o dono manda print da parte de desempenho do perfil (ligações, pedidos de rota, cliques, mensagens) para o placar.

## O que não prometer

Não diga em que posição o negócio vai aparecer, nem em quanto tempo. O Google diz que a posição depende de relevância, distância e destaque, e a distância de quem procura não se controla. Diga o que está ao alcance: perfil completo, verdadeiro, com fotos e avaliações respondidas.
