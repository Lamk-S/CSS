# Curso de CSS - Apuntes y Practicas

Repositorio dedicado al aprendizaje progresivo de CSS, desde fundamentos hasta nivel intermedio. Contiene apuntes teoricos con ejemplos interactivos, documentacion comentada y practicas organizadas por modulos.

Repositorio: https://github.com/Lamk-S/CSS

---

## Descripcion

Este repositorio centraliza mis apuntes del curso de CSS. Cada modulo (B01, I01, etc.) es una pagina HTML independiente con su propia hoja de estilos, donde se documenta y demuestra visualmente un concepto especifico.

El enfoque es aprender haciendo: cada `index.html` incluye teoria, ejemplos de codigo y resultados visuales; cada `css/style.css` esta completamente comentado para explicar decisiones de diseno, accesibilidad y arquitectura.

El repositorio esta dividido en dos niveles:

- **Basic:** Fundamentos - introduccion, colores, tipografia, fondos y pseudo-clases
- **Intermediate:** Diagramacion y modelo de caja - unidades, layouts, box model y posicionamiento

---

## Objetivo

1.  Comprender los fundamentos: cascada, herencia y especificidad
2.  Dominar color, tipografia, fondos y manejo de fuentes locales y externas
3.  Entender unidades absolutas vs relativas y su impacto en accesibilidad y responsive
4.  Dominar el modelo de caja, box-sizing y tecnicas de layout tradicionales y modernas
5.  Aprender posicionamiento y apilamiento con z-index
6.  Mantener material de consulta versionado, limpio y reutilizable

---

## Tecnologias y herramientas

- **Lenguajes:** HTML5, CSS3 moderno (vanilla, sin frameworks)
- **Fuentes:** @font-face con .woff y .woff2, Google Fonts (Inter, Merriweather), Font Awesome 6
- **Conceptos clave:** Variables CSS (custom properties), clamp(), calc(), gradientes, backdrop-filter, box-sizing
- **Layout:** Float con clearfix, flujo normal, posicionamiento, display
- **Editor recomendado:** Visual Studio Code con Live Server
- **Navegador:** Chrome, Firefox, Edge modernos

---

## Estructura del repositorio

```
CSS/
|
├── Basic/
|   ├── B01-Introduction/
|   │   ├── index.html
|   │   └── css/styles.css
|   ├── B02-Colors/
|   │   ├── index.html
|   │   └── css/styles.css
|   ├── B03-Typography/
|   │   ├── index.html
|   │   ├── css/style.css
|   │   └── fonts/
|   │       ├── Atkinson-hyperlegible-Regular.woff2
|   │       ├── Atkinson-hyperlegible-Bold.woff2
|   │       ├── Grandstander-Regular.woff
|   │       └── Grandstander-Bold.woff
|   └── B04-Backgrounds-Pseudo/
|       ├── index.html
|       └── css/style.css
|
├── Intermediate/
|   ├── I01-CSS-Units/
|   │   ├── index.html
|   │   └── css/style.css
|   ├── I02-CSS-Layouts/
|   │   ├── index.html
|   │   └── css/style.css
|   ├── I03-Box-Model/
|   │   ├── index.html
|   │   └── css/style.css
|   └── I04-Positioning/
|       ├── index.html
|       └── css/style.css
|
└── README.md
```

---

## Contenido detallado

### Nivel Basico

#### B01 - Introduction: Fundamentos de CSS
`Basic/B01-Introduction/`

- Sintaxis basica `selector { propiedad: valor; }`
- Selectores: elemento, grupal (`h1, h2, h3`), ID (`#id`) y clase (`.class`)
- User agent styles
- Cascada: la ultima regla gana
- Especificidad: inline > ID > clase > etiqueta
- Herencia: `color` y `font-family`
- Buenas practicas: hojas externas vs inline, comentarios
- Demos: dos reglas `p` compitiendo y `p#miIdentificador` ganando por especificidad

#### B02 - Colors: Modelos de color y transparencia
`Basic/B02-Colors/`

- Modelos: keywords, HEX, RGB/RGBA, HSL/HSLA, HEX 8 digitos
- Diferencia critica: canal alfa (`rgba`) vs `opacity` (afecta a hijos)
- Propiedades: `color`, `background-color`, `border-color`
- Variables CSS centralizadas en `:root`
- Diseno: `radial-gradient`, `linear-gradient`, `backdrop-filter: blur()`
- Demos: `.bg-alfa` con fondo semitransparente y texto legible vs `.bg-opacity` con todo transparente

