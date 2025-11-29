# Progreso de Migración Next.js → Astro + Vite

**Proyecto:** shzcode.tech - Portfolio de Jeff Barragán
**Fecha de inicio:** 2025-11-29
**Fecha estimada de finalización:** 2025-12-24 (25 días)
**Stack objetivo:** Astro 4.x + Vite + TypeScript + React Islands

---

## Estado General

| Fase | Estado | Progreso | Días Estimados |
|------|--------|----------|----------------|
| Fase 0: Preparación | ✅ Completado | 100% | 1-2 días |
| Fase 1: CSS | ⏳ Pendiente | 0% | 3-5 días |
| Fase 2: Componentes Astro | ⏳ Pendiente | 0% | 6-8 días |
| Fase 3: React Islands | ⏳ Pendiente | 0% | 9-13 días |
| Fase 4: Content Collections | ⏳ Pendiente | 0% | 14-16 días |
| Fase 5: TypeScript | ⏳ Pendiente | 0% | 17-19 días |
| Fase 6: SEO | ⏳ Pendiente | 0% | 20-22 días |
| Fase 7: Testing & Deploy | ⏳ Pendiente | 0% | 23-25 días |

**Leyenda:**
- ⏳ Pendiente
- 🔄 En progreso
- ✅ Completado
- ❌ Bloqueado

---

## Fase 0: Preparación y Setup ✅

**Objetivo:** Inicializar proyecto Astro y configurar dependencias

### Tareas
- [x] Proyecto Astro inicializado
- [x] Integraciones instaladas (@astrojs/react, @astrojs/mdx, @astrojs/sitemap)
- [x] Dependencias instaladas (typed.js, isotope-layout, fslightbox-react)
- [x] `astro.config.mjs` configurado
- [x] `tsconfig.json` configurado (strict mode)
- [x] Estructura de carpetas creada
- [x] `package.json` configurado
- [x] Backup del proyecto Next.js creado (nextjs-backup-20251129-175906.tar.gz)
- [x] Servidor de desarrollo verificado funcionando

### Estructura de Carpetas a Crear
```
/nuevo-proyecto/
├── src/
│   ├── components/
│   │   ├── astro/
│   │   └── react/
│   │       └── modals/
│   ├── layouts/
│   ├── content/
│   │   ├── portfolio/
│   │   └── blog/
│   ├── styles/
│   │   └── components/
│   ├── utils/
│   ├── types/
│   └── pages/
│       ├── portfolio/
│       └── blog/
└── public/
    ├── images/
    └── fonts/
```

### Notas
- [ ] Decisión: ¿Crear proyecto en carpeta nueva o migrar in-place?
- [ ] Ubicación del nuevo proyecto: _________________

---

## Fase 1: Migración y Modernización de CSS ⏳

**Objetivo:** Convertir LESS a CSS moderno manteniendo diseño visual

### Tareas
- [ ] `src/styles/theme.css` creado con variables CSS
- [ ] Variables extraídas de `setting.less`
- [ ] `src/styles/global.css` modernizado (de glitche-basic.css)
- [ ] Prefijos de navegador eliminados
- [ ] CSS nesting nativo implementado
- [ ] `glitche-layout.css` dividido en componentes:
  - [ ] `hero.css`
  - [ ] `portfolio.css`
  - [ ] `skills.css`
  - [ ] `resume.css`
  - [ ] `services.css`
  - [ ] `modals.css`
- [ ] `animations.css` copiado
- [ ] Ionicons CSS + fonts migrados
- [ ] Fuentes Roboto Mono configuradas con @fontsource
- [ ] Color variants implementados (orange, blue, green, pink, purple, red)
- [ ] Dark mode CSS preservado

### Archivos de Referencia
- `/workspaces/Shzcode/Frontend/public/less/setting.less`
- `/workspaces/Shzcode/Frontend/public/css/glitche-basic.css`
- `/workspaces/Shzcode/Frontend/public/css/glitche-layout.css`

### Validación
- [ ] Side-by-side comparison con diseño original
- [ ] Todas las clases CSS funcionan correctamente
- [ ] No hay estilos rotos

---

## Fase 2: Componentes Estáticos en Astro ⏳

**Objetivo:** Migrar componentes sin interactividad a Astro

### Layouts
- [ ] `BaseLayout.astro` creado
- [ ] `Header.astro` creado
- [ ] `Footer.astro` creado

### Componentes Estáticos
- [ ] `About.astro` migrado
- [ ] `Resume.astro` migrado
- [ ] `Services.astro` migrado
- [ ] `ContactsInfo.astro` migrado

### Validación
- [ ] HTML estructura idéntica al original
- [ ] CSS aplicado correctamente
- [ ] Componentes renderizan sin errores

### Archivos de Referencia
- `/workspaces/Shzcode/Frontend/src/components/About.tsx`
- `/workspaces/Shzcode/Frontend/src/components/Resume.tsx`
- `/workspaces/Shzcode/Frontend/src/components/Services.tsx`
- `/workspaces/Shzcode/Frontend/src/components/ContactsInfo.tsx`

