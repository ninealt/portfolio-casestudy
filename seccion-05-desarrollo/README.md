# Sección 5: Desarrollo Web

## De Figma a React

Esta sección documenta la implementación técnica del portafolio usando **React 19 + Vite**, desde la estructura de componentes hasta el deployment en producción.

---

## Stack Tecnológico

| Categoría | Tecnología | Justificación |
|-----------|------------|---------------|
| **Framework** | React 19 | Componentes reutilizables, estado moderno |
| **Build Tool** | Vite 8 | Hot reload rápido, builds optimizadas |
| **Lenguaje** | JavaScript ES6+ | Sintaxis moderna, módulos nativos |
| **Estilos** | CSS3 | Vanilla CSS con variables custom |
| **Linting** | ESLint 9 | Calidad de código consistente |
| **Deploy** | GitHub Pages / Netlify | Gratuito, confiable |

---

## Estructura del Proyecto

```
cv-react/
│
├── src/
│   ├── components/     ← Componentes React reutilizables
│   ├── sections/       ← Secciones del portafolio (Hero, Skills, etc.)
│   ├── hooks/          ← Custom hooks (useScroll, useClipboard, etc.)
│   ├── styles/         ← CSS global y variables
│   ├── utils/          ← Funciones auxiliares
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

## Scripts de Desarrollo

```bash
npm run dev      # Servidor de desarrollo con HMR
npm run build    # Build optimizado para producción
npm run preview  # Preview del build local
npm run lint     # Revisar código con ESLint
```

---

## Contenido de esta Sección

- **Stack Técnico** — Tecnologías y herramientas
- **Implementación** — Componentes React y código
- **Despliegue** — Publicación online
