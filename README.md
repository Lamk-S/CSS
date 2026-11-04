# Curso de CSS - Apuntes y Practicas

Repositorio dedicado al aprendizaje progresivo de CSS, desde fundamentos hasta tecnicas modernas de estilizado. Contiene apuntes teoricos con ejemplos interactivos, documentacion comentada y ejercicios practicos organizados por modulos.

Repositorio: https://github.com/Lamk-S/CSS

---

## Descripcion

Este repositorio centraliza mis apuntes del curso de CSS. Cada modulo (B01, B02, etc.) es una pagina HTML independiente con su propia hoja de estilos, donde se documenta y demuestra un concepto especifico del lenguaje.

El enfoque es aprender haciendo: cada archivo `index.html` incluye teoria, ejemplos de codigo y resultados visuales; cada `css/style.css` esta completamente comentado para explicar decisiones de diseno, accesibilidad y arquitectura.

Actualmente el contenido cubre el nivel basico y se expandira hacia nivel intermedio y avanzado.

---

## Objetivo

1.  Comprender los fundamentos del modelo de CSS: cascada, herencia y especificidad.
2.  Dominar el manejo de color, tipografia y fondos.
3.  Aprender a usar fuentes locales, externas e iconos como texto.
4.  Aplicar buenas practicas de arquitectura CSS (variables, :root, metodologia limpia).
5.  Mantener un material de consulta versionado y reutilizable.

---

## Tecnologias y herramientas

- **Lenguaje:** HTML5, CSS3 moderno
- **Fuentes:** @font-face con .woff y .woff2, Google Fonts, Font Awesome
- **Conceptos clave:** Variables CSS (custom properties), clamp(), gradientes, backdrop-filter
- **Editor recomendado:** Visual Studio Code con Live Server
- **Navegador:** Cualquier navegador moderno con soporte para CSS3

---

## Estructura del repositorio

```
CSS/
|
├── Basic/
|   ├── B01-Introduction/
|   │   ├── index.html
|   │   └── css/
|   │       └── styles.css
|   │
|   ├── B02-Colors/
|   │   ├── index.html
|   │   └── css/
|   │       └── styles.css
|   │
|   ├── B03-Typography/
|   │   ├── index.html
|   │   ├── css/
|   │   │   └── style.css
|   │   └── fonts/
|   │       ├── Atkinson-hyperlegible-Regular.woff2
|   │       ├── Atkinson-hyperlegible-Bold.woff2
|   │       ├── Grandstander-Regular.woff
|   │       └── Grandstander-Bold.woff
|   │
|   └── B04-Backgrounds-Pseudo/
|       ├── index.html
|       └── css/
|           └── style.css
|
├── Intermediate/ (en preparacion)
└── README.md
```

---

## Contenido detallado - Nivel Basico

### B01 - Introduction: Fundamentos de CSS

Ubicacion: `Basic/B01-Introduction/`

Conceptos cubiertos:

- Que es CSS y sintaxis basica `selector { propiedad: valor; }`
- Tipos de selectores: elemento, grupal (`h1, h2, h3`), ID (`#miIdentificador`) y clase (`.miClase`)
- Caracteristicas basicas del navegador: user agent styles
- **Cascada:** el orden importa, la ultima regla gana
- **Especificidad:** inline > ID > clase > etiqueta
- **Herencia:** propiedades como `color` y `font-family` se heredan
- Buenas practicas: preferir hojas externas y clases, evitar estilos inline
- Comentarios en CSS y HTML

Archivo CSS demuestra: variables en `:root`, ejemplos practicos de cascada con dos reglas `p` compitiendo y especificidad con `p#miIdentificador`.

### B02 - Colors: Modelos de color y transparencia

Ubicacion: `Basic/B02-Colors/`

Conceptos cubiertos:

- Modelos de color: keywords, HEX (`#FF0000`), RGB/RGBA, HSL/HSLA, HEX de 8 digitos
- Diferencia critica entre canal alfa y propiedad `opacity`:
  - `rgba() / hsla()`: solo el color es transparente, el texto sigue legible
  - `opacity`: afecta a todo el elemento y sus hijos
- Aplicacion practica: `color`, `background-color`, `border-color`
- Uso de variables CSS para paleta centralizada
- Diseno moderno: `radial-gradient`, `linear-gradient`, `backdrop-filter: blur()`, sombras suaves y bordes redondeados
- Estructura de tarjeta centrada para presentar contenido

Demos incluidas: `.bg-alfa` vs `.bg-opacity` para ver la diferencia visual.

### B03 - Typography: Tipografia y legibilidad

Ubicacion: `Basic/B03-Typography/`

Conceptos cubiertos:

