# Adaptar portfolio de Midudev a Antoine Peña Amores

## Objetivo

Reemplazar TODOS los datos personales de Midudev (Miguel Ángel Durán) en este portfolio Astro por los de Antoine Peña Amores, manteniendo intactos los estilos y el diseño.

## Problema

El repo es un clone del portfolio de Midudev. El código/estilos están bien y el usuario quiere conservarlos, pero todos los datos (nombre, bio, redes, experiencia, proyectos, SEO, metadatos) pertenecen a Midudev.

## Por qué

El usuario quiere un portfolio personal con su identidad y sus proyectos reales, listo para desplegar luego en GitHub Pages (deploy pendiente, se hará en otra sesión).

## Datos del usuario (autorizado)

| Dato | Valor |
| --- | --- |
| Nombre completo | Antoine Miguel Peña Amores (en UI: "Antoine") |
| Ubicación | San José de Las Lajas, Mayabeque, Cuba 🇨🇺 |
| Experiencia | 3 años en programación |
| Rol | Fullstack, especializado en Backend |
| Email | antoinepdeveloper@gmail.com |
| GitHub | https://github.com/antoinepdev |
| Telegram | https://t.me/antoinepdev (@antoinepdev) |
| Otras redes | NINGUNA (borrar LinkedIn, X/Twitter) |
| Estudios | 1er año Ingeniería en Ciencias Informáticas, UCI |
| Proyecto principal | Ecosistema Cinerat (canal TG +17.7k suscriptores, +1600 pelis en latino/castellano, bot, CMS, web) |
| Proyectos | Cinerat, telegram-file-gatekeeper, Shine.dots (sin imágenes → placeholder SVG) |
| Tecnologías (20) | HTML, CSS, JS, TS, React, Node.js, Express, Mongoose, Zod, PostgreSQL, Tailwind, vitest, Astro, node-telegram-bot-api, GitHub Actions, Python, Bash, Bun, Linux, Git |

## Alcance autorizado

- Editar: Layout, Hero, AboutMe, Header, Footer, index, Projects, components, projects.json
- Crear: Skills.astro, skills.json, icono Telegram.astro, 3 SVG placeholder de proyectos
- Eliminar: experience.json, Experience.astro, ExperienceItem.astro, svgl.webp, adventjs.webp, porfolio.webp
- NO tocar (pendiente por decisión del usuario): astro.config.mjs (site/base), workflow de deploy

## Decisiones de diseño tomadas

- Badge "Disponible para trabajar" apunta a mailto (antes LinkedIn)
- Sección "Experiencia laboral" se ELIMINA (usuario no tiene experiencia laboral formal)
- Nueva sección "Tecnologías" (Skills.astro + data/skills.json, 4 grupos)
- Footer enlaza el nombre al perfil de GitHub
- OG image por defecto pasa a /me.jpg (foto del usuario)
- Placeholders SVG elegantes para proyectos sin capturas

## Checklist

- [x] P1 Inventario de datos de Midudev (mapeo)
- [x] P2 Recopilar datos del usuario (entrevista)
- [ ] P3 Layout.astro: identidad, JSON-LD, og:site_name, quitar twitter
- [ ] P4 Hero.astro: nombre, intro, Telegram, quitar LinkedIn, badge → mailto
- [ ] P5 AboutMe.astro: bio 3 párrafos + limpiar comentarios
- [ ] P6 Header.astro: nav (sin Experiencia, con Tecnologías) + mailto
- [ ] P7 Footer.astro: nombre + mailto
- [ ] P8 index.astro: SEO, quitar Experiencia, agregar Tecnologías
- [ ] P9 Skills.astro + skills.json
- [ ] P10 projects.json + placeholders SVG
- [ ] P11 Projects.astro: extender TAGS
- [ ] P12 Icono Telegram.astro
- [ ] P13 Eliminar archivos de Midudev
- [ ] P14 components.astro sin LinkedIn
- [ ] P15 Build de verificación (bun run build)

## Criterios de aceptación

- No queda NINGUNA referencia a midudev/midu/Miguel/Durán/miduga en el código o datos (verificar con grep)
- El hero muestra "Hey, soy Antoine" con la intro de Cuba
- El único enlace social visible es Telegram + GitHub + mailto
- La sección Tecnologías muestra las 20 tecnologías en 4 grupos
- Los 3 proyectos son de Antoine con placeholder elegante
- Build: `bun run build` pasa sin errores

## Checks aplicables

- TDD: OFF (el proyecto no tiene runner de tests configurado; solo build script)
- Check funcional: `bun run build` (astro check + astro build)

## Ruta de implementación

INLINE (con delegación intentada). Disparadores de delegación activados (4+ archivos, 2+ archivos no triviales), pero el runtime no puede lanzar subagentes (error de transporte: "OpenCode's free tier can only be used from within OpenCode"). Se documenta y se procede inline con verificación de build.

## Progreso

- 2026-09-19: inventario completo + entrevista de datos terminada. Arranca implementación.