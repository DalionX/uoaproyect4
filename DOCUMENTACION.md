# Documentación completa del clon UOAS

## 1. Cómo está documentado el código

Cada archivo de código lleva **un comentario en cada línea**, marcado con `L` y su número:

- En HTML: `<!-- L15: enlace de la marca al primer slide -->`
- En CSS: `/* L3: azul principal de enlaces y botones del original */`
- En JavaScript: `// L34: declaro la función que recibe el contenedor del slider`

Por tanto, **la explicación línea a línea está dentro de los propios archivos**, justo al lado de la instrucción que explica. Este documento es el índice general, el inventario de imágenes y la guía de herramientas.

> También existe **`DOCUMENTACION.pdf`**, la versión en PDF de esta guía (4 páginas, 23.605 bytes). Incluye el cuadro de programas y herramientas en su página 3. Su diseño sigue el modelo del PDF que adjuntaste: colores `#12315A`, `#1D4E89`, `#F4F7FB`, bordes `#B8C4D6`, código `#8A2BE2` y tipografías Helvetica/Courier. La guía reusable está en **`ESTILO_DOCUMENTACION.md`** y la plantilla de generación en **`generar_documento.py`**. Todas las documentaciones futuras deben aplicar ese mismo estilo. En este entorno Python estaba bloqueado por directiva de grupo, así que se usó **`generar_pdf_navegador.html`**: contiene el mismo diseño en JavaScript y permite descargar el PDF desde el navegador. **`verificar_pdf.html`** sirve para comprobar tamaño, cabecera, páginas y fuentes del archivo resultante.

> Para una lectura desde cero, usa **`GUIA_PRINCIPIANTES.md`** (14 secciones: conceptos básicos, apertura del proyecto, mapa de archivos, portada, las 12 páginas internas, CSS, JS, videos, inventario de imágenes, cambios seguros, programas, PDF, GitHub y aviso legal). Su resumen impreso es **`GUIA_PRINCIPIANTES.pdf`** (4 páginas A4, 37.147 bytes) y se regenera con **`generar_guia_principiantes.py`** o, si Python está bloqueado, con **`generar_guia_navegador.html`**. Ambos respetan `ESTILO_DOCUMENTACION.md`.

| Archivo | Líneas | Comentarios |
|---|---:|---|
| `index.html` | 219 | una explicación por línea (L1–L219) |
| `nosotros.html` | 203 | una explicación por línea (L1–L203) |
| `sede-escuela-hogar-ancon-de-ninas.html` | 160 | una explicación por línea (L1–L160) |
| `sede-escuela-hogar-ancon-de-ninos.html` | 160 | una explicación por línea (L1–L160) |
| `sede-hogar-transitorio-san-luis.html` | 160 | una explicación por línea (L1–L160) |
| `sede-cuna-jardin-san-francisco.html` | 160 | una explicación por línea (L1–L160) |
| `sede-cuna-jardin-santa-rosa-04.html` | 160 | una explicación por línea (L1–L160) |
| `sede-nido-aurora.html` | 160 | una explicación por línea (L1–L160) |
| `sede-centro-de-atencion-integral-aurora.html` | 160 | una explicación por línea (L1–L160) |
| `alianzas.html` | 164 | una explicación por línea (L1–L164) |
| `como-ayudar.html` | 160 | una explicación por línea (L1–L160) |
| `galeria.html` | 157 | una explicación por línea (L1–L157) |
| `contacto.html` | 128 | una explicación por línea (L1–L128) |
| `assets/css/styles.css` | 996 | una explicación por línea (L1–L996) |
| `assets/js/main.js` | 227 | una explicación por línea (L1–L167) |
| `INICIAR_SERVIDOR.bat` | 34 | un clic para servir el sitio en `http://localhost:8000` |
| `servir_local.py` / `servir_local.js` | 26 / 46 | servidor mínimo usado por el `.bat` |

> Nota: las líneas en blanco sirven solo de separación visual y no llevan número `L`; por eso el número de línea física puede diferir en una unidad dentro de los archivos escritos a mano. En las fichas de sedes generadas con plantilla, `L` y línea física coinciden exactamente.

---

## 2. Índice por bloques

### `index.html`

