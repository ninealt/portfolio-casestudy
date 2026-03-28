# Iteraciones

## Cambios Aplicados Post-Testeo

Basado en el feedback recibido, se realizaron las siguientes mejoras al portafolio.

---

## Iteración 1: Mobile Optimization

### Problema Identificado
Texto pequeño y scroll excesivo en mobile.

### Solución

```css
/* Antes */
.tech-card {
  padding: 16px;
  font-size: 14px;
}

/* Después */
@media (max-width: 768px) {
  .tech-card {
    padding: 20px;
    font-size: 16px; /* Mejor legibilidad */
  }
  
  .tech-card__description {
    display: none; /* Reducir clutter en mobile */
  }
}
```

### Resultado
- ✅ Mejor legibilidad
- ✅ Menor scroll
- ✅ Foco en información crítica

---

## Iteración 2: Descripción de Experiencia

### Problema Identificado
Falta de detalle sobre logros en cada rol.

### Solución

```jsx
// Antes
function ExperienceItem({ title, company, period }) {
  return (
    <div className="experience__item">
      <h3>{title}</h3>
      <p>{company}</p>
      <p>{period}</p>
    </div>
  );
}

// Después
function ExperienceItem({ title, company, period, achievements, tech }) {
  return (
    <div className="experience__item">
      <h3>{title}</h3>
      <p>{company}</p>
      <p>{period}</p>
      
      <ul className="experience__achievements">
        {achievements.map((achievement, index) => (
          <li key={index}>{achievement}</li>
        ))}
      </ul>
      
      <span className="experience__tech">{tech.join(' • ')}</span>
    </div>
  );
}

// Uso
<ExperienceItem
  title="Senior Developer"
  company="iProspect"
  period="2025 - Presente"
  achievements={[
    "Lideré equipo de 3 desarrolladores frontend",
    "Reduje tiempo de carga en 40%",
    "Implementé sistema de diseño unificado"
  ]}
  tech={["React", "TypeScript", "AWS"]}
/>
```

### Resultado
- ✅ Contexto de impacto claro
- ✅ Tecnologías por proyecto
- ✅ Valor demostrable

---

## Iteración 3: Performance

### Problema Identificado
Carga lenta en conexiones débiles.

### Soluciones Aplicadas

#### 3.1 Compresión de Imágenes

| Asset | Antes | Después | Reducción |
|-------|-------|---------|-----------|
| Avatar.png | 450KB | 85KB | 81% |
| Favicon | 32KB | 4KB | 87% |
| Icons SVG | 120KB | 45KB | 62% |

**Herramienta:** TinyPNG + SVGO

#### 3.2 Lazy Loading en React

```jsx
// Antes - Carga inmediata
import { Avatar } from './components/Avatar';

// Después - Lazy loading
import { lazy, Suspense } from 'react';

const Avatar = lazy(() => import('./components/Avatar'));

function App() {
  return (
    <Suspense fallback={<div className="skeleton" />}>
      <Avatar />
    </Suspense>
  );
}
```

#### 3.3 Reduced Motion

```css
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

### Resultado
- First Contentful Paint: 2.1s → 0.8s
- Lighthouse Performance: 75 → 95

---

## Iteración 4: Navegación Mobile

### Problema Identificado
Bottom tabs no eran inmediatamente reconocibles.

### Solución

```jsx
// Antes
function TabBar() {
  return (
    <nav className="tab-bar">
      <a href="#home">🏠</a>
      <a href="#skills">⚡</a>
      <a href="#experience">💼</a>
      <a href="#contact">✉️</a>
    </nav>
  );
}

