# CHANGELOG.md - Evolução do Produto

Todos os Notable Changes deste projeto serão documentados neste arquivo.

O formato é baseado em [Keep a Changelog](https://keepachangelog.com/pt-BR/1.0.0/).
Por favor, siga este formato ao adicionar novas entradas.

---

## [0.1.0] - Lançamento da PoC

### Added
- **Estrutura Base HTML5** semântico com meta tags para SEO básico
- **Tailwind CSS via CDN** configurado com design tokens customizados
- **Google Fonts**: Inter (corpo), Space Grotesk (labels), Material Symbols (ícones)
- **Design System completo**: Todas as cores, tipografia e spacing definidos no Tailwind config

### Created
- **TopNavBar** com navegação fixa e backdrop-blur
- **Hero Section** com título impactante e 2 CTAs
- **Seção de Trilhas**: 3 cards (Engenharia de Software, IA/ML, Ciência de Dados)
- **Seção de Projetos**: 2 cards com screenshots e descrições
- **Sidebar de Recrutamento** com indicador LIVE, contadores e CTA final
- **Footer** com links e copyright

### Implemented
- **Glassmorphism**: Classe `.glass-panel` com backdrop-blur e bordas translúcidas
- **Background Grid Pattern**: Grid sutil 40x40px para efecto "laboratório técnico"
- **Glow Effect**:`.glow-hover` para CTAs no hover
- **Animação Pulse**: Indicador LIVE com animação infinita
- **Responsividade Mobile**: Grid stack em mobile

### Documentation
- **DESIGN.md**: Design tokens originales (fonte)
- **screen.png**: Screenshot do design final

---

## [0.0.1] - Setup Inicial

### Added
- **Repositório Git** inicializado com `.gitignore` padrão
- Estrutura de pastas vazia preparada para evolução

---

## Notas de Versão

### Convenções de Versionamento

Usamos [Semantic Versioning](https://semver.org/):

```
MAJOR.MINOR.PATCH
│    │    │
│    │    └── Correção de bugs
│    │
│    └──── Novas funcionalidades (backward compatible)
│
└───── Mudanças breaking (retrocompatibilidade quebrada)
```

### Prefixos de Commits

| Prefixo | Uso |
|--------|-----|
| `feat:` | Nova funcionalidade |
| `fix:` | Correção de bug |
| `docs:` | Documentação |
| `style:` | Formatação (CSS, identação) |
| `refactor:` | Refatoração de código |
| `perf:` | Otimização de performance |

---

## Migration Guides

### coming soon

Durante a evolução do projeto, guias de migração serão adicionados aqui quando houver breaking changes.

---

## Links Úteis

- [Keep a Changelog](https://keepachangelog.com/pt-BR/1.0.0/)
- [Conventional Commits](https://www.conventionalcommits.org/)
- [Semantic Versioning](https://semver.org/)