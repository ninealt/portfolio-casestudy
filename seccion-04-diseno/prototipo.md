# Prototipo Figma

## Navegación e Interacciones

El prototipo en Figma permite validar el flujo de usuario y las interacciones antes del desarrollo.

***

## Estructura del Prototipo

### Páginas en Figma

```
📁 Figma File: Portafolio Tamara Palma
│
├── 📄 Cover
│   └── Thumbnail del proyecto
│
├── 📄 Design System
│   ├── Paleta de colores
│   ├── Tipografía
│   ├── Componentes
│   └── Iconos
│
├── 📄 Wireframes
│   └── Iteraciones iniciales
│
├── 📄 Desktop - Home
│   └── Pantalla principal desktop
│
├── 📄 Desktop - Scroll States
│   └── Estados de scroll
│
├── 📄 Mobile - Home
│   └── Pantalla principal mobile
│
└── 📄 Prototype Flows
    └── Flujos navegables
```

***

## Flujos de Prototipo

link figma: [url](https://www.figma.com/design/uimTgFiB48cUfT29eEXYDl/CV-F?m=auto\&t=OeNeZt0bioZpINB7-1)

### Flow 1: Recorrido Completo (Desktop)

<figure><img src="../.gitbook/assets/Captura de pantalla 2026-03-27 a las 9.47.45 p.m..png" alt=""><figcaption></figcaption></figure>

**Interacciones:**

* Scroll suave entre secciones
* Hover effects en cards
* Click en email → estado "copiado"
* Nav sidebar → scroll to section

### Flow 2: Validación Rápida (Desktop)

```
[Start] → Hero → Skills → Contact
            ↓       ↓         ↓
         Ver stack  Confirma  Copia email
         principal  skills    ↓
                              [Shortlist]
```

**Duración estimada:** 15-20 segundos

### Flow 3: Mobile Experience

```
[Start] → Hero → Tab Skills → Tab Experience → Tab Contact
            ↓         ↓             ↓              ↓
         Scroll   Accordion     Timeline       Email CTA
         down     expand        scroll         ↓
                                                 [Copied!]
```

***

## Interacciones Detalladas

### Navegación

| Acción       | Trigger        | Respuesta                |
| ------------ | -------------- | ------------------------ |
| Ir a sección | Click nav item | Smooth scroll a sección  |
| Hover nav    | Mouse over     | Background highlight     |
| Active nav   | En sección     | Border left + text cyan  |
| Mobile tab   | Click tab      | Cambio de sección activa |

### Cards

| Acción     | Trigger      | Respuesta                |
| ---------- | ------------ | ------------------------ |
| Hover card | Mouse over   | Lift + border glow       |
| Click card | Click        | Link a proyecto/detalles |
| Accordion  | Click header | Expand/colapse content   |

### Botones

| Acción     | Trigger    | Respuesta                       |
| ---------- | ---------- | ------------------------------- |
| Hover CTA  | Mouse over | Fill + glow + arrow move        |
| Click CTA  | Click      | Ripple effect + navigate        |
| Copy email | Click card | Copia al portapapeles + tooltip |

### Timeline

| Acción           | Trigger    | Respuesta             |
| ---------------- | ---------- | --------------------- |
| Scroll into view | Scroll     | Draw line animation   |
| Hover item       | Mouse over | Highlight + elevation |

***

## Especificaciones para Handoff

### Documentación en Figma

```
Cada componente incluye:
├── 🔤 Nombre semántico
├── 📏 Especificaciones (spacing, sizing)
├── 🎨 Estilos aplicados
├── ♿ Notas de accesibilidad
└── 🔗 Links a variantes
```

### Modo Dev en Figma

* **Inspect mode:** CSS, iOS, Android code
* **Assets:** Exportables en 1x, 2x, 3x
* **Comments:** Anotaciones para desarrollador

***

## Links del Prototipo

### Versión Navegable

🔗 [**Ver Prototipo en Figma**](https://www.figma.com/design/uimTgFiB48cUfT29eEXYDl/CV-F?m=auto\&t=OeNeZt0bioZpINB7-1)

**Configuración:**

* Starting frame: Desktop - Home
* Flow 1: Recorrido completo
* Device: Desktop (1440x900)

### Versión Mobile

🔗 [**Ver Prototipo Mobile**](https://33-orpin-one.vercel.app/)

**Configuración:**

* Starting frame: Mobile - Home
* Flow: Mobile experience
* Device: iPhone 14 Pro (393x852)

***

## Testing del Prototipo

### Escenarios de Test

#### Escenario 1: Roberto (Reclutador)

**Tarea:** Encuentra el stack tecnológico y contacta al candidato.

**Pasos esperados:**

1. Abre prototipo
2. Ve stack en hero (React, Python)
3. Explora skills si necesita detalle
4. Click en contacto
5. Copia email

**Éxito:** Completa en < 30 segundos.

#### Escenario 2: Usuario Curioso

**Tarea:** Explora todo el portafolio.

**Pasos esperados:**

1. Navega por todas las secciones
2. Interactúa con cards
3. Revisa timeline
4. Valora diseño

**Éxito:** Encuentra información completa sin frustración.

***

## Iteraciones del Prototipo

### v1.0 - Estructura base

* Wireframes interactivos
* Navegación básica

### v1.1 - Visual design

* Aplicación de color
* Tipografía real

### v1.2 - Interacciones

* Hover states
* Animaciones

### v1.3 - Responsive

* Versión mobile
* Adaptaciones

### v2.0 - Final

* Polish completo
* Listo para dev handoff
