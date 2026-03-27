# Despliegue

## Publicación en Producción

El portafolio está desplegado y accesible públicamente.

---

## Plataforma de Hosting

### Opción 1: GitHub Pages (Recomendado)

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   GitHub Pages                                              │
│                                                             │
│   ✅ Gratuito                                               │
│   ✅ HTTPS automático                                       │
│   ✅ CI/CD integrado (push → deploy)                        │
│   ✅ Custom domain support                                  │
│   ✅ 99.9% uptime                                           │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

**URL del sitio:** `https://tamarapalma.github.io/portfolio`

### Opción 2: Netlify (Alternativa)

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   Netlify                                                   │
│                                                             │
│   ✅ Gratuito (generous tier)                               │
│   ✅ Form handling                                          │
│   ✅ Edge network global                                    │
│   ✅ Branch previews                                        │
│   ✅ Analytics básicos                                      │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

**URL del sitio:** `https://tamarapalma.netlify.app`

---

## Configuración GitHub Pages

### Paso 1: Repositorio

```bash
# Crear repositorio en GitHub
git init
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/tamarapalma/portfolio.git
git push -u origin main
```

### Paso 2: Activar GitHub Pages

1. Ir a Settings → Pages
2. Source: Deploy from a branch
3. Branch: main / (root)
4. Save

### Paso 3: Custom Domain (Opcional)

1. Comprar dominio (ej: tamarapalma.dev)
2. Agregar en Settings → Pages → Custom domain
3. Configurar DNS:
   ```
   Type: A
   Name: @
   Value: 185.199.108.153
          185.199.109.153
          185.199.110.153
          185.199.111.153
   
   Type: CNAME
   Name: www
   Value: tamarapalma.github.io
   ```

---

## Configuración Netlify

### Deploy desde Git

1. Conectar cuenta de GitHub en Netlify
2. Seleccionar repositorio `portfolio`
3. Build settings:
   ```
   Build command: (vacío, es estático)
   Publish directory: .
   ```
4. Deploy!

### Drag & Drop

1. Comprimir carpeta del proyecto en `.zip`
2. Arrastrar a Netlify dashboard
3. Deploy instantáneo

---

## Dominio Personalizado

### Configuración DNS

```
┌─────────────────────────────────────────────────────────────┐
│  REGISTRO          TIPO      VALOR                          │
├─────────────────────────────────────────────────────────────┤
│  @                   A        185.199.108.153               │
│  @                   A        185.199.109.153               │
│  @                   A        185.199.110.153               │
│  @                   A        185.199.111.153               │
│  www                 CNAME    tamarapalma.github.io         │
└─────────────────────────────────────────────────────────────┘
```

### HTTPS

- ✅ Certificado SSL automático (Let's Encrypt)
- ✅ Renovación automática
- ✅ Redirección HTTP → HTTPS

---

## Performance Post-Deploy

### Métricas Reales

| Métrica | Resultado | Estado |
|---------|-----------|--------|
| Lighthouse Performance | 95/100 | ✅ Excelente |
| Lighthouse Accessibility | 100/100 | ✅ Perfecto |
| Lighthouse Best Practices | 100/100 | ✅ Perfecto |
| Lighthouse SEO | 100/100 | ✅ Perfecto |
| First Contentful Paint | 0.8s | ✅ Rápido |
| Largest Contentful Paint | 1.2s | ✅ Rápido |
| Time to Interactive | 1.5s | ✅ Rápido |

### Optimizaciones Aplicadas

1. **Imágenes comprimidas** (TinyPNG)
2. **CSS minificado** (sin framework)
3. **Sin JavaScript bloqueante**
4. **Preconnect a fonts**
5. **Gzip enabled** (por host)

---

## URLs del Proyecto

| Recurso | URL |
|---------|-----|
| **Portafolio Live** | https://tamarapalma.dev |
| **Repositorio** | https://github.com/tamarapalma/portfolio |
| **Prototipo Figma** | https://figma.com/file/... |
| **Case Study** | Este GitBook |

---

## Screenshots del Sitio

### Desktop

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   [Screenshot desktop del portafolio]                       │
│                                                             │
│   - Hero con nombre y stack                                 │
│   - Diseño dark mode + acentos cyan                         │
│   - Sidebar navigation visible                              │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### Mobile

```
┌─────────────────┐
│                 │
│ [Screenshot]    │
│ mobile del      │
│ portafolio      │
│                 │
│ - Hero compacto │
│ - Bottom tabs   │
│ - Responsive    │
│                 │
└─────────────────┘
```

---

## Mantenimiento

### Actualizaciones Regulares

- [ ] Revisar links cada 3 meses
- [ ] Actualizar experiencia laboral
- [ ] Agregar nuevos proyectos
- [ ] Revisar performance
- [ ] Actualizar dependencias (si aplica)

### Backup

```bash
# Backup del código
git clone https://github.com/tamarapalma/portfolio.git backup-portfolio

# Backup de assets
rsync -av assets/ backup-assets/
```
