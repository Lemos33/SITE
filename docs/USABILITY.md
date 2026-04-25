# USABILITY.md - Usabilidade & Microinterações

## Visão Geral de Usabilidade

Este documento detalha as microinterações e comportamentos interativos implementados no site NERDS, seguindo os princípios de **Feedback Imediato** e **Engajamento Visual**.

---

## Microinterações Implementadas

### 1. Contador Numérico Animado (Métricas)

**Localização**: Sidebar de Recrutamento

**Elementos**:
- Membros Ativos: `30+`
- Projetos Entregues: `12`
- Áreas de Pesquisa: `4`

**Comportamento**:
```javascript
// JavaScript implementar: animateCountUp()
function animateCountUp(element, target, duration = 2000) {
  let start = 0;
  const increment = target / (duration / 16);
  
  const timer = setInterval(() => {
    start += increment;
    if (start >= target) {
      element.textContent = target + (target === 30 ? '+' : '');
      clearInterval(timer);
    } else {
      element.textContent = Math.floor(start);
    }
  }, 16);
}
```

**Efeito**: Números "contam" de 0 até o valor final quando a seção entra na viewport.

---

### 2. Glow em Botões (Hover)

**Localização**: Todos os botões CTA

**CSS**:
```css
.glow-hover:hover {
  box-shadow: 0 0 20px rgba(233, 196, 0, 0.4);
}
```

**Comportamento**:
- Hover: Glow dourado aparece suavemente
- Active: Escala para 0.98 (feedback de clique)
- Transition: 200ms ease-in-out

**Finalidade**: Feedback visual确认 botão é clicável

---

### 3. Animação de Pulse (LIVE)

**Localização**: Indicador de status de recrutamento

**CSS**:
```css
@keyframes pulse {
  0%, 100% { opacity: 1; }
  50% { opacity: 0.5; }
}

.animate-pulse {
  animation: pulse 2s cubic-bezier(0.4, 0, 0.6, 1) infinite;
}
```

**Comportamento**: 
- Ponto verde pisca lentamente (2s ciclo)
- Cria sensação de "em viva" / urgência

---

### 4. Elevação de Cards (Hover)

**Localização**: Cards de Trilhas e Projetos

**Comportamento**:
- **Hover entrada**: 
  - Borda muda para dourado/50
  - Background blur intensidade sutil aumenta
  - Imagem (se houver) escala para 1.05

```css
.group:hover .group-hover\:scale-105 {
  transform: scale(1.05);
}

.group:hover {
  border-color: rgba(233, 196, 0, 0.5);
}
```

**Finalidade**: Feedback visual que elemento é interactivo

---

### 5. Efeito de Glassmorphism

**Localização**: Todos os panels

**CSS**:
```css
.glass-panel {
  background: rgba(255, 255, 255, 0.05);
  backdrop-filter: blur(12px);
  border: 1px solid rgba(255, 255, 255, 0.1);
}
```

**Comportamento**: 
- Bordas superiores mais brilhantes (gradiente simula luz)
- Profundidade implícita através de opacidade

---

## Comportamentos JavaScript

### Estrutura do Script Inline

```html
<script>
  // 1. Contador animado ao scrollar (Intersection Observer)
  // 2. Animação de entrada (fade-in)
  // 3. Event listeners para botões
</script>
```

### Intersection Observer (Contador)

```javascript
const observer = new IntersectionObserver((entries) => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      // Iniciar animação do contador
      animateCountUp();
      observer.unobserve(entry.target);
    }
  });
}, { threshold: 0.5 });
```

---

## Responsividade Mobile First

### Breakpoints

| Dispositivo | Largura | Comportamento |
|------------|---------|---------------|
| Mobile | < 640px | Stack vertical completo |
| Tablet | 640-1024px | Grid 2 colunas |
| Desktop | > 1024px | Grid 12 colunas + sidebar |

### Adeolações Mobile

| Componente | Desktop | Mobile |
|------------|---------|---------|
| Navbar | Layout completo | Hamburger menu |
| Grid Trilhas | 3 colunas | 1 coluna |
| Grid Projetos | 2 colunas | 1 coluna |
| Sidebar | Coluna direita | Abaixo do conteúdo |
| Hero | Texto centrado | Texto centrado |

### Touch Targets

- **Botões**: Mínimo 44x44px (iOS guidelines)
- **Links de navegação**: 48px height mínimo
- **Espaçamento**: 16px mínimo entre elementos clicáveis

---

## Métricas de Usabilidade

### Core Web Vitals (Alvo)

| Métrica | Target | Implementação |
|--------|--------|---------------|
| LCP | < 2.5s | Fontes pré-carregadas |
| FID | < 100ms | JS mínimo |
| CLS | < 0.1 | Dimensões explícitas |

### Taxa de Conclusão de Tarefa

| Tarefa | Taxa Esperada |
|--------|--------------|
| Ler Hero completo | > 90% |
| Ver todas as trilhas | > 70% |
| Chegar ao CTA final | > 40% |
| Clicar em inscrição | > 5% |

---

## Testes de Usabilidade Recomendados

### Testes Manuais

| Teste | Procedimento | Êxito |
|------|---------------|-------|
| 1. Tempo na página | Cronometrar tempo até clique no CTA | < 30s |
| 2. Primeiro clique | Observar primeiro elemento clicado | Hero CTA |
| 3. Scroll depth | Analisar analytics scroll | > 50% |
| 4. Mobile | Testar em device real (iPhone + Android) | Sem quebrar |

### Testes Automatizados

```bash
# Lighthouse (CI/CD)
lighthouse http://localhost:3000 \
  --preset=desktop \
  --view \
  --output=json > lighthouse.json
```

---

## Problemas Conhecidos

| Problema | Severidade | Workaround |
|----------|-----------|------------|
| Slow LCP em mobile | Média | Otimizar carregamento de fontes |
| CLS em imagens | Baixa | Definir aspect-ratio |
| Navbar em mobile | Baixa | Implementar hamburger JS |