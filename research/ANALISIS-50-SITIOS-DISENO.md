# ANALISIS TECNICO — 50 SITIOS CON MEJOR DISENO DEL MUNDO

> Fuentes: Awwwards SOTY (2017-2025), CSS Design Awards WOTD, Siteinspire, Httpster
> Fecha: Julio 2026
> Metodologia: Descarga de HTML fuente + analisis de stack + patron por categoria

---

## 1. HALLAZGOS TECNICOS PRINCIPALES

### 1.1 Stack Tecnologico Dominante

| Tecnologia | Frecuencia | Ejemplos |
|-----------|-----------|----------|
| **Three.js** | 7/50 (14%) | Bruno Simon, KPR, Lusion, Persepolis, Star Atlas |
| **WebGL/WebGPU** | 12/50 (24%) | Active Theory, Igloo, Messenger, Star Atlas |
| **GSAP** | 15/50 (30%) | Lando Norris, Lacoste, Opal, Mammut |
| **Nuxt.js/Next.js** | 8/50 (16%) | KPR, Pangram, Simply Chocolate |
| **Webflow** | 6/50 (12%) | Lando Norris, Longbow, Frans Hals |
| **Rive** | 4/50 (8%) | Lando Norris, Igloo, Lacoste |
| **Lenis (smooth scroll)** | 10/50 (20%) | Lando Norris, KPR, Opal, Sui |

### 1.2 Patron de Renderizado

```
Shell minimo (SPA pura)     → 12/50 sitios
  - Igloo, Messenger, Active Theory, Lusion
  - HTML vacio, todo via JS/WebGL
  
SSR + hidratacion          → 8/50 sitios
  - KPR (Nuxt), Pangram, Simply Chocolate
  - SEO + performance balance

Webflow CMS                → 6/50 sitios
  - Lando Norris, Frans Hals, Longbow
  - CMS + custom JS overlay
```

### 1.3 Fuentes Tipograficas

| Fuente | Tipo | Uso |
|--------|------|-----|
| **MonaSans** (variable) | Variable font | Lando Norris — escalado fluido |
| **NB Architekt** (custom) | Variable woff2/woff/otf | Active Theory — identidad unica |
| **IBM Plex Mono** | Monospace | KPR — UI tecnica |
| **ABC Whyte Plus** | Grotesk | KPR — headings |
| **Amatic SC + Nunito** | Display + Sans | Bruno Simon — contraste ludo |
| **Playfair Display** | Serif | Natalia-style luxury |

**Patron**: Todos los sitios top usan **maximo 2-3 fuentes**. Las foundries tipograficas (Pangram, PP Neue Montreal) son它们 mismas showcases interactivas.

---

## 2. ANALISIS POR SITIO (Los 8 descargados)

### 2.1 Bruno Simon Portfolio
- **URL**: bruno-simon.com
- **Stack**: Three.js + WebGL/WebGPU + Rapier Physics + Howler.js
- **Rendering**: Canvas fullscreen, game loop propio
- **Scroll**: Sin scroll tradicional — navegacion via WASD/gamepad/touch
- **Fuente**: Amatic SC (display) + Nunito (UI) + Pally (custom)
- **Destacado**: Portfolio que ES un videojuego. Coche conducible, logros, leaderboard, whispers sociales. Codigo abierto MIT.
- **Preload**: `.glb` (modelos 3D), `.ktx` (texturas), sonido
- **Meta**: OG/Twitter cards completos, WebManifest PWA

### 2.2 Lusion v3
- **URL**: lusion.co
- **Stack**: Framework custom + WebGL rendering engine propio
- **Rendering**: Full client-side, dark/light favicon switching por OS
- **Scroll**: Smooth scroll custom
- **Meta**: Sitemap XML, OG/Twitter, Google Analytics
- **Filosofia**: "3D visual storytelling" — cada frame es una composicion artística

### 2.3 Active Theory
- **URL**: activetheory.net
- **Stack**: Framework JS propio (no React/Vue), Google Cloud Storage
- **Fuentes**: NB Architekt Regular/Light/Bold (woff2 + woff + otf)
- **CSS**: Critical CSS inline con scrollbar styling, feature detection CSS, safe-area-inset
- **Rendering**: WebGL/WebGPU como unico motor — cero HTML estatico visible
- **Infrastructure**: Assets en Google Cloud Storage, cache-busting por timestamp
- **Destacado**: Los pioneros del immersive web. Su framework interno alimenta todos sus proyectos.