---

## Fase 3: React Islands - Componentes Interactivos ⏳

**Objetivo:** Migrar componentes interactivos como React Islands

### State Management
- [ ] `ModalProvider.tsx` creado con TypeScript completo
- [ ] Context API configurado
- [ ] ModalProvider envuelve la app en BaseLayout

### React Islands
- [ ] `Hero.tsx` migrado (client:load)
  - [ ] Typed.js funciona correctamente
  - [ ] Links convertidos de Next.js Link a <a>
- [ ] `Skills.tsx` migrado (client:visible)
  - [ ] Animaciones funcionan
  - [ ] Múltiples modos de visualización (circles, dotted, list)
- [ ] `RecentWorks.tsx` migrado (client:idle)
  - [ ] Isotope inicializa correctamente
  - [ ] Filters funcionan
  - [ ] Conectado a ModalProvider
- [ ] `Blog.tsx` migrado (client:idle)
  - [ ] Isotope funciona
  - [ ] Filters funcionan
- [ ] `Clients.tsx` migrado (client:idle)
- [ ] `Preloader.tsx` migrado (client:load)
  - [ ] Animación funciona

### Validación
- [ ] Todos los islands cargan correctamente
- [ ] Client directives optimizados
- [ ] Isotope no causa errores de timing
- [ ] Modals abren/cierran correctamente
- [ ] Estado compartido funciona entre componentes

### Archivos de Referencia
- `/workspaces/Shzcode/Frontend/src/context/context.tsx`
- `/workspaces/Shzcode/Frontend/src/components/Hero.tsx`
- `/workspaces/Shzcode/Frontend/src/components/Skills.tsx`
- `/workspaces/Shzcode/Frontend/src/components/RecentWorks.tsx`
- `/workspaces/Shzcode/Frontend/src/components/Blog.tsx`
- `/workspaces/Shzcode/Frontend/src/components/Clients.tsx`

---

## Fase 4: Content Collections - CMS Setup ⏳

**Objetivo:** Configurar CMS con Content Collections

### Configuración
- [ ] `src/content/config.ts` creado
- [ ] Schema para portfolio definido (Zod)
- [ ] Schema para blog definido (Zod)

### Migración de Contenido
- [ ] Proyectos portfolio extraídos de RecentWorks.tsx
- [ ] ~9 archivos Markdown creados en `src/content/portfolio/`
  - [ ] Canvas Tote Bag MockUp
  - [ ] Coffee Cup In Hand (video)
  - [ ] Love & Care Ceramic Bottles (link)
  - [ ] Shopping gift bag (image)
  - [ ] Amore Mio Three Cups (gallery)
  - [ ] Marta Veludo Poster (music)
  - [ ] Minimal Poster Frame (image)
  - [ ] Cardboard Box 1 (content)
  - [ ] Cardboard Box 2 (content)
- [ ] ~5 posts de blog creados en `src/content/blog/`

### Páginas Dinámicas
- [ ] `src/pages/portfolio/[slug].astro` creado
- [ ] `src/pages/blog/[slug].astro` creado
- [ ] getStaticPaths() configurado correctamente

### Integración
- [ ] RecentWorks actualizado para usar Content Collections
- [ ] Blog actualizado para usar Content Collections
- [ ] Props correctamente tipadas

### Validación
- [ ] Build genera todas las rutas dinámicas
- [ ] Contenido renderiza correctamente
- [ ] Tipos validados con Zod
- [ ] No hay errores de TypeScript

---

## Fase 5: Migración Completa a TypeScript ⏳

**Objetivo:** Convertir todo a TypeScript strict

### Utilities
- [ ] `useClickOutside.ts` convertido
- [ ] `useWindowSize.ts` convertido
- [ ] Otros archivos .js en /utility convertidos

### Tipos
- [ ] `src/types/index.ts` creado
- [ ] Interface `PortfolioItem` definida
- [ ] Interface `BlogPost` definida
- [ ] Interface `ModalContextType` definida
- [ ] Props de todos los componentes tipadas

