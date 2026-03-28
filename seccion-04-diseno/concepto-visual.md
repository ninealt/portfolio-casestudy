# Concepto Visual

## "Quest Log"

### Filosofía de Diseño

> **"Un portafolio profesional con la atmósfera de un videojuego RPG, donde cada sección es una nueva área por explorar y cada habilidad es un skill desbloqueado."**

El concepto integra elementos de gamificación de manera sutil y profesional, sin caer en lo infantil o saturado. Haciendo que esto sea un viaje.

***

## Inspiración Visual

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

### Fuentes de Inspiración

| Fuente             | Elemento Adaptado                    |
| ------------------ | ------------------------------------ |
| **Cyberpunk 2077** | Neones, contrastes, futurismo        |
| **Expedition 33**  | Clasico, apocaliptico, contrastante, |
| **Nier Automata**  | Tecnico, mecanico                    |

<figure><img src="../.gitbook/assets/Captura de pantalla 2026-03-27 a las 9.34.07 p.m..png" alt=""><figcaption></figcaption></figure>

<figure><img src="../.gitbook/assets/Captura de pantalla 2026-03-27 a las 9.34.34 p.m..png" alt=""><figcaption></figcaption></figure>

### Moodboard

***

## Elementos de Gamificación (Sutiles)

### 1. Metáfora de "Quest"

| Elemento Tradicional | Versión "Quest Log"             | Implementación                        |
| -------------------- | ------------------------------- | ------------------------------------- |
| Proyectos            | Misiones completadas            | Cards con badge "Quest Completed"     |
| Habilidades          | Skills desbloqueados            | Progress bars tipo RPG                |
| Experiencia          | Nivel profesional               | "Lv. 5 Full Stack", como con la edad. |
| Disponibilidad       | Estado de "Listo para aventura" | Badge 🟢 "In duty"                    |
| Educación            | Habilidades aprendidas          | Iconos de "skill books"               |

### 2. Lenguaje Visual RPG

**En lugar de:**

* &#x20;"Experiencia laboral"
* &#x20;"Habilidades técnicas"
* &#x20;"Proyectos"

**Usar:**

* &#x20;"Quest Log"
* &#x20;"Skill Tree"
* &#x20;"Completed Quests"

**Nota:** Esta terminología se usa sutilmente, sin sacrificar claridad profesional. Por eso, se decidio mezclar ambas cosas, para que las personas que no conozcan el contexto, no se pierdan.

***

## Estética Neón + Línea Clásica

### Balance Visual

```
┌──────────────────────────────────────────────────────────┐
│                                                          │
│   ELEMENTOS NEÓN              ELEMENTOS CLÁSICOS         │
│                                                          │
│   ━━━━━━━━━━━━━━━━            ━━━━━━━━━━━━━━━━━━         │
│                                                          │
│   • Accent cyan #00d4ff       • Layout grid estricto     │
│   • Glow effects              • Tipografía Inter         │
│   • Gradients sutiles         • Espaciado consistente    │
│   • Animated elements         • Jerarquía clara          │
│   • Glassmorphism             • Contraste alto           │
│                                                          │
│   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━            │
│                    RESULTADO                             │
│                                                          │
│        Profesional + Moderno + Memorable                 │
│                                                          │
└──────────────────────────────────────────────────────────┘
```

### Aplicación de Neón

| Elemento       | Efecto         | Intensidad    |
| -------------- | -------------- | ------------- |
| CTA Button     | Glow on hover  | 30% opacity   |
| Accent borders | Static glow    | 20% opacity   |
| Active states  | Pulsing subtle | CSS animation |
| Hover cards    | Border glow    | 40% opacity   |

***

## Micro-interacciones

### Hover States

| Elemento | Efecto               | Duración |
| -------- | -------------------- | -------- |
| Cards    | Lift + border glow   | 250ms    |
| Buttons  | Fill + glow increase | 200ms    |
| Links    | Underline slide      | 150ms    |
| Icons    | Scale 1.1            | 200ms    |

### Scroll Animations

| Trigger       | Efecto              |
| ------------- | ------------------- |
| Section enter | Fade up + opacity   |
| Cards         | Staggered fade in   |
| Timeline      | Draw line animation |

***

## Responsive Adaptation

### Desktop

* Sidebar navigation visible
* Grid completo de skills (4 cols)
* Timeline completa
* Efectos neón al 100%

### Mobile

* Bottom tab navigation
* Skills en accordion (ahorro espacio)
* Timeline simplificada
* Efectos neón reducidos (performance)

***

## Assets Necesarios

### Iconos

* Tech stack (SVG, monocromáticos)
* UI icons (tabler-icons o similar)
* RPG-inspired icons sutiles

### Imágenes

* Avatar/placeholder con gradiente
* Opcional: Screenshots de proyectos

### Fuentes

* Inter (Google Fonts)
* Cinzel (Google Fonts)

***

## Decisiones Clave

### ✅ Lo que SÍ incluir

1. **Dark mode por defecto** — Moderno, reduce fatiga
2. **Acentos neón sutiles** — Diferenciador sin saturar
3. **Glassmorphism en cards** — Profundidad visual
4. **Skill bars** — Gamificación funcional
5. **Micro-animations** — Deleite sin distraer

### ❌ Lo que NO incluir

1. **Sonidos** — No apropiado para portafolio profesional, insonoro.
2. **Animaciones excesivas** — Distractor, afecta performance, animaciones para darle dinamismo.
3. **Tipografía "gaming"** — Puede parecer amateur
4. **Elementos 3D complejos** — Problemas de performance
5. **Story/narrativa larga** — El usuario quiere información rápida, condesar info
