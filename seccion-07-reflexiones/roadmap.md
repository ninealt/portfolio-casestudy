# Roadmap Futuro

## Próximos Pasos

El portafolio es un producto vivo. Estas son las mejoras planificadas para el futuro.

---

## Fase 1: Mejoras Inmediatas (1-2 meses)

### 1.1 Blog Técnico

**Objetivo:** Compartir conocimiento y demostrar expertise.

```
Estructura propuesta:
/blog
  ├── /introduccion-a-react-hooks
  ├── /diseno-para-developers
  ├── /optimizacion-web-performance
  └── /mi-experiencia-con-ux-research
```

**Implementación con React Router:**
```jsx
import { BrowserRouter, Routes, Route } from 'react-router-dom';

function App() {
  return (
    <BrowserRouter>
      <Routes>
        <Route path="/" element={<Home />} />
        <Route path="/blog" element={<Blog />} />
        <Route path="/blog/:slug" element={<BlogPost />} />
      </Routes>
    </BrowserRouter>
  );
}
```

**Beneficios:**
- SEO mejorado
- Posicionamiento como experta
- Contenido para compartir

---

### 1.2 Dark/Light Mode Toggle

**Objetivo:** Respetar preferencia del usuario.

```jsx
// ThemeContext.js
import { createContext, useContext, useState, useEffect } from 'react';

const ThemeContext = createContext();

export function ThemeProvider({ children }) {
  const [theme, setTheme] = useState(() => {
    return localStorage.getItem('theme') || 
           (window.matchMedia('(prefers-color-scheme: dark)').matches ? 'dark' : 'light');
  });

  useEffect(() => {
    document.documentElement.setAttribute('data-theme', theme);
    localStorage.setItem('theme', theme);
  }, [theme]);

  const toggleTheme = () => setTheme(prev => prev === 'dark' ? 'light' : 'dark');

  return (
    <ThemeContext.Provider value={{ theme, toggleTheme }}>
      {children}
    </ThemeContext.Provider>
  );
}

export const useTheme = () => useContext(ThemeContext);

// Uso en componente
function ThemeToggle() {
  const { theme, toggleTheme } = useTheme();
  
  return (
    <button onClick={toggleTheme} aria-label="Cambiar tema">
      {theme === 'dark' ? '🌙' : '☀️'}
    </button>
  );
}
```

**Criterios:**
- [ ] Detectar preferencia del sistema
- [ ] Toggle manual accesible
- [ ] Persistir selección (localStorage)
- [ ] Transición suave entre temas

---

### 1.3 Multilenguaje (ES/EN)

**Objetivo:** Alcanzar mercado internacional.

```
/es  →  Versión actual
/en  →  English version
```

**Implementación con React i18n:**
```jsx
import { useTranslation } from 'react-i18next';

function HeroSection() {
  const { t, i18n } = useTranslation();
  
  return (
    <section className="hero">
      <h1>{t('hero.name')}</h1>
      <p>{t('hero.tagline')}</p>
      
      <select onChange={(e) => i18n.changeLanguage(e.target.value)}>
        <option value="es">Español</option>
        <option value="en">English</option>
      </select>
    </section>
  );
}
```

**Estrategia:**
- JSON con strings traducidos
- Selector de idioma prominente
- URL structure para SEO

---

## Fase 2: Expansión (3-6 meses)

### 2.1 Páginas de Proyecto Detalladas

**Objetivo:** Mostrar proceso de diseño completo.

```
/proyectos
  ├── /banco-digital-redesign
  │   ├── Problema
  │   ├── Research
  │   ├── Wireframes
  │   ├── UI Design
  │   ├── Desarrollo
  │   └── Resultados
  └── /ecommerce-platform
```

**Contenido por proyecto:**
- Contexto y problema
- Proceso de research
- Wireframes y arquitectura
- UI system
- Código destacado
- Métricas de éxito

---

### 2.2 Formulario de Contacto Funcional

**Objetivo:** Reducir fricción al contactar.

