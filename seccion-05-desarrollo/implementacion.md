# Implementación

## Estructura React

### main.jsx — Punto de Entrada

```jsx
import React from 'react'
import ReactDOM from 'react-dom/client'
import App from './App.jsx'
import './styles/global.css'

ReactDOM.createRoot(document.getElementById('root')).render(
  <React.StrictMode>
    <App />
  </React.StrictMode>,
)
```

---

### App.jsx — Componente Raíz

```jsx
import { useState, useEffect } from 'react'
import Header from './components/Header'
import Sidebar from './components/Sidebar'
import HeroSection from './sections/HeroSection'
import SkillsSection from './sections/SkillsSection'
import ExperienceSection from './sections/ExperienceSection'
import EducationSection from './sections/EducationSection'
import ContactSection from './sections/ContactSection'
import TabBar from './components/TabBar'
import './styles/App.css'

function App() {
  const [activeSection, setActiveSection] = useState('home')
  const [isMobile, setIsMobile] = useState(window.innerWidth < 768)

  useEffect(() => {
    const handleResize = () => setIsMobile(window.innerWidth < 768)
    window.addEventListener('resize', handleResize)
    return () => window.removeEventListener('resize', handleResize)
  }, [])

  return (
    <div className="app">
      <Header />
      {!isMobile && <Sidebar activeSection={activeSection} />}
      
      <main className="main-content">
        <HeroSection setActiveSection={setActiveSection} />
        <SkillsSection />
        <ExperienceSection />
        <EducationSection />
        <ContactSection />
      </main>
      
      {isMobile && <TabBar activeSection={activeSection} />}
    </div>
  )
}

export default App
```

---

### Componentes Principales

#### Header.jsx

```jsx
import { useState, useEffect } from 'react'
import './Header.css'

function Header() {
  const [scrolled, setScrolled] = useState(false)

  useEffect(() => {
    const handleScroll = () => setScrolled(window.scrollY > 100)
    window.addEventListener('scroll', handleScroll)
    return () => window.removeEventListener('scroll', handleScroll)
  }, [])

  const scrollToContact = () => {
    document.getElementById('contact').scrollIntoView({ behavior: 'smooth' })
  }

  return (
    <header className={`header ${scrolled ? 'header--scrolled' : ''}`}>
      <nav className="nav" role="navigation">
        <div className="nav__logo">
          <span className="logo__icon">🎮</span>
          <span className="logo__text">Tamara Palma</span>
        </div>
        <button 
          className="nav__cta" 
          onClick={scrollToContact}
          aria-label="Contactar"
        >
          Contactar
          <span className="cta__arrow" aria-hidden="true">→</span>
        </button>
      </nav>
    </header>
  )
}

export default Header
```

#### HeroSection.jsx

```jsx
import ProfileCard from '../components/ProfileCard'
import './HeroSection.css'

function HeroSection({ setActiveSection }) {
  const techStack = [
    { name: 'React', icon: '⚛️' },
    { name: 'Python', icon: '🐍' },
    { name: 'Node.js', icon: '⬢' },
    { name: 'Figma', icon: '📐' },
  ]

  return (
    <section className="hero" id="home" aria-labelledby="hero-title">
      <div className="container">
        <div className="hero__content">
          <h1 id="hero-title" className="hero__title">
            Tamara Palma
          </h1>
          <p className="hero__tagline">
            Full Stack Developer & UX Designer
          </p>
          
          <div className="hero__stack" aria-label="Stack tecnológico">
            {techStack.map((tech) => (
              <span key={tech.name} className="hero__tech" title={tech.name}>
                {tech.icon}
              </span>
            ))}
          </div>
          
          <button 
            className="hero__cta"
            onClick={() => document.getElementById('contact').scrollIntoView({ behavior: 'smooth' })}
          >
            Iniciar Contacto
            <span aria-hidden="true">→</span>
          </button>
        </div>
        
        <ProfileCard />
      </div>
    </section>
  )
}

export default HeroSection
```

#### ProfileCard.jsx

```jsx
import './ProfileCard.css'

function ProfileCard() {
  const skills = [
    { name: 'React', level: 80 },
    { name: 'Python', level: 90 },
    { name: 'UX Design', level: 75 },
  ]

  return (
    <div className="profile-card">
      <div className="profile-card__avatar">
        <div className="avatar__placeholder">👤</div>
      </div>
      
      <h3 className="profile-card__title">Full Stack Developer</h3>
      <p className="profile-card__level">Level 5</p>
      
      <div className="profile-card__skills">
        {skills.map((skill) => (
          <div key={skill.name} className="skill">
            <span className="skill__name">{skill.name}</span>
            <div className="skill-bar">
              <div 
                className="skill-bar__fill" 
                style={{ width: `${skill.level}%` }}
              />
            </div>
          </div>
        ))}
      </div>
      
      <div className="profile-card__status">
        <span className="status__indicator">🟢</span>
        <span className="status__text">Available for quests</span>
      </div>
      
      <div className="profile-card__location">
        <span>📍</span>
        <span>Remote from Quillota</span>
      </div>
    </div>
  )
}

export default ProfileCard
```

