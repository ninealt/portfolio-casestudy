# Wireframes

## Proceso de Iteración

### Iteración 1: Low-Fidelity Wireframes

**Objetivo:** Validar estructura y flujo de información sin distracciones visuales.

#### Características

- Bloques básicos de contenido (cajas grises)
- Jerarquía visual definida con tamaños
- Anotaciones de decisiones de diseño
- Sin color, solo estructura

#### Estructura Validada

```
┌─────────────────────────────────────────┐
│              HEADER                     │
│    [Logo]              [Contact CTA]    │
├──────┬──────────────────────────────────┤
│      │                                  │
│ NAV  │           HERO SECTION           │
│      │  ┌──────────────────────────┐    │
│ HOME │  │  Nombre                  │    │
│      │  │  "Full Stack Developer"  │    │
│ SKILL│  │                          │    │
│      │  │  [Stack Icons Row]       │    │
│ EXP  │  │  React Python Node       │    │
│      │  │                          │    │
│ EDU  │  │  [CTA Button]            │    │
│      │  └──────────────────────────┘    │
│      │                                  │
│      │  ┌──────────────────────────┐    │
│      │  │   PROFILE CARD           │    │
│      │  │   - Avatar               │    │
│      │  │   - Stats                │    │
│      │  │   - Status               │    │
│      │  └──────────────────────────┘    │
│      │                                  │
│      └──────────────────────────────────┘
│                      ▼
│           [SCROLL INDICATOR]
│                      ▼
│           SKILLS SECTION
│    ┌─────┐ ┌─────┐ ┌─────┐ ┌─────┐
│    │Lang │ │Frame│ │Runt │ │Tools│
│    │uages│ │works│ │ime  │ │     │
│    └─────┘ └─────┘ └─────┘ └─────┘
│                      ▼
│        EXPERIENCE SECTION
│    ●─────────────────────────────
│    │ 2025  iProspect
│    │       Senior Dev
│    ●
│    │
│    ● 2023  Banco Bice
│    │       Full Stack
│    ●
│                      ▼
│         EDUCATION GRID
│    ┌─────┐ ┌─────┐ ┌─────┐
│    │UI/UX│ │Unity│ │Full │
│    └─────┘ └─────┘ └─────┘
│                      ▼
│         CONTACT SECTION
│    ┌─────────┐ ┌─────────┐
│    │  Email  │ │LinkedIn │
│    └─────────┘ └─────────┘
│                      ▼
│              FOOTER
```

#### Validación de Iteración 1

**✅ Aspectos que funcionaron:**
- Estructura clara y escaneable
- Información crítica visible en hero
- Flujo lógico de arriba hacia abajo

**⚠️ Áreas de mejora identificadas:**
- Necesidad de más diferenciación visual entre secciones
- CTA podría ser más prominente
- Card de perfil necesita más jerarquía

---

### Iteración 2: Mid-Fidelity

**Ajustes realizados:**

1. **Hero más impactante**
   - Tagline más grande
   - Stack en formato visual más prominente
   - CTA de contacto con color de acento

2. **Diferenciación de secciones**
   - Headers de sección con fondo distintivo
   - Separadores visuales sutiles
   - Variaciones en layout por sección

3. **Card de perfil mejorada**
   - Stats más visibles
   - Indicador de "disponible para trabajar"
   - Skill bars para nivel de dominio

---

### Evolución a High-Fidelity

Con la estructura validada, se procedió al diseño visual completo incorporando:

- Paleta de colores dark mode + neón
- Tipografía Inter con jerarquía definida
- Espaciado de 8px system
- Componentes con estados hover/active
- Animaciones sutiles planificadas

---

## Wireframes Detallados

### Desktop Layout

