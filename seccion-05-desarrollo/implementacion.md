# Implementación

## Estructura HTML

### index.html - Estructura Base

```html
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tamara Palma | Full Stack Developer & UX Designer</title>
    <meta name="description" content="Portafolio profesional...">
    
    <!-- Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
    
    <!-- Styles -->
    <link rel="stylesheet" href="css/styles.css">
    <link rel="stylesheet" href="css/components.css">
    <link rel="stylesheet" href="css/responsive.css">
    
    <!-- Favicon -->
    <link rel="icon" type="image/x-icon" href="assets/favicon.ico">
</head>
<body>
    <!-- Skip link for accessibility -->
    <a href="#main" class="skip-link">Saltar al contenido</a>
    
    <!-- Navigation -->
    <header class="header" role="banner">
        <nav class="nav" role="navigation" aria-label="Navegación principal">
            <div class="nav__logo">
                <span class="logo__icon">🎮</span>
                <span class="logo__text">Tamara Palma</span>
            </div>
            <button class="nav__cta" aria-label="Contactar">
                Contactar
                <span class="cta__arrow" aria-hidden="true">→</span>
            </button>
        </nav>
    </header>
    
    <!-- Sidebar (desktop) -->
    <aside class="sidebar" role="navigation" aria-label="Navegación de secciones">
        <!-- Nav items -->
    </aside>
    
    <!-- Main content -->
    <main id="main" role="main">
        
        <!-- Hero Section -->
        <section class="hero" id="home" aria-labelledby="hero-title">
            <div class="container">
                <div class="hero__content">
                    <h1 id="hero-title" class="hero__title">
                        Tamara Palma
                    </h1>
                    <p class="hero__tagline">
                        Full Stack Developer & UX Designer
                    </p>
                    <div class="hero__stack" aria-label="Stack tecnológico">
                        <!-- Tech icons -->
                    </div>
                    <button class="hero__cta">
                        Iniciar Contacto
                        <span aria-hidden="true">→</span>
                    </button>
                </div>
                
                <div class="hero__card profile-card">
                    <!-- Profile card content -->
                </div>
            </div>
        </section>
        
        <!-- Skills Section -->
        <section class="skills" id="skills" aria-labelledby="skills-title">
            <!-- Skills grid -->
        </section>
        
        <!-- Experience Section -->
        <section class="experience" id="experience" aria-labelledby="exp-title">
            <!-- Timeline -->
        </section>
        
        <!-- Education Section -->
        <section class="education" id="education" aria-labelledby="edu-title">
            <!-- Education cards -->
        </section>
        
        <!-- Contact Section -->
        <section class="contact" id="contact" aria-labelledby="contact-title">
            <!-- Contact cards -->
        </section>
        
    </main>
    
    <!-- Footer -->
    <footer class="footer" role="contentinfo">
        <!-- Copyright, social links -->
    </footer>
    
    <!-- Mobile tab bar -->
    <nav class="tab-bar" role="navigation" aria-label="Navegación móvil">
        <!-- Tab items -->
    </nav>
    
    <!-- Scripts -->
    <script src="js/main.js"></script>
</body>
</html>
```

---

## CSS Arquitectura

### styles.css - Variables y Base

```css
/* ========================================
   CSS VARIABLES (Design Tokens)
   ======================================== */
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
  --space-9: 96px;
  
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

/* ========================================
   RESET & BASE
   ======================================== */
*, *::before, *::after {
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

/* ========================================
   LAYOUT
   ======================================== */
.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 var(--space-5);
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
```

### components.css - Componentes UI