| Líneas | Bloque | Función |
|---|---|---|
| L1–L10 | Cabecera del documento | Declara HTML5, idioma, título, icono y hoja de estilos. |
| L11 | `<body>` | Inicia el contenido visible. |
| L12–L44 | Barra superior | Logo, botón de hamburguesa, menú de 7 ítems y submenú de sedes. |
| L45–L109 | Hero | Siete diapositivas: la primera con logo central y las otras con título, foto circular y botón. Puntos de navegación. |
| L110–L113 | Aniversario | Título centrado "91 Aniversario...". |
| L114–L124 | Videos | Dos tarjetas 16:9 con botón de reproducción. |
| L125–L140 | Misión | Texto a la izquierda y collage de tres imágenes a la derecha. |
| L141–L180 | Historia y sedes | Párrafo histórico, slider de 6 fotos, foto decorativa y listado de 7 sedes. |
| L181–L211 | Pie de página | Tres columnas de contacto y franja inferior con copyright y menú. |
| L212–L216 | Modal | Escenario con imagen, `<video>` e `<iframe>`; muestra el reproductor elegido. |
| L217–L219 | Script y cierre | Carga `main.js` al final y cierra el documento. |

### Páginas internas (12 archivos nuevos)

Todas usan la misma cabecera (`L1–L44`, con `body[data-page]` en L11), la misma cabecera azul `.page-hero` (`L45–L53`) y el mismo pie (`site-bottom` + `bottom-bar`). Solo cambia el bloque central y el `data-page` que resalta el enlace del menú.

| Página | Bloques centrales |
|---|---|
| `nosotros.html` | L54–L63 presentación; L64–L77 historia; L78–L102 misión/visión/valores; L103–L132 objetivos; L133–L148 estructura; L149–L162 registros; L163–L168 CTA. |
| `sede-*.html` (7 fichas) | L54–L63 imagen y texto de la sede; L64–L103 seis servicios; L104–L119 seis datos de apoyo; L120–L125 CTA de contacto. |
| `alianzas.html` | L54–L67 texto de alianzas; L68–L107 convenios (6 tarjetas); L108–L123 formas de sumarse; L124–L129 CTA. |
| `como-ayudar.html` | L54–L63 foto de voluntariado; L64–L103 seis formas de ayuda; L104–L119 requisitos; L120–L125 CTA. |
| `galeria.html` | L54–L112 siete álbumes; L113–L118 CTA; L120–L150 pie; L151–L154 visor modal; L155–L157 script. |
| `contacto.html` | L54–L77 datos y formulario; L78–L93 áreas; L95–L128 pie. |

Los enlaces de la portada (`index.html` L23–L40, L59–L104, L170–L176 y L201–L207) apuntan ahora a estos archivos; ya no quedan anclas `#historia` ni `#sedes` como sustitutos de sección.

### `assets/css/styles.css`

| Líneas | Bloque | Función |
|---|---|---|
| L1–L11 | Variables | Paleta de colores centralizada (`--azul`, `--naranja`, etc.). |
| L12–L46 | Reset y contenedor | Quita márgenes por defecto, define `box-sizing` y el ancho máximo. |
| L47–L142 | Cabecera | Barra fija de 80px, logo, menú, desplegable y hamburguesa. |
| L143–L254 | Hero | Slides absolutos, degradado oscuro, títulos, fotos circulares, botones y puntos. |
| L255–L270 | Aniversario y videos | Padding del título y rejilla de dos columnas. |
| L271–L307 | Tarjetas y play | Proporción 16:9, botones circulares y su hover. |
| L308–L368 | Misión | Fondo gris, rejilla 4/8, imágenes superpuestas con marco blanco. |
| L369–L471 | Historia | Cabecera centrada, slider con marco, contador, foto decorativa y lista de sedes. |
| L472–L525 | Pie de página | Fondo azul, iconos SVG, columnas y franja inferior. |
| L526–L551 | Modal | Fondo oscuro, imagen con marco y botón de cierre. |
| L552–L627 | Media queries | Adaptación a 1200, 992, 768, 576 y 1400px. |
| L628–L978 | Páginas internas | `.page-hero`, `.breadcrumb`, `.section`, `.intro-grid`, `.feature-grid`, `.partner-grid`, `.gallery-grid`, `.contact-grid`, `.form-card`, `.sede-index`, `.cta-band`, `.is-active`. |
| L979–L996 | Responsive interno | Una columna en tablet y celular para las rejillas de las páginas nuevas. |

### `assets/js/main.js`

| Líneas | Bloque | Función |
|---|---|---|
| L1–L2 | Arranque | Espera a que el DOM esté listo. |
| L3–L7 | Cabecera | Añade sombra al hacer scroll. |
| L8–L32 | Menú | Abre/cierra hamburguesa, desplegable de Sedes y cierra al pulsar un enlace. |
| L33–L77 | Sliders | Crea puntos, controla el slide activo, flechas, contador y reproducción automática. |
| L78–L101 | Modal | Extrae la foto de portada, abre/cierra la ventana con clic o Escape; tolera páginas sin modal. |
| L102–L108 | Estado activo | Resalta en el menú el enlace cuyo `data-page-link` coincide con `body[data-page]`. |
| L109–L118 | Galería | Al pulsar un álbum abre el visor con una versión `w=1400` de la foto. |
| L119–L135 | Formulario | Valida los campos y muestra un aviso de demostración sin enviar nada a un servidor. |

