# La Bóveda — Contexto del proyecto

## Quién soy
Soy el creador de este proyecto. Soy diseñador gráfico con más de 10 años de experiencia en branding. Fundador de **Join Media Co.** y parte de la alianza **JOINKOD** (con Renzo Muñoz de KODIAK, empresa de contenidos audiovisuales). No tengo experiencia técnica en desarrollo web.

## Qué es La Bóveda
Sub-marca de Join Media Co. Es una plataforma web — centro/archivo de recursos gratuitos y premium para diseñadores, mercadólogos y creativos. Incluye templates, fuentes, paletas, herramientas, mockups, guías y más.

**URL actual:** https://laboveda-ten.vercel.app/  
**Repositorio:** https://github.com/joinkod/laboveda  
**Deploy:** Vercel (conectado a GitHub, auto-deploy en cada push)

## Sistema de identidad visual (NO modificar sin instrucción)

### Paleta de color
```
--boveda:    #0E0D0B   /* Fondo principal — negro cálido */
--interior:  #1A1916   /* Cards y contenedores */
--sombra:    #2C2B28   /* Bordes, hover states */
--pergamino: #EDE8DF   /* Texto principal */
--oro:       #C9A55A   /* Acento premium — dial, detalles */
--vivo:      #A3F55A   /* Acción, CTAs, comunidad, gamificación */
```

### Tipografía
- **Serif:** EB Garamond (titulares, wordmark, "La" en cursiva)
- **Sans:** DM Sans (UI, body, labels, botones)

### Logo / Wordmark
- "La" en EB Garamond itálica, tamaño menor, color pergamino con opacidad reducida
- "B" en EB Garamond regular
- La **Ó** es un dial de caja fuerte SVG en color oro (#C9A55A) con indicador verde (#A3F55A) arriba
- "VEDA" en EB Garamond regular
- Sello discreto: "BY JOIN MEDIA CO." en sans, opacidad baja

### Concepto de diseño
"Archivo vivo" — base oscura y densa (permanencia, valor) + acentos vivos (comunidad, movimiento). Premium en la estructura, humano en los detalles.

## Estructura actual del proyecto
```
laboveda/
├── index.html    ← única página actual, todo incluido (CSS + JS inline)
└── CLAUDE.md     ← este archivo
```

## Sistema de gamificación
La moneda interna se llama **bóvedas**.

Niveles de usuario:
1. **Visitante** — acceso a recursos básicos sin registro
2. **Curador** — guarda favoritos, accede a colecciones
3. **Archivista** — sube recursos, gana bóvedas, accede a premium
4. **Guardián** — modera, acceso total, insignia especial

## Páginas planeadas (aún no construidas)
- `/recursos` — catálogo completo con filtros
- `/recurso/[id]` — página individual de recurso
- `/perfil` — perfil de usuario con nivel y bóvedas
- `/registro` — onboarding
- `/login` — ingreso

## Stack tecnológico
- **HTML + CSS + JS vanilla** (sin frameworks por ahora — mantener simple)
- **Fuentes:** Google Fonts (EB Garamond + DM Sans)
- **Hosting:** Vercel (free tier)
- **Repositorio:** GitHub

## Reglas de trabajo
1. Mantener TODO el CSS inline en el mismo archivo HTML mientras sea una sola página
2. Cuando haya múltiples páginas, migrar a archivos separados: `styles.css`, `main.js`
3. No usar frameworks (React, Vue, etc.) sin instrucción explícita
4. Respetar el sistema de color — nunca cambiar variables sin pedirlo
5. Comentar el código en español
6. Después de cada cambio significativo, hacer commit descriptivo en español
7. El diseño es responsivo — siempre verificar mobile

## Cómo trabajamos
- Las decisiones de diseño y estrategia se definen en **Claude.ai** (claude.ai)
- La implementación y ajustes de código se hacen aquí con **Claude Code**
- Cada sesión: revisar este CLAUDE.md primero para tener contexto completo

## Próximos pasos inmediatos
- [ ] Revisar y ajustar homepage en mobile
- [ ] Crear página `/recursos` con catálogo y filtros
- [ ] Implementar sistema de navegación entre páginas
- [ ] Agregar favicon con el símbolo del dial
