# La Bóveda — Contexto del proyecto

## Quién soy
Soy el creador de este proyecto. Soy diseñador gráfico con más de 10 años de experiencia en branding. Fundador de **Join Media Co.** y parte de la alianza **JOINKOD** (con Renzo Muñoz de KODIAK, empresa de contenidos audiovisuales). No tengo experiencia técnica en desarrollo web.

## Qué es La Bóveda
Sub-marca de Join Media Co. Es una plataforma web — centro/archivo de recursos gratuitos y premium para diseñadores, mercadólogos y creativos. Incluye templates, fuentes, paletas, herramientas, mockups, guías y más.

**URL activa:** https://laboveda-ten.vercel.app/  
**Repositorio:** https://github.com/joinkod/laboveda  
**Deploy:** Vercel — auto-deploy activado en cada push a rama `main`

---

## Sistema de identidad visual (NO modificar sin instrucción)

### Paleta de color
```
--boveda:    #080807          /* Fondo principal — negro cálido (actualizado) */
--pergamino: #EDE8DF          /* Texto principal */
--oro:       #C9A55A          /* Acento premium — dial, detalles */
--vivo:      #A3F55A          /* Acción, CTAs, comunidad, gamificación */
--glass:     rgba(255,255,255,0.045)   /* Fondo glass de panels/cards */
--glass-border: rgba(255,255,255,0.09) /* Bordes glass */
```
El fondo usa gradientes radiales fijos (`background-attachment: fixed`) con orbs de color dorado y verde para que el efecto glass tenga algo que difuminar.

### Tipografía
- **Serif:** EB Garamond — titulares, wordmark, "La" en cursiva
- **Sans:** DM Sans — UI, body, labels, botones
- Ambas desde Google Fonts

