# Stack Técnico

## Tecnologías Utilizadas

### Frontend Core

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   HTML5  +  CSS3  +  JavaScript (ES6+)                      │
│                                                             │
│   Sin frameworks, vanilla para:                             │
│   • Performance óptimo                                      │
│   • Carga instantánea                                       │
│   • Control total del código                                │
│   • Menos dependencias                                      │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### CSS Features

| Feature | Uso | Soporte |
|---------|-----|---------|
| CSS Grid | Layout principal | > 96% |
| Flexbox | Componentes | > 99% |
| CSS Variables | Temas, tokens | > 96% |
| backdrop-filter | Glassmorphism | > 94% |
| CSS Animations | Micro-interacciones | > 98% |
| @media queries | Responsive | > 99% |

### JavaScript Features

| Feature | Uso |
|---------|-----|
| const/let | Variables modernas |
| Arrow functions | Callbacks limpios |
| Template literals | Strings dinámicos |
| querySelector | DOM selection |
| addEventListener | Event handling |
| Intersection Observer | Scroll animations |
| Clipboard API | Copy to clipboard |

---

## Herramientas de Desarrollo

### Editor
- **VS Code** con extensiones:
  - Live Server
  - Prettier
  - CSS Peek
  - Auto Rename Tag

### Version Control
```bash
# Git workflow
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/.../portfolio.git
git push -u origin main
```

### Optimización
- **Images:** TinyPNG para compresión
- **SVG:** SVGO para optimización
- **CSS:** PurgeCSS (si escalamos)

---

## Performance Targets

| Métrica | Objetivo | Cómo lograrlo |
|---------|----------|---------------|
| First Contentful Paint | < 1.5s | HTML crítico inline |
| Largest Contentful Paint | < 2.5s | Optimización de imágenes |
| Time to Interactive | < 3.5s | JS no bloqueante |
| Cumulative Layout Shift | < 0.1 | Dimensiones explícitas |
| Total Blocking Time | < 200ms | JS eficiente |

---

## Accesibilidad

### Checklist Técnico

- [x] HTML semántico (`<header>`, `<main>`, `<section>`, `<footer>`)
- [x] ARIA labels donde necesario
- [x] Contraste de color WCAG AA
- [x] Navegación por teclado completa
- [x] Focus indicators visibles
- [x] Alt text en imágenes
- [x] Skip to content link
- [x] Reduced motion support

---

## SEO

### Meta Tags

```html
<title>Tamara Palma | Full Stack Developer & UX Designer</title>
<meta name="description" content="Portafolio de Tamara Palma, desarrolladora Full Stack con experiencia en React, Python y diseño UI/UX.">
<meta name="keywords" content="Full Stack Developer, UX Designer, React, Python, JavaScript">
<meta name="author" content="Tamara Palma">

<!-- Open Graph -->
<meta property="og:title" content="Tamara Palma | Full Stack Developer">
<meta property="og:description" content="Portafolio profesional con proyectos de desarrollo y diseño.">
<meta property="og:image" content="./assets/og-image.png">
<meta property="og:url" content="https://tamarapalma.dev">

<!-- Twitter -->
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:title" content="Tamara Palma | Full Stack Developer">
<meta name="twitter:description" content="Portafolio profesional">
<meta name="twitter:image" content="./assets/og-image.png">
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
