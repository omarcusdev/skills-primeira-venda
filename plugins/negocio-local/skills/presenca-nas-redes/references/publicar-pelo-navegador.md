# Publicar pelo navegador (conta que já posta)

A Meta restringe acesso automatizado às suas páginas. Mesmo com o usuário olhando, existe risco de a conta ser revisada ou limitada. Diga isso ao usuário antes de começar.

Só para conta que já tem posts e algumas semanas de uso. Em conta nova, as primeiras publicações são do dono, pelo app, com o kit. Ferramenta: Claude in Chrome, com o usuário logado e olhando a tela. Sem ela, vira passo a passo numerado. Se a ferramenta não responde no primeiro uso, siga pelo manual sem insistir.

**Ok por item.** Antes de cada publicação, mostre: imagem ou vídeo, legenda, conta ou Página (nome na tela) e o que vai ser publicado. Só vai o que tem "sim". Registre em `negocio/decisoes.md`. Nada de código injetado na página.

## Instagram web (feed e reel)

Fluxo que funcionou no caso:

1. Criar (menu lateral) > Publicação.
2. Enviar o arquivo. O Claude in Chrome acha o campo de arquivo da janela de criar e envia o arquivo. Esse envio aceita até 10 MB por chamada (confira o limite atual). Vídeo maior: exporte menor no celular ou, com ok, reduza com ffmpeg (instalação com ok; veja a skill `conteudo`).
3. No passo de corte, abra "Selecionar proporção" e escolha **Original**. Avançar.
4. Legenda. Compartilhar. Confirme a janela de sucesso e confira o post no perfil.

Armadilhas:

- Um fluxo alternativo, sem a opção de manter o tamanho original, cortou a imagem em quadrado e comeu o título. O corte de um post publicado não se edita. Só corrige apagando e republicando.
- Apagar é sem volta no Instagram, exceto os 30 dias em "Excluídos recentemente". **Apagar é ação para fora: peça ok antes**, diga o que será apagado e que a ordem da grade vai mudar.
- Reel pelo web não aceita música do Instagram. Sem música, o reel sai só com o áudio do vídeo. Escolha a capa a partir de um quadro. Se o reel tem voz, mantenha a versão com voz.
- A extensão ou o Chrome pode cair (por exemplo, ao reiniciar). Reconecte a extensão antes de continuar.
- Link clicável só na bio, pelo app.

## Business Suite (posts e stories)

- O botão de adicionar foto ou vídeo pode abrir o seletor de arquivos do sistema, que o Claude não enxerga. Se a ferramenta de envio de arquivo não achar o campo, o dono escolhe o arquivo na janela do sistema e o Claude continua dali. Não use código para contornar.
- No composer de story, o mesmo campo costuma ser reaproveitado a cada "Adicionar foto/vídeo".
- Story pelo Business Suite não tem link clicável nem enquete, nem figurinha interativa. Escreva o número ou o chamado na própria arte.
- Carrossel: o Claude in Chrome pode enviar as imagens numa chamada só, respeitando os 10 MB.
- Story e post podem ir só ao Instagram ou também ao Facebook; confira o seletor de destino na tela antes do ok.

## Programar

O Business Suite tem "Programar" para data e hora futuras. **O caso não fez isso.** Tudo que saiu foi publicado na hora, depois do ok. Se o dono quiser programar:

1. Cada item agendado tem ok próprio, com data e hora dito no resumo.
2. Confira na tela o fuso e a data antes de confirmar.
3. Peça ao dono para conferir a lista de agendados depois.
4. Lembretes e `/loop` do Claude Code **não** são agendamento de post: somem se o terminal fecha ou a máquina reinicia.

## Ordem da grade

O último post fica em cima. Para a linha do perfil sair, por exemplo, bolo, brownie, brigadeiro, poste na ordem inversa. Stories vão na ordem em que o cliente deve ver.

## Escala: API oficial (avançado, não testado)

Para publicar de forma automática toda semana, o caminho técnico é a API oficial de publicação da Meta: criar um app de desenvolvedor, autorizar a permissão de publicação e hospedar a imagem numa URL pública. No caso, foi avaliada e não adotada; para poucos posts, o navegador bastou. Marque como avançado e não prometa que funciona sem testar.

## Antes de cada "sim"

- Preço e texto iguais aos da ficha.
- Sem número antigo, sem endereço, sem rosto de cliente sem autorização (veja `conteudo`).
- Conta e Página certas na tela.
- Imagem com a proporção certa e legível no celular.
