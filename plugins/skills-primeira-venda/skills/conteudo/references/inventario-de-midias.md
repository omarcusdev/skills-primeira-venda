# Inventário de mídias

Faça antes de criar qualquer peça. Sem a lista, é comum o material bom ficar parado e as peças saírem com o que estava à mão.

## Como fazer

1. Liste a pasta com as fotos e vídeos do dono. Copie tudo para `midia/originais/`. Nunca mexa nessa pasta depois.
2. Abra cada foto (o Claude lê imagens). Para vídeo, extraia 1 quadro por segundo e olhe (comando em `video-do-celular.md`). Sem ffmpeg, marque o vídeo como "não visto: descrito pelo dono" e peça uma frase sobre o que ele mostra.
3. Preencha uma linha por arquivo. Seja honesto na qualidade: a decisão de uso depende dela.
4. Feche com as três listas abaixo da tabela.
5. Mostre ao dono. Ele corrige o que você não tinha como saber (qual é qual produto, o que é de quem).

## Modelo de `midia/inventario.md`

```markdown
# Inventário de mídias

Atualizado em AAAA-MM-DD. Total: N arquivos (F fotos, V vídeos).

| Arquivo | Tipo | O que mostra | Qualidade | Uso possível | Dado pessoal visível | Autorização de imagem | Decisão |
|---|---|---|---|---|---|---|---|
| IMG_0412.jpg | foto | bolo de cenoura cortado, luz de janela | boa (4000x3000, nítida) | feed, catálogo, anúncio | nenhum | não se aplica | usar |
| IMG_0413.jpg | foto | mesma cena, de longe | ok (desfocada na borda) | story | nenhum | não se aplica | usar como apoio |
| VID_0021.mov | vídeo | calda caindo no bolo, 8 s | boa (1080p, HDR) | reel, anúncio | nenhum | não se aplica | usar (converter HDR) |
| IMG_0430.jpg | foto | cliente com o produto | boa | feed | rosto de cliente | NÃO registrada | não usar até autorizar |
| IMG_0431.jpg | foto | caixa de entrega na bancada | ok | story | telefone pessoal no adesivo | não se aplica | não usar |
| IMG_0440.jpg | foto | recebida por WhatsApp, 540 px | baixa (comprimida) | nenhum em tela cheia | nenhum | não se aplica | pedir foto nova |

## Melhores tomadas
(as que seguram anúncio e feed: nítidas, produto inteiro, luz boa)

## Não usar
(com o motivo: dado pessoal, logo ou marca de terceiro, qualidade baixa, produto que não bate com a ficha)

## Pedir ao dono para gravar
(o que falta: o corte do produto, o antes e depois, o momento do pedido saindo. Use `lista-de-tomadas.md`.)
```

## Colunas, uma a uma

- **Qualidade:** boa, ok ou baixa, sempre com o porquê (resolução, desfoque, compressão, luz). Foto recebida pelo WhatsApp costuma vir comprimida. Print de tela ampliado fica borrado em tela cheia e nunca é a imagem principal de um anúncio.
- **Uso possível:** feed, story, reel, anúncio, catálogo, só apoio, nenhum.
- **Dado pessoal visível:** nome, telefone, endereço, placa de carro, rosto, tela de celular, logo ou embalagem de outro negócio, adesivo com número antigo ou pessoal.
- **Autorização de imagem:** só para foto ou vídeo com rosto ou pet de cliente. "Registrada" quer dizer que existe aceite por escrito guardado (veja `autorizacao-de-imagem.md`). Sem isso: recortar, desfocar ou não usar.
- **Decisão:** usar, usar como apoio, recortar, converter, não usar ou pedir nova.

## O que cai direto em "não usar"

- Print de status, foto ou vídeo de outra pessoa ou de outro negócio. Só material próprio entra.
- Qualquer coisa com marca, logo ou fundo de um vizinho ou concorrente.
- Telefone, endereço da casa ou e-mail pessoal visíveis, mesmo pequenos.
- Foto de bastidor com lixeira, fio, chão sujo ou objeto que não é do produto.
- Produto que não é o que se entrega hoje (embalagem antiga, sabor que saiu do cardápio).

## Perguntas ao dono que o inventário costuma abrir

Faça uma por vez, só as que mudam a decisão:

- Qual dessas fotos é de qual produto? Este tamanho médio e este grande são mesmo diferentes?
- Esta embalagem ainda é a que vai para o cliente?
- Quem é esta pessoa? Ela sabe que a foto pode ser publicada?