#### B03 - Typography: Tipografia y legibilidad
`Basic/B03-Typography/`

- Web Safe Fonts y font stacks de sistema
- @font-face local:
  - Atkinson Hyperlegible Regular/Bold (.woff2) para texto base
  - Grandstander Regular/Bold (.woff) para titulos
  - `font-display: swap`
- Google Fonts via `<link>` (Inter + Merriweather)
- Iconos como fuente: Font Awesome
- Unidades: `px` (estatica), `em` (padre), `rem` (raiz, recomendada)
- Legibilidad: `line-height` 1.5-1.75, `max-width: 65ch`, `text-align: left`
- Demos: cajas por fuente, comparativa 16px vs 1.5rem, parrafo optimizado, iconos HTML5/CSS3/JS

#### B04 - Backgrounds and Pseudo: Fondos y pseudo
`Basic/B04-Backgrounds-Pseudo/`

- `background-image`, `background-repeat`: repeat, no-repeat, repeat-x/y
- `background-position`: center, top right, valores porcentuales
- `background-size`: `cover` vs `contain`
- Multiples fondos: `linear-gradient(...), url(...)` con overlay para legibilidad
- Pseudoclases: `:hover`, `:active`, `:link`, `:visited` (orden LoVe HAte)
- Pseudoelementos: `::before`, `::after` con `content` obligatorio
- Demos: repeat vs no-repeat, cover centrado, gradiente + foto, boton con hover y transform, decoracion con ::before, enlace con icono SVG como background

### Nivel Intermedio

#### I01 - CSS Units: Unidades de medida
`Intermediate/I01-CSS-Units/`

Concepto clave para interfaces escalables y accesibles.

- **Absolutas:** `px`, `cm`, `mm`, `in` - fijas, para bordes/sombras, no para tipografia responsive. Problema de `width: 300px` que genera scroll horizontal
- **Relativas tipograficas:**
  - `em`: relativo al padre, efecto cascada/bola de nieve al anidar
  - `rem`: relativo a `<html>` (root em), predecible, estandar moderno
  - `ch`: ancho del caracter "0", ideal para limitar parrafos a 65 caracteres
- **Viewport:**
  - `vw`: 1% del ancho de ventana
  - `vh`: 1% del alto (100vh = pantalla completa)
  - `vmin`/`vmax`: minimo/maximo entre vw y vh
- Demos visuales:
  - Caja de 300px vs responsive
  - Comparativa em (se multiplica 1.2em > 1.44em > 1.728em) vs rem (siempre 1.2rem = 19.2px)
  - Caja de 50vw que crece/encoge al redimensionar navegador
  - Transicion `width 0.2s ease-out` para ver efecto fluido

#### I02 - CSS Layouts: Diagramacion
`Intermediate/I02-CSS-Layouts/`

Control del flujo del documento antes de Flexbox/Grid.

- **Dimensiones:** `width`/`height` vs `max-width`/`min-height` - `max-width: 400px` se adapta en movil pero no crece de mas en desktop, centrado con `margin: auto`
- **Display, Float y Clear:**
  - `display: block` ocupa toda la linea, `inline` se ajusta al contenido
  - `float: left/right` saca del flujo para que texto rodee imagen (estilo periodico)
  - Problema: contenedor colapsa, solucion: hack `clearfix::after { content: ""; display: table; clear: both; }`
  - `box-sizing: border-box` critico para columnas con porcentaje
- **Diagramacion por filas:** Flujo normal de bloques apilados (Header, Main, Footer)
- **Diagramacion por columnas:** Tecnica tradicional con `float: left` y `width: 33.33%`
- Demos:
  - Caja con `max-width: 400px`
  - Imagen flotante con texto rodeando y contenedor con clearfix
  - Layout de 3 filas con colores distintos
  - 3 columnas flotantes que en movil (max-width 768px) pasan a `float: none; width: 100%`

#### I03 - Box Model: Modelo de caja
`Intermediate/I03-Box-Model/`

Todo en CSS es una caja rectangular.

- **4 capas de adentro hacia afuera:**
  1. Content: texto/imagen
  2. Padding: relleno interior, expande fondo
  3. Border: linea visible (necesita ancho, estilo, color)
  4. Margin: espacio exterior, empuja vecinos