```jsx
import { useState } from 'react';

function ContactForm() {
  const [formData, setFormData] = useState({ name: '', email: '', message: '' });
  const [status, setStatus] = useState('idle'); // idle | submitting | success | error

  const handleSubmit = async (e) => {
    e.preventDefault();
    setStatus('submitting');
    
    try {
      // Opción 1: Netlify Forms
      // Opción 2: Formspree
      // Opción 3: Serverless function
      await fetch('/api/contact', {
        method: 'POST',
        body: JSON.stringify(formData),
      });
      
      setStatus('success');
      setFormData({ name: '', email: '', message: '' });
    } catch (error) {
      setStatus('error');
    }
  };

  return (
    <form onSubmit={handleSubmit} className="contact-form">
      <input
        type="text"
        value={formData.name}
        onChange={(e) => setFormData({...formData, name: e.target.value})}
        placeholder="Nombre"
        required
      />
      <input
        type="email"
        value={formData.email}
        onChange={(e) => setFormData({...formData, email: e.target.value})}
        placeholder="Email"
        required
      />
      <textarea
        value={formData.message}
        onChange={(e) => setFormData({...formData, message: e.target.value})}
        placeholder="Mensaje"
        required
      />
      <button type="submit" disabled={status === 'submitting'}>
        {status === 'submitting' ? 'Enviando...' : 'Enviar mensaje'}
      </button>
      
      {status === 'success' && <p className="success">¡Mensaje enviado!</p>}
      {status === 'error' && <p className="error">Error al enviar. Intenta de nuevo.</p>}
    </form>
  );
}
```

**Backend options:**
- Netlify Forms (gratuito)
- Formspree
- Serverless function (Vercel/Netlify Functions)

---

### 2.3 Analytics y Heatmaps

**Objetivo:** Entender comportamiento real de usuarios.

| Herramienta | Uso | Costo |
|-------------|-----|-------|
| Google Analytics 4 | Métricas generales | Gratis |
| Hotjar | Heatmaps, recordings | Freemium |
| Plausible | Privacy-focused | $9/mes |

**Implementación en React:**
```jsx
// useAnalytics.js
import { useEffect } from 'react';

export function usePageView() {
  useEffect(() => {
    // Google Analytics
    gtag('event', 'page_view', {
      page_path: window.location.pathname,
    });
  }, []);
}

// Uso en cada página
function SkillsSection() {
  usePageView();
  // ...
}
```

**Métricas a trackear:**
- Páginas más visitadas
- Tiempo en página
- Click en contacto
- Scroll depth

---

## Fase 3: Innovación (6-12 meses)

### 3.1 Interacciones Avanzadas

| Feature | Tecnología | Impacto |
|---------|------------|---------|
| Scroll-based animations | GSAP + ScrollTrigger | Deleite |
| 3D elements sutiles | Three.js / CSS 3D | Diferenciador |
| Micro-interactions | Lottie | Polish |

**Ejemplo con GSAP en React:**
```jsx
import { useEffect, useRef } from 'react';
import { gsap } from 'gsap';
import { ScrollTrigger } from 'gsap/ScrollTrigger';

gsap.registerPlugin(ScrollTrigger);

function AnimatedSection() {
  const sectionRef = useRef(null);

  useEffect(() => {
    gsap.from(sectionRef.current, {
      opacity: 0,
      y: 50,
      duration: 1,
      scrollTrigger: {
        trigger: sectionRef.current,
        start: 'top 80%',
      },
    });
  }, []);

  return <section ref={sectionRef}>...</section>;
}
```

**Nota:** Mantener performance como prioridad #1.

---

### 3.2 PWA (Progressive Web App)

**Objetivo:** Experiencia app-like.

```
Features:
├── Service Worker (Vite PWA plugin)
├── Offline support
├── Add to home screen
├── Push notifications (blog)
└── App shell
```

**Implementación con Vite PWA:**
```bash
npm install vite-plugin-pwa -D
```