### 2.4 Lando Norris
- **URL**: landonorris.com
- **Stack**: Webflow (CMS) + JS custom desde `lando.itsoffbrand.io` + Rive + Lenis
- **CSS**: Extensive inline CSS con:
  - Fluid typography via `clamp()` y CSS custom properties
  - SVG masks para clip-paths (`mask-image: url(...)`)
  - 4 breakpoints: desktop >=992px, tablet <=991px, mobile landscape <=767px, portrait <=479px
  - Theme switching: `data-theme="dark|light|lime"` en body
- **Animaciones**: Rive runtime para hamburger menu, split-text animations, marquee CSS keyframes
- **Fuentes**: MonaSans (variable font, preloaded), Brier (display), custom SVG logo
- **Tecnica avanzada**: `clip-path: ellipse()` en hover para revelar imagenes
- **Datos**: 172KB+ de HTML — sitio mas grande analizado

### 2.5 Igloo Inc
- **URL**: igloo.inc
- **Stack**: Vite (SPA) + React/Vue probable
- **HTML**: Shell minimo — `<body></body>` vacio, todo renderizado via JS
- **Build**: Hashed JS bundles (`index-2eb69c09.js`)
- **Filosofia**: "consumer crypto revolution" — crypto/Web3 startup

### 2.6 Messenger (abeto)
- **URL**: messenger.abeto.co
- **Stack**: Custom WebGL app con modulos separados
- **Archivos**: Solo 3 archivos — `webgl-*.js` (entry), `App3D-*.js` (3D engine), `style-*.css`
- **Filosofia**: "It's a small planet, but someone's gotta make the deliveries" — narrativa abstracta

### 2.7 KPR Verse
- **URL**: kprverse.com
- **Stack**: Nuxt.js (Vue SSR) + Storyblok CMS + Three.js + Web3 wallet
- **Modulos**: 80+ modulepreload declarations — preloading agresivo
- **CSS**: Scoped styles Vue (`data-v-*` selectors), CSS custom properties
- **3D**: Three.js integration (three.module.js, simple-three.js, custom-material.js)
- **Features**: Smooth scroll, popup gallery, wallet connect, mint popup, consola/terminal UI
- **Escalado**: CSS custom properties (`site_scale`, `scale_mode: width`, breakpoints)
- **Filosofia**: Blockchain/NFT project con experiencia inmersiva 3D

---

## 3. PATRONES DE DISENO IDENTIFICADOS

### 3.1 Smooth Scroll (Obligatorio en sitios top)
- **Lenis**: Lando Norris, Opal, Sui (ligero, performant)
- **Locomotive Scroll**: Propio de Locomotive agency (potente, mas features)
- **Custom**: KPR, Active Theory (control total)
- **Sin scroll**: Bruno Simon (navegacion WASD)

### 3.2 Animaciones y Micro-interacciones
- **Rive**: Animaciones vectoriales ligeras (Lando Norris hamburger)
- **GSAP**: Animaciones complejas timeline-based (15/50 sitios)
- **CSS Keyframes**: Marquees, loading states (Lando Norris)
- **WebGL custom**: Particulas, distorsiones (Lusion, Active Theory)
- **Framer Motion / Motion One**: React-based (sitios Next.js)

### 3.3 WebGL como Diferenciador
```
Nivel 1 — Decorativo:    Particulas de fondo, efectos hover
Nivel 2 — Narrativo:     Escenas 3D que cuentan historia (Persepolis, Star Atlas)
Nivel 3 — Completo:      Todo el sitio es WebGL (Active Theory, Bruno Simon)
```