---

## 3. Inventario de imágenes

### 3.1 Imágenes locales (originales, sin derechos de terceros)

| Archivo | Ubicación exacta | Dónde se usa |
|---|---|---|
| `logo-uoas.svg` | `C:\Users\g0j\Documents\Proyecto predeterminado\uoas-clone\assets\img\logo-uoas.svg` | Cabecera (`index.html` L16) e icono de pestaña (L8). |
| `logo-uoas-blanco.svg` | `C:\Users\g0j\Documents\Proyecto predeterminado\uoas-clone\assets\img\logo-uoas-blanco.svg` | Primera diapositiva del hero (`index.html` L51) y logo decorativo de las 12 páginas internas (L51 de cada una). |

Son SVG escritos a mano: círculo azul, estrella naranja y texto. Puedes editarlos con VS Code, Inkscape o Illustrator.

### 3.2 Fotografías libres (Unsplash)

Todas se sirven desde `images.unsplash.com` con parámetros `auto=format&fit=crop&w=...&q=80`. Licencia Unsplash: uso gratuito, comercial y modificación permitidos, sin obligación de atribución.

| N.º | URL | Dónde se usa |
|---|---|---|
| 1 | `https://images.unsplash.com/photo-1509062522246-3755977927d7?auto=format&fit=crop&w=1920&q=80` | Fondo del hero slide 1 (L49) y slide 7 (L99); slider histórico 1 (L152); Escuela Hogar Niños L56; galería álbum 3. |
| 2 | `https://images.unsplash.com/photo-1503676260728-1c00da094a0b?auto=format&fit=crop&w=1920&q=80` | Fondo del hero slide 2 (L54); slider histórico 2 (L153); Nosotros L56; galería álbum 1. La misión ya no usa foto: es un degradado. |
| 3 | `https://images.unsplash.com/photo-1491013516836-7db643ee125a?auto=format&fit=crop&w=1920&q=80` | Fondo del hero slide 3 (L63); slider histórico 3 (L154). La portada del video 1 ya es la miniatura de YouTube. |
| 4 | `https://images.unsplash.com/photo-1516627145497-ae6968895b74?auto=format&fit=crop&w=600&q=80` | Foto circular del slide 2 (L58), del slide 6 (L94), slider histórico 4 (L155); Escuela Hogar Niñas L56; galería álbum 6. La portada del video 2 ya es la miniatura de YouTube. |
| 5 | `https://images.unsplash.com/photo-1544776193-352d25ca82cd?auto=format&fit=crop&w=600&q=80` | Foto circular de los slides 3 y 7 (L67, L103), foto superpuesta de la misión (L137, `w=700`), slider histórico 5 (L156); Cuna Jardín San Francisco L56; galería álbum 5. |
| 6 | `https://images.unsplash.com/photo-1580582932707-520aed937b7b?auto=format&fit=crop&w=1920&q=80` | Fondo del hero slide 4 (L72), foto decorativa de la historia (L149, `w=500`) y slider histórico 6 (L157). |
| 7 | `https://images.unsplash.com/photo-1571260899304-425eee4c7efc?auto=format&fit=crop&w=1920&q=80` | Fondo del hero slide 5 (L81). |
| 8 | `https://images.unsplash.com/photo-1503454537195-1dcabb73ffb9?auto=format&fit=crop&w=600&q=80` | Foto circular del slide 4 (L76), foto pequeña de la misión (L133, `w=300`). |
| 9 | `https://images.unsplash.com/photo-1596464716127-f2a82984de30?auto=format&fit=crop&w=600&q=80` | Foto circular del slide 5 (L85); Hogar Transitorio San Luis L56; galería álbum 4. |
| 10 | `https://images.unsplash.com/photo-1607453998774-d533f65dac99?auto=format&fit=crop&w=1920&q=80` | Fondo del hero slide 6 (L90); Cuna Jardin Santa Rosa 04 L56. |
| 11 | `https://images.unsplash.com/photo-1587654780291-39c9404d746b?auto=format&fit=crop&w=1000&q=80` | Foto de Nido Aurora L56 y galería álbum 2 (`w=800`). |
| 12 | `https://images.unsplash.com/photo-1576091160399-112ba8d25d1d?auto=format&fit=crop&w=1000&q=80` | Foto del Centro de Atención Integral Aurora L56 y galería álbum 7 (`w=800`). |
| 13 | `https://images.unsplash.com/photo-1559027615-cd4628902d4a?auto=format&fit=crop&w=1000&q=80` | Foto de voluntariado en `como-ayudar.html` L56. |

