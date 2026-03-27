# Sistema de Diseño

## Fundamentos

Este sistema de diseño define los cimientos visuales del portafolio, asegurando consistencia, accesibilidad y diferenciación.

---

## Sistema de Color

### Paleta Principal

```css
/* Backgrounds */
--bg-primary: #1a1a1a;        /* Dark base - fondo principal */
--bg-secondary: #2d2d2d;      /* Elevated surfaces - cards, secciones */
--bg-tertiary: #3d3d3d;       /* Hover states */

/* Accents */
--accent-primary: #00d4ff;    /* Cyan - Tech, Moderno, Energía */
--accent-secondary: #ffd700;  /* Gold - Premium, Destacado, Éxito */

/* Text */
--text-primary: #ffffff;      /* 100% white - títulos */
--text-secondary: rgba(255,255,255,0.6);  /* 60% white - body */
--text-tertiary: rgba(255,255,255,0.38);  /* 38% white - captions */

/* Utility */
--border-subtle: rgba(255,255,255,0.12);
--success: #4ade80;
--warning: #fbbf24;
--error: #f87171;
```

### Visualización de Paleta

```
┌─────────────────────────────────────────────────────────────┐
│ BACKGROUNDS                                                 │
│                                                             │
│ ┌──────────────┐  ┌──────────────┐  ┌──────────────┐       │
│ │              │  │              │  │              │       │
│ │   #1a1a1a    │  │   #2d2d2d    │  │   #3d3d3d    │       │
│ │    Base      │  │   Elevated   │  │    Hover     │       │
│ │              │  │              │  │              │       │
│ └──────────────┘  └──────────────┘  └──────────────┘       │
│                                                             │
├─────────────────────────────────────────────────────────────┤
│ ACCENTS                                                     │
│                                                             │
│ ┌──────────────────────┐  ┌──────────────────────┐         │
│ │                      │  │                      │         │
│ │      #00d4ff         │  │      #ffd700         │         │
│ │       Cyan           │  │       Gold           │         │
│ │   Tech, Moderno      │  │  Premium, Éxito      │         │
│ │                      │  │                      │         │
│ └──────────────────────┘  └──────────────────────┘         │
│                                                             │
├─────────────────────────────────────────────────────────────┤
│ TEXT                                                        │
│                                                             │
│ ████████████ 100%  Primary     - Títulos                    │
│ ██████░░░░░░  60%  Secondary   - Body                       │
│ ███░░░░░░░░░  38%  Tertiary    - Captions, hints            │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### Rationale del Color

| Color | Justificación |
|-------|---------------|
| **Dark theme (#1a1a1a)** | Moderno, reduce fatiga, destaca contenido, trending en tech |
| **Cyan (#00d4ff)** | Asociado con tecnología, innovación, energía, contraste óptimo en oscuro |
| **Gold (#ffd700)** | Jerarquiza información crítica, añade calidez, destaca logros |

---

## Tipografía

### Font Stack

```css
/* Primary font family */
font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;

