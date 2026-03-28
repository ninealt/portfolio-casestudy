# Despliegue

## Publicación en Producción

El portafolio está desplegado y accesible públicamente. El build de Vite genera archivos estáticos optimizados listos para cualquier hosting.

---

## Build de Producción

### Generar el Build

```bash
# En la carpeta del proyecto
cd /Users/ninealt/develop/memory-octo

# Instalar dependencias (si no lo has hecho)
npm install

# Generar build de producción
npm run build

# El resultado está en la carpeta /dist
```

### Contenido del Build

```
dist/
├── index.html              ← HTML principal optimizado
├── assets/
│   ├── index-XXXX.js       ← JavaScript bundle
│   ├── index-XXXX.css      ← CSS optimizado
│   └── vendor-XXXX.js      ← Vendor chunk (React)
└── [assets estáticos]      ← Imágenes, favicon, etc.
```

### Preview Local del Build

```bash
# Verificar que todo funciona antes de deploy
npm run preview

# Abre http://localhost:4173
```

---

## Plataformas de Hosting

### Opción 1: GitHub Pages (Recomendada)

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   GitHub Pages                                              │
│                                                             │
│   ✅ Gratuito                                               │
│   ✅ HTTPS automático                                       │
│   ✅ Integrado con Git workflow                             │
│   ✅ Custom domain support                                  │
│   ✅ 99.9% uptime                                           │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

**Configuración para GitHub Pages:**

1. **Instalar gh-pages:**
   ```bash
   npm install --save-dev gh-pages
   ```

2. **Actualizar package.json:**
   ```json
   {
     "scripts": {
       "dev": "vite",
       "build": "vite build",
       "preview": "vite preview",
       "predeploy": "npm run build",
       "deploy": "gh-pages -d dist"
     },
     "homepage": "https://tamarapalma.github.io/cv-react"
   }
   ```

3. **Actualizar vite.config.js:**
   ```javascript
   export default defineConfig({
     base: '/cv-react/',  // ← Nombre del repo
     plugins: [react()],
   })
   ```

4. **Deploy:**
   ```bash
   npm run deploy
   ```

---

### Opción 2: Netlify (Recomendada para SPAs)

```
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│   Netlify                                                   │
│                                                             │
│   ✅ Drag & drop simple                                     │
│   ✅ CI/CD automático desde GitHub                          │
│   ✅ Form handling integrado                                │
│   ✅ Edge network global                                    │
│   ✅ Branch previews                                        │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

**Deploy en Netlify:**

#### Método A: Drag & Drop
1. Ejecuta `npm run build`
2. Arrastra la carpeta `dist` a [netlify.com](https://netlify.com)
3. Listo!

#### Método B: Git Integration
1. Conecta tu repo de GitHub en Netlify
2. Configuración:
   ```
   Build command: npm run build
   Publish directory: dist
   ```
3. Deploy automático en cada push

---

### Opción 3: Vercel

```bash
# Instalar Vercel CLI
npm i -g vercel

# Deploy
vercel --prod
```

**Configuración automática:** Vercel detecta Vite y configura todo.

---

## Configuración de Dominio Personalizado

### GitHub Pages + Custom Domain

1. Agrega archivo `CNAME` en la carpeta `public/`:
   ```
   tamarapalma.dev
   ```

2. En GitHub: Settings → Pages → Custom domain

3. Configura DNS:
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

### Netlify Custom Domain

1. Ve a Site settings → Domain management
2. Add custom domain
3. Configura DNS según instrucciones

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
| Bundle Size | ~150KB | ✅ Optimizado |

### Optimizaciones de Vite

- **Code splitting** automático
- **Tree shaking** para eliminar código no usado
- **Minificación** con esbuild
- **Asset hashing** para cache busting

---

## URLs del Proyecto

| Recurso | URL |
|---------|-----|
| **Portafolio Live** | https://tamarapalma.dev |
| **Repositorio** | https://github.com/tamarapalma/cv-react |
| **Prototipo Figma** | https://figma.com/file/... |
| **Case Study** | Este GitBook |

---

## Troubleshooting

### Problema: Rutas rotas en refresh (404)

**Solución para GitHub Pages/Netlify:**

Crear archivo `public/_redirects` (Netlify):
```
/* /index.html 200
```

O `public/404.html` (GitHub Pages):
Copiar el contenido de `index.html`

### Problema: Assets no cargan

Verificar que `base` en `vite.config.js` coincida con el subdirectorio:
```javascript
// Si el repo se llama 'cv-react' y es proyecto de usuario
base: '/cv-react/',

// Si es usuario.github.io (sin subdirectorio)
base: '/',
```

### Problema: Build muy grande

Analizar bundle:
```bash
npm install --save-dev rollup-plugin-visualizer

// vite.config.js
import { visualizer } from 'rollup-plugin-visualizer'

export default defineConfig({
  plugins: [
    react(),
    visualizer(),
  ],
})
```

---

## Mantenimiento

### Actualizaciones Regulares

- [ ] `npm update` mensualmente
- [ ] Revisar links cada 3 meses
- [ ] Actualizar experiencia laboral
- [ ] Agregar nuevos proyectos
- [ ] Revisar métricas de Lighthouse

### Actualizar Dependencias

```bash
# Verificar actualizaciones
npm outdated

# Actualizar seguro
npm update

# Actualizar major versions (con cuidado)
npm install react@latest react-dom@latest
```

---

## Checklist Pre-Deploy

- [ ] `npm run build` ejecuta sin errores
- [ ] `npm run preview` muestra el sitio correctamente
- [ ] Todos los links funcionan
- [ ] Imágenes cargan correctamente
- [ ] Responsive funciona en mobile
- [ ] Meta tags de SEO están presentes
- [ ] No hay errores en consola
- [ ] Lighthouse score > 90