```css
/* ========================================
   HEADER
   ======================================== */
.header {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  height: 64px;
  background: rgba(26, 26, 26, 0.85);
  backdrop-filter: blur(12px);
  border-bottom: 1px solid var(--border-subtle);
  z-index: 1000;
}

.nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 100%;
  padding: 0 var(--space-5);
}

.nav__cta {
  padding: var(--space-2) var(--space-4);
  background: transparent;
  border: 1px solid var(--accent-primary);
  color: var(--accent-primary);
  border-radius: var(--radius-md);
  cursor: pointer;
  transition: all var(--transition-base);
}

.nav__cta:hover {
  background: var(--accent-primary);
  color: var(--bg-primary);
  box-shadow: var(--shadow-glow);
}

/* ========================================
   HERO SECTION
   ======================================== */
.hero {
  min-height: 100vh;
  display: flex;
  align-items: center;
  padding-top: 64px;
  background: linear-gradient(180deg, var(--bg-primary) 0%, #0f172a 100%);
}

.hero__title {
  font-size: var(--text-display);
  font-weight: 700;
  line-height: 1.1;
  background: linear-gradient(135deg, var(--text-primary), var(--accent-primary));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.hero__tagline {
  font-size: var(--text-h3);
  color: var(--text-secondary);
  margin-top: var(--space-4);
}

.hero__stack {
  display: flex;
  gap: var(--space-4);
  margin-top: var(--space-6);
}

.hero__cta {
  margin-top: var(--space-6);
  padding: var(--space-3) var(--space-6);
  font-size: var(--text-body);
  font-weight: 600;
  background: transparent;
  border: 2px solid var(--accent-primary);
  color: var(--accent-primary);
  border-radius: var(--radius-md);
  cursor: pointer;
  transition: all var(--transition-base);
}

.hero__cta:hover {
  background: var(--accent-primary);
  color: var(--bg-primary);
  transform: translateY(-2px);
  box-shadow: var(--shadow-glow);
}

/* ========================================
   PROFILE CARD
   ======================================== */
.profile-card {
  background: rgba(45, 45, 45, 0.6);
  backdrop-filter: blur(10px);
  border: 1px solid var(--border-subtle);
  border-radius: var(--radius-xl);
  padding: var(--space-6);
}

.profile-card__avatar {
  width: 100px;
  height: 100px;
  border-radius: 50%;
  background: linear-gradient(135deg, var(--accent-primary), var(--accent-secondary));
}

.skill-bar {
  height: 6px;
  background: var(--border-subtle);
  border-radius: 3px;
  overflow: hidden;
  margin-top: var(--space-2);
}

.skill-bar__fill {
  height: 100%;
  background: linear-gradient(90deg, var(--accent-primary), #00a8cc);
  border-radius: 3px;
  transition: width 1s ease;
}

/* ========================================
   TECH CARDS
   ======================================== */
.tech-card {
  background: var(--bg-secondary);
  border: 1px solid var(--border-subtle);
  border-radius: var(--radius-lg);
  padding: var(--space-5);
  text-align: center;
  transition: all var(--transition-base);
}

.tech-card:hover {
  transform: translateY(-4px);
  border-color: var(--accent-primary);
  box-shadow: var(--shadow-glow);
}

.tech-card__icon {
  font-size: 48px;
  margin-bottom: var(--space-3);
}
```

### responsive.css - Media Queries

```css
/* ========================================
   TABLET (768px - 1024px)
   ======================================== */
@media (max-width: 1024px) {
  :root {
    --text-display: 56px;
    --text-h1: 40px;
  }
  
  .sidebar {
    display: none;
  }
  
  .hero .container {
    flex-direction: column;
    text-align: center;
  }
  
  .hero__card {
    margin-top: var(--space-6);
  }
}

/* ========================================
   MOBILE (< 768px)
   ======================================== */
@media (max-width: 768px) {
  :root {
    --text-display: 40px;
    --text-h1: 32px;
    --text-h2: 24px;
  }
  
  .nav__logo {
    font-size: var(--text-small);
  }
  
  .hero__stack {
    justify-content: center;
    flex-wrap: wrap;
  }
  
  .skills__grid {
    grid-template-columns: 1fr;
  }
  
  /* Show mobile tab bar */
  .tab-bar {
    display: flex;
  }
  
  /* Hide desktop header on scroll */
  .header {
    transform: translateY(-100%);
    transition: transform var(--transition-base);
  }
  
  .header--visible {
    transform: translateY(0);
  }
}
```

