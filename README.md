# Cabeça no Bailarico

Uma página só, sem servidor e sem instalações: escolhes a formação — **solo**, **trio**
ou **grupo de quatro** —, cada cara vai parar a um corpo de dançarino e o microfone do
telemóvel trata do resto: apanha o compasso da música que estiver a tocar à volta e eles
dançam ao ritmo. No fim, o botão de fotografia compõe uma imagem quadrada do palco para
mandares no WhatsApp.

As fotos e o som nunca saem do aparelho. Não há back-end nenhum: é tudo HTML, CSS e
JavaScript dentro do `index.html`.

## Ficheiros

| Ficheiro                 | O que é                                                   |
| ------------------------ | --------------------------------------------------------- |
| `index.html`             | A aplicação inteira. É o único ficheiro obrigatório.       |
| `natal.html`             | A versão de Natal, com neve, prendas e tema próprio.       |
| `preview.jpg`            | A imagem do link partilhado no WhatsApp.                   |
| `preview-natal.jpg`      | O mesmo, para a versão de Natal.                           |
| `bailarico-de-natal.mid` | O tema de Natal em MIDI, para abrires noutro programa.     |
| `README.md`              | Isto.                                                       |

Depois de publicares, a versão normal fica em `.../` e a de Natal em `.../natal.html`.

## O tema de Natal

É um original — nada de músicas de outras pessoas. Ré maior, 126 bpm, 16 compassos
em ciclo: caixa de música na melodia, contrabaixo, harpa nos acordes e guizos de trenó
em cada colcheia. Dentro da página é tocado por um sintetizador feito à mão com a Web
Audio API, e a dança anda agarrada ao mesmo relógio — por isso o compasso nunca foge.
O `.mid` tem exactamente as mesmas notas, para abrires num teclado ou numa DAW.

## Pôr online no GitHub Pages

Precisas de uma conta em [github.com](https://github.com) — é grátis.

1. **Cria o repositório.** No canto superior direito, `+` → **New repository**.
   Dá-lhe o nome `bailarico`, deixa em **Public** e carrega em **Create repository**.
2. **Carrega os ficheiros.** Na página que aparece a seguir, clica em
   *uploading an existing file*. Arrasta para lá o `index.html` e o `preview.jpg`
   (e este `README.md`, se quiseres) e carrega em **Commit changes**.
3. **Liga o Pages.** No repositório: **Settings** → **Pages** (menu da esquerda).
   Em *Source* escolhe **Deploy from a branch**, em *Branch* escolhe **main** e a
   pasta **/ (root)**. **Save**.
4. **Espera um minuto** e recarrega essa página do Pages: aparece lá o endereço,
   qualquer coisa como `https://o-teu-nome.github.io/bailarico/`.
5. É esse o link para mandares no WhatsApp.

### Se preferires a linha de comandos

```bash
git init
git add index.html preview.jpg README.md
git commit -m "Cabeça no Bailarico"
git branch -M main
git remote add origin https://github.com/O-TEU-NOME/bailarico.git
git push -u origin main
```

Depois faz na mesma o passo 3 (Settings → Pages).

### Para mudar alguma coisa mais tarde

No GitHub, abre o `index.html`, carrega no lápis, edita e faz **Commit changes**.
O site atualiza-se sozinho um minuto depois. Se não vires a alteração, é a cache do
browser: abre numa janela anónima ou acrescenta `?v=2` ao fim do endereço.

## Porquê pôr online

Além de teres um link para dar a quem quiseres, no GitHub Pages a página corre em
HTTPS e como página principal (não dentro de outra) — e é isso que faz o **microfone**
e o **botão de partilha do telemóvel** funcionarem sem obstáculos. No iPhone, o Safari
pede autorização do microfone na primeira vez e guarda a resposta para esse endereço.

Dá também para **adicionar ao ecrã principal** (Partilhar → Adicionar ao ecrã principal),
e a partir daí abre em ecrã inteiro, como se fosse uma app instalada.

## Se o microfone não pegar

A página tem duas alternativas, ambas no cartão *De onde vem a música*:

- **Ficheiro** — escolhes um mp3 do telemóvel e a análise é feita a esse som.
- **Ritmo manual** — marcas o compasso com o dedo ou arrastas o BPM.

## Créditos

Feito com o Claude. Os bonecos são SVG desenhado à mão; a deteção de batida usa a
Web Audio API (energia dos graves com limiar adaptativo) e o enquadramento automático
da cara usa a `FaceDetector` quando o browser a tem.