```javascript
// vite.config.js
import { VitePWA } from 'vite-plugin-pwa';

export default defineConfig({
  plugins: [
    react(),
    VitePWA({
      registerType: 'autoUpdate',
      manifest: {
        name: 'Tamara Palma - Portfolio',
        short_name: 'Tamara Dev',
        theme_color: '#1a1a1a',
        icons: [
          { src: '/icon-192.png', sizes: '192x192' },
          { src: '/icon-512.png', sizes: '512x512' },
        ],
      },
    }),
  ],
});
```

**Beneficios:**
- Funciona offline
- Carga instantánea en visitas repetidas
- Icono en home screen del usuario

---

### 3.3 CMS para Contenido

**Objetivo:** Actualizar sin tocar código.

**Opciones:**
- **Netlify CMS** (Git-based)
- **Contentful** (Headless CMS)
- **Notion API** (Base de datos)
- **Sanity** (CMS moderno para React)

**Ejemplo con Sanity + React:**
```jsx
import { useEffect, useState } from 'react';
import { client } from './sanityClient';

function Projects() {
  const [projects, setProjects] = useState([]);

  useEffect(() => {
    client.fetch(`*[_type == "project"]`).then(setProjects);
  }, []);

  return (
    <div className="projects">
      {projects.map(project => (
        <ProjectCard key={project._id} data={project} />
      ))}
    </div>
  );
}
```

**Casos de uso:**
- Agregar nuevos proyectos
- Actualizar experiencia laboral
- Publicar artículos de blog

---

## Priorización

### Matriz de Impacto vs Esfuerzo

```
         BAJO ESFUERZO          ALTO ESFUERZO
            │                      │
ALTO   ┌────┴────┐            ┌────┴────┐
IMPACTO│ 1. Blog │            │ 3. PWA  │
       │ 2. Tema │            │ 5. CMS  │
       │toggle   │            │         │
       └────┬────┘            └────┬────┘
            │                      │
BAJO   ┌────┴────┐            ┌────┴────┐
IMPACTO│ 4. Lottie│            │ 6. 3D  │
       │ anims    │            │ complex│
       └──────────┘            └────────┘
```

**Orden recomendado:**
1. Blog técnico (Alto impacto, bajo esfuerzo)
2. Dark/light toggle
3. Formulario de contacto
4. Analytics
5. Multilenguaje
6. Páginas de proyecto
7. PWA
8. CMS

---

## Mantenimiento Continuo

### Actualizaciones Regulares

| Frecuencia | Tarea |
|------------|-------|
| Mensual | Revisar links rotos |
| Trimestral | Actualizar experiencia |
| Semestral | Revisar performance |
| Anual | Rediseño mayor si es necesario |

### Métricas de Éxito

| KPI | Meta | Medición |
|-----|------|----------|
| Visitas mensuales | 500+ | Analytics |
| Tiempo promedio | > 2 min | Analytics |
| Contactos recibidos | 2+/mes | Email/Form |
| Ranking en búsqueda | Página 1 | Google Search |

---

## Visión a Largo Plazo

> **"Este portafolio es el punto de partida, no el destino final."**

### Objetivos 2026

- [ ] Posicionamiento como referente UX/Dev híbrido
- [ ] Blog con audiencia activa
- [ ] Al menos 3 case studies detallados
- [ ] Oportunidades inbound regulares
- [ ] Charlas/workshops basados en el proceso

### El Portafolio Evolutivo

```
v1.0 (Actual)
   └── React + Vite, one-page, componentes
   
v2.0 (6 meses)
   └── + React Router, blog, multilenguaje, tema toggle
   
v3.0 (1 año)
   └── + Páginas de proyecto, form contacto, analytics
   
v4.0 (2 años)
   └── + PWA, CMS, interacciones avanzadas con GSAP
```

---

## Conclusión del Roadmap

El portafolio actual es **suficiente para el objetivo inmediato**: conseguir oportunidades laborales.

Las mejoras futuras son **inversión a largo plazo**:
- Posicionamiento de marca personal
- Autoridad técnica
- Diferenciación sostenida

> **"El mejor portafolio no es el más complejo, es el que mejor comunica quién eres y qué puedes hacer. El resto es bonus."**
