# Clon de estudio — UOAS

Copia visual de `https://www.uoas.org.pe/` hecha con **HTML + CSS + JavaScript puro**, sin frameworks ni dependencias. Reproduce colores, tipografías, formas, tamaños, posiciones y comportamiento de los sliders. Incluye también las 12 páginas internas (Nosotros, siete sedes, Alianzas, Cómo Ayudar, Galería y Contacto), todas enlazadas desde el menú y el pie. Las fotografías originales se sustituyeron por imágenes libres; el logo es un SVG creado para este proyecto.

## Cómo verlo

1. Abre la carpeta `uoas-clone` en tu editor de código.
2. **Para que los videos de YouTube reproduzcan, haz doble clic en `INICIAR_SERVIDOR.bat`.** Se abre solo `http://localhost:8000/index.html`. No instales nada: el script usa Python o Node si están disponibles.
3. El doble clic en `index.html` sigue sirviendo para ver el diseño y el video vertical, pero YouTube muestra el error 153 (falta de referidor). En ese caso la tarjeta ofrece un enlace “Abrir en YouTube”.
4. Alternativas: `python -m http.server 8000` en esta carpeta, o la extensión **Live Server** de VS Code.

## Estructura

```
uoas-clone/
├── INICIAR_SERVIDOR.bat        → un clic: abre el sitio en http://localhost:8000
├── servir_local.py / .js       → servidor mínimo usado por el .bat
├── index.html                  → portada: sliders, aniversario, 3 videos, misión e historia
├── nosotros.html               → página institucional
├── sede-*.html (7 archivos)    → fichas de las siete sedes
├── alianzas.html               → convenios y alianzas
├── como-ayudar.html            → formas de colaborar
├── galeria.html                → álbumes con visor de imágenes
├── contacto.html               → datos y formulario de demostración
├── assets/css/styles.css       → estilos, colores y media queries
├── assets/js/main.js           → sliders, menú, modal, galería y formulario
├── assets/img/logo-uoas.svg        → logo para la cabecera (original)
├── assets/img/logo-uoas-blanco.svg → logo para el hero (original)
├── assets/video/LEEME.txt       → instrucciones para video-03.mp4 (vertical)
├── DOCUMENTACION.md             → explicación línea a línea e inventario de imágenes
├── DOCUMENTACION.pdf            → la misma documentación en PDF, con el cuadro de programas
├── GUIA_PRINCIPIANTES.md        → guía para alguien que no sabe código (14 secciones)
├── GUIA_PRINCIPIANTES.pdf       → resumen impreso de esa guía (4 páginas A4)
├── generar_documento.py         → plantilla Python para regenerar DOCUMENTACION.pdf
├── generar_guia_principiantes.py → plantilla Python para regenerar GUIA_PRINCIPIANTES.pdf
├── generar_pdf_navegador.html   → alternativa en JS si Python está bloqueado
├── generar_guia_navegador.html  → alternativa en JS para la guía para principiantes
├── verificar_pdf.html           → comprobador de tamaño, páginas y fuentes del PDF
├── ESTILO_DOCUMENTACION.md      → guía de estilo extraída del PDF de referencia
└── README.md                    → este archivo
```

## Documentación en PDF

Abre `DOCUMENTACION.pdf` para ver el resumen impreso en 4 páginas:

1. Qué se hizo y mapa de archivos (portada, páginas internas, CSS y JS).
2. Inventario de imágenes (SVG propios y fotos de Unsplash, con su página).
3. **Cuadro de programas y herramientas utilizadas** + flujo de trabajo.
4. Guía rápida de modificación, enlaces internos y aviso legal.

El PDF sigue el **modelo visual extraído del PDF de referencia** que adjuntaste: A4, Helvetica/Helvetica-Bold/Courier, tablas azules con filas alternas y código violeta. Los detalles están en `ESTILO_DOCUMENTACION.md`; las futuras documentaciones deben usar esa misma guía. Para regenerarlo, ejecuta `python generar_documento.py` en esta carpeta. Si Python está bloqueado, abre `generar_pdf_navegador.html`, pulsa *Descargar PDF* y guarda el archivo como `DOCUMENTACION.pdf`; con `verificar_pdf.html` puedes confirmar que tiene 4 páginas, 23.605 bytes, `xref` válido y las tres fuentes del modelo.

## Guía para principiantes

Abre `GUIA_PRINCIPIANTES.md` si es la primera vez que trabajas con este proyecto. Explica, sin suponer conocimientos previos, qué es HTML/CSS/JS, cómo abrir el sitio, qué contiene cada una de las 13 páginas, dónde está cada imagen, cómo se abren los tres videos, cómo hacer cambios seguros y cómo publicar en GitHub.

También se entrega `GUIA_PRINCIPIANTES.pdf`: un resumen impreso de 4 páginas A4 con el mismo modelo visual obligatorio. Se regenera con `python generar_guia_principiantes.py`; si Python está bloqueado, abre `generar_guia_navegador.html` y pulsa *Descargar PDF*. Verifícalo con `verificar_pdf.html` (4 páginas, 37.147 bytes, `xref` válido y fuentes Helvetica/Helvetica-Bold/Courier).

## Videos

Los tres botones `▶` reproducen el video **dentro de su propio recuadro**, sin pantalla superpuesta. El botón desaparece mientras se reproduce y vuelve a aparecer al terminar. El modal queda reservado para ampliar las fotos de la galería.

