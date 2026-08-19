# Alfat Alfaiataria — Site institucional

Site estático de uma página (`index.html`), 100% responsivo (mobile, tablet e desktop), pronto para deploy no GitHub + Vercel.

## Estrutura

```
alfat-alfaiataria/
├── index.html      # site completo (HTML + CSS + JS inline)
├── vercel.json      # config de deploy (headers, clean URLs)
├── package.json      # metadados do projeto (não há build step)
└── .gitignore
```

Não há processo de build: é um único `index.html` autossuficiente.

## 1. Subir para o GitHub

```bash
cd alfat-alfaiataria
git init
git add .
git commit -m "Site Alfat Alfaiataria"
git branch -M main
git remote add origin https://github.com/SEU_USUARIO/alfat-alfaiataria.git
git push -u origin main
```

## 2. Deploy na Vercel

**Opção A — pelo painel (mais simples):**
1. Acesse https://vercel.com/new
2. Importe o repositório `alfat-alfaiataria` do GitHub
3. Em "Framework Preset" selecione **Other** (site estático)
4. Build Command: deixe em branco
5. Output Directory: `.` (raiz)
6. Clique em **Deploy**

**Opção B — pela CLI:**
```bash
npm i -g vercel
cd alfat-alfaiataria
vercel        # ambiente de preview
vercel --prod # produção
```

## 3. Antes de publicar, atualize

- Todos os links `https://wa.me/55XXXXXXXXXXX` pelo número real do WhatsApp (com DDI+DDD, só números).
- Links de "Nossas Lojas" (Mercado Livre, Shopee, TikTok Shop) que ainda estejam com `#` ou placeholder.
- Domínio próprio: em **Vercel → Project → Settings → Domains**, adicione seu domínio e siga as instruções de DNS.

## Responsividade

O layout usa CSS Grid fluido e breakpoints em `1200px`, `960px`, `768px`, `560px` e `380px`, cobrindo desde celulares pequenos até desktops grandes. Também foram adicionados:
- `viewport` meta tag e `overflow-x:hidden` para evitar rolagem horizontal;
- alvos de toque maiores no menu hambúrguer e no botão flutuante do WhatsApp;
- tipografia fluida (`clamp()`) nos títulos.

Teste local antes do deploy:
```bash
npx serve .
```
