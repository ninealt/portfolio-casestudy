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

```html
<!-- Antes -->
<div class="experience__item">
  <h3>Senior Developer</h3>
  <p>iProspect</p>
  <p>2025 - Presente</p>
</div>

<!-- Después -->
<div class="experience__item">
  <h3>Senior Developer</h3>
  <p>iProspect</p>
  <p>2025 - Presente</p>
  <ul class="experience__achievements">
    <li>Lideré equipo de 3 desarrolladores frontend</li>
    <li>Reduje tiempo de carga en 40%</li>
    <li>Implementé sistema de diseño unificado</li>
  </ul>
  <span class="experience__tech">React • TypeScript • AWS</span>
</div>
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

#### 3.2 Lazy Loading

```html
<!-- Antes -->
<img src="avatar.png" alt="Tamara Palma">

<!-- Después -->
<img src="avatar.png" alt="Tamara Palma" loading="lazy">
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

```html
<!-- Antes -->
<nav class="tab-bar">
  <a href="#home">🏠</a>
  <a href="#skills">⚡</a>
  <a href="#experience">💼</a>
  <a href="#contact">✉️</a>
</nav>

<!-- Después -->
<nav class="tab-bar" aria-label="Navegación principal">
  <a href="#home" class="tab-bar__item">
    <span class="tab-bar__icon" aria-hidden="true">🏠</span>
    <span class="tab-bar__label">Inicio</span>
  </a>
  <a href="#skills" class="tab-bar__item">
    <span class="tab-bar__icon" aria-hidden="true">⚡</span>
    <span class="tab-bar__label">Skills</span>
  </a>
  <a href="#experience" class="tab-bar__item">
    <span class="tab-bar__icon" aria-hidden="true">💼</span>
    <span class="tab-bar__label">Exp</span>
  </a>
  <a href="#contact" class="tab-bar__item tab-bar__item--cta">
    <span class="tab-bar__icon" aria-hidden="true">✉️</span>
    <span class="tab-bar__label">Contacto</span>
  </a>
</nav>
```

### Resultado
- ✅ Labels para claridad
- ✅ CTA destacado en contacto
- ✅ Mejor accesibilidad (aria-labels)

---

## Iteración 5: Features Adicionales

### 5.1 Descargar CV

```html
<a href="assets/cv-tamara-palma.pdf" download class="button button--secondary">
  📄 Descargar CV
</a>
```

**Solicitado por:** Reclutador #1

### 5.2 Toast Notifications

```javascript
// Feedback al copiar email
function showToast(message) {
  const toast = document.createElement('div');
  toast.className = 'toast';
  toast.textContent = message;
  document.body.appendChild(toast);
  
  setTimeout(() => toast.remove(), 3000);
}

// Uso
showToast('✓ Email copiado al portapapeles');
```

### 5.3 Scroll Progress Indicator

```css
.progress-bar {
  position: fixed;
  top: 0;
  left: 0;
  height: 3px;
  background: var(--accent-primary);
  z-index: 1001;
  transition: width 0.1s;
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

- [ ] **Blog técnico** — Compartir conocimiento
- [ ] **Dark/light toggle** — Preferencia de usuario
- [ ] **Multilenguaje** — Inglés/español
- [ ] **Analytics** — Entender comportamiento real
- [ ] **Formulario de contacto** — Sin salir del sitio
