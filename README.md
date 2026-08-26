# Portfólio — Vue 3 + Tailwind CSS

## Como rodar

```bash
npm install
npm run dev
```

Abre em `http://localhost:5173`.

## Como editar

- **Projetos** → `src/data/projects.js` (nome, descrição, tags, link de cada card)
- **Textos do "Sobre"** → `src/components/About.vue`
- **Stack técnica** → array `skills` dentro de `src/components/About.vue`
- **Nome, headline e links de contato** → `src/components/Hero.vue`, `src/components/Contact.vue`, `src/components/NavBar.vue`
- **Cores e fontes** → `tailwind.config.js` (chave `theme.extend`)

## Build para produção

```bash
npm run build
```

Gera os arquivos estáticos finais em `dist/`, prontos para hospedar em Netlify, Vercel, GitHub Pages, etc.
