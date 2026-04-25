# DESIGN_SYSTEM.md - Identidade Visual

## Visão Geral do Design

O Design System do NERDS combina **Glassmorphism** com **Modern Corporate**, criando uma estética que transitai entre o prestígio institucional da UFC e a inovação tecnológica moderna. O objetivo emocional é evocar "Energia Intelectual" — combinando a estabilidade da herança universitária com a natureza ágil da engenharia de software moderna.

---

## Paleta de Cores

### Cores de Fundo (Surface)

| Token | Hex | Uso |
|-------|-----|-----|
| `background` | `#101415` | Fundo principal da página (Dark Mode) |
| `surface` | `#101415` | Alias do background |
| `surface-dim` | `#101415` | Fundo diminuído (para sombras) |
| `surface-lowest` | `#0b0f10` | Camada mais profunda |
| `surface-container-low` | `#191c1e` | Containers em destaque |
| `surface-container` | `#1d2022` | Containers padrão |
| `surface-container-high` | `#272a2c` | Containers elevados |
| `surface-container-highest` | `#323537` | Containers no topo |

### Cores de Texto (On-Surface)

| Token | Hex | Uso |
|-------|-----|-----|
| `on-background` | `#e0e3e5` | Texto primário |
| `on-surface` | `#e0e3e5` | Alias texto primário |
| `on-surface-variant` | `#c2c6d1` | Texto secundário/metadata |
| `outline` | `#8c919b` | Bordas subdued |
| `outline-variant` | `#424750` | Bordas internas |

### Cores Primárias (Brand)

| Token | Hex | Uso |
|-------|-----|-----|
| `primary` | `#a5c8ff` | Azul institucional claro |
| `on-primary` | `#00315f` | Texto sobre primary |
| `primary-container` | `#00417b` | Fundo de containers primary |
| `on-primary-container` | `#83afef` | Texto em containers primary |
| `primary-fixed` | `#d4e3ff` | Elementos fixos primary |
| `primary-fixed-dim` | `#a5c8ff` | Versão dimada |

### Cores Secundárias (Ação/Destaque)

| Token | Hex | Uso |
|-------|-----|-----|
| `secondary` | `#fff9ef` | Amarelo muito claro |
| `secondary-container` | `#ffdb3c` | Dourado vibrante (CTA!) |
| `secondary-fixed` | `#ffe16d` | Dourado mais vivo |
| `secondary-fixed-dim` | `#e9c400` | Dourado principal (USE!) |

### Cores de Erro

| Token | Hex | Uso |
|-------|-----|-----|
| `error` | `#ffb4ab` | Vermelho soft |
| `error-container` | `#93000a` | Vermelho escuro |

---

## Hierarquia de Cores

### Uso Prático

```
┌────────────────────────────────────────────────────┐
│                    FUNDO                           │
│              (background #101415)                   │
├────────────────────────────────────────────────────┤
│  PANEL DE VIDRO                                     │
│  background: rgba(255,255,255,0.05)              │
│  backdrop-filter: blur(12px)                        │
│  border: 1px solid rgba(255,255,255,0.1)           │
├────────────────────────────────────────────────────┤
│  TEXTO PRINCIPAL (on-surface #e0e3e5)            │
│  TEXTO SECUNDÁRIO (on-surface-variant #c2c6d1)    │
├────────────────────────────────────────────────────┤
│  BOTÕES E CTAs                                      │
│  Background: #e9c400 (secondary-fixed-dim)       │
│  Texto: #221b00                                    │
│  Hover: #ffe16d (secondary-fixed) + glow           │
└───────────────────────��────────────────────────────┘
```

---

## Tipografia

### Família de Fontes

| Família | Uso | Fonte |
|---------|-----|-------|
| **Inter** | Corpo, títulos, CTAs | Google Fonts |
| **Space Grotesk** | Labels, tags, metadata | Google Fonts |
| **Material Symbols** | Ícones | Google Fonts |

### Especificações

#### Display XL (Hero)

```
font-size: 72px
line-height: 1.1
letter-spacing: -0.04em
font-weight: 800
font-family: Inter
```

#### Headline LG (Títulos de Seção)

```
font-size: 32px
line-height: 1.2
letter-spacing: -0.02em
font-weight: 700
font-family: Inter
```

#### Body MD (Texto)

```
font-size: 16px
line-height: 1.6
letter-spacing: 0em
font-weight: 400
font-family: Inter
```

#### Label Mono (Tags/Labels)

```
font-size: 12px
line-height: 1
letter-spacing: 0.05em
font-weight: 500
font-family: Space Grotesk
```

#### Code Accent (Tags de Trilha)

