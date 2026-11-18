# Vídeo do celular

O caminho padrão não instala nada: o dono edita no editor do próprio celular. O ffmpeg é opcional, para quem prefere o computador ou precisa de uma conversão que o celular não faz.

## Caminho padrão: editor do celular

Entregue ao dono, em `conteudo/<semana>/`, um roteiro por peça: tomada, duração, texto na tela, legenda. Ele faz:

1. **Corta** cada tomada para o trecho bom, com meio segundo de folga no início e no fim.
2. **Formato vertical 9:16.** Se gravou na horizontal, ajusta o enquadramento para o assunto ficar no centro.
3. **Texto na tela legível sem som:** preço e como pedir. Letra grande (corpo de uns 44 px num quadro de 1080 de largura), contraste forte, dentro da área segura (`formatos-e-area-segura.md`).
4. **Sem música de fora.** Música só a da biblioteca do próprio aplicativo na hora de publicar. A licença de uso comercial de uma música pode ser diferente em conta de negócio; confira no aplicativo.
5. **Exporta em qualidade alta**, e confere o tamanho: para o envio pelo navegador, deixe cada arquivo abaixo de 10 MB.
6. **Envia ao computador como documento** (veja `lista-de-tomadas.md`).

Peça ao dono para assistir o resultado no celular, sem pular, antes de aprovar.

### Juntar os trechos no celular

- Pergunte uma vez se o celular é iPhone ou Android e responda no mesmo turno, com o caminho daquele celular.
- iPhone: o app Fotos corta cada trecho; para juntar, o iMovie (gratuito, da Apple) ou o editor de Reels do Instagram. Android: o editor da Galeria ou do Google Fotos corta e, em muitos aparelhos, junta; se não juntar, o editor de Reels do Instagram. Os nomes mudam; confira na tela.
- Sem Instagram, monte e salve no próprio celular, e só depois suba, quando o perfil existir.
- O ffmpeg (abaixo) é opcional e fica para quem prefere o computador.

## Opcional: ffmpeg no computador

Instalar (mostre o comando e peça o ok antes):

- Windows: `winget install Gyan.FFmpeg`
- macOS: `brew install ffmpeg`
- Linux (Debian e Ubuntu): `sudo apt install ffmpeg`

Confira com `ffmpeg -version`. Se o instalador mudou, use a página oficial do ffmpeg.

Trabalhe sempre em cópia: a entrada vem de `midia/originais/`, a saída vai para `midia/tratadas/`.

### Ver o vídeo (para o inventário e a revisão)

```bash
mkdir -p midia/quadros/VID_0021
ffmpeg -i midia/originais/VID_0021.mov -vf fps=1,scale=360:-1 midia/quadros/VID_0021/q_%03d.png
```

Um quadro por segundo. O Claude abre as imagens e descreve o vídeo.

### HDR do iPhone para SDR

Vídeo de iPhone costuma ser HDR (HLG). Sem conversão ele aparece lavado em muitos aparelhos e em anúncio. Receita padrão (precisa do filtro `zscale`):

```bash
ffmpeg -i midia/originais/VID_0021.mov \
  -vf "zscale=t=linear:npl=100,format=gbrpf32le,zscale=p=bt709,tonemap=tonemap=hable:desat=0,zscale=t=bt709:m=bt709:r=tv,format=yuv420p" \
  -c:v libx264 -preset slow -crf 18 -r 30 -an midia/tratadas/VID_0021-sdr.mp4
```

Ela funciona quando o arquivo vem marcado como HDR, como os do iPhone. Se o ffmpeg reclamar de `zscale` ou der "no path between colorspaces", o arquivo não está marcado ou o ffmpeg não tem o filtro: use a versão mais simples. Ela é menos fiel, então confira um quadro:

```bash
ffmpeg -i midia/originais/VID_0021.mov \
  -vf "scale=in_color_matrix=bt2020:out_color_matrix=bt709,format=yuv420p" \
  -c:v libx264 -preset slow -crf 18 -r 30 -an midia/tratadas/VID_0021-sdr.mp4
```

Confira se o branco continua branco (chocolate branco, jaleco, parede) e se o vermelho está vivo, não laranja. Se a cor mudou, não use.

### Horizontal para 9:16

Corta o centro e amplia para 1080x1920. Ampliar piora a nitidez: use só quando o assunto cabe no recorte e o original é 1080p ou mais.

```bash
ffmpeg -i entrada.mp4 -vf "crop=trunc(ih*9/32)*2:ih,scale=1080:1920:flags=lanczos" \
  -c:v libx264 -preset slow -crf 18 -r 30 -an saida-9x16.mp4
```

### Cortar um trecho

```bash
ffmpeg -ss 00:00:01.5 -to 00:00:09 -i entrada.mp4 -c:v libx264 -crf 18 -an saida-corte.mp4
```

Os comandos desta página usam `-an`, que tira o áudio. Se o som do próprio vídeo deve ficar, troque `-an` por `-c:a aac -b:a 128k`.

### Peso abaixo de 10 MB

Suba o CRF até caber. Confira o tamanho depois de cada tentativa:

```bash
ffmpeg -i entrada.mp4 -c:v libx264 -preset slow -crf 23 -maxrate 6M -bufsize 12M \
  -pix_fmt yuv420p -movflags +faststart -an saida-leve.mp4
ls -l saida-leve.mp4
```

Tentativas em ordem: CRF 21, 23, 26, 28. Se ainda passar de 10 MB, encurte o vídeo antes de piorar a imagem.

No Windows, `ls -l` vira `dir saida-leve.mp4`. Se o usuário usa o prompt do Windows, troque a barra invertida de continuação de linha por `^` ou ponha o comando numa linha só.

### Câmera lenta

Câmera lenta abaixo de 0,7x pede o vídeo original gravado a 60 quadros por segundo. Se o original é de 30, o movimento fica picotado: deixe em velocidade normal.

## O que conferir no resultado

- A cor do produto está igual à do original e à do que se entrega.
- O primeiro segundo já mostra o assunto.
- Nada pessoal ou de terceiros no quadro (olhe os quadros extraídos).
- O texto na tela cabe na área segura e dá para ler sem som.
- O arquivo abre e o tamanho está abaixo de 10 MB.