- **Web Safe Fonts:** Arial, Times New Roman, Courier New, stacks de sistema `system-ui`
- **Fuentes locales con @font-face:**
  - Atkinson Hyperlegible (Regular 400 y Bold 700) en `.woff2` para texto base, alta legibilidad
  - Grandstander (Regular y Bold) en `.woff` para titulos
  - Propiedades: `font-display: swap`, `font-weight`, `src` con `format()`
- **Google Fonts:** integracion via `<link>` en `<head>` (Inter y Merriweather)
- **Iconos como fuente:** Font Awesome, tratados como texto (pueden cambiar `color` y `font-size`)
- Unidades de tamano:
  - `px`: estatica, no recomendada para texto
  - `em`: relativa al padre
  - `rem`: relativa a la raiz (recomendada para accesibilidad)
- Legibilidad de parrafos:
  - `line-height` entre 1.5 y 1.75
  - `max-width: 65ch` para limitar ancho de linea
  - `text-align: left` preferible a `justify`
- Jerarquia visual con variables `--font-base`, `--font-heading`, `--font-serif`

Demos incluidas: cajas con cada fuente, comparativa 16px vs 1.5rem, parrafo optimizado y iconos HTML5/CSS3/JS con hover.

### B04 - Backgrounds and Pseudo: Fondos y pseudo-clases

Ubicacion: `Basic/B04-Backgrounds-Pseudo/`

Conceptos cubiertos:

- `background-image` y `background-repeat`: `repeat`, `repeat-x`, `repeat-y`, `no-repeat`
- `background-position`: keywords (`center`, `top right`) y valores (`50% 50%`)
- `background-size`: `cover` (cubre todo recortando) vs `contain` (imagen completa)
- Multiples fondos: `background-image: linear-gradient(...), url(...)` - el primero esta arriba
- Tecnica de overlay: gradiente oscuro sobre foto para mejorar legibilidad de texto
- Pseudoclases (estado): `:hover`, `:focus`, `:active`, `:first-child` - orden recomendado LoVe HAte para enlaces
- Pseudoelementos (estructura virtual): `::before` y `::after` - requieren `content`
- Uso en enlaces: estilos interactivos y iconos como `background-image` con SVG Base64

Demos incluidas: grid con repeat vs no-repeat, cover centrado, gradiente + foto, boton con `:hover` y `transform`, decoracion con `::before`, enlaces con icono de descarga.

---

## Como ejecutar el proyecto

Este repositorio no necesita compilacion ni dependencias.

### Opcion 1: Abrir directamente

1.  Clona el repositorio:
    ```bash
    git clone https://github.com/Lamk-S/CSS.git
    cd CSS
    ```
2.  Abre cualquier `index.html` con doble clic:
    - `Basic/B01-Introduction/index.html`
    - `Basic/B02-Colors/index.html`
    - etc.

### Opcion 2: Live Server (recomendado)

1.  Instala la extension Live Server en VS Code
2.  Click derecho sobre `Basic/B03-Typography/index.html` -> Open with Live Server
3.  Navega entre modulos

No se requiere `npm install`. Todo el CSS es vanilla.

---

## Buenas practicas aplicadas

- Uso de `:root` para variables globales de color, radios y sombras
- Metodologia de comentarios por bloques para documentar cada seccion
- Accesibilidad: `aria-labelledby`, contraste adecuado, `rem` para fuentes
- Fuentes con `font-display: swap` para evitar FOIT
- HTML semantico: `header`, `main`, `article`, `section`, `footer`
- CSS sin frameworks, enfocado en entender el fundamento
- Demos visuales aisladas en clases `.box` para no contaminar el estilo base

---

## Roadmap

- [x] B01 - Introduccion, cascada, herencia, especificidad
- [x] B02 - Colores y transparencias
- [x] B03 - Tipografia, @font-face, Google Fonts, iconos
- [x] B04 - Fondos, posicionamiento, multiples fondos, pseudo-clases y pseudo-elementos
- [ ] B05 - Box Model, margin, padding, border, box-sizing
- [ ] B06 - Display, Position y Flexbox
- [ ] B07 - Grid Layout
- [ ] Intermediate - Responsive Design, Animaciones, Transiciones, Variables avanzadas

---

## Requisitos

- Navegador web moderno (Chrome 90+, Firefox 88+, Edge 90+)
- Editor de codigo (VS Code recomendado)
- Extension Live Server opcional pero recomendada

---

## Autor

**Melvin López (Lamk-S)**
GitHub: https://github.com/Lamk-S

---

## Licencia

Este proyecto se distribuye bajo licencia MIT. Libre para uso educativo y como material de referencia.