---

### CSS con Variables

#### variables.css

```css
:root {
  /* Colors */
  --bg-primary: #1a1a1a;
  --bg-secondary: #2d2d2d;
  --bg-tertiary: #3d3d3d;
  
  --accent-primary: #00d4ff;
  --accent-secondary: #ffd700;
  
  --text-primary: #ffffff;
  --text-secondary: rgba(255, 255, 255, 0.6);
  --text-tertiary: rgba(255, 255, 255, 0.38);
  
  --border-subtle: rgba(255, 255, 255, 0.12);
  
  /* Spacing */
  --space-1: 4px;
  --space-2: 8px;
  --space-3: 12px;
  --space-4: 16px;
  --space-5: 24px;
  --space-6: 32px;
  --space-7: 48px;
  --space-8: 64px;
  
  /* Typography */
  --font-primary: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
  
  --text-display: 72px;
  --text-h1: 48px;
  --text-h2: 32px;
  --text-h3: 24px;
  --text-body: 16px;
  --text-small: 14px;
  
  /* Radius */
  --radius-sm: 4px;
  --radius-md: 8px;
  --radius-lg: 12px;
  --radius-xl: 16px;
  
  /* Shadows */
  --shadow-sm: 0 1px 2px rgba(0, 0, 0, 0.3);
  --shadow-md: 0 4px 6px rgba(0, 0, 0, 0.4);
  --shadow-glow: 0 0 20px rgba(0, 212, 255, 0.3);
  
  /* Transitions */
  --transition-fast: 150ms ease;
  --transition-base: 250ms ease;
}

/* Responsive font sizes */
@media (max-width: 768px) {
  :root {
    --text-display: 40px;
    --text-h1: 32px;
    --text-h2: 24px;
  }
}
```

#### global.css

```css
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap');
@import './variables.css';

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

html {
  scroll-behavior: smooth;
}

body {
  font-family: var(--font-primary);
  font-size: var(--text-body);
  line-height: 1.6;
  color: var(--text-primary);
  background-color: var(--bg-primary);
}

/* Skip link for accessibility */
.skip-link {
  position: absolute;
  top: -40px;
  left: 0;
  background: var(--accent-primary);
  color: var(--bg-primary);
  padding: 8px;
  text-decoration: none;
  z-index: 100;
}

.skip-link:focus {
  top: 0;
}

/* Container */
.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 var(--space-5);
}

/* Reduced motion */
@media (prefers-reduced-motion: reduce) {
  *,
  *::before,
  *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
  }
}
```

---

### Hooks Personalizados

#### useClipboard.js

```javascript
import { useState, useCallback } from 'react'

export function useClipboard(timeout = 2000) {
  const [copied, setCopied] = useState(false)

  const copy = useCallback(async (text) => {
    try {
      await navigator.clipboard.writeText(text)
      setCopied(true)
      setTimeout(() => setCopied(false), timeout)
      return true
    } catch (err) {
      console.error('Error al copiar:', err)
      return false
    }
  }, [timeout])

  return { copied, copy }
}
```

#### useIntersectionObserver.js

```javascript
import { useEffect, useRef, useState } from 'react'

export function useIntersectionObserver(options = {}) {
  const [isIntersecting, setIsIntersecting] = useState(false)
  const ref = useRef(null)

  useEffect(() => {
    const observer = new IntersectionObserver(([entry]) => {
      setIsIntersecting(entry.isIntersecting)
    }, options)

    if (ref.current) {
      observer.observe(ref.current)
    }

    return () => observer.disconnect()
  }, [options])

  return [ref, isIntersecting]
}
```

---

### vite.config.js

```javascript
import { defineConfig } from 'vite'
import react from '@vitejs/plugin-react'

export default defineConfig({
  plugins: [react()],
  server: {
    port: 3000,
    open: true,
  },
  build: {
    outDir: 'dist',
    sourcemap: true,
    rollupOptions: {
      output: {
        manualChunks: {
          vendor: ['react', 'react-dom'],
        },
      },
    },
  },
})
```

---

## Funcionalidades Implementadas

### ✅ Completadas

- [x] Estructura React con componentes modulares
- [x] Hooks personalizados (clipboard, scroll, observer)
- [x] CSS con variables y responsive design
- [x] Navegación smooth scroll
- [x] Animaciones con Intersection Observer
- [x] Copiar al portapapeles
- [x] Mobile-first responsive
- [x] SEO meta tags
- [x] Accesibilidad (ARIA, keyboard nav)
- [x] Reduced motion support

### 🚧 Mejoras Futuras

- [ ] Dark/light mode toggle con Context API
- [ ] Service Worker para offline
- [ ] Lazy loading de secciones
- [ ] Contact form con validación
- [ ] Analytics con React GA