---

## JavaScript

### main.js - Lógica Principal

```javascript
// ========================================
// PORTFOLIO MAIN JS
// ========================================

document.addEventListener('DOMContentLoaded', () => {
  initNavigation();
  initScrollAnimations();
  initCopyToClipboard();
  initMobileNav();
});

// ========================================
// NAVIGATION
// ========================================
function initNavigation() {
  const sections = document.querySelectorAll('section[id]');
  const navLinks = document.querySelectorAll('.nav__link');
  
  // Smooth scroll para nav links
  navLinks.forEach(link => {
    link.addEventListener('click', (e) => {
      e.preventDefault();
      const targetId = link.getAttribute('href');
      const targetSection = document.querySelector(targetId);
      
      if (targetSection) {
        targetSection.scrollIntoView({ behavior: 'smooth' });
      }
    });
  });
  
  // Active state en scroll
  window.addEventListener('scroll', () => {
    let current = '';
    
    sections.forEach(section => {
      const sectionTop = section.offsetTop;
      const sectionHeight = section.clientHeight;
      
      if (scrollY >= sectionTop - 200) {
        current = section.getAttribute('id');
      }
    });
    
    navLinks.forEach(link => {
      link.classList.remove('active');
      if (link.getAttribute('href') === `#${current}`) {
        link.classList.add('active');
      }
    });
  });
}

// ========================================
// SCROLL ANIMATIONS
// ========================================
function initScrollAnimations() {
  const observerOptions = {
    threshold: 0.1,
    rootMargin: '0px 0px -50px 0px'
  };
  
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.add('animate-in');
        observer.unobserve(entry.target);
      }
    });
  }, observerOptions);
  
  // Observar elementos a animar
  document.querySelectorAll('.tech-card, .timeline-item, .education-card')
    .forEach(el => observer.observe(el));
}

// ========================================
// COPY TO CLIPBOARD
// ========================================
function initCopyToClipboard() {
  const copyButtons = document.querySelectorAll('[data-copy]');
  
  copyButtons.forEach(btn => {
    btn.addEventListener('click', async () => {
      const text = btn.getAttribute('data-copy');
      
      try {
        await navigator.clipboard.writeText(text);
        
        // Feedback visual
        const originalText = btn.textContent;
        btn.textContent = '¡Copiado!';
        btn.classList.add('copied');
        
        setTimeout(() => {
          btn.textContent = originalText;
          btn.classList.remove('copied');
        }, 2000);
        
      } catch (err) {
        console.error('Error al copiar:', err);
      }
    });
  });
}

// ========================================
// MOBILE NAVIGATION
// ========================================
function initMobileNav() {
  const header = document.querySelector('.header');
  let lastScroll = 0;
  
  window.addEventListener('scroll', () => {
    const currentScroll = window.scrollY;
    
    // Mostrar/ocultar header en mobile
    if (currentScroll > lastScroll && currentScroll > 100) {
      header.classList.remove('header--visible');
    } else {
      header.classList.add('header--visible');
    }
    
    lastScroll = currentScroll;
  });
}
```

---

## Funcionalidades Implementadas

### ✅ Completadas

- [x] Estructura HTML semántica y accesible
- [x] CSS Grid y Flexbox layouts
- [x] Variables CSS para theming
- [x] Glassmorphism effects
- [x] Responsive design (mobile-first)
- [x] Smooth scroll navigation
- [x] Intersection Observer animations
- [x] Copy to clipboard functionality
- [x] Mobile tab navigation
- [x] SEO meta tags
- [x] Open Graph tags
- [x] Schema.org structured data

### 🚧 Mejoras Futuras

- [ ] Dark/light mode toggle
- [ ] Service Worker para offline
- [ ] Lazy loading de imágenes
- [ ] Contact form funcional
- [ ] Analytics integration
