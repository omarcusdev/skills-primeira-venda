# Kit `publicar/`

A estratégia que funcionou: preparar tudo em arquivos antes de abrir qualquer conta. Assim, o trabalho do dono é passar para o celular e colar. O kit tira dele a parte de escrever. Ele ainda cria as contas, digita os códigos e configura no app o que só existe lá.

## Estrutura

```
publicar/
├── LEIA-PRIMEIRO.md
├── 1-whatsapp-business/
│   ├── textos.md            descrição, saudação, ausência, respostas rápidas, itens de catálogo
│   └── catalogo-1.png ...   uma imagem por item
├── 2-pagina-facebook/
│   ├── textos.md            nome, categoria, descrição
│   └── foto-de-perfil.png, capa.png
├── 3-instagram/
│   ├── bio.md               nome, @, bio de 3 linhas, link wa.me com texto pré-preenchido (com {telefone} até o número existir; colar só quando ele chegar)
│   ├── foto-de-perfil.png
│   ├── post-1/ (imagens + legenda.md), post-2/, post-3/
│   └── destaques/ (capas + manifesto.md)
├── 4-status-do-dia/         imagens para o status do WhatsApp (o dono posta)
└── 5-para-imprimir/         adesivo e etiquetas, só depois de o número existir
```

Adapte as pastas ao negócio. Um salão não tem etiqueta para imprimir; tem tabela de serviços para o catálogo.

## `LEIA-PRIMEIRO.md` (modelo)

```
# Como usar este kit

Ordem:
1. [ ] Número do negócio ativo e WhatsApp Business registrado.
2. [ ] Pasta 1: cole os textos no WhatsApp Business (descrição, ausência, respostas rápidas).
3. [ ] Pasta 2: crie a Página e cole os textos.
4. [ ] Ligue o WhatsApp à Página.
5. [ ] Pasta 3: crie o Instagram e use a bio e a foto.
6. [ ] Ligue o Instagram à Página.
7. [ ] Link na bio (só pelo app).
8. [ ] 3 primeiros posts, de trás para frente (o último postado fica em cima).

Campos para você preencher (o Claude não inventa):
- chave Pix: ______
- nome do titular: ______
- ponto de referência da retirada: ______
- horário de atendimento: ______

Nunca ponha na bio ou nas fotos: telefone ou e-mail pessoal, endereço da casa, número antigo.
```

## Manifesto com pendências por peça

Cada peça que depende de algo ainda não decidido ganha uma linha de pendência. Exemplo:

```
| Peça | Uso | Pendência |
|---|---|---|
| destaque-entrega | destaque do Instagram | só publicar quando a regra de entrega estiver definida |
| destaque-clientes | destaque do Instagram | só com autorização de imagem dos clientes |
| catalogo-5 | WhatsApp Business | só depois de o dono confirmar os ingredientes |
```

O Claude relê o manifesto antes de cada publicação.

## Como levar o kit ao celular

| Caminho | Quando |
|---|---|
| Google Drive | funciona em qualquer sistema; sobe a pasta e abre no celular |
| E-mail | arquivos pequenos; o dono manda para si mesmo |
| WhatsApp, só "como documento" | foto e vídeo mandados como foto saem comprimidos e borrados; como documento saem inteiros |
| AirDrop | só entre Mac e iPhone |

Antes de levar, confira que nenhum arquivo do kit mostra número antigo, endereço ou rosto de cliente sem autorização.

## Atualizar o kit

Quando o nome, o número ou um preço mudam, mude na ficha e na fonte (`marca/marca.json`) e regenere ou refaça as peças. Depois de trocar um nome, olhe cada peça de novo: um nome mais largo pode quebrar o layout.