### Logo / Wordmark
- `La` en EB Garamond itálica, tamaño menor (~0.75em), pergamino con opacidad reducida
- `B` en EB Garamond regular
- La **Ó** es un dial de caja fuerte SVG en oro (#C9A55A) con indicador triangular verde (#A3F55A) arriba
- `VEDA` en EB Garamond regular
- Sello: "BY JOIN MEDIA CO." en sans, tracking alto, opacidad muy baja
- Archivo fuente del logo: `laboveda-logo.svg`

#### Técnica SVG del dial (importante para futuros ajustes)
El dial usa **dos `<g>` anidados** para separar posición de rotación:
```html
<g transform="translate(X,Y)">        <!-- solo posiciona, nunca tocar con JS -->
  <g id="heroDial" style="transform-origin:center; transform-box:fill-box; transition:...">
    <!-- contenido del dial -->
  </g>
</g>
```
`transform-box:fill-box` + `transform-origin:center` garantiza que gire sobre su propio eje. Si se pone el translate y la rotación en el mismo `<g>`, el JS sobreescribe la posición al rotar.

#### Posiciones actuales del wordmark hero (SVG viewBox="0 0 415 100")
- `La` italic 64px → x=0
- `B` 76px → x=84
- Dial → `translate(135,5)`, circle cx=36 cy=44 r=34
- `VEDA` 76px → x=214

#### Posiciones actuales del logo nav (SVG viewBox="0 0 146 36", height=26)
- `La` italic 22px → x=0
- `B` 26px → x=30
- Dial → `translate(48,1)`, circle cx=13 cy=16 r=13
- `VEDA` 26px → x=76

### Concepto de diseño
"Archivo vivo" — base oscura y densa (permanencia, valor) con acentos vivos (comunidad, movimiento). Premium en estructura, humano en detalles.

---

## Sistema de gamificación
La moneda interna se llama **bóvedas**.

| Nivel | Nombre | Beneficios |
|-------|--------|------------|
| 1 | Visitante | Recursos básicos sin registro |
| 2 | Curador | Favoritos + colecciones |
| 3 | Archivista | Sube recursos, gana bóvedas, acceso premium |
| 4 | Guardián | Modera, acceso total, insignia especial |

---

## Estructura actual del proyecto
```
laboveda/
├── index.html          ← homepage completo (CSS + JS inline)
├── laboveda-logo.svg   ← logo fuente para Illustrator
└── CLAUDE.md           ← este archivo
```

## Páginas planeadas (pendientes)
- [ ] `/recursos` — catálogo completo con filtros
- [ ] `/recurso/[id]` — página individual de recurso
- [ ] `/perfil` — perfil de usuario con nivel y bóvedas
- [ ] `/registro` — onboarding
- [ ] `/login` — ingreso

---

## Stack tecnológico
- **HTML + CSS + JS vanilla** — sin frameworks por ahora
- **Fuentes:** Google Fonts (EB Garamond + DM Sans)
- **Hosting:** Vercel (free tier — laboveda-ten.vercel.app)
- **Repositorio:** GitHub (github.com/joinkod/laboveda)

---

## Reglas de trabajo
1. Mantener CSS y JS inline en el HTML mientras sea una sola página
2. Al tener múltiples páginas, migrar a `styles.css` y `main.js` separados
3. No usar frameworks sin instrucción explícita
4. Respetar el sistema de color — nunca cambiar variables sin pedirlo
5. Comentar el código en español
6. Commits descriptivos en español después de cada cambio significativo
7. El diseño es responsivo — siempre verificar mobile
8. Después de cada sesión: actualizar la sección de Registro de cambios de este archivo

---

## Cómo trabajamos
- **Claude.ai** → decisiones de diseño, estrategia, nuevas páginas, identidad
- **Claude Code** → implementación, ajustes técnicos, commits, push
- **Este archivo** → puente de contexto entre ambos. Mantenerlo actualizado es prioridad

---

## Registro de cambios

### v0.1 — 2025-01-21
- ✅ Definición del nombre: La Bóveda
- ✅ Sistema de identidad completo (paleta, tipografía, logo, gamificación)
- ✅ Homepage diseñado y publicado en Vercel
- ✅ Repositorio GitHub creado: joinkod/laboveda
- ✅ Auto-deploy Vercel ↔ GitHub configurado
- ✅ Claude Code instalado y configurado
- ✅ Logo exportado en SVG para Illustrator (3 variantes)
- ✅ CLAUDE.md creado con contexto completo

### v0.2 — 2026-05-21
- ✅ **Rediseño glassmorphism estilo iOS**
  - Fondo con 4 orbs de gradiente (dorado + verde) fijos al viewport
  - Nav, cards, pills, botones, gamif-banner: `backdrop-filter: blur() saturate()`
  - Variables CSS `--glass` y `--glass-border` unificadas
  - Border-radius más redondeado: 20px cards, 24px banner, 16px íconos de nivel
  - Íconos de nivel: círculos → squircles (iOS style)
- ✅ **Animación de intro "cerradura de bóveda"**
  - Pantalla completa oscura con el dial centrado
  - 3 giros combinados (derecha → izquierda → derecha) con puntos de progreso
  - Al desbloquear: dial brilla verde, texto "Desbloqueado", línea dorada en el centro
  - Las dos mitades se abren (arriba/abajo) revelando la web
  - Solo se reproduce **una vez por sesión** (sessionStorage)
- ✅ **Fix rotación del dial hero** — el dial giraba desplazándose porque el `transform` CSS sobreescribía el `translate` SVG del mismo elemento. Solución: dos `<g>` anidados (uno para posición, otro para rotación) + `transform-origin:center; transform-box:fill-box`
- ✅ **Espaciado uniforme wordmark hero** — gap antes y después del dial igualados (~6-9px). ViewBox ajustado de 580 a 415 para centrar el logo
- ✅ **Espaciado uniforme logo nav** — mismo ajuste proporcional. Dial: translate(58→48), VEDA: x=86→76, viewBox: 220→146
- ✅ Git configurado con identidad: Davo / joinmediaco@gmail.com

### Próxima sesión
- [ ] Revisar homepage en mobile y corregir lo que sea necesario
- [ ] Crear página `/recursos` con catálogo y filtros
- [ ] Agregar favicon con el símbolo del dial
- [ ] Definir estructura de navegación entre páginas
