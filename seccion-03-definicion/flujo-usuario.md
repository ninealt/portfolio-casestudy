# Flujo de Usuario

## User Flow: Roberto (Reclutador)

Este flujo representa el recorrido óptimo del usuario objetivo principal basado en el journey map desarrollado en investigación.

***

## Flujo Ideal

INICIO

↓

LLEGA AL HERO

├─ ¿Stack tecnológico visible? → SÍ&#x20;

├─ ¿Experiencia clara? → SÍ&#x20;

├─ ¿Diseño profesional? → SÍ&#x20;

↓

EXPLORA HABILIDADES

├─ ¿Tiene React + Python? → SÍ&#x20;

├─ ¿Años de experiencia visible? → SÍ&#x20;

↓

VALIDA EXPERIENCIA

├─ ¿Empresas reconocidas? → SÍ (Bice, JP Morgan)

├─ ¿Descripción de roles? → SÍ&#x20;

↓

BUSCA CONTACTO

├─ ¿Email visible? → SÍ&#x20;

├─ ¿LinkedIn accesible? → SÍ&#x20;

↓

TOMA ACCIÓN

└─ Copia contacto / Agenda entrevista

***

## Puntos de Fricción Eliminados

### Antes → Después

| Problema             | Solución Implementada                        | Impacto                           |
| -------------------- | -------------------------------------------- | --------------------------------- |
| ❌ Navegación confusa | ✅ Sidebar fijo + Header sticky               | Acceso rápido a cualquier sección |
| ❌ Stack no visible   | ✅ Sección dedicada con iconos + Hero preview | Validación inmediata              |
| ❌ Contacto oculto    | ✅ CTA en hero + sección dedicada + footer    | 0 fricción para contactar         |
| ❌ Carga lenta        | ✅ Optimización de assets + lazy loading      | Retención de usuarios             |
| ❌ Diseño genérico    | ✅ Estética neón + dark mode distintiva       | Memorabilidad                     |

***

## Momentos de Decisión

### Momento 1: Los Primeros 3 Segundos (Hero)

**Pregunta del usuario:** _"¿Este perfil calza con lo que busco?"_

**Elementos clave:**

* Nombre prominente
* Rol claro: "Full Stack Developer & UX Designer"
* Stack principal en iconos: React, Python, Node
* Años de experiencia visible

**Resultado esperado:** Validación rápida de match básico.

***

### Momento 2: Validación Técnica (Skills)

**Pregunta del usuario:** _"¿Tiene las tecnologías que necesitamos?"_

**Elementos clave:**

* Grid de tecnologías categorizado
* Años de experiencia por stack
* Nivel de dominio (skill bars)

**Resultado esperado:** Confirmación de stack alineado.

***

### Momento 3: Validación Profesional (Experience)

**Pregunta del usuario:** _"¿Tiene experiencia relevante?"_

**Elementos clave:**

* Timeline con empresas reconocidas
* Descripción de roles y logros
* Cronología clara

**Resultado esperado:** Confianza en nivel profesional.

***

### Momento 4: Conversión (Contact)

**Pregunta del usuario:** _"¿Cómo contacto a este candidato?"_

**Elementos clave:**

* Email copiable con 1 click
* Link directo a LinkedIn
* Confirmación visual de acción

**Resultado esperado:** Contacto obtenido, candidato en shortlist.

***

## Flujos Alternativos

### Flujo B: Usuario Curioso

```
INICIO
  │
  ▼
EXPLORA TODAS LAS SECCIONES
  │
  ├── Habilidades
  ├── Experiencia
  ├── Educación
  └── Contacto
        │
        ▼
    IMPRESIÓN GLOBAL POSITIVA
```

**Perfil:** Alguien que tiene más tiempo o está genuinamente interesado.

**Diseño soporta:**

* Scroll suave entre secciones
* Información progresiva
* Detalles adicionales

***

### Flujo C: Mobile User

```
INICIO (mobile)
  │
  ▼
HERO COMPACTO
  │
  ▼
TAB NAVIGATION
  │
  ├── Skills (accordion)
  ├── Experience (timeline simplificada)
  └── Contact (sticky button)
        │
        ▼
    CONTACTO RÁPIDO
```

**Consideraciones:**

* Información condensada pero completa
* Navegación táctil optimizada
* Contacto siempre accesible

***

## Métricas de Flujo

### Objetivos KPI

| Métrica            | Objetivo      | Medición       |
| ------------------ | ------------- | -------------- |
| Tiempo a contacto  | < 30 segundos | Analytics      |
| Bounce rate        | < 40%         | Analytics      |
| Scroll depth       | > 60%         | Analytics      |
| Contact CTA clicks | > 15%         | Event tracking |

### Puntos de Abandono a Monitorear

1. **Antes de scroll:** Hero no comunica valor
2. **Sección Skills:** Stack no alineado con necesidad
3. **Timeline:** Experiencia no relevante
4. **Sin contacto visible:** Fricción final

***

## Validación del Flujo

### Test de Usuario Simulado

**Escenario:** Roberto busca Full Stack con React/Python

| Paso      | Acción            | Resultado                   | Tiempo  |
| --------- | ----------------- | --------------------------- | ------- |
| 1         | Abre portafolio   | Ve hero con "React, Python" | 2s      |
| 2         | Scrollea a Skills | Confirma stack completo     | 5s      |
| 3         | Revisa Experience | Ve Bice, JP Morgan          | 5s      |
| 4         | Click en Contact  | Email copiado               | 3s      |
| **Total** |                   | **Decisión positiva**       | **15s** |

**Resultado:** Flujo optimizado cumple objetivo de < 30 segundos.