### Configuración
- [ ] `tsconfig.json` actualizado con strict mode
- [ ] Path aliases configurados (@/*, @/components/*, @/styles/*)
- [ ] Sin errores de compilación TypeScript

### Validación
- [ ] `npm run build` sin errores TypeScript
- [ ] No hay tipos `any` (excepto donde sea absolutamente necesario)
- [ ] Todos los archivos .js convertidos a .ts/.tsx

---

## Fase 6: SEO y Optimizaciones ⏳

**Objetivo:** Implementar SEO completo y optimizaciones de performance

### Meta Tags
- [ ] Componente `SEO.astro` creado
- [ ] Meta tags esenciales (title, description)
- [ ] Open Graph tags
- [ ] Twitter Card tags
- [ ] Canonical URLs

### Imágenes
- [ ] `@astrojs/image` instalado (si necesario)
- [ ] Imágenes optimizadas a WebP
- [ ] Lazy loading implementado
- [ ] Alt tags en todas las imágenes

### SEO Técnico
- [ ] `@astrojs/sitemap` instalado
- [ ] Sitemap.xml generado
- [ ] `robots.txt` creado
- [ ] Structured data (JSON-LD) implementado
  - [ ] Schema.org Person
  - [ ] Schema.org CreativeWork para portfolio

### Performance
- [ ] Fuentes preloaded
- [ ] Scripts defer/async donde corresponda
- [ ] CSS critical path optimizado
- [ ] Bundle size analizado

### Validación
- [ ] Lighthouse Score > 90 (Performance)
- [ ] Lighthouse Score > 90 (Accessibility)
- [ ] Lighthouse Score > 90 (Best Practices)
- [ ] Lighthouse Score > 90 (SEO)
- [ ] Structured data válido en schema.org validator
- [ ] Sitemap accesible en /sitemap.xml

---

## Fase 7: Testing y Deployment ⏳

**Objetivo:** Testing completo y deploy a producción

### Testing Visual
- [ ] Hero section idéntico (animación typed.js funciona)
- [ ] About section - layout correcto
- [ ] Resume timeline - espaciado correcto
- [ ] Skills - visualización correcta (circles/dotted/list)
- [ ] Services grid - alineación correcta
- [ ] Portfolio filters - Isotope funciona
- [ ] Modals - abren/cierran correctamente
- [ ] Blog filters - Isotope funciona
- [ ] Footer - layout correcto
- [ ] Preloader - animación funciona
- [ ] Responsive design verificado:
  - [ ] Mobile (< 768px)
  - [ ] Tablet (768px - 1024px)
  - [ ] Desktop (> 1024px)

### Testing de Funcionalidad
- [ ] Typed.js inicia automáticamente
- [ ] Isotope filters cambian categorías (Portfolio)
- [ ] Isotope filters cambian categorías (Blog)
- [ ] Lightbox gallery funciona
- [ ] Modals muestran contenido correcto
- [ ] Links internos funcionan (#about, #resume, etc.)
- [ ] Navegación a portfolio/[slug] funciona
- [ ] Navegación a blog/[slug] funciona
- [ ] Formulario de contacto (si aplica)

### Testing de Performance
- [ ] Lighthouse Performance > 90
- [ ] First Contentful Paint < 1.5s
- [ ] Time to Interactive < 3.5s
- [ ] Total Bundle Size < 300KB (gzipped)
- [ ] Images lazy loading
- [ ] No layout shifts (CLS < 0.1)

### Cross-Browser Testing
- [ ] Chrome (última versión)
- [ ] Edge (última versión)
- [ ] Firefox (última versión)
- [ ] Safari macOS (si disponible)
- [ ] Safari iOS (si disponible)

### Build y Deploy
- [ ] `npm run build` exitoso
- [ ] `npm run preview` verificado localmente
- [ ] Deploy a Vercel configurado
- [ ] Dominio shzcode.tech apuntado
- [ ] SSL configurado (automático en Vercel)
- [ ] DNS propagado
- [ ] Sitio accesible en producción

### Post-Deploy
- [ ] Analytics configurado (si aplica)
- [ ] Error monitoring (si aplica)
- [ ] Backup del proyecto Next.js original
- [ ] Documentación actualizada

---

## Notas y Bloqueos

### Decisiones Pendientes
- [ ] ¿Dónde crear el nuevo proyecto Astro? (carpeta separada vs in-place)
- [ ] ¿Mantener proyecto Next.js como backup o eliminarlo?

### Problemas Encontrados
_Documentar aquí cualquier bloqueador o issue encontrado durante la migración_

**Formato:**
```
[FECHA] - [FASE] - [PROBLEMA]
Descripción: ...
Solución: ...
Estado: Resuelto/Pendiente/Bloqueado
```

---

### Riesgos Identificados

| Riesgo | Estado | Mitigación |
|--------|--------|------------|
| Pérdida de paridad visual CSS | ⏳ | Side-by-side comparison continuo |
| Isotope no funciona en Astro | ⏳ | Client directives correctos + timeout |
| TypeScript errors bloquean build | ⏳ | Migración gradual |
| Performance degradada | ⏳ | Lighthouse monitoring |
| Modals no comparten estado | ⏳ | ModalProvider client:only |

---

## Recursos y Referencias

### Documentación
- [Astro Docs](https://docs.astro.build)
- [Astro Content Collections](https://docs.astro.build/en/guides/content-collections/)
- [Astro React Integration](https://docs.astro.build/en/guides/integrations-guide/react/)

### Archivos Críticos del Proyecto Original
1. `/workspaces/Shzcode/Frontend/public/less/setting.less`
2. `/workspaces/Shzcode/Frontend/public/css/glitche-basic.css`
3. `/workspaces/Shzcode/Frontend/public/css/glitche-layout.css`
4. `/workspaces/Shzcode/Frontend/src/context/context.tsx`
5. `/workspaces/Shzcode/Frontend/src/components/RecentWorks.tsx`

### Plan Completo
- Ubicación: `/home/node/.claude/plans/snazzy-jumping-moth.md`

---

**Última actualización:** 2025-11-29