```
ANCHO: 1440px (max-container: 1200px)

┌─────────────────────────────────────────────────────┐
│ MARGEN: 24px (desktop)                              │
│                                                     │
│  ┌────────────┬──────────────────────────────────┐  │
│  │            │  HEADER (fixed, 64px height)     │  │
│  │  SIDEBAR   │  [Logo]            [Contact ▶]   │  │
│  │  (240px)   ├──────────────────────────────────┤  │
│  │            │                                  │  │
│  │  [Avatar]  │  HERO SECTION                    │  │
│  │  Tamara    │                                  │  │
│  │  Palma     │  ┌────────────────────────────┐  │  │
│  │            │  │ TAMARA PALMA               │  │  │
│  │  ──────────│  │                            │  │  │
│  │            │  │ Full Stack Developer       │  │  │
│  │  [🏠] Home │  │ & UX Designer              │  │  │
│  │  [⚡] Skill│  │                            │  │  │
│  │  [💼] Exp  │  │ [⚛️] [🐍] [⬢] [📐]        │  │  │
│  │  [🎓] Edu  │  │ React Python Node Figma    │  │  │
│  │  [✉️] Cont │  │                            │  │  │
│  │            │  │ [ INICIAR CONTACTO ▶ ]     │  │  │
│  │            │  └────────────────────────────┘  │  │
│  │            │                                  │  │
│  │            │  ┌────────────────────────────┐  │  │
│  │            │  │  PROFILE CARD              │  │  │
│  │            │  │  ┌────┐                     │  │  │
│  │            │  │  │ 👤 │ Full Stack Lv.5    │  │  │
│  │            │  │  └────┘                     │  │  │
│  │            │  │  [████░░░░░] React          │  │  │
│  │            │  │  [██████░░░] Python         │  │  │
│  │            │  │  [████░░░░░] UX Design      │  │  │
│  │            │  │                             │  │  │
│  │            │  │  🟢 Disponible para quests  │  │  │
│  │            │  │  📍 Remoto desde Quillota   │  │  │
│  │            │  └────────────────────────────┘  │  │
│  │            │                                  │  │
│  └────────────┴──────────────────────────────────┘  │
│                                                     │
└─────────────────────────────────────────────────────┘
```

### Mobile Layout

```
ANCHO: 375px

┌───────────────────────────┐
│ HEADER (sticky, 56px)     │
│ [≡]  Tamara Palma  [✉️]   │
├───────────────────────────┤
│                           │
│  HERO SECTION             │
│                           │
│  TAMARA                   │
│  PALMA                    │
│                           │
│  Full Stack               │
│  Developer                │
│                           │
│  [⚛️] [🐍] [⬢]           │
│                           │
│  [ CONTÁCTAME ▶ ]         │
│                           │
│  ─────────────────────    │
│                           │
│  🟢 Disponible            │
│  📍 Remoto                │
│                           │
├───────────────────────────┤
│ SKILLS                    │
│ ┌─────────────────────┐   │
│ │ ⚛️ React    ▼       │   │
│ ├─────────────────────┤   │
│ │ 🐍 Python    ▼      │   │
│ ├─────────────────────┤   │
│ │ ⬢ Node.js    ▼      │   │
│ └─────────────────────┘   │
├───────────────────────────┤
│ EXPERIENCE                │
│ ● 2025  iProspect         │
│   Senior Developer        │
│ ● 2023  Banco Bice        │
│   Full Stack              │
│ ● 2021  Clever            │
│   Frontend                │
├───────────────────────────┤
│ CONTACT                   │
│ [ 📧 tamara@email.com ]   │
│ [ 💼 linkedin.com/in/...] │
├───────────────────────────┤
│ FOOTER                    │
│  © 2025 Tamara Palma      │
├───────────────────────────┤
│  [🏠]  [⚡]  [💼]  [✉️]   │ ← Tab bar
└───────────────────────────┘
```

---

## Anotaciones de Diseño

### Decisiones Clave

| Elemento | Decisión | Justificación |
|----------|----------|---------------|
| Sidebar fijo | Desktop only | Navegación rápida sin scroll |
| Hero prominente | 60% viewport | Primera impresión crítica |
| Card de perfil | Glassmorphism | Diferenciador visual |
| Timeline vertical | Conectores visuales | Claridad cronológica |
| Tab bar mobile | Bottom sticky | Accesibilidad táctil |
| Skills grid | 4 cols → 2 cols → 1 col | Responsive progresivo |

### Consideraciones de Contenido

1. **Hero:** Máximo 2 líneas de tagline
2. **Skills:** Máximo 4 por categoría (evitar overwhelm)
3. **Experiencia:** Últimos 5 roles máximo
4. **Educación:** Solo formación relevante al rol
5. **Contacto:** Email copiable con un click
