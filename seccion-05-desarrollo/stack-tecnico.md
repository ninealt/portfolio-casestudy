# Stack Técnico

## Tecnologías Utilizadas

### Frontend Core

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   React 19 + Vite 8                                         │
│                                                             │
│   • React 19.2.4 — Framework UI moderno                     │
│   • Vite 8.0.1 — Build tool ultrarrápido                    │
│   • JavaScript ES Modules — Sintaxis moderna                │
│   • ESLint 9 — Linting y calidad de código                  │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### Dependencias Principales

| Paquete | Versión | Uso |
|---------|---------|-----|
| **react** | ^19.2.4 | Framework UI |
| **react-dom** | ^19.2.4 | Renderizado DOM |
| **vite** | ^8.0.1 | Build tool y dev server |
| **@vitejs/plugin-react** | ^6.0.1 | Soporte React para Vite |
| **eslint** | ^9.39.4 | Análisis estático de código |

---

## Scripts de Desarrollo

```bash
# Servidor de desarrollo con hot reload
npm run dev

# Build para producción (optimizado)
npm run build

# Preview del build local
npm run preview

# Revisar código con ESLint
npm run lint
```

---

## Estructura del Proyecto

```
cv-react/
├── src/
│   ├── components/     ← Componentes React reutilizables
│   │   ├── Header.jsx
│   │   ├── Sidebar.jsx
│   │   ├── Hero.jsx
│   │   ├── SkillCard.jsx
│   │   ├── Timeline.jsx
│   │   └── ContactCard.jsx
│   │
│   ├── sections/       ← Secciones principales
│   │   ├── HeroSection.jsx
│   │   ├── SkillsSection.jsx
│   │   ├── ExperienceSection.jsx
│   │   ├── EducationSection.jsx
│   │   └── ContactSection.jsx
│   │
│   ├── hooks/          ← Custom hooks
│   │   ├── useScrollPosition.js
│   │   ├── useClipboard.js
│   │   └── useIntersectionObserver.js
│   │
│   ├── styles/         ← Estilos globales
│   │   ├── global.css
│   │   ├── variables.css
│   │   └── components.css
│   │
│   ├── utils/          ← Utilidades
│   │   └── constants.js
│   │
│   ├── App.jsx         ← Componente raíz
│   └── main.jsx        ← Punto de entrada
│
├── public/             ← Assets estáticos
│   ├── images/
│   └── favicon.ico
│
├── dist/               ← Build de producción (generado)
├── index.html          ← Template HTML principal
├── vite.config.js      ← Configuración de Vite
├── package.json        ← Dependencias y scripts
└── eslint.config.js    ← Configuración de ESLint
```

---

## Características del Stack

### ⚛️ React 19
- Componentes funcionales con hooks
- JSX para templating declarativo
- Virtual DOM eficiente
- Ecosistema amplio y maduro

### ⚡ Vite
- **Hot Module Replacement (HMR)** instantáneo
- Builds optimizadas con esbuild
- Soporte nativo ES modules
- Configuración mínima
- Tiempo de build ~2s vs ~10s en CRA

### 🔧 ESLint
- Reglas recomendadas de React
- Validación de hooks (react-hooks)
- React Refresh para HMR
- Código consistente y sin errores comunes

---

## Ventajas vs HTML/Vanilla

| Aspecto | React + Vite | HTML Vanilla |
|---------|--------------|--------------|
| **Componentes** | Reutilizables, modulares | Estáticos, repetitivos |
| **Estado** | useState, useEffect | Manual con DOM |
| **Performance** | Virtual DOM optimizado | Reflows/paints costosos |
| **Developer XP** | Hot reload, debugging tools | Refresh manual |
| **Escalabilidad** | Componentes composables | Complejidad creciente |
| **Build** | Optimizado automático | Manual o ninguno |

---

## CSS en React

Aunque usamos React, los estilos son **CSS vanilla** con variables custom:

```css
/* variables.css */
:root {
  --bg-primary: #1a1a1a;
  --bg-secondary: #2d2d2d;
  --accent-primary: #00d4ff;
  --accent-secondary: #ffd700;
  --text-primary: #ffffff;
  --text-secondary: rgba(255, 255, 255, 0.6);
}
```

### Por qué no Tailwind o CSS-in-JS

| Enfoque | Decisión | Razón |
|---------|----------|-------|
| Tailwind | ❌ No usar | Menos control, más bundle |
| Styled-components | ❌ No usar | Overhead de runtime |
| CSS Modules | ✅ Opcional | Encapsulamiento sin overhead |
| Vanilla CSS | ✅ Usado | Simplicidad, performance |

---

## Performance Targets

| Métrica | Objetivo | Cómo lograrlo |
|---------|----------|---------------|
| Build time | < 2s | Vite esbuild |
| Bundle size | < 200KB | Code splitting, lazy load |
| Lighthouse Performance | > 90 | Optimización automática Vite |
| First Contentful Paint | < 1.5s | SSR no necesario para este caso |
| Time to Interactive | < 3s | Lazy loading de componentes |

---

## Accesibilidad

### En React

- **Semantic JSX** (`<header>`, `<main>`, `<section>`, `<footer>`)
- **ARIA labels** — En componentes interactivos
- **Focus management** — Con useRef y useEffect
- **Keyboard navigation** — Event listeners optimizados
- **Reduced motion** — Media query respetada

```jsx
// Ejemplo: Botón accesible
<button 
  aria-label="Copiar email al portapapeles"
  onClick={handleCopy}
  className="contact-button"
>
  Copiar Email
</button>
```

---

## SEO

### Meta Tags en index.html

```html
<title>Tamara Palma | Full Stack Developer & UX Designer</title>
<meta name="description" content="Portafolio de Tamara Palma, desarrolladora Full Stack con experiencia en React, Python y diseño UI/UX.">
<meta name="keywords" content="Full Stack Developer, UX Designer, React, Python, JavaScript">
<meta name="author" content="Tamara Palma">

<!-- Open Graph -->
<meta property="og:title" content="Tamara Palma | Full Stack Developer">
<meta property="og:description" content="Portafolio profesional con proyectos de desarrollo y diseño.">
<meta property="og:image" content="/og-image.png">
<meta property="og:url" content="https://tamarapalma.dev">

<!-- Twitter -->
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:title" content="Tamara Palma | Full Stack Developer">
<meta name="twitter:description" content="Portafolio profesional">
<meta name="twitter:image" content="/og-image.png">
```

### Structured Data

```json
{
  "@context": "https://schema.org",
  "@type": "Person",
  "name": "Tamara Palma",
  "jobTitle": "Full Stack Developer & UX Designer",
  "url": "https://tamarapalma.dev",
  "sameAs": [
    "https://linkedin.com/in/tamarapalma",
    "https://github.com/tamarapalma"
  ]
}
```

---

## Herramientas de Desarrollo

### VS Code Extensions recomendadas

- **ES7+ React/Redux/React-Native snippets** — Snippets de React
- **Auto Rename Tag** — Renombrar tags JSX automáticamente
- **CSS Peek** — Ver CSS desde JSX
- **Prettier** — Formateo consistente
- **ESLint** — Linting en tiempo real

### Chrome DevTools

- React Developer Tools — Inspeccionar componentes
- Lighthouse — Auditar performance
- Network — Analizar carga de recursos
