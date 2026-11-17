# Curso de CSS — Apuntes Técnicos y Laboratorio Práctico

[![HTML5](https://img.shields.io/badge/HTML5-Semántico-E34F26?style=flat-square&logo=html5&logoColor=white)](https://developer.mozilla.org/es/docs/Web/HTML)
[![CSS3](https://img.shields.io/badge/CSS3-Moderno_&_Vanilla-1572B6?style=flat-square&logo=css3&logoColor=white)](https://developer.mozilla.org/es/docs/Web/CSS)
[![Arquitectura](https://img.shields.io/badge/Enfoque-Mobile_First_&_A11y-10B981?style=flat-square)](https://github.com/Lamk-S/CSS)
[![Progreso](https://img.shields.io/badge/Módulos-12%2F12_Completados-2563EB?style=flat-square)](#roadmap-del-curso)
[![Licencia](https://img.shields.io/badge/Licencia-MIT-64748B?style=flat-square)](#licencia)

Repositorio de ingeniería frontend dedicado al aprendizaje progresivo de **CSS moderno**, desde sus fundamentos hasta arquitectura de layouts (Flexbox y Grid), diseño responsivo y animaciones aceleradas por GPU. Cada módulo funciona como una pieza de documentación interactiva autocontenida.

**Repositorio:** [github.com/Lamk-S/CSS](https://github.com/Lamk-S/CSS)

---

## Descripción y Filosofía

Este proyecto centraliza apuntes estructurados bajo una premisa de **aprender construyendo**:

- **Teoría aplicada:** Cada `index.html` presenta el concepto técnico, fragmentos de código listos para producción y laboratorios visuales interactivos en tiempo real.
- **Código autodocumentado:** Cada `css/style.css` está comentado por bloques arquitectónicos explicando el *porqué* detrás de cada decisión de diseño, rendimiento y accesibilidad (a11y).
- **Cero dependencias:** Todo está construido con HTML5 semántico y CSS3 nativo, sin frameworks ni preprocesadores, para dominar el estándar web real.

### Niveles del programa

| Nivel | Enfoque técnico | Módulos |
| :--- | :--- | :--- |
| **`Basic/`** | Fundamentos del lenguaje: cascada, especificidad, modelos de color, tipografía web, fondos y pseudo-selectores. | `B01` – `B04` |
| **`Intermediate/`** | Arquitectura de interfaz: unidades relativas, modelo de caja, posicionamiento, Flexbox, CSS Grid, diseño responsivo y *motion UI*. | `I01` – `I08` |

---

## Objetivos de Aprendizaje

1. Comprender el motor de renderizado de CSS: **cascada, herencia y especificidad**.
2. Gestionar sistemas de color, tipografía legible (`@font-face`, escalas fluidas) y recursos visuales.
3. Dominar las unidades relativas (`rem`, `em`, `ch`, `vw/vh`) y su impacto directo en la accesibilidad.
4. Controlar el **Box Model**, el flujo del documento, el posicionamiento y los contextos de apilamiento (`z-index`).
5. Construir arquitecturas unidimensionales con **Flexbox** y bidimensionales con **CSS Grid** (`fr`, `minmax()`, `grid-template-areas`).
6. Implementar interfaces **Mobile-First**, tipografía fluida con `clamp()` y adaptabilidad por componente con **Container Queries**.
7. Desarrollar micro-interacciones a **60fps** respetando las preferencias de movimiento del usuario (`prefers-reduced-motion`).

---

## Stack y Estándares Aplicados

- **Lenguajes:** HTML5 semántico, CSS3 moderno (Vanilla).
- **Arquitectura CSS:** Design Tokens mediante *Custom Properties* (`:root`), metodología *Mobile-First* (`min-width`), `box-sizing: border-box` global.
- **Sistemas de Layout:** Flujo normal, `float`/`clearfix`, **Flexbox**, **CSS Grid** (`repeat()`, `auto-fit`, `minmax()`, `grid-template-areas`).
- **Funciones y APIs modernas:** `clamp()`, `calc()`, `@container` (*Container Queries*), `backdrop-filter`, `@keyframes`.
- **Tipografía e Iconografía:** `@font-face` local (`.woff2` / `.woff` con `font-display: swap`), Google Fonts (`Inter`, `Merriweather`) y Font Awesome 6.
- **Entorno recomendado:** Visual Studio Code + extensión *Live Server* y navegadores modernos (Chrome, Firefox, Edge).

---

## 📂 Estructura del Repositorio

```text
CSS/
├── Basic/
│   ├── B01-Introduction/          # Sintaxis, cascada, herencia y especificidad
│   │   ├── index.html
│   │   └── css/styles.css
│   ├── B02-Colors/                # Modelos de color, canal alfa vs opacity y gradientes
│   │   ├── index.html
│   │   └── css/styles.css
│   ├── B03-Typography/            # @font-face, Google Fonts, unidades tipográficas y legibilidad
│   │   ├── index.html
│   │   ├── css/style.css
│   │   └── fonts/
│   └── B04-Backgrounds-Pseudo/    # Fondos múltiples, overlays, pseudoclases y pseudoelementos
│       ├── index.html
│       └── css/style.css
│
├── Intermediate/
│   ├── I01-CSS-Units/             # Unidades absolutas, relativas (em/rem/ch) y viewport
│   │   ├── index.html
│   │   └── css/style.css
│   ├── I02-CSS-Layouts/           # Flujo normal, display, float, clearfix y columnas
│   │   ├── index.html
│   │   └── css/style.css
│   ├── I03-Box-Model/             # Capas de caja, shorthand y content-box vs border-box
│   │   ├── index.html
│   │   └── css/style.css
│   ├── I04-Positioning/           # static, relative, absolute, fixed, sticky y z-index
│   │   ├── index.html
│   │   └── css/style.css
│   ├── I05-Flexbox/               # Layout unidimensional, ejes, alineación y patrones UI
│   │   ├── index.html
│   │   └── css/style.css
│   ├── I06-Grid/                  # Layout bidimensional, fr, repeat(), minmax() y áreas
│   │   ├── index.html
│   │   └── css/style.css
│   ├── I07-Responsive/            # Mobile-First, breakpoints, clamp() y Container Queries
│   │   ├── index.html
│   │   └── css/style.css
│   └── I08-Animations/            # Transiciones, transformaciones GPU, @keyframes y 60fps
│       ├── index.html
│       └── css/style.css
│
└── README.md

```

---

## 📚 Contenido Detallado por Módulo

### Nivel Básico (`Basic/`)

* **Conceptos:** Sintaxis `selector { propiedad: valor; }`, selectores de etiqueta, grupales (`h1, h2, h3`), clase (`.class`) e ID (`#id`), hojas de estilo del navegador (*User Agent Styles*).
* **Motor de resolución:** Orden de cascada, cálculo de especificidad (`inline > ID > clase > etiqueta`) y propiedades heredables (`color`, `font-family`).
* **Laboratorios:** Competencia de reglas `p` por orden de aparición y resolución de conflictos mediante `p#miIdentificador`.

* **Conceptos:** Palabras clave, HEX (6 y 8 dígitos), `rgb()`/`rgba()`, `hsl()`/`hsla()`, centralización de paleta mediante variables CSS en `:root`.
* **Diferencia crítica:** Canal alfa (`rgba`) frente a la propiedad `opacity` (herencia de opacidad en elementos hijos).
* **Laboratorios:** Comparativa visual entre `.bg-alfa` (fondo translúcido con texto 100% legible) y `.bg-opacity` (degradación de contraste en todo el bloque), además de efectos `backdrop-filter: blur()`.

* **Conceptos:** *Web Safe Fonts*, carga local mediante `@font-face` (`Atkinson Hyperlegible` en `.woff2` y `Grandstander` en `.woff`) con `font-display: swap` para evitar *FOIT*.
* **Escalabilidad y UX:** Unidades `px` vs `em` vs `rem`, medida óptima de lectura (`max-width: 65ch`), interlineado (`line-height: 1.5 - 1.75`) e iconografía con Font Awesome.
* **Laboratorios:** Comparativa de escalado `16px` vs `1.5rem` y bloque editorial optimizado para lectura prolongada.

* **Conceptos:** `background-image`, `background-repeat`, `background-position`, `background-size` (`cover` vs `contain`) y capas múltiples (`linear-gradient` + imagen como *overlay* de contraste).
* **Interactividad y decoración:** Pseudoclases de estado (`:link`, `:visited`, `:hover`, `:active` bajo la regla *LoVe HAte*) y pseudoelementos (`::before`, `::after`).
* **Laboratorios:** Tarjetas con *overlay* legible, botones interactivos y enlaces enriquecidos con iconos SVG inyectados por CSS.

---

### Nivel Intermedio (`Intermediate/`)

* **Conceptos:** Unidades absolutas (`px`) frente a relativas tipográficas (`em`, `rem`, `ch`) y relativas al viewport (`vw`, `vh`, `vmin`, `vmax`).
* **Laboratorios:** Demostración del efecto compuesto ("bola de nieve") en `em` anidados (`1.2em → 1.44em → 1.728em`) frente a la estabilidad de `rem`, y contenedores fluidos basados en `50vw`.

* **Conceptos:** Restricciones fluidas (`max-width` + `margin: auto`), comportamiento de `display` (`block` vs `inline`), posicionamiento flotante (`float`) y solución al colapso de contenedores mediante `clearfix`.
* **Laboratorios:** Artículos estilo editorial con imágenes flotantes y grillas clásicas de 3 columnas adaptables.

* **Conceptos:** Anatomía de 4 capas (*Content → Padding → Border → Margin*), sintaxis *shorthand* horaria y reset universal de `box-sizing: border-box`.
* **Laboratorios:** Diagrama interactivo inspirado en Chrome DevTools y comparativa directa entre `content-box` (desbordamiento por suma de padding/borde) y `border-box` (dimensiones exactas).

* **Conceptos:** Valores de `position` (`static`, `relative`, `absolute`, `fixed`, `sticky`), el patrón maestro **Padre `relative` + Hijo `absolute**`, y control del eje Z mediante `z-index`.
* **Laboratorios:** Cabeceras `sticky` dentro de contenedores con scroll, tarjetas con *badges* flotantes absolutos y superposición de capas por índice Z.

* **Conceptos:** Contenedor e ítems flexibles (`display: flex`), control de ejes (*Main Axis* y *Cross Axis*) con `flex-direction`, distribución con `justify-content`, alineación transversal con `align-items`, espaciado nativo con `gap`, envoltura (`flex-wrap`) y factores de flexibilidad (`flex-grow`, `flex-shrink`, `flex-basis`, `flex: 1`).
* **Laboratorios:** Comparativas de distribución (`space-between`, `space-evenly`), centrado absoluto, barra de navegación (*navbar*), tarjetas con igualación automática de altura (`stretch`) y distribución proporcional (`flex: 1` vs `flex: 2`).

* **Conceptos:** Grillas bidimensionales (`display: grid`), unidad fraccionaria `fr`, funciones `repeat()` y `minmax()`, grillas intrínsecas (`auto-fit`), expansión de celdas con `span`, trazado semántico mediante `grid-template-areas` y centrado con `place-items: center`.
* **Laboratorios:** Grilla responsiva automática sin media queries, galería asimétrica tipo *Pinterest / Dashboard* y estructura completa **Holy Grail Layout** adaptable a móvil.

* **Conceptos:** Arquitectura *Mobile-First* (`min-width`), definición de *breakpoints* basados en contenido, tipografía fluida con `clamp()`, grillas intrínsecas (`auto-fit` + `minmax()`) y **Container Queries** (`container-type: inline-size` y `@container`).
* **Laboratorios:** Navbar responsivo *CSS-only* (patrón `:checked`), grid adaptable sin media queries y tarjeta redimensionable en vivo gobernada por `@container`.

* **Conceptos:** Interpolación con `transition`, curvas `cubic-bezier()`, transformaciones 2D/3D aceleradas por GPU (`translate`, `scale`, `rotate`), secuencias con `@keyframes` y accesibilidad mediante `@media (prefers-reduced-motion: reduce)`.
* **Laboratorios:** Pista comparativa de curvas de aceleración, escenarios anti-*jitter* para transformaciones, *spinners*, indicadores de pulso y *Skeleton Shimmer* para carga percibida.

---

## Cómo Ejecutar en Local

Este proyecto no requiere compilación ni instalación de paquetes.

1. **Clonar el repositorio:**
```bash
git clone [https://github.com/Lamk-S/CSS.git](https://github.com/Lamk-S/CSS.git)
cd CSS

```


2. **Abrir con Live Server (Recomendado):**
* Abre la carpeta en **Visual Studio Code**.
* Haz clic derecho sobre cualquier archivo `index.html` (por ejemplo, `Intermediate/I06-Grid/index.html`) y selecciona **Open with Live Server**.


3. **Apertura directa:**
* También puedes abrir cualquier archivo `index.html` directamente en tu navegador web.



---

## Buenas Prácticas Transversales

* **Consistencia visual:** Todos los módulos comparten un sistema de tokens (`--color-primary`, `--radius-md`, `--shadow-card`) para mantener coherencia editorial.
* **Aislamiento de componentes:** Los ejemplos interactivos viven encapsulados dentro de contenedores `.box` para evitar colisiones de estilos.
* **Accesibilidad (a11y):** Uso de atributos ARIA (`aria-labelledby`, `role="status"`), navegación por teclado (`:focus-visible`) y soporte nativo para reducción de movimiento.

---

## Roadmap del Curso

* [x] **B01** — Introducción, cascada, herencia y especificidad
* [x] **B02** — Colores, canal alfa y transparencias
* [x] **B03** — Tipografía web, `@font-face`, Google Fonts e iconografía
* [x] **B04** — Fondos, overlays y pseudo-selectores
* [x] **I01** — Unidades de medida (`px`, `em`, `rem`, `ch`, `vw`, `vh`)
* [x] **I02** — Layouts tradicionales (`display`, `float`, `clearfix`)
* [x] **I03** — Box Model y `box-sizing`
* [x] **I04** — Posicionamiento y `z-index`
* [x] **I05** — Flexbox (alineación unidimensional y distribución dinámica)
* [x] **I06** — CSS Grid (arquitectura bidimensional, `minmax()` y `grid-template-areas`)
* [x] **I07** — Responsive Design, `clamp()` y Container Queries
* [x] **I08** — Transiciones, Transformaciones GPU y Animaciones `@keyframes`

---

## Autor

**Melvin López (`Lamk-S`)**

* GitHub: [@Lamk-S](https://github.com/Lamk-S)

---

## Licencia

Licencia MIT - Uso libre con fines educativos y de referencia técnica.