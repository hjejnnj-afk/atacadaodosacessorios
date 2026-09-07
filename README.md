# Atacadão dos Acessórios — Landing Page

Landing page institucional premium para a **Atacadão dos Acessórios**.  
HTML + CSS inline + JS inline — arquivo único, sem build step.

---

## Estrutura do projeto

```
atacadao/
│
├── index.html                  ← página principal (todo CSS e JS embutidos)
│
├── logo.png                    ← logo em fundo transparente/claro (usada na hero flutuante)
├── logo-final.png              ← logo versão fundo preto (usada no fechamento do vídeo)
├── mascot.png                  ← mascote (balão "Clique aqui pra que eu possa te ajudar!")
├── favicon.png                 ← ícone da aba do browser
├── apple-touch-icon.png        ← ícone para iOS (salvar na tela inicial)
│
├── phones/
│   └── cutout/
│       ├── hero-iphone.png     ← iPhone hero (cutout sem fundo)
│       ├── 1.png               ← Apple iPhone (card de marca)
│       ├── 2.png               ← Samsung Galaxy (card de marca)
│       ├── 3.png               ← Xiaomi (card de marca)
│       └── 4.png               ← Motorola (card de marca)
│
├── loja/
│   ├── 1.jpg                   ← foto da loja (galeria)
│   ├── 2.jpg                   ← foto da loja (galeria)
│   ├── 3.jpg                   ← foto da loja (galeria)
│   └── 4.jpg                   ← foto da loja (galeria)
│
├── depoimentos/
│   ├── diene-sirqueira.png     ← print do depoimento (WhatsApp ou Google)
│   ├── francisco-frazao.png    ← print do depoimento
│   ├── magno-santos.png        ← print do depoimento
│   └── tiana-moura.png         ← print do depoimento
│
└── videos/
    └── kling-2.5_Create_an_8-second_premium_exploded-view_repair_animation_of_a_modern_gold_bronz-0.mp4
                                ← vídeo scroll-scrubbed da seção de reparo
```

---

## Como rodar localmente

1. Abra a pasta `atacadao/` no **VS Code**
2. Instale a extensão **Live Server** (se não tiver)
3. Clique direito em `index.html` → **Open with Live Server**
4. Acesse `http://127.0.0.1:5500`

> ⚠️ O vídeo (`videos/*.mp4`) só carrega via servidor HTTP — não funciona
> abrindo o HTML diretamente pelo explorador de arquivos (protocolo `file://`).
> O Live Server resolve isso automaticamente.

---

## Personalização

### 1. Número de WhatsApp
Busque no `index.html` por:
```
WHATSAPP_NUMBER = "
```
Substitua pelo número real com DDI:
```js
const WHATSAPP_NUMBER = "5598999999999"; // DDI 55 + DDD + número
```

### 2. Imagens a adicionar

| Pasta             | Arquivo               | Descrição                        |
|-------------------|-----------------------|----------------------------------|
| `phones/cutout/`  | `hero-iphone.png`     | iPhone recortado, sem fundo      |
| `phones/cutout/`  | `1.png` – `4.png`    | Fotos dos 4 aparelhos (brands)   |
| `loja/`           | `1.jpg` – `4.jpg`    | Fotos reais da loja              |
| `depoimentos/`    | `*.png`              | Prints de depoimentos reais      |
| `videos/`         | `*.mp4`              | Vídeo scroll-scrubbed            |

### 3. Texto de conteúdo
Edite diretamente no `index.html`:
- Hero: `<h1>Quebrou? A gente resolve na hora.</h1>`
- Serviços: seção `#servicos`
- Localização: seção `#localizacao`
- Dados da loja: endereço, horários, mapa (iframe do Google Maps)

### 4. Mapa do Google
Na seção `#localizacao`, substitua o `src` do `<iframe>`:
```html
<iframe src="https://www.google.com/maps/embed?pb=SEU_EMBED_AQUI" ...></iframe>
```

---

## Deploy

### GitHub Pages (gratuito)
1. Crie o repositório no GitHub (pode ser público ou privado)
2. Faça upload de toda a pasta
3. Settings → Pages → Branch: `main` / root → Save
4. Acesse `https://seuusuario.github.io/atacadao/`

> **Atenção:** GitHub Pages serve arquivos estáticos com HTTPS, então o vídeo
> carregará corretamente desde que o arquivo `.mp4` esteja na pasta `videos/`.

### Hostinger / cPanel
1. File Manager → `public_html`
2. Upload de todos os arquivos
3. Pronto — o domínio já aponta para o `index.html`

### Vercel (recomendado para domínio customizado)
```bash
npm i -g vercel
cd atacadao
vercel
```

---

## Dependências externas (CDN — sem instalação)

| Biblioteca              | Versão   | Uso                                    |
|-------------------------|----------|----------------------------------------|
| Locomotive Scroll       | 4.1.4    | Scroll suave + seções com fundo        |
| GSAP                    | 3.12.5   | Animações (ScrollTrigger)              |
| Google Fonts / DM Sans  | —        | Tipografia principal                   |

Todas carregadas via CDN — sem `npm install` necessário.

---

## Arquivos a criar/adicionar ainda

- [ ] `phones/cutout/hero-iphone.png`
- [ ] `phones/cutout/1.png` (Apple)
- [ ] `phones/cutout/2.png` (Samsung)
- [ ] `phones/cutout/3.png` (Xiaomi)
- [ ] `phones/cutout/4.png` (Motorola)
- [ ] `loja/1.jpg` – `loja/4.jpg`
- [ ] `depoimentos/diene-sirqueira.png`
- [ ] `depoimentos/francisco-frazao.png`
- [ ] `depoimentos/magno-santos.png`
- [ ] `depoimentos/tiana-moura.png`
- [ ] `videos/kling-2.5_[...].mp4`

---

Desenvolvido por **AWC Digital Solutions** — @washingtoncarvalho