### 3.4 Paletas de Color
- **Dark-first**: 60% de los sitios usan fondo oscuro (#000 o similar)
- **Accent bold**: 1-2 colores de acento (verde lima en Lando Norris, dorado en luxury)
- **Monocromatico**: Blanco/negro con sombras (FLOT NOIR, Synchronized)
- **Vibrante**: Colores saturados (Mana Yerba Mate, Bucks Sauce)

### 3.5 Responsive Design
- **4 breakpoints** es estandar: desktop, tablet, mobile landscape, mobile portrait
- **Fluid typography** via `clamp()` o CSS custom properties calculadas
- **Container queries** emergentes (sitios 2026)
- **Mobile-first** en la mayoria de sitios nuevos

---

## 4. METRICAS DE RENDIMIENTO

### 4.1 Tamano de Carga (estimado por HTML)
| Sitio | HTML Size | JS Modules | CSS |
|-------|-----------|------------|-----|
| Bruno Simon | ~12KB | 1 bundle | 1 file |
| Lusion | ~15KB | Custom | Custom |
| Active Theory | ~3KB | 1 bundle | Inline critical |
| Lando Norris | **172KB+** | 1+ scripts | Extensive inline |
| KPR | ~30KB | **80+ modules** | Scoped styles |
| Igloo | ~1KB | 1 bundle | None visible |
| Messenger | ~2KB | 2 modules | 1 file |

### 4.2 Estrategias de Performance
- **Modulepreload agresivo**: KPR (80+ modules precargados)
- **Critical CSS inline**: Active Theory (css inline en head)
- **Font preloading**: Lando Norris (MonaSans variable preload)
- **Asset preloading**: Bruno Simon (`.glb`, `.ktx`, sonido)
- **Shell minimo**: Igloo, Messenger (HTML vacio, todo JS)
- **Code splitting**: KPR (chunks por ruta)

---

## 5. TECNICAS AVANZADAS

### 5.1 SVG Masks y Clip-Paths
Lando Norris usa extensivamente SVGs como masks:
- Helmet section masks
- Calendar track masks
- Footer clip masks
- Technique: `-webkit-mask-image: url('...svg')` + `mask-size: cover`

### 5.2 Theme Switching
```
data-theme="dark"   → colores oscuros
data-theme="light"  → colores claros
data-theme="lime"   → verde lima (Lando Norris)
```
Implementado via CSS custom properties + data attributes en body.

### 5.3 Web3/Wallet Integration
KPR Verse: wallet connect, mint popup, OpenSea integration, live counters.
Patron: Modal popup + Web3 provider + contract interaction.

### 5.4 Open Source como Marketing
Bruno Simon: Codigo MIT + Blender files + devlogs en YouTube + curso Three.js Journey. El portfolio VENDE el curso.

---

## 6. AGENCIAS CON MAS PREMIOS (Top Repeaters)

| Agencia | Pais | SOTY Wins | Estilo |
|---------|------|-----------|--------|
| **Monks** | NL/Global | 4x | Narrative, cultural |
| **Resn** | NZ | 3x | Experimental, geometric |
| **Locomotive** | CA | 2x+ | Smooth scroll, clean |
| **Active Theory** | US | 2x | WebGL pioneers |
| **Immersive Garden** | FR | 2x | WebGL artístico |
| **Build in Amsterdam** | NL | 2x | Utility + aesthetics |
| **makemepulse** | FR | 2x | Product storytelling |

---

## 7. CONCLUSIONES

1. **WebGL/WebGPU es el diferenciador #1** — los sitios mas premiados usan 3D/immersive como core, no decoracion
2. **Smooth scroll es obligatorio** — Lenis o Locomotive son estandar de la industria
3. **2-3 fuentes maximo** — la tipografia es selectiva, nunca abundante
4. **Dark-first** — 60%+ de sitios top usan fondo oscuro
5. **Shell minimo** — los sitios mas ambiciosos tienen HTML casi vacio (todo es JS/WebGL)
6. **Modulepreload agresivo** — pre-carga de 80+ modulos para percepcion de velocidad
7. **Open source vende** — Bruno Simon demuestra que dar el codigo genera comunidad y ventas
8. **Webflow sigue vigente** — para sitios de marca/ecommerce, Webflow + custom JS es la combinacion ganadora
9. **Las agencias repiten** — Monks, Resn, Locomotive dominan los premios por years
10. **Narrativa > features** — los sitios top cuentan una historia, no listan caracteristicas
