# ARCHITECTURE.md - Tecnologia & Escalabilidade

## Stack Tecnológica Atual

### Visão Geral

| Camada | Tecnologia |
|--------|-------------|
| **Markup** | HTML5 Semântico |
| **Estilização** | Tailwind CSS (via CDN) |
| **Interatividade** | Vanilla JavaScript (ES6+) |
| **Fontes** | Google Fonts (Inter, Space Grotesk) |
| **Ícones** | Material Symbols Outlined |

---

## Justificativa Técnica

### Por que HTML + Tailwind CDN?

| Critério | Decisão | Justificativa |
|----------|---------|----------------|
| **Velocidade de Setup** | ✅ CDN | Zero build step; deploy em segundos |
| **Curva de Aprendizado** | ✅ Baixa | Equipe pequena; foco em produto |
| **Custo de Hospedagem** | ✅ Zero | GitHub Pages + CDN = free forever |
| **Manutenibilidade** | ⚠️ Média | Sem componentização, mas simples de editar |
| **Escalabilidade** | ❌ Limitada | Não serve >1000 páginas |

### Por que não React/Next.js agora?

1. **Prematuridade**: O site atual é 1 página única (Landing Page)
2. **Sem dados dinâmicos**: Conteúdo é estático; não precisa de CMS
3. **Time small**: 1-2 pessoas; manutenção de bundle JS seria overhead
4. **Time-to-market**: Entregar agora é mais valioso que escalar depois

---

## Estrutura de Pastas

```
Site-NERDS/
├── .git/                      # Git repository (version control)
├── .gitignore
├── docs/                      # Documentação do projeto
│   ├── PRODUCT.md
│   ├── ARCHITECTURE.md
│   ├── DESIGN_SYSTEM.md
│   ├── UX.md
│   ├── CHANGELOG.md
│   └── ...
├── code.html                  # Arquivo principal (single page app)
├── screen.png                # Screenshot do design final
├── DESIGN.md                # Design tokens (fonte)
└── README.md                # Quick start
```

### Legenda

- `code.html` = Arquivo único contendo todo o HTML, CSS (via Tailwind config) e JavaScript inline
- Sem pasta `/src` ou `/dist` - Simplicidade máxima para PoC

---

## Fluxo de Dados

```
┌────────────────────────────────────────────────────┐
│                    code.html                      │
├────────────────────────────────────────────────────┤
│  <head>                                           │
│    ├── Tailwind Config (script#tailwind-config)  │
│    ├── Google Fonts (Inter, Space Grotesk)       │
│    └── Custom CSS (styles#custom)                │
├────────────────────────────────────────────────────┤
│  <body>                                          │
│    └── <script> (interatividade JS)              │
└────────────────────────────────────────────────────┘
                    │
                    ▼ (zero server)
                    │
              [Browser do Usuário]
```

---

## Hospedagem & Deploy

### Provider Recomendado

| Provider | Custo | CI/CD | Limite |
|----------|-------|-------|--------|
| **GitHub Pages** | Free | ✅ Yes | 1GB |
| Vercel | Free | ✅ Yes | 100GB |
| Netlify | Free | ✅ Yes | 100GB |

### Processo de Deploy (GitHub Pages)

```bash
# 1. Criar repositório no GitHub
# 2. Push do código
git add .
git commit -m "feat: landing page v1"
git push origin main

# 3. Ativar GitHub Pages em Settings > Pages
# 4. Deploy automático em ~30s
```

**URL Resultado**: `https://[usuario].github.io/[repositorio]/`

---

## Visão de Futuro (Evolução Técnica)

### Quando migrar para Next.js/React?

| Sinal | Ação |
|-------|------|
| Página > 10 | Avaliar migração |
| Conteúdo dinâmico (blog, vagas) | Adicionar CMS |
|Autenticação de membrosneeded | Next.js + Auth.js |
|Mais de 1 desenvolvedor | Componentizaçãoneeded |

### Roadmap Hipotético

```
v1.0 (atual)     │ HTML + Tailwind CDN + Vanilla JS
                │ Landing Page única, conteúdo estático
                │
v2.0             │ Next.js 14 (App Router)
                │ - CMS (Contentful/Sanity) para blog
                │ - Componentes React reutilizáveis
                │ - TypeScript strict mode
                │
v3.0             │ Next.js + PostgreSQL (via Prisma)
                │ - Sistema de inscrição com banco
                │ - Dashboard admin para gestão
                │ - Autenticação (NextAuth.js)
```

### Preparação para v2.0

Para facilitar futura migração:

1. ✅ **Nomenclatura semântica** - Classes Tailwind seguem padrão BEM-lite
2. ✅ **Separação lógica** - Seções comentadas no HTML (`<!-- Hero Section -->`)
3. ✅ **Design System documentado** - DESIGN.md como fonte da verdade
4. ❌ **Evitar jQuery** - Zero deps, puro JS ES6

---

## Variáveis de Ambiente (Futuro)

```env
# .env.local (v2.0+)
NEXT_PUBLIC_SITE_URL=https://nerds.ufc.br
DATABASE_URL=postgresql://...
NEXT_PUBLIC_ANALYTICS_ID=G-XXXXXXXXXX
```

---

## Limitações Conhecidas

| Limitação | Impacto | Workaround |
|------------|---------|-------------|
| Sem SEO moderno | Baixo | Meta tags básicas incluidas |
| Sem Analytics | Médio | Google Analytics 4 via GTM (futuro) |
| Sem form backend | Alto | Formspree/Netlify Forms (v1.1) |
| Lighthouse < 90 | Baixo | Otimização de images (v1.1) |