> Si quieres que funcione sin internet, descarga cada URL y guarda el archivo en `assets/img/`. Después cambia la URL en el HTML por `assets/img/nombre-del-archivo.jpg`. La URL de Unsplash acepta `&w=800` para obtener una versión más ligera.

---

## 4. Programas utilizados y para qué sirven

| Programa / herramienta | Qué hace | Alternativa gratuita |
|---|---|---|
| **OpenCode + navegador integrado (Chromium)** | Permitió abrir la página original, inspeccionar el DOM, leer estilos calculados (colores, fuentes, posiciones, tamaños) y comprobar el clon. | DevTools de Chrome/Firefox (F12). |
| **webfetch** | Descargó el HTML y las hojas de estilo originales para extraer reglas como `padding: 75px 0` o `background: #2058A5`. | `curl` o el propio navegador guardando la página. |
| **Visual Studio Code** | Editor recomendado para modificar los archivos; resalta la sintaxis y permite buscar/reemplazar. | Notepad++, Sublime Text, Notepad del Windows. |
| **HTML5** | Lenguaje de marcado: define la estructura (cabecera, secciones, pies). | — |
| **CSS3** | Define colores, fuentes, formas, tamaños, posiciones y diseño responsive. | — |
| **JavaScript (DOM)** | Crea los puntos de los sliders, cambia de diapositiva, abre el menú móvil y el modal. | — |
| **SVG** | Formato vectorial usado para los logos y los iconos del pie; escala sin perder calidad y lo escribe un editor de texto. | Inkscape (editor gráfico de SVG). |
| **Unsplash** | Banco de fotografías con licencia gratuita. | Pexels, Pixabay. |
| **Python `http.server` / Live Server** | Opcional: sirve la carpeta por HTTP para probar como en un servidor real. | Abrir `index.html` directamente. |

### Flujo de trabajo seguido

1. **Analizar:** se abrió `https://www.uoas.org.pe/` en el navegador y se leyó su estructura real (Joomla + SP Page Builder + plantilla Edulif).
2. **Extraer estilos:** se tomaron los valores exactos: azul `#0560a9`, texto `#185587`, gris `#718390`, pie `#2058A5`, fuentes Inter/Arial/Open Sans, hero de 880px y padding de 110px/170px en la misión.
3. **Sustituir imágenes:** se eliminaron las fotos originales y se usaron fotografías libres de Unsplash; los logos se redibujaron en SVG.
4. **Construir:** se escribieron `index.html`, `styles.css` y `main.js` con un comentario por línea.
5. **Ampliar:** se leyeron las 12 URLs internas del sitio original y se creó una página local para cada una con la misma cabecera, pie y paleta.
6. **Conectar:** se sustituyeron los anclas del menú y del pie por rutas reales (`nosotros.html`, `sede-*.html`, `alianzas.html`, `como-ayudar.html`, `galeria.html`, `contacto.html`).
7. **Completar comportamiento:** se añadió el resaltado de página activa, el visor de la galería y la validación del formulario en `main.js`.
8. **Verificar:** se comprobó que las 13 páginas cargan sin errores de consola, que los enlaces son locales y que sliders, menú, modal, galería y formulario responden.

---

## 5. Guía rápida de modificación

| Quieres cambiar... | Ve a... |
|---|---|
| Los colores | `styles.css` L1–L11 |
| El texto de la misión | `index.html` L130 |
| Las fotos del hero | `index.html` L49, L54, L63, L72, L81, L90, L99 |
| La velocidad de los sliders | `index.html` L46 (`5000`) y L150 (`4000`) |
| El número de diapositivas | Añade/quita un `<article class="slide">` en `index.html`; el JS crea los puntos automáticamente. |
| El listado de sedes | `index.html` L28–L34 y L170–L176 |
| El pie de página | `index.html` L181–L211 y `styles.css` L472–L525 |
| El comportamiento en móvil | `styles.css` L552–L627 |
| El logo | Edita los dos SVG de `assets/img/` |
| El texto de Nosotros | `nosotros.html` L54–L162 |
| Una ficha de sede | `sede-*.html` L49–L119 (resumen, servicios y datos) |
| Los convenios | `alianzas.html` L68–L123 |
| Las formas de ayuda | `como-ayudar.html` L64–L119 |
| Los álbumes | `galeria.html` L60–L110 |
| El formulario | `contacto.html` L62–L74 y `main.js` L119–L135 |
| El resaltado del menú | `main.js` L102–L108 y `styles.css` L976–L978 |
| Los estilos de las páginas internas | `styles.css` L628–L996 |

