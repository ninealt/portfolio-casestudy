# UI System

## Aplicación de Tokens de Diseño

Esta sección documenta la implementación visual completa del sistema de diseño, incluyendo todas las variantes y estados de componentes.

---

## Componentes UI Detallados

### 1. Navigation Header

#### Desktop Header

```
┌──────────────────────────────────────────────────────────────┐
│  🎮  TAMARA PALMA                            [ CONTACTAR ▶ ] │
│                                                              │
│  Height: 64px                                                │
│  Background: rgba(26, 26, 26, 0.85)                          │
│  Backdrop-filter: blur(12px)                                 │
│  Border-bottom: 1px solid rgba(255,255,255,0.1)              │
└──────────────────────────────────────────────────────────────┘
```

**Estados:**

| Estado | Apariencia |
|--------|------------|
| Default | Opacity 0.85, blur activo |
| Scrolled (>100px) | Opacity 0.95, sombra sutil |
| Mobile | Hamburger menu, logo centrado |

---

### 2. Sidebar Navigation

```
┌──────────┐
│  ╭────╮  │
│  │ 👤 │  │
│  ╰────╯  │
│  Tamara  │
│  Palma   │
│  ─────── │
│          │
│  🏠 Home │ ← Active state: border-left cyan
│  ─────── │
│  ⚡ Skill│
│  💼 Exp  │
│  🎓 Edu  │
│  ✉️ Cont │
│          │
│ Width:   │
│ 240px    │
└──────────┘
```

**Active State:**
```css
border-left: 3px solid var(--accent-primary);
background: linear-gradient(90deg, rgba(0,212,255,0.1) 0%, transparent 100%);
```

---

### 3. Hero Section

#### Estructura

```
┌──────────────────────────────────────────────────────────────┐
│                                                              │
│                    ╭────────────────────────╮                │
│                    │                        │                │
│   TAMARA PALMA     │   ┌────────────────┐   │                │
│   ~~~~~~~~~~~~     │   │   👤 Avatar    │   │  Profile Card  │
│                    │   │                │   │                │
│   Full Stack       │   │ Full Stack     │   │                │
│   Developer        │   │ Lv.5           │   │                │
│   & UX Designer    │   │                │   │                │
│                    │   │ [Skill bars]   │   │                │
│   [⚛️] [🐍] [⬢]   │   │                │   │                │
│                    │   │ 🟢 Available   │   │                │
│   ┌──────────────┐ │   └────────────────┘   │                │
│   │  CONTACTAR ▶ │ │                        │                │
│   └──────────────┘ ╰────────────────────────╯                │
│                                                              │
└──────────────────────────────────────────────────────────────┘
```

#### Tipografía Hero

| Elemento | Font | Weight | Size | Color |
|----------|------|--------|------|-------|
| Nombre | Inter | 700 | 72px | White |
| Tagline | Inter | 400 | 24px | 60% white |
| Tech icons | - | - | 32px | Cyan |
| CTA | Inter | 600 | 16px | Cyan |

---

### 4. Profile Card

```
┌─────────────────────────────┐
│                             │
│    ╭──────────────────╮     │
│    │                  │     │
│    │   👤 (avatar)    │     │
│    │                  │     │
│    ╰──────────────────╯     │
│                             │
│    Full Stack Developer     │
│    Level 5                  │
│                             │
│    ━━━━━━━━━━━━━━━━━━━━━    │
│    React    ████████░░ 80%  │
│    Python   █████████░ 90%  │
│    UX/UI    ██████░░░░ 75%  │
│    ━━━━━━━━━━━━━━━━━━━━━    │
│                             │
│    🟢 Available for quests  │
│    📍 Remote from Quillota  │
│                             │
└─────────────────────────────┘

Background: rgba(45, 45, 45, 0.6)
Border: 1px solid rgba(255,255,255,0.1)
Border-radius: 16px
Backdrop-filter: blur(10px)
```

**Skill Bars:**
```css
.skill-bar {
  height: 6px;
  background: rgba(255,255,255,0.1);
  border-radius: 3px;
  overflow: hidden;
}

.skill-bar-fill {
  height: 100%;
  background: linear-gradient(90deg, #00d4ff, #00a8cc);
  border-radius: 3px;
}
```

---

### 5. Tech Stack Grid

```
┌─────────────────────────────────────────────────────┐
│ SKILL TREE                                          │
│                                                     │
│  ┌──────────┐  ┌──────────┐  ┌──────────┐          │
│  │[LENGUAJE]│  │[FRAMEWORK│  │[RUNTIME] │          │
│  │          │  │]         │  │          │          │
│  │    ⚛️    │  │    🅰️    │  │    ⬢     │          │
│  │          │  │          │  │          │          │
│  │  React   │  │  Angular │  │ Node.js  │          │
│  │          │  │          │  │          │          │
│  │ Library  │  │  Google  │  │ Runtime  │          │
│  │   for UI │  │          │  │          │          │
│  └──────────┘  └──────────┘  └──────────┘          │
│                                                     │
└─────────────────────────────────────────────────────┘
```

**Card Hover:**
```css
.tech-card:hover {
  transform: translateY(-4px);
  border-color: var(--accent-primary);
  box-shadow: 0 0 20px rgba(0,212,255,0.2);
}
```

