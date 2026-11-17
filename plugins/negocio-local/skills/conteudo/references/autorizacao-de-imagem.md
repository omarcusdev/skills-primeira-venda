# Autorização de imagem

Rosto de cliente e pet de cliente em foto ou vídeo do negócio precisam de autorização de uso de imagem, registrada. Imagem de uma pessoa é dado pessoal. Sem autorização, a imagem é recortada, o rosto é desfocado ou a peça não usa aquela tomada.

Este é um **modelo simples, não é parecer jurídico**. Para um caso diferente do comum (criança, uso em anúncio pago por muito tempo, pessoa famosa, dúvida sobre direitos), o usuário deve falar com um profissional.

## Quando precisa

- Cliente reconhecível por rosto, tatuagem marcante ou voz.
- Pet de cliente, com o dono do pet identificado.
- Funcionário ou prestador que aparece. A autorização dele também vale ser registrada.
- Criança: só com autorização do responsável, e, na dúvida, não use.

Não precisa de autorização: mão sem identificação, produto sozinho, o espaço sem pessoas, uma pessoa de costas sem nada que a identifique. Mesmo assim, se a pessoa pediu para não aparecer, respeite.

## Modelo de texto

Entregue ao dono em `conteudo/autorizacao-de-imagem.md`, para ele copiar e mandar ao cliente (o dono envia, não o Claude), ou para a pessoa assinar no balcão.

```text
Autorização de uso de imagem

Eu, [nome completo], autorizo [nome do negócio] a usar fotos e vídeos em que eu
[ou meu pet, [nome do pet]] apareço, nas redes sociais e nos anúncios do negócio,
por [prazo: por exemplo 12 meses], sem pagamento.

Posso retirar esta autorização quando quiser, escrevendo para [contato do negócio].
O negócio então retira a imagem dos próprios perfis e deixa de usá-la em novos
anúncios. Já entendi que o que outras pessoas já compartilharam não pode ser recolhido.

Cidade e data: [ ]
Assinatura ou resposta "autorizo": [ ]
```

Se a pessoa for menor de idade, o responsável preenche o nome dele e o do menor.

## Como registrar

1. O aceite pode ser uma assinatura em papel (foto do papel) ou a resposta escrita "autorizo" a essa mensagem, com data. Guarde o que mostra o texto, a data e quem autorizou.
2. Guarde em `midia/autorizacoes/`. Essa pasta não vai para e-mail, nuvem compartilhada nem peça pública. Só se a pasta do projeto já for um repositório git (conferido), sugira pôr `midia/autorizacoes/` e `midia/originais/` no `.gitignore`. Não guarde CPF, RG nem telefone completo: só o que prova o aceite. Se aparecerem no papel, cubra antes de guardar a foto.
3. Marque na coluna "autorização de imagem" de `midia/inventario.md`: "registrada em AAAA-MM-DD, vale até AAAA-MM-DD, por <primeiro nome ou id>".
4. Ponha uma lembrança no inventário para o fim do prazo. Passou o prazo: tire a peça do ar ou peça uma nova.

Para quem trabalha para um cliente (agência, freelancer): essa autorização é do cliente do negócio, não da agência. Guarde também, em `negocio/decisoes.md`, a autorização por escrito do dono do negócio para tratar os dados dos clientes dele.

## Sem autorização

- **Recorte** o produto e deixe a pessoa de fora, se a imagem ainda serve.
- **Desfoque** o rosto, só se continuar claro que a imagem é de verdade (não finja que é outra pessoa).
- **Escolha outra tomada** da mesma sessão.
- **Peça a autorização** (o dono pede, não o Claude) e espere.
- Não use IA de imagem para "criar" uma pessoa no lugar. Pessoa gerada por IA não entra nas peças.

Quando um cliente pede para retirar a imagem, o dono tira a peça dos perfis. O Claude lista onde ela foi usada, a partir de `conteudo/` e `negocio/decisoes.md`.