// Después
function TabBar({ activeSection }) {
  const tabs = [
    { id: 'home', icon: '🏠', label: 'Inicio' },
    { id: 'skills', icon: '⚡', label: 'Skills' },
    { id: 'experience', icon: '💼', label: 'Exp' },
    { id: 'contact', icon: '✉️', label: 'Contacto' },
  ];

  return (
    <nav className="tab-bar" aria-label="Navegación principal">
      {tabs.map((tab) => (
        <a
          key={tab.id}
          href={`#${tab.id}`}
          className={`tab-bar__item ${activeSection === tab.id ? 'active' : ''}`}
          aria-current={activeSection === tab.id ? 'page' : undefined}
        >
          <span className="tab-bar__icon" aria-hidden="true">{tab.icon}</span>
          <span className="tab-bar__label">{tab.label}</span>
        </a>
      ))}
    </nav>
  );
}
```

### Resultado
- ✅ Labels para claridad
- ✅ CTA destacado en contacto
- ✅ Mejor accesibilidad (aria-labels)

---

## Iteración 5: Features Adicionales

### 5.1 Descargar CV

```jsx
function DownloadCV() {
  return (
    <a 
      href="/assets/cv-tamara-palma.pdf" 
      download 
      className="button button--secondary"
    >
      📄 Descargar CV
    </a>
  );
}
```

**Solicitado por:** Reclutador #1

### 5.2 Toast Notifications

```jsx
import { useState, useCallback } from 'react';

function useToast() {
  const [toast, setToast] = useState(null);

  const showToast = useCallback((message) => {
    setToast(message);
    setTimeout(() => setToast(null), 3000);
  }, []);

  return { toast, showToast };
}

// Uso en componente
function ContactCard() {
  const { toast, showToast } = useToast();
  
  const handleCopy = async () => {
    await navigator.clipboard.writeText('tamara@email.com');
    showToast('✓ Email copiado al portapapeles');
  };

  return (
    <>
      <button onClick={handleCopy}>
        Copiar Email
      </button>
      {toast && <div className="toast">{toast}</div>}
    </>
  );
}
```

### 5.3 Scroll Progress Indicator

```jsx
import { useState, useEffect } from 'react';

function ScrollProgress() {
  const [progress, setProgress] = useState(0);

  useEffect(() => {
    const handleScroll = () => {
      const scrollTop = window.scrollY;
      const docHeight = document.documentElement.scrollHeight - window.innerHeight;
      const scrollPercent = (scrollTop / docHeight) * 100;
      setProgress(scrollPercent);
    };

    window.addEventListener('scroll', handleScroll);
    return () => window.removeEventListener('scroll', handleScroll);
  }, []);

  return (
    <div 
      className="progress-bar" 
      style={{ width: `${progress}%` }}
      aria-hidden="true"
    />
  );
}
```

---

## Resumen de Cambios

| Iteración | Impacto | Esfuerzo | ROI |
|-----------|---------|----------|-----|
| Mobile optimization | Alto | Medio | Alto |
| Descripción de experiencia | Alto | Medio | Alto |
| Performance | Alto | Medio | Muy alto |
| Navegación mobile | Medio | Bajo | Alto |
| Features adicionales | Medio | Bajo | Medio |

---

## Resultado Final

### Métricas Post-Iteraciones

| Métrica | Antes | Después | Mejora |
|---------|-------|---------|--------|
| Lighthouse Performance | 75 | 95 | +27% |
| Lighthouse Accessibility | 90 | 100 | +11% |
| Mobile usability | 7.5/10 | 9/10 | +20% |
| SUS Score | 82 | 87 | +6% |
| Tarea completada < 30s | 80% | 100% | +25% |

### Feedback Post-Iteraciones

> "Las mejoras notan. Ahora en mobile se ve perfecto." — Reclutador #3

> "Me encanta el detalle de los logros. Ahora entiendo mejor tu impacto." — Engineering Manager

---

## Próximas Iteraciones Consideradas

- [ ] **Blog técnico** — Compartir conocimiento (usando React Router)
- [ ] **Dark/light toggle** — Context API para tema global
- [ ] **Multilenguaje** — i18n para inglés/español
- [ ] **Analytics** — React GA o Plausible
- [ ] **Formulario de contacto** — Estado controlado con validación