---

## 5b. Ampliación de videos y accesibilidad

**Videos en línea, sin pantalla superpuesta.** Los botones `▶` de `index.html` L118, L121 y L135 ya no abren el modal: cada video se reproduce dentro de su propio recuadro. El modal queda reservado para la galería de fotos.

| Video | Origen | Portada antes del play | Elemento | Crédito |
|---|---|---|---|---|
| 1 | YouTube `mFhIfWReCLU` | Miniatura `i.ytimg.com/vi/.../hqdefault.jpg` | `iframe` con `autoplay=1` (L94) | `title` del iframe |
| 2 | YouTube `vIoNbwq3mKM` | Miniatura `i.ytimg.com/vi/.../hqdefault.jpg` | `iframe` con `autoplay=1` (L94) | `title` del iframe |
| 3 | `assets/video/video-03.mp4` | Primer fotograma del propio video | `<video controls playsinline>` (L90) | `aria-label` del video |

El recuadro vertical mide `380 × 676 px` y usa `aspect-ratio: 9 / 16` (`styles.css` L1060–L1074), igual que el archivo 576×1024. No hay fondo negro a los lados ni fotos decorativas: se eliminaron `mission-accent` y `mission-overlap`. Tampoco hay atributo `poster`: `main.js` L159b–L159d usa `loadeddata` para colocar el video en `currentTime = 0.1`, muestra su propio fotograma, vuelve a `0` al pulsar play y devuelve el botón `▶` cuando termina. Si el archivo local no está copiado, `main.js` L161–L162b prueba `Descargas/VideoTiktok1.mp4`, luego `Descargas/videoTiktok.mp4` y después ofrece un selector dentro del recuadro. Instrucciones en `assets/video/LEEME.txt`.

En YouTube, `main.js` L81b–L81s carga la API oficial `youtube.com/iframe_api`, crea un `YT.Player` sobre cada iframe y usa `onStateChange` con `YT.PlayerState.ENDED` para devolver el botón y limpiar el recuadro. Como respaldo, L100b–L100i también detecta el final por mensajes `infoDelivery` cuando el progreso llega al final.

YouTube rechaza los `iframe` con **error 153** cuando la página se abre con `file://`: el navegador no envía referidor. No es un bloqueo por derechos. Por eso `main.js` L92 detecta `location.protocol === 'file:'` y muestra dentro de la tarjeta un aviso que indica ejecutar `INICIAR_SERVIDOR.bat` y abrir `http://localhost:8000/index.html`, además del enlace “Abrir en YouTube”. Ese `.bat` usa `servir_local.py` (o `servir_local.js` si no hay Python) y da el origen `http` que YouTube exige; con `http://` o `https://` los videos arrancan automáticamente. Para reproducirlos sin internet habría que descargarlos y servirlos como archivos locales.

**Accesibilidad.** `index.html` L11 incluye “Saltar al contenido”; `main.js` L165–L167 lo añade también a las páginas internas. `styles.css` L998–L1010 da foco visible y estilo al enlace; L1057 respeta `prefers-reduced-motion`. Los sliders se pausan con mouse o teclado (`main.js` L74 y L136–L144). El modal mueve el foco al cierre y lo devuelve al botón pulsado.

**Rendimiento.** Las fotos fuera de la primera pantalla llevan `loading="lazy"`, `srcset` y `sizes` en `index.html` (9 imágenes) y `galeria.html` (7 imágenes). No se copiaron las fotos de Unsplash al proyecto: se siguen sirviendo desde internet.

**Galería.** `main.js` L145–L156 crea dos flechas dentro de `.gallery-grid`; recorren los siete álbumes de forma circular usando el índice guardado en `modal-image.dataset.indice`. No se añadieron filtros por sede.

**Enlaces.** Se comprobaron los `href` locales de las 13 páginas: todos apuntan a archivos existentes. Las páginas HTML se mantienen como 12 archivos independientes; no se centralizaron en JSON.

---

## 6. Aviso

Este clon se realizó con fines de **estudio y práctica**. No reproduce los archivos multimedia originales de la institución. Los dos videos de YouTube se usan con derechos aportados por la institución y el video vertical es un archivo local proporcionado para este proyecto. Si deseas publicarlo, sustituye los textos e imágenes por contenidos propios o cuenta con autorización expresa del titular del sitio original.