/* Monospace for code/technical text */
font-family: 'Fira Code', 'SF Mono', Monaco, monospace;
```

### Escala Tipográfica

| Elemento | Tamaño | Weight | Line Height | Usage |
|----------|--------|--------|-------------|-------|
| Display | 72px | 700 | 1.1 | Hero name |
| H1 | 48px | 700 | 1.2 | Section titles |
| H2 | 32px | 600 | 1.3 | Subsection titles |
| H3 | 24px | 600 | 1.4 | Card titles |
| H4 | 20px | 600 | 1.4 | Subtitles |
| Body Large | 18px | 400 | 1.6 | Lead paragraphs |
| Body | 16px | 400 | 1.6 | General text |
| Small | 14px | 400 | 1.5 | Secondary text |
| Caption | 12px | 500 | 1.4 | Labels, tags |

### Visualización

```
Display   - TAMARA PALMA (72px, Bold)
H1        - Sección Título (48px, Bold)
H2        - Subsección Título (32px, Semibold)
H3        - Card Title (24px, Semibold)
Body      - Párrafo de contenido general (16px, Regular)
Small     - Texto secundario (14px, Regular)
Caption   - LABEL TAG (12px, Medium)
```

### Rationale Tipográfico

- **Inter:** Legibilidad óptima en pantallas, diseñada específicamente para UI
- **System fonts fallback:** Performance, carga instantánea
- **Scale jerárquico:** Ratio de 1.25 (major third) para armonía visual

---

## Espaciado y Grid

### Sistema de 8px

```css
/* Spacing scale */
--space-1: 4px;
--space-2: 8px;      /* Base unit */
--space-3: 12px;
--space-4: 16px;
--space-5: 24px;
--space-6: 32px;
--space-7: 48px;
--space-8: 64px;
--space-9: 96px;
--space-10: 128px;
```

### Grid System

```
Desktop (> 1024px):
┌──────────────────────────────────────────────────────────────┐
│ Margin: 24px                                                 │
│  ┌──────────────────────────────────────────────────────┐    │
│  │             Container: 1200px max                    │    │
│  │  ┌────┬────┬────┬────┬────┬────┬────┬────┬────┬────┬─┐ │    │
│  │  │ 1  │ 2  │ 3  │ 4  │ 5  │ 6  │ 7  │ 8  │ 9  │ 10 │11│12│ │    │
│  │  └────┴────┴────┴────┴────┴────┴────┴────┴────┴────┴─┘ │    │
│  │  Gutter: 24px                                        │    │
│  └──────────────────────────────────────────────────────┘    │
└──────────────────────────────────────────────────────────────┘

Tablet (768px - 1024px):
- 8 columns
- Gutter: 16px
- Margin: 16px

Mobile (< 768px):
- 4 columns
- Gutter: 16px
- Margin: 16px
```

### Padding por Componente

| Componente | Padding |
|------------|---------|
| Cards | 24px |
| Buttons | 12px 24px |
| Section containers | 48px 0 |
| Input fields | 12px 16px |

---

## Sistema de Componentes

### 1. Navigation Header

```
┌─────────────────────────────────────────────────────┐
│ [Logo]                          [Contacto ▶]        │
│ Fixed, 64px height                                  │
│ Background: bg-primary with 80% opacity + blur      │
└─────────────────────────────────────────────────────┘
```

**Props:**
- Position: Fixed top
- Z-index: 1000
- Background: `rgba(26, 26, 26, 0.8)` + `backdrop-filter: blur(12px)`

**Estados:**
- Default: Semi-transparente
- Scrolled: Opacidad aumentada

---

### 2. Sidebar Navigation

```
┌──────────┐
│ [Avatar] │
│  Tamara  │
│  Palma   │
├──────────┤
│    🏠    │ Home
│    ⚡    │ Skills
│    💼    │ Exp
│    🎓    │ Edu
│    ✉️    │ Contact
└──────────┘
Width: 240px
Fixed left
```

**Interacciones:**
- Hover: Background highlight
- Active: Accent border left

---

### 3. Hero Card (Profile Card)

```
┌─────────────────────────────┐
│  ┌────┐                     │
│  │ 👤 │  Full Stack Lv.5    │
│  └────┘                     │
│                             │
│  React    [████░░░░░] 80%   │
│  Python   [██████░░░] 90%   │
│  UX       [████░░░░░] 75%   │
│                             │
│  🟢 Disponible para quests  │
│  📍 Remoto desde Quillota   │
└─────────────────────────────┘
Background: bg-secondary
Border: 1px solid border-subtle
Border-radius: 12px
```

**Features:**
- Glassmorphism effect
- Skill progress bars
- Status indicator

---

### 4. Tech Stack Cards

```
┌───────────────────────┐
│ [BADGE: LENGUAJE]     │
│                       │
│        ⚛️             │
│                       │
│       React           │
│   Librería UI         │
│                       │
└───────────────────────┘