---

### 6. Timeline Experience

```
┌─────────────────────────────────────────────────────┐
│ QUEST LOG                                           │
│                                                     │
│      ╭──●──────────────────────────────╮            │
│      │  2025 - Presente                 │            │
│      │                                  │            │
│      │  🏆 Senior Developer             │            │
│      │  🏦 iProspect                    │            │
│      │                                  │            │
│      │  Leading frontend development    │            │
│      │  for enterprise clients...       │            │
│      ╰──────────────────────────────────╯            │
│      │                                               │
│      ●                                               │
│      │                                               │
│      ╭──────────────────────────────────╮            │
│      │  2023 - 2024                       │            │
│      │                                  │            │
│      │  Full Stack Developer            │            │
│      │  🏦 Banco Bice                   │            │
│      ╰──────────────────────────────────╯            │
│                                                     │
└─────────────────────────────────────────────────────┘
```

**Timeline Styles:**
```css
.timeline-line {
  width: 2px;
  background: linear-gradient(180deg, #00d4ff, transparent);
}

.timeline-dot {
  width: 12px;
  height: 12px;
  background: #00d4ff;
  border-radius: 50%;
  box-shadow: 0 0 10px rgba(0,212,255,0.5);
}
```

---

### 7. Education Cards

```
┌──────────┐ ┌──────────┐ ┌──────────┐
│[DESARROL │ │[DESARROL │ │[DISEÑO]  │
│VO]       │ │VO]       │ │          │
│          │ │          │ │          │
│  2025-26 │ │  2021-22 │ │ 2021     │
│          │ │          │ │          │
│  🎓 UI/  │ │  🎮 Unity│ │  🐍 Full │
│     UX   │ │     2D/3D│ │     Stack│
│          │ │          │ │     Python│
│  Univ... │ │  Acad... │ │  Acad... │
│          │ │          │ │          │
└──────────┘ └──────────┘ └──────────┘
```

---

### 8. Contact Section

```
┌─────────────────────────────────────────────────────┐
│ INICIAR CONTACTO                                    │
│                                                     │
│  ┌──────────────────┐  ┌──────────────────┐        │
│  │     ✉️           │  │     💼           │        │
│  │                  │  │                  │        │
│  │     Email        │  │    LinkedIn      │        │
│  │                  │  │                  │        │
│  │ tamara@email.com │  │ /in/tamarapalma  │        │
│  │                  │  │                  │        │
│  │ [Copiar email]   │  │ [Ver perfil]     │        │
│  └──────────────────┘  └──────────────────┘        │
│                                                     │
└─────────────────────────────────────────────────────┘
```

**Copy Interaction:**
```javascript
// Click on email card
- Copiar al portapapeles
- Mostrar tooltip: "¡Email copiado!"
- Cambiar icono temporalmente a ✓
```

---

## Variantes de Componentes

### Buttons

| Variante | Default | Hover | Active |
|----------|---------|-------|--------|
| **Primary** | Outline cyan | Filled cyan + glow | Darken 10% |
| **Secondary** | Filled dark | Lighter background | Pressed |
| **Ghost** | Transparent | Background subtle | Background visible |

### Cards

| Variante | Uso | Sombra |
|----------|-----|--------|
| **Default** | Contenido general | None |
| **Elevated** | Hover states | Shadow md |
| **Glass** | Profile, destacados | Backdrop blur |

### Tags/Badges

| Variante | Background | Text |
|----------|------------|------|
| **Category** | bg-tertiary | text-secondary |
| **Active** | accent-primary | bg-primary |
| **Gold** | accent-secondary (20%) | accent-secondary |

---

## Estados y Feedback

### Form States

| Estado | Border | Icon |
|--------|--------|------|
| Default | border-subtle | - |
| Focus | accent-primary | - |
| Valid | success | ✓ |
| Invalid | error | ✕ |
| Loading | border-subtle | Spinner |

### Loading States

```
Botón cargando:
┌─────────────────────┐
│  ◠ Cargando...      │  ← Spinner animado
└─────────────────────┘
```

---

## Especificaciones para Handoff

### Espaciado Consistente

```
Section padding: 80px 0 (desktop), 48px 0 (mobile)
Container max-width: 1200px
Container padding: 24px (desktop), 16px (mobile)
Card padding: 24px
Grid gap: 24px (desktop), 16px (mobile)
```

### Breakpoints

```css
/* Mobile first */
@media (min-width: 768px) { /* Tablet */ }
@media (min-width: 1024px) { /* Desktop */ }
@media (min-width: 1440px) { /* Large desktop */ }
```

### Assets Export

| Asset | Formato | Tamaño |
|-------|---------|--------|
| Tech icons | SVG | 24x24, 32x32, 48x48 |
| Avatar | PNG/WebP | 200x200, 400x400 |
| Favicon | ICO/PNG | 16x16, 32x32, 180x180 |

---

## Checklist de UI

- [ ] Todos los estados de componentes definidos
- [ ] Responsive en todos los breakpoints
- [ ] Contraste WCAG AA cumplido
- [ ] Animaciones con `prefers-reduced-motion`
- [ ] Focus states visibles
- [ ] Loading states considerados
- [ ] Error states definidos
- [ ] Iconografía consistente
