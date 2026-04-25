# UX.md - Experiência do Usuário

## Princípios de Design UX

### 1. Clareza de Propósito
Cada elemento na página serve a um objetivo claro: **converter o visitante em candidato**.

### 2. Hierarquia Visual
O usuário é guiado por uma hierarquia de注意力:

```
[CTA Dourado] ← Olhos vão aqui primeiro (cores vibram)
    │
    ▼
[Título Hero] ← Texto mais importante
    │
    ▼
[Subtítulo] ← Explicação breve
    │
    ▼
[CTAs Secundários] ← Opções de exploração
```

### 3. Progressão Natural
O layout segue a lógica de "espiral de envolvimento":
1. **Atenção** (Hero) → "O que é isso?"
2. **Interesse** (Trilhas) → "Que trilhas são essas?"
3. **Desejo** (Projetos) → "Que projetos legais!"
4. **Ação** (CTA Final) → "Vou me inscrver!"

---

## Anatomia da Página

### TopNav (Navegação Fixa)

```
┌────────────────────────────────────────────────────┐
│  NERDS        Sobre  Trilhas  Projetos    [Entrar] │
└────────────────────────────────────────────────────┘
                    ↑
              Posição fixa (top: 0)
              Backdrop blur para legibilidade
```

**Características UX**:
- Fixo no topo durante scroll
- Backdrop-blur mantém legibilidade sobre conteúdo
- "Entrar" como botão secundário ( أقل importância)
- Link "Sobre" ativo (underline) indica página atual

### Hero Section

```
┌────────────────────────────────────────────────────┐
│                                                      │
│    Codifique o seu futuro na UFC.                    │
│    Faça parte do NERDS.                             │
│                                                      │
│    Junte-se ao principal grupo de pesquisa          │
│    e desenvolvimento de software da UFC.            │
│                                                      │
│    [Ver Processo Seletivo]  [Conoce Projetos]      │
│                                                      │
└────────────────────────────────────────────────────┘
```

**Decisões UX**:
- Headline em 2 linhas: 1 Institucional + 1 CTA implícito
- Subtítulo menciona benefícios (não funcionalidades)
- 2 CTAs: Primário (dourado) e Secundário (ghost)

### Seção de Trilhas

```
┌────────────────────────────────────────────────────┐
│  🛤️ Nossas Trilhas de Estudo                       │
│                                                      │
│  ┌──────────┐ ┌──────────┐ ┌──────────┐           │
│  │#ENG_SOFT │ │#IA_ML    │ │#DATA_SCI │           │
│  │          │ │          │ │          │           │
│  │ Engenh... │ │ Int.Art. │ │ Ciênc... │           │
│  │ Software │ │ Artificial│ │ Dados  │           │
│  └──────────┘ └──────────┘ └──────────┘           │
└────────────────────────────────────────────────────┘
```

**Decisões UX**:
- 3 colunas em desktop (grid igual)
- Tags codificadas criam identificação com público tech
- Border-radius XL (1rem) para aspecto moderno

### Seção de Projetos

```
┌────────────────────────────────────────────────────┐
│  💻 Projetos Reais                                 │
│                                                      │
│  ┌─────────────────┐  ┌─────────────────┐           │
│  │    [IMAGEM]     │  │    [IMAGEM]     │           │
│  │                 │  │                 │           │
│  │ Sist. Gestão    │  │ Motor de Rec.   │           │
│  │ Acadêmica v2    │  │ IA              │           │
│  └─────────────────┘  └─────────────────┘           │
└────────────────────────────────────────────────────┘
```

**Decisões UX**:
- Screenshots reais (não placeholders)
- Layout 2 colunas cria paralaxe visual
- Screenshots com opacity reduzida (70%) que aumenta no hover

### Sidebar de Recrutamento

```
┌────────────────────────────────────────────────────┐
│  Status do Recrutamento      [LIVE ●]              │
│                                                      │
│  As inscrições para a turma 2026.1 estão            │
│  oficialmente abertas. Vagas limitadas...           │
│                                                      │
│  [Inscreva-se na Turma 2026.1 →]                    │
│                                                      │
│  Membros Ativos       30+                            │
│  Projetos Entregues 12                             │
│  Áreas de Pesquisa   4                             │
└────────────────────────────────────────────────────┘
```

**Decisões UX**:
- Indicador "LIVE" cria urgência real
- Contadores criam prova social
- CTA fixo no final da página (sempre visível no scroll)

---

## Fluxo de Scroll

### Scroll Depth Médio

| Seção | Ponto de Decisão | % Usuários |
|-------|----------------|------------|
| Hero | Vê título + CTAs | 100% |
| Trilhas | Vê trilhas | 75% |
| Projetos | Vê projetos | 60% |
| Sidebar | Vê CTAfinal | 45% |
| Footer | Chega ao fundo | 35% |

**Meta**: Manter >60% até seção de Projetos

---

## Acessibilidade (a11y)

### Requisitos WCAG AA Cumpridos

| Requisito | Implementação |
|----------|---------------|
| ✅ Contraste | Texto ≥ 4.5:1, UI ≥ 3:1 |
| ✅ Foco visível | Outline dourado em focus |
| ✅ Labels | Todos inputs tienen label |
| ✅ Sem blink | Animação sem flashing |
| ✅ Sem cor única | Info não dependede cor |
| ✅ Keyboard nav | Todos clickáveis via Tab |

### ARIA Implementados

```html
<!-- Indicador live -->
<div role="status" aria-live="polite">
  <span class="animate-pulse">LIVE</span>
</div>
```

---

## Tarefas do Usuário

| Tarefa | Caminho | Tempo Esperado |
|--------|--------|---------------|
| Entender o que é o NERDS | Ler Hero | < 5s |
| Ver trilhas disponíveis | Scroll → Trilhas | < 10s |
| Ver projetos reales | Scroll → Projetos | < 15s |
| Verificarinscrição aberta | Scroll → Sidebar | < 20s |
| Clicar em inscrição | Sidebar → CTA | < 25s |

**Meta de tempo total**: < 30 segundos da chegada à conversão