| Botón | Contenido | Portada antes del play | Internet |
|---|---|---|---|
| Video 1 | YouTube `mFhIfWReCLU` en `iframe` privado | Miniatura real del video (`i.ytimg.com`) | Sí |
| Video 2 | YouTube `vIoNbwq3mKM` en `iframe` privado | Miniatura real del video (`i.ytimg.com`) | Sí |
| Video de la misión | `assets/video/video-03.mp4`, vertical 9:16 | Primer fotograma del propio video | No |

Los dos videos de YouTube arrancan automáticamente al pulsar `▶` cuando la página se abre con `http://` o `https://`. El crédito está en el atributo `title` del `iframe`; no se añadió texto visible. Los enlaces fueron aportados con derechos de la institución.

**Solución al error 153 de YouTube:** el doble clic (`file://`) no envía referidor y YouTube rechaza el `iframe`. Ejecuta `INICIAR_SERVIDOR.bat` y usa `http://localhost:8000/index.html`: allí los dos videos arrancan solos al pulsar `▶`, con sonido si el navegador lo permite, y el botón vuelve al terminar gracias a la API oficial `youtube.com/iframe_api`. Con `file://` la tarjeta muestra el aviso y el enlace “Abrir en YouTube”. Si necesitas que funcionen sin internet, descarga los dos videos y dime sus rutas para integrarlos como archivos locales.

**Importante:** el video comprimido `VideoTiktok1.mp4` pesa 5.085.898 bytes (4,85 MiB) y entra en el límite de 5 MiB, pero las herramientas disponibles no pueden escribir binarios dentro del proyecto. Copia ese archivo a `assets/video/` con el nombre `video-03.mp4`. Mientras tanto, la página prueba esa ruta, luego `Descargas/VideoTiktok1.mp4`, luego el original `videoTiktok.mp4` y, si fallan, muestra un selector dentro del recuadro. No hay fotos de Unsplash asociadas al video vertical: solo su primer fotograma y un degradado de fondo. Detalles en `assets/video/LEEME.txt`.

## Mejoras incluidas

- **Accesibilidad:** enlace “Saltar al contenido”, `:focus-visible`, navegación con teclado y cierre del modal con `Escape`; los sliders se pausan con el mouse o el foco y respetan `prefers-reduced-motion`.
- **Rendimiento:** `loading="lazy"`, `srcset` y `sizes` en las fotos de `index.html` y `galeria.html`; las imágenes siguen viniendo de Unsplash.
- **Galería:** flechas anterior/siguiente para recorrer los siete álbumes, sin filtros por sede.
- **Enlaces:** revisión de los `href` internos de las 13 páginas; no se encontraron rutas rotas.

## Programas y herramientas utilizados

| Herramienta | Para qué se usó |
|---|---|
| **Navegador integrado de OpenCode (Chromium)** | Abrir la web original, leer su DOM, estilos computados, posiciones y textos; comprobar el resultado. |
| **webfetch** | Descargar el HTML original y sus reglas CSS para analizarlas. |
| **Visual Studio Code (recomendado)** | Editar HTML, CSS y JS. Cualquier editor de texto sirve: Notepad++, Sublime Text, Atom. |
| **Google Chrome / Firefox / Edge** | Probar el clon y la vista responsive. |
| **Python 3 o Live Server (opcional)** | Servir la carpeta por HTTP. |
| **SVG (XML)** | Crear los dos logos originales sin depender de imágenes con copyright. |
| **Unsplash** | Fuente de las fotografías bajo licencia gratuita. |

No se usó WordPress, Joomla ni gestores de paquetes: todo es estático.

## Cómo modificarlo

- **Cambiar colores:** edita las variables en `styles.css`, líneas 1-11 (`--azul`, `--naranja`, etc.).
- **Cambiar textos:** busca el texto en `index.html` y reemplázalo; los textos institucionales están en las líneas 112, 130, 144-145 y 186-194.
- **Cambiar fotos:** sustituye las URLs de Unsplash en `index.html` por tus archivos locales, por ejemplo `assets/img/mi-foto.jpg`. El inventario completo está en `DOCUMENTACION.md`.
- **Cambiar la velocidad del slider:** modifica `data-interval="5000"` en la línea 46 de `index.html` (milisegundos).
- **Añadir una sede:** copia `sede-escuela-hogar-ancon-de-ninas.html`, cambia el título, el `data-page` y los textos; luego añade el enlace en el menú (L28-L34) y en el listado del pie de todas las páginas.
- **Cambiar el texto de una sección interna:** abre el HTML correspondiente y edita los bloques `page-hero` y `section` (por ejemplo `alianzas.html` L46-L123).
- **Añadir un álbum:** copia un bloque `gallery-card` en `galeria.html` (L61-L109) y cambia la URL de Unsplash y la leyenda.
- **Cambiar tamaños responsive:** ajusta las media queries al final de `styles.css` (L552-L627 y L979-L996 para las páginas internas).

## Nota legal

Este proyecto es una **copia de estudio** de la estructura visual. No incluye los logotipos ni fotografías originales de la institución. Las fotos proceden de Unsplash (licencia gratuita que permite uso comercial y modificación sin atribución obligatoria) y los SVG son creaciones originales hechas para este clon. Los dos videos de YouTube se usan con derechos aportados por la institución y el video vertical es un archivo local proporcionado para este proyecto.
