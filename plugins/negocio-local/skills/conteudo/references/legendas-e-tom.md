# Legendas e tom

A legenda segue o tom da ficha (`negocio/ficha.md`) e só afirma o que a ficha sustenta. Preço, prazo, ingrediente, horário e entrega vêm de lá. O que faltar vira pergunta ao dono, nunca chute.

## Estrutura

1. **Gancho** (primeira linha): mostra o produto ou o resultado. É o que aparece antes do "ver mais".
2. **Corpo** (1 a 3 linhas curtas): o que é, de que é feito ou o que inclui, o que o cliente ganha. Só fato.
3. **Preço**, igual ao da ficha. Se o preço depende do tamanho, diga os dois.
4. **Como pedir:** o link do WhatsApp com um código por peça.
5. **Hashtags:** poucas (de 3 a 5), do negócio e da região em termos gerais. Nada de bairro ou endereço da casa.

## Como pedir, com código por peça

O link de WhatsApp (`wa.me`) aceita um texto já preenchido. Ponha um código diferente em cada peça: assim a mensagem que chega mostra de qual peça veio.

```text
https://wa.me/{telefone}?text=Oi!%20Vi%20o%20post%20{codigo}%20e%20quero%20pedir
```

- `{telefone}` é o número do negócio, só dígitos, com país e DDD, tirado da ficha. Enquanto ele não existe, a peça fica como rascunho.
- `{codigo}` é curto e único por peça (por exemplo `F01`, `R02`).
- O link wa.me não aceita UTM; o código no texto é o rastreio.
- Na legenda do Instagram o link não é clicável. Ele vale no link da bio, no anúncio e em mensagens. Em post, escreva "link na bio" e deixe o link na bio com `presenca-nas-redes`.
- Registre o mapa peça, código e link em `conteudo/<semana>/legendas.md`.

Atenção: uma mensagem pronta muito curta rastreia bem, mas pode levar o cliente a pedir só o cardápio e parar. Se isso acontecer, o atendimento precisa ter foto do cardápio ou da tabela para mandar logo em seguida (veja `atendente-ia`). No caso, 5 de 8 conversas pararam depois de um cardápio só em texto.

## O que não dizer

- Escassez falsa: "últimas unidades", "só hoje", "corra", se não for verdade comprovada.
- Desconto, brinde ou promoção que o dono não aprovou por escrito.
- Número inventado: "mais de 500 clientes", "o melhor da cidade".
- "Feito na hora", "artesanal", "sem conservantes", "natural", "sem glúten" e outras afirmações que a ficha não sustenta. Ingrediente e alergênico só do que o dono confirmou.
- Promessa de resultado ("emagreça", "cabelo novo em 1 dia").
- Nome de outro negócio, "ao lado de", "melhor que".
- Telefone pessoal, e-mail pessoal ou endereço da casa.
- No máximo 1 emoji por legenda, quando combina com o tom.

## Tom

O tratamento ("você", "tu") e o grau de formalidade vêm da ficha. Frase curta. Direto. Sempre dizer como pedir. Se a ficha diz "o que nunca dizer", essa lista vale mais que qualquer exemplo daqui.

## Exemplos inventados

**Doceria Aurora (produto)**
> Por dentro é assim. Massa de {sabor da ficha} com cobertura de {cobertura da ficha}.
> Fatia: {preço da ficha}. Bolo inteiro: {preço da ficha}.
> Pedidos pelo link na bio ou pelo WhatsApp: {link com código}

**Salão (serviço com horário)**
> Corte e escova com hora marcada. Agende pelo WhatsApp e já diga se quer só o corte ou o pacote.
> Horário de atendimento: {horário da ficha}. {link com código}

**Pet shop**
> Banho e tosa com agendamento. O tempo muda com o porte do pet. Mande uma foto e o peso aproximado e combinamos o horário. {link com código}

## Voz sintética em reel (opcional, paga)

Padrão: reel sem voz, com texto na tela. Voz só se o usuário tem chave de um serviço de voz (por exemplo, o da ElevenLabs ou o de um provedor de nuvem) e pede.

- **Custo dito antes:** quantos caracteres, em qual plano, e o limite de gasto que o usuário pôs.
- **A chave** vai no `.env` do projeto, preenchido pelo usuário. Nunca no chat, nunca impressa.
- **Voz:** use uma voz do catálogo do serviço, aprovada pelo dono. Nunca imite a voz de uma pessoa real sem autorização dela.
- **Roteiro da fala:** escreva as linhas em `conteudo/<semana>/falas.md` e o dono aprova antes de gerar.
- **Cache por linha:** guarde o áudio de cada linha com o nome igual ao resumo (hash) de "voz, modelo, texto". Linha igual não é paga duas vezes.
- **Termos em inglês** costumam sair com sotaque estranho. Escreva a pronúncia como soa em português (por exemplo "ví-di-ou" para vídeo) e ouça.
- **O revisor automático não ouve áudio.** A voz fica para o dono ouvir, inteira, antes de aprovar.
- **Rótulo:** a plataforma pode pedir o aviso de conteúdo feito com IA. Confira antes de publicar.
- Se o usuário não quer voz de IA, ele pode gravar a própria locução no celular. Vale mais.