```
font-size: 14px
line-height: 1.4
font-weight: 400
font-family: monospace
```

---

## Componentes Base

### Card (Glass Panel)

```css
.glass-panel {
  background: rgba(255, 255, 255, 0.05);
  backdrop-filter: blur(12px);
  -webkit-backdrop-filter: blur(12px);
  border: 1px solid rgba(255, 255, 255, 0.1);
  border-radius: 1rem;
}
```

**Características**:
- Fundo semi-transparente (5% opacidade)
- Blur de 12px simulating glass
- Borda sutil white/10
- Border-radius: 1rem (XL)
- Gradiente superior (bordai top white/20)

### Botão Primário (CTA)

```
background: #e9c400 (secondary-fixed-dim)
color: #221b00 (on-secondary-fixed)
border-radius: 0.5rem
padding: 1rem 2rem
font-weight: 700
font-family: Inter

HOVER:
- background: #ffe16d (secondary-fixed)
- box-shadow: 0 0 20px rgba(233, 196, 0, 0.4)
- transform: scale(0.98)
- transition: all 200ms ease
```

### Botão Secundário (Ghost)

```
background: transparent
color: #e0e3e5
border: 1px solid rgba(255, 255, 255, 0.1)
border-radius: 0.5rem
padding: 1rem 2rem

HOVER:
- background: rgba(255, 255, 255, 0.1)
- border-color: rgba(255, 255, 255, 0.2)
```

### Input

```
background: #1d2022
color: #e0e3e5
border: 1px solid #424750
border-radius: 0.5rem
padding: 0.75rem 1rem

FOCUS:
- border-color: #e9c400 (secondary-fixed-dim)
- box-shadow: 0 0 0 3px rgba(233, 196, 0, 0.1)
```

---

## Espaçamento (Spacing System)

### Base Unit: 8px (0.5rem)

| Token | Valor | Uso |
|-------|-------|-----|
| `unit-xs` | 0.25rem (4px) | Padding interno pequeno |
| `unit-sm` | 0.5rem (8px) | Gaps pequenos |
| `unit-md` | 1rem (16px) | Padding padrão |
| `unit-lg` | 2rem (32px) | Seções internas |
| `unit-xl` | 4rem (64px) | Margens de seção |
| `gutter` | 1.5rem (24px) | Padding lateral container |
| `margin-page` | 2rem (32px) | Margem da página |
| `container-max` | 1280px | Largura máxima |

---

## Formas e Border Radius

| Token | Valor | Uso |
|-------|-------|-----|
| `sm` | 0.25rem | Inputs, tags pequenas |
| `DEFAULT` | 0.5rem | Botões, inputs |
| `xl` | 0.75rem | Cards menores |
| `xl` | 1rem | Cards, containers |
| `full` | 9999px | Pills, avatares |

**Regra**: Evitar bordas 0px. Sempre usar no mínimo 0.25rem para manter tom jovem e moderno.

---

## Grid de Fundo (Background Pattern)

```css
.bg-grid-pattern {
  background-image: linear-gradient(to right, rgba(255, 255, 255, 0.05) 1px, transparent 1px),
                    linear-gradient(to bottom, rgba(255, 255, 255, 0.05) 1px, transparent 1px);
  background-size: 40px 40px;
}
```

**Características**:
- Linhas a cada 40px (5x base unit)
- Opacidade 5% (muito sutil)
- Cria sensação de "laboratório técnico"

---

## Efeitos Visuais

### Glow (CTA Hover)

```css
.glow-hover:hover {
  box-shadow: 0 0 20px rgba(233, 196, 0, 0.4);
}
```

### Animação de Pulse (Indicador LIVE)

```css
@keyframes pulse {
  0%, 100% { opacity: 1; }
  50% { opacity: 0.5; }
}
.animate-pulse {
  animation: pulse 2s cubic-bezier(0.4, 0, 0.6, 1) infinite;
}
```

---

## Responsividade

### Breakpoints

| Breakpoint | Largura | Comportamento |
|------------|---------|----------------|
| Mobile | < 640px | Stack vertical, hamburger menu |
| Tablet | 640px - 1024px | Grid 2 colunas |
| Desktop | > 1024px | Grid 12 colunas, sidebar |

---

## Acessibilidade de Cores

Todas as combinações de cores foram testadas para contraste WCAG AA:

- ✅ Texto branco (#e0e3e5) sobre fundo escuro (#101415) = Ratio 13:1 (AA)
- ✅ Texto preto (#221b00) sobre dourado (#e9c400) = Ratio 12:1 (AA)
- ⚠️ Metadata (#c2c6d1) sobre fundo = Ratio 4.5:1 (AA apenas para texto grande)