Hover state:
- Border: accent-primary
- Elevation: +4px
- Scale: 1.02
```

**Props:**
- Category badge: Language, Framework, Runtime, Tool
- Icon: SVG tech logo
- Name: Technology name
- Description: Brief tagline

---

### 5. Timeline Items

```
●───────────────────────────────
│
│  2025 - PRESENTE
│  Senior Developer
│  🏦 iProspect
│  Descripción del rol...
│
●
│
│  2023 - 2024
│  Full Stack Developer  
│  🏦 Banco Bice
│  Descripción del rol...
│
●
```

**Features:**
- Dot indicator con línea conectora
- Badge de fechas
- Empresa destacada en gold
- Descripción colapsable

**Hover:**
- Elevation
- Border highlight

---

### 6. Education Cards

```
┌──────────────────────────┐
│ [BADGE: DESARROLLO]      │
│                          │
│    2025 - 2026           │
│                          │
│  🎓 Diseño UI/UX         │
│     Universidad X        │
│                          │
│  Especialización en...   │
│                          │
└──────────────────────────┘
```

**Props:**
- Badge category: Diseño, Desarrollo, Grado
- Date range
- Institution icon
- Title
- Institution name
- Description

---

### 7. Contact Cards

```
┌──────────────────────────┐
│ [CANAL]                  │
│                          │
│         ✉️               │
│                          │
│        Email             │
│   tamara@email.com       │
│                          │
│   Click para copiar      │
│                          │
└──────────────────────────┘

Active state:
- Background: accent-primary
- Text: bg-primary
- Checkmark animation
```

**Interacción:**
- Click → Copy to clipboard
- Feedback visual inmediato

---

### 8. CTA Button

```
Default:        Hover:          Active:
┌──────────┐    ┌──────────┐    ┌──────────┐
│ Contacto │    │ Contacto │    │ Contacto │
│    ▶     │    │    ▶     │    │    ▶     │
└──────────┘    └──────────┘    └──────────┘
Outline         Filled          Pressed
accent          accent          darken 10%
```

**Props:**
- Size: Default / Large
- Variant: Primary / Secondary / Ghost
- Icon: Optional arrow/icon

---

## Tokens de Diseño

### Border Radius

```css
--radius-sm: 4px;    /* Buttons, inputs */
--radius-md: 8px;    /* Cards, containers */
--radius-lg: 12px;   /* Modals, large cards */
--radius-xl: 16px;   /* Hero elements */
--radius-full: 9999px; /* Pills, avatars */
```

### Sombras

```css
--shadow-sm: 0 1px 2px rgba(0,0,0,0.3);
--shadow-md: 0 4px 6px rgba(0,0,0,0.4);
--shadow-lg: 0 10px 15px rgba(0,0,0,0.5);
--shadow-glow: 0 0 20px rgba(0,212,255,0.3); /* Cyan glow */
```

### Transiciones

```css
--transition-fast: 150ms ease;
--transition-base: 250ms ease;
--transition-slow: 350ms ease;
```

---

## Accesibilidad

### Contraste

| Elemento | Ratio | Cumple |
|----------|-------|--------|
| White on #1a1a1a | 16.1:1 | ✅ AAA |
| Cyan on #1a1a1a | 8.2:1 | ✅ AAA |
| Gold on #1a1a1a | 10.4:1 | ✅ AAA |
| 60% white on #1a1a1a | 7.2:1 | ✅ AA |

### Focus States

```css
:focus-visible {
  outline: 2px solid var(--accent-primary);
  outline-offset: 2px;
}
```

### Motion

```css
@media (prefers-reduced-motion: reduce) {
  * {
    animation-duration: 0.01ms !important;
    transition-duration: 0.01ms !important;
  }
}
```