- **Shorthand:** sentido horario Arriba, Derecha, Abajo, Izquierda (`padding: 10px 20px 15px 5px` o `margin: 2rem 1rem`)
- **Border-radius:** para suavizar esquinas
- **Box-sizing - el concepto mas importante:**
  - `content-box` (default): width 100% + padding + border = mas de 100%, rompe layout y genera scroll
  - `border-box`: padding y border se descuentan dentro del width, mantiene 100% exacto
  - Mejor practica global: `html { box-sizing: border-box; } *, *:before, *:after { box-sizing: inherit; }`
- Demos con colores estilo DevTools:
  - Grafico de capas: margin #f9cc9d, border #fce18b, padding #c4d79b, content #9ec3e5
  - Padding vs Margin: `.only-padding` con fondo que crece vs `.only-margin` que empuja
  - Borders: solid + radius, dashed, double
  - Comparativa `sizing-bad` (content-box desbordada, borde rojo) vs `sizing-good` (border-box perfecta, borde verde)

#### I04 - Positioning: Posicionamiento
`Intermediate/I04-Positioning/`

Sacar elementos del flujo normal y controlar ejes X, Y, Z.

- **Propiedades de desplazamiento:** `top`, `right`, `bottom`, `left` solo funcionan si `position` no es `static`
- **Valores:**
  - `static`: default, flujo normal, ignora top/left/z-index
  - `relative`: se mueve respecto a su posicion original, deja fantasma (espacio reservado)
  - `absolute`: sale completamente del flujo (vecinos actuan como si no existiera), se posiciona respecto al ancestro posicionado mas cercano
  - `fixed`: similar a absolute pero respecto al viewport, no se mueve con scroll (boton de chat flotante)
  - `sticky`: hibrido relative hasta cruzar limite (top: 0), luego se vuelve fixed
- **Patron maestro obligatorio:** Padre `position: relative` + Hijo `position: absolute` - el padre se vuelve referencia de coordenadas para el hijo. Si no hay ancestro posicionado, usa la pagina completa
- **Z-index:** controla eje Z (profundidad), numero mayor = mas cerca del usuario, solo funciona en elementos posicionados
- Demos:
  - 3 cajas static / relative (top 20px left 30px con fantasma) / static
  - Scroll box de 180px con `sticky-header` que se pega en top: 0
  - Tarjeta `card-relative` (relative) con badge `badge-absolute` (absolute top: -15px right: -15px)
  - 3 cajas superpuestas con z-index 1 (gris), 2 (celeste), 3 (rosa/rojo arriba del todo)

---

## Como ejecutar

No requiere compilacion.

1. Clonar:
```bash
git clone https://github.com/Lamk-S/CSS.git
cd CSS
```

2. Abrir con Live Server (recomendado):
- Instalar extension Live Server en VS Code
- Click derecho sobre cualquier `index.html` -> Open with Live Server

3. Abrir directo:
- Doble clic en `Basic/B01-Introduction/index.html` o `Intermediate/I03-Box-Model/index.html`

---

## Buenas practicas aplicadas en todo el repo

- Variables CSS en `:root` para paleta, radios y sombras (consistencia)
- Comentarios por bloques explicando objetivo y por que
- `clamp()` para padding y font-size responsive
- `box-sizing: border-box` como base en layouts
- HTML semantico y accesible con `aria-labelledby`
- `font-display: swap` para evitar FOIT
- Demos aisladas en `.box` para no contaminar estilo base
- Mobile first con media queries en 640px/768px

---

## Roadmap

- [x] B01 - Introduccion, cascada, herencia, especificidad
- [x] B02 - Colores y transparencias
- [x] B03 - Tipografia, @font-face, Google Fonts, iconos
- [x] B04 - Fondos, posicionamiento de fondos, pseudo-clases/elementos
- [x] I01 - Unidades: px, em, rem, ch, vw, vh, vmin/vmax
- [x] I02 - Layouts: width/max-width, float, clearfix, filas y columnas
- [x] I03 - Box Model: content, padding, border, margin, box-sizing
- [x] I04 - Positioning: static, relative, absolute, fixed, sticky, z-index, patron padre relativo + hijo absoluto
- [ ] I05 - Flexbox
- [ ] I06 - Grid
- [ ] I07 - Responsive Design y Media Queries avanzadas
- [ ] I08 - Transiciones, Transformaciones y Animaciones

---

## Requisitos

- Navegador moderno con soporte CSS3 (Chrome 90+, Firefox 88+, Edge 90+)
- VS Code + Live Server opcional
- No necesita Node.js ni dependencias

---

## Autor

**Melvin López (Lamk-S)**
GitHub: https://github.com/Lamk-S

---

## Licencia

Licencia MIT - Uso libre para aprendizaje y referencia.
