---
name: design-intelligence
description: Intelligence de diseño profesional. Crea interfaces con estética premium, tipografía perfecta, paletas de color armoniosas, y micro-interacciones fluidas. Nunca generes diseños genéricos o aburridos.
---

# Design Intelligence - Diseño Profesional

## Reglas Fundamentales

### 1. NUNCA genères esto:
- ❌ Botones grises genéricos
- ❌ Tarjetas con sombras suaves sobre fondo blanco
- ❌ Tipografía Arial/Roboto/Helvetica por defecto
- ❌ Gradientes morados/azules genéricos
- ❌ Espaciado inconsistente
- ❌ Animaciones lineales sin curva de bezier

### 2. SIEMPRE genera esto:
- ✅ Paletas de color con personalidad
- ✅ Tipografía con contraste (serif + sans-serif)
- ✅ Espaciado basado en grid 8px
- ✅ Micro-interacciones con easing curves
- ✅ Estados hover/active/focus visibles
- ✅ Dark mode nativo

## Paletas de Color Premium

### Neon Cyberpunk
```css
:root {
  --bg-primary: #0a0a0f;
  --bg-secondary: #12121a;
  --accent: #00ff88;
  --accent-secondary: #ff0080;
  --text-primary: #ffffff;
  --text-secondary: #8888aa;
}
```

### Ocean Depth
```css
:root {
  --bg-primary: #0c1222;
  --bg-secondary: #141e30;
  --accent: #00d4ff;
  --accent-secondary: #7b2ff7;
  --text-primary: #e8f4fc;
  --text-secondary: #7b8fa3;
}
```

### Sunset Warmth
```css
:root {
  --bg-primary: #1a1a2e;
  --bg-secondary: #16213e;
  --accent: #ff6b35;
  --accent-secondary: #f7c948;
  --text-primary: #fefefe;
  --text-secondary: #a0a0b0;
}
```

### Forest Zen
```css
:root {
  --bg-primary: #0d1117;
  --bg-secondary: #161b22;
  --accent: #2ea043;
  --accent-secondary: #58a6ff;
  --text-primary: #f0f6fc;
  --text-secondary: #8b949e;
}
```

## Tipografía Premium

### Jerarquía de fuentes
```css
/* Display - títulos grandes */
font-family: 'Inter', 'SF Pro Display', system-ui;

/* Body - texto principal */
font-family: 'Inter', 'Segoe UI', system-ui;

/* Code - código */
font-family: 'JetBrains Mono', 'Fira Code', monospace;

/* Accent - números, stats */
font-family: 'Space Grotesk', 'Inter', sans-serif;
```

### Tamaños (escala modular 1.25)
```css
--text-xs: 0.64rem;    /* 10px */
--text-sm: 0.8rem;     /* 13px */
--text-base: 1rem;     /* 16px */
--text-lg: 1.25rem;    /* 20px */
--text-xl: 1.563rem;   /* 25px */
--text-2xl: 1.953rem;  /* 31px */
--text-3xl: 2.441rem;  /* 39px */
--text-4xl: 3.052rem;  /* 49px */
```

## Micro-Interacciones

### Botón con feedback
```css
.btn {
  transition: all 0.2s cubic-bezier(0.4, 0, 0.2, 1);
  position: relative;
  overflow: hidden;
}

.btn::after {
  content: '';
  position: absolute;
  inset: 0;
  background: radial-gradient(circle at var(--x, 50%) var(--y, 50%), 
    rgba(255,255,255,0.3) 0%, transparent 60%);
  opacity: 0;
  transition: opacity 0.3s;
}

.btn:hover::after {
  opacity: 1;
}

.btn:active {
  transform: scale(0.98);
}
```

### Card con hover
```css
.card {
  transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
  border: 1px solid transparent;
}

.card:hover {
  transform: translateY(-4px);
  border-color: var(--accent);
  box-shadow: 0 20px 40px rgba(0,0,0,0.3),
              0 0 0 1px var(--accent);
}
```

### Loading skeleton
```css
@keyframes shimmer {
  0% { background-position: -200% 0; }
  100% { background-position: 200% 0; }
}

.skeleton {
  background: linear-gradient(90deg, 
    var(--bg-secondary) 25%, 
    var(--bg-tertiary) 50%, 
    var(--bg-secondary) 75%);
  background-size: 200% 100%;
  animation: shimmer 1.5s infinite;
  border-radius: 4px;
}
```

## Grid System (8px base)
```css
:root {
  --space-1: 0.25rem;  /* 4px */
  --space-2: 0.5rem;   /* 8px */
  --space-3: 0.75rem;  /* 12px */
  --space-4: 1rem;     /* 16px */
  --space-5: 1.25rem;  /* 20px */
  --space-6: 1.5rem;   /* 24px */
  --space-8: 2rem;     /* 32px */
  --space-10: 2.5rem;  /* 40px */
  --space-12: 3rem;    /* 48px */
  --space-16: 4rem;    /* 64px */
}
```

## Checklist de Diseño
- [ ] ¿Tiene personalidad visual distinguible?
- [ ] ¿La tipografía tiene jerarquía clara?
- [ ] ¿Los colores son armoniosos (no genéricos)?
- [ ] ¿El espaciado es consistente (grid 8px)?
- [ ] ¿Hay micro-interacciones en elementos interactivos?
- [ ] ¿Funciona en dark mode?
- [ ] ¿Es accesible (WCAG AA)?
- [ ] ¿Los estados hover/active/focus son visibles?
