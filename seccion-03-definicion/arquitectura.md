# Arquitectura de Información

## Estructura del Sitio

Basándome en los insights de investigación, definí la siguiente estructura optimizada para el escenario de uso del reclutador.

---

## Mapa de Sitio

```
 HOME (Hero)
   │
   ├── Nombre + Tagline
   ├── Descripción profesional
   ├── CTA principal: "Iniciar Contacto"
   └── Card de perfil (Skills, Experiencia, Estado)
   │
   ▼
 HABILIDADES
   │
   ├── Stack Tecnológico Principal (Grid 4 cols)
   │   ├── Lenguajes (Python, JS, TS, HTML/CSS)
   │   ├── Frameworks (Angular, React, Rails)
   │   └── Runtime (Node.js)
   │
   └── Herramientas Adicionales (Git, Docker, Cloud, etc.)
   │
   ▼
 EXPERIENCIA PROFESIONAL
   │
   └── Timeline Vertical
       ├── iProspect (2025-Actual)
       ├── Banco Bice (2023-2024)
       ├── Clever by Bice (2021-2023)
       ├── J.P. Morgan (2017-2018)
       └── Museo Marítimo (2018-2019)
   │
   ▼
 EDUCACIÓN
   │
   └── Grid de Formación
       ├── Diseño UI/UX (2025-2026)
       ├── Unity 2D/3D (2021-2022)
       ├── Full Stack Python (2021)
       ├── Java y .NET (2017)
       ├── Diseño (2008-2015)
       └── Pedagogía (2004-2007)
   │
   ▼
 CONTACTO
   │
   ├── Email (directo)
   ├── LinkedIn (perfil profesional)
   └── Ubicación (remoto desde Quillota)
```

---

## Principios de Arquitectura

### 1. Flujo F-Pattern

El contenido sigue el patrón de lectura natural:
- **Izquierda a derecha** (línea superior)
- **Top to bottom** (escaneo vertical)

**Aplicación:**
- Información crítica alineada izquierda
- Títulos de sección prominente
- Stack horizontal en hero

### 2. Jerarquía de 3 Niveles

```
NIVEL 1: Información Crítica
├── Nombre + Rol
├── Stack principal
└── Años de experiencia

NIVEL 2: Información Complementaria
├── Timeline de experiencia
├── Detalle de educación
└── Proyectos destacados

NIVEL 3: Información Adicional
├── Certificaciones
├── Habilidades blandas
└── Intereses
```

### 3. Navegación Fija

**Sidebar siempre accesible + Header sticky**

```
┌─────────────────────────────────────────┐
│  [LOGO]                    [CONTACTO]   │ ← Header sticky
├──────┬──────────────────────────────────┤
│      │                                  │
│ HOME │      CONTENIDO PRINCIPAL         │
│      │                                  │
│ SKIL │                                  │
│      │                                  │
│ EXP  │                                  │
│      │                                  │
│ EDU  │                                  │
│      │                                  │
│ CONTACT│                                │
│      │                                  │
└──────┴──────────────────────────────────┘
    ↑
  Sidebar fijo
```

### 4. One-Page Structure

Todo el contenido en una página con scroll suave entre secciones.

**Ventajas:**
- Flujo controlado de información
- Navegación predecible
- Performance óptimo (una sola carga)
- Mobile-friendly

### 5. Mobile-First Approach

Diseño que colapsa de manera elegante en dispositivos móviles.

**Breakpoints:**
- Mobile: < 768px
- Tablet: 768px - 1024px
- Desktop: > 1024px

---

## Priorización de Contenido

### Para Desktop (> 1024px)

| Orden | Elemento | Justificación |
|-------|----------|---------------|
| 1 | Hero con nombre + rol | Identificación inmediata |
| 2 | Stack con iconos | 78% busca esto primero |
| 3 | Timeline experiencia | Validación de nivel |
| 4 | Educación | Contexto de formación |
| 5 | Contacto prominente | Conversión |

### Para Mobile (< 768px)

| Orden | Elemento | Adaptación |
|-------|----------|------------|
| 1 | Hero compacto | Stack reducido a íconos principales |
| 2 | Skills accordion | Expandible para ahorrar espacio |
| 3 | Timeline simplificada | Solo últimos 3 roles |
| 4 | Educación resumida | Solo formación relevante |
| 5 | Sticky contact bar | Siempre accesible |

---

## Sistema de Navegación

### Desktop: Sidebar + Header

```
Sidebar (izquierda, fijo)
├── [Avatar] Tamara Palma
├── [Icon] Home
├── [Icon] Skills
├── [Icon] Experience
├── [Icon] Education
└── [Icon] Contact

Header (superior, sticky)
├── Logo/Name
└── CTA "Contactar"
```

### Mobile: Bottom Tab Bar

```
┌─────────────────────────────────┐
│                                 │
│         CONTENIDO               │
│                                 │
├─────────┬─────────┬─────────────┤
│  Home   │ Skills  │   Contact   │
│   👤    │   ⚡    │     ✉️       │
└─────────┴─────────┴─────────────┘
```

---

## SEO y Accesibilidad

### Meta-información

```html
<title>Tamara Palma | Full Stack Developer & UX Designer</title>
<meta name="description" content="Portafolio de Tamara Palma, desarrolladora Full Stack con experiencia en React, Python y diseño UI/UX. Disponible para proyectos freelance y oportunidades remotas.">
```

### Accesibilidad

- [ ] Contraste WCAG AA mínimo
- [ ] Navegación por teclado completa
- [ ] Alt text en imágenes
- [ ] Skip links para navegación
- [ ] Focus indicators visibles
- [ ] Aria labels donde corresponda

---

## Validación de Arquitectura

### Test con Escenario de Roberto

| Paso | ¿Encuentra lo que busca? | Tiempo estimado |
|------|-------------------------|-----------------|
| 1. Rol y stack | ✅ Hero inmediato | 2 seg |
| 2. Años de experiencia | ✅ En card de perfil | 3 seg |
| 3. Empresas anteriores | ✅ Timeline visible | 5 seg |
| 4. Contacto | ✅ Hero + footer | 3 seg |

**Total estimado:** ~13 segundos para decisión positiva

Esto cumple con el requisito de "30 segundos para decidir" con margen de sobra.
