# NexEmpreende — Site Institucional

Site estático moderno da startup **NexEmpreende**, pronto para hospedagem no **GitHub Pages**.
Construído apenas com **HTML, CSS e JavaScript puro** — sem frameworks ou build step.

---

## 📁 Estrutura do projeto

```
nexempreende/
├── index.html              ← Home / Landing page
├── sobre.html              ← Página institucional
├── artigos.html            ← Lista de artigos
├── contato.html            ← Página de contato
├── ultimo-artigo.html      ← Aponta para o último artigo (usado pelo app mobile)
├── css/
│   └── style.css           ← Design system + estilos
├── js/
│   └── main.js             ← Navbar, menu mobile, animações
├── images/                 ← Imagens e favicon
└── articles/
    ├── _template.html      ← TEMPLATE reutilizável para novos artigos
    ├── financas-em-5-passos.html
    ├── marketing-digital.html
    ├── produtividade.html
    └── plano-de-crescimento.html
```

---

## 🚀 Como publicar no GitHub Pages

1. Crie um repositório no GitHub (ex: `nexempreende-site`).
2. Faça upload de **todos os arquivos desta pasta** para a raiz do repositório.
3. Vá em **Settings → Pages**.
4. Em **Source**, selecione a branch `main` e a pasta `/ (root)`.
5. Salve. Em alguns minutos seu site estará disponível em
   `https://seu-usuario.github.io/nexempreende-site/`.

---

## ✍️ Como publicar um novo artigo

1. Copie o arquivo `articles/_template.html` e renomeie
   (ex: `articles/meu-novo-artigo.html`).
2. Edite os campos marcados como `[EDITAR]`: título, descrição, imagem, conteúdo.
3. Abra `artigos.html` e adicione um novo card no grid apontando para o novo arquivo:
   ```html
   <article class="article-card">
     <div class="article-card-img"><img src="images/sua-imagem.jpg" alt="..." /></div>
     <div class="article-card-body">
       <span class="tag">Categoria</span>
       <h3>Título do novo artigo</h3>
       <p>Descrição curta.</p>
       <a href="articles/meu-novo-artigo.html" class="read-more">Ler artigo →</a>
     </div>
   </article>
   ```
4. **Importante** — se este for o artigo mais recente, atualize também o
   `ultimo-artigo.html` para o app mobile saber qual é o novo destaque:
   - `<meta name="latest-*">` (title, description, image, url, date)
   - O JSON `#latest-article-data`
   - O `<meta http-equiv="refresh">` e o `<a id="latest-link">`

---

## 📱 Integração com o aplicativo mobile

A página `ultimo-artigo.html` foi pensada para ser lida pelo app NexEmpreende.
O app pode obter os dados do último artigo de **três formas**, escolha a mais
conveniente:

### Opção 1 — Ler tags `<meta>` (mais simples)

```
<meta name="latest-title"       content="..." />
<meta name="latest-description" content="..." />
<meta name="latest-image"       content="..." />
<meta name="latest-url"         content="..." />
<meta name="latest-date"        content="YYYY-MM-DD" />
```

### Opção 2 — Ler o JSON embarcado

```html
<script type="application/json" id="latest-article-data">
{ "title": "...", "description": "...", "image": "...", "url": "..." }
</script>
```

### Opção 3 — Seguir o redirect

A página faz `meta refresh` automático para o artigo mais recente.

---

## 🎨 Design system

- **Cor principal:** azul (#2563eb / #3b82f6)
- **Neutros:** branco, cinzas frios (#0f172a → #f8fafc)
- **Tipografia:** Inter (Google Fonts)
- **Estilo:** minimalista, moderno, inspirado em SaaS e fintechs

Todos os tokens visuais estão definidos em `css/style.css`, no bloco `:root`.

---

## ✅ Recursos incluídos

- Layout 100% responsivo (mobile-first)
- Navbar fixa com efeito ao rolar
- Menu mobile funcional
- Animações de scroll (reveal)
- Scroll suave
- Hover effects modernos
- SEO básico + Open Graph em todas as páginas
- Favicon
- Footer profissional
- Template reutilizável de artigo
- Estrutura preparada para manutenção via GitHub

Feito com 💙 para microempreendedores.
