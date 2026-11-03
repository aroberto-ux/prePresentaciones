# HTML Presentation · Versión para vídeo

<p align="center"><strong>Convierte guiones literales o guiones de dirección en prompts listos para que una IA genere presentaciones HTML</strong></p>

<p align="center">
  <a href="https://juanjuanjie.github.io/html-presentation/">Usar en línea</a> ·
  <a href="https://www.bilibili.com/video/BV1HToiBCEwg">Tutorial del proyecto</a> ·
  <a href="https://www.bilibili.com/video/BV1g5j46iE5C">Por qué usar HTML en lugar de PPT</a>
</p>

HTML Presentation es una herramienta estática y respetuosa con la privacidad para crear presentaciones HTML y storyboards de vídeo. En la página de inicio puedes importar un guion, elegir el modo de generación y una plantilla visual, y obtener un prompt completo con el guion, el código fuente de la plantilla y las reglas de generación, para dárselo después a tu agente de IA habitual y que genere el HTML final.

- **HTML de charla**: extrae las ideas del guion literal y organiza las páginas según el contenido; ideal para clases, charlas y presentaciones manuales.
- **HTML de dirección**: genera estrictamente una página por plano según el guion de dirección, conservando la locución, la imagen y los requisitos de animación de cada plano.
- **Lectura local**: el guion se procesa solo en la página actual del navegador; no se sube ni se guarda de forma persistente.
- **Pensado para vídeo**: las plantillas usan un lienzo 16:9 y permiten exportar storyboards PNG de 1920×1080 por lotes.

## Páginas en línea

El archivo [`index.html`](./index.html) de la raíz es la entrada de GitHub Pages e incluye cuatro páginas:

- **Inicio**: elige HTML de charla o de dirección, importa el guion y prepara el prompt completo para el agente.
- **Plantillas**: explora 3 plantillas con sus paletas y despliega el panel de edición para ajustar colores y tipografías en tiempo real.
- **Animaciones**: consulta componentes de animación reutilizables adecuados para guiones de dirección.
- **README**: lee esta documentación directamente en el sitio.

Este sitio no usa claves de modelos ni llama automáticamente a ninguna IA. Tras generar el prompt, cópialo en el agente de IA que uses y revisa página por página el contenido, los desbordamientos y la legibilidad.

## Plantillas actuales

| Plantilla | Páginas | Características visuales | Paleta |
|---|---:|---|---|
| **Doodle Cream** | 15 | Papel blanco y amarillo cálido, avatar circular de Juanjuanjie, flujos irregulares, páginas de transición de serie | Papel blanco y amarillo cálido |
| **BlockFrame** | 13 | Bordes negros gruesos, bloques de color caramelo, neobrutalismo | Caramelo claro, papel retro, caramelo oscuro |
| **Professional** | 15 | Espacios en blanco sobrios, tipografía tecnológica, estructura de informe | Crema y azul cobalto, púrpura y oro oscuro, negro y verde profesional |

Las tarjetas de plantilla, el panel de edición y el generador comparten los mismos datos de plantilla. La edición de colores solo sobrescribe variables CSS mediante parámetros de URL y no modifica los archivos fuente de las plantillas.

## Vista previa

Todas las imágenes se capturan directamente del HTML de las plantillas actuales y están unificadas a 1920×1080. Cada plantilla muestra 3 páginas representativas para evitar portadas de distintos tamaños.

### Doodle Cream

<table>
  <tr>
    <td width="33.33%"><img src="assets/readme-previews/doodle-cream-01.png" alt="Portada de Doodle Cream" width="100%"></td>
    <td width="33.33%"><img src="assets/readme-previews/doodle-cream-02.png" alt="Página de presentación de la plataforma de Doodle Cream" width="100%"></td>
    <td width="33.33%"><img src="assets/readme-previews/doodle-cream-03.png" alt="Página de flujo de Doodle Cream" width="100%"></td>
  </tr>
</table>

### BlockFrame

<table>
  <tr>
    <td width="33.33%"><img src="assets/readme-previews/blockframe-01.png" alt="Portada de BlockFrame" width="100%"></td>
    <td width="33.33%"><img src="assets/readme-previews/blockframe-02.png" alt="Página de características de BlockFrame" width="100%"></td>
    <td width="33.33%"><img src="assets/readme-previews/blockframe-03.png" alt="Página de línea de tiempo de BlockFrame" width="100%"></td>
  </tr>
</table>

### Professional

<table>
  <tr>
    <td width="33.33%"><img src="assets/readme-previews/professional-01.png" alt="Portada de Professional" width="100%"></td>
    <td width="33.33%"><img src="assets/readme-previews/professional-02.png" alt="Página de análisis de Professional" width="100%"></td>
    <td width="33.33%"><img src="assets/readme-previews/professional-03.png" alt="Página de flujo de Professional" width="100%"></td>
  </tr>
</table>

## Inicio rápido

### 1. Uso en línea

Abre [GitHub Pages](https://juanjuanjie.github.io/html-presentation/), elige el modo, la plantilla y el guion, y copia el prompt completo en tu agente de IA.

### 2. Vista previa local

Abre el proyecto a través de un servidor HTTP local. No se recomienda hacer doble clic en `index.html`, porque el navegador puede bloquear la lectura de los archivos de plantilla.

```bash
python -m http.server 9966
```

Accede desde el navegador a `http://127.0.0.1:9966/`.

### 3. Crear directamente a partir de una plantilla

Copia cualquier plantilla como punto de partida:

```bash
cp themes/doodle-cream/template.html my-presentation.html
```

Cada página usa un elemento `.slide` y la página actual lleva la clase `.active`. Las plantillas son HTML de un solo archivo, fáciles de copiar, versionar y pasar a una IA para modificarlas.

## Formato mínimo del guion de dirección

El HTML de dirección comprueba la numeración consecutiva a partir de «镜 01» (Plano 01) y no añade planos automáticamente, no fusiona planos ni agrega portadas adicionales. Se recomienda que cada plano incluya composición, imagen, texto destacado, esquema, animación, transición y locución.

> **Nota:** los nombres de los campos del formato (`镜`, `布局`, `画面`, `花字`, `图示`, `动效`, `转场`, `口播`) son los que reconoce el validador del proyecto original, por lo que se conservan en chino y se acompañan de su traducción.

```md
## 镜 01｜开场提问          (Plano 01 | Pregunta inicial)

- 布局：居中大字，画面留白        (Composición: texto grande centrado, con espacio en blanco)
- 画面：问题从模糊逐渐变清晰      (Imagen: la pregunta pasa de borrosa a nítida)
- 花字：学编程还值得吗？          (Texto destacado: ¿Todavía vale la pena aprender a programar?)
- 图示：抽象代码符号与一个问号    (Esquema: símbolos de código abstractos y un signo de interrogación)
- 动效：花字淡入，问号轻微放大    (Animación: el texto aparece con fundido, el signo se agranda ligeramente)
- 转场：问题向左退出，衔接下一镜  (Transición: la pregunta sale por la izquierda y enlaza con el siguiente plano)
- 口播：如果 AI 一秒钟就能写出你练三个月的代码，那你辛苦学的编程，还值钱吗？
  (Locución: Si una IA puede escribir en un segundo el código que tú tardaste tres meses en practicar, ¿sigue valiendo la pena todo lo que te costó aprender a programar?)
```

Las reglas detalladas están en [`docs/generation-modes.md`](./docs/generation-modes.md).

## Exportar storyboards PNG

Instala las dependencias y Chromium:

```bash
pip install -r requirements.txt
playwright install chromium
```

Exporta todas las páginas de una plantilla:

```bash
python scripts/screenshot_html_slides.py themes/doodle-cream/template.html -o slides_out
```

Los archivos de salida son `slides_out/page_01.png`, `page_02.png`…, con formato predeterminado de 1920×1080. Consulta todos los parámetros en [`scripts/README.md`](./scripts/README.md).

## Estructura del proyecto

```text
html-presentation/
├── index.html                       # Entrada de GitHub Pages y datos de plantillas
├── README.md                        # Descripción del proyecto
├── SKILL.md                         # Guía de diseño para vídeo
├── NOTICE.md                        # Agradecimientos y declaración de origen
├── assets/
│   ├── generator.css                # Estilos del generador y del panel de edición de plantillas
│   ├── generator.js                 # Validación de los dos modos y composición del prompt
│   ├── navigation.js                # Rutas: inicio / plantillas / animaciones / README
│   ├── previews/                    # Imágenes de vista previa de las tarjetas de plantilla
│   └── readme-previews/             # Vistas previas unificadas 3×3 del README
├── scripts/
│   ├── screenshot_html_slides.py    # Exportación por lotes de diapositivas a PNG
│   ├── generate_variant_previews.py # Actualiza las vistas previas de las variantes de color
│   └── test_generator.py            # Pruebas básicas de la página y del generador
├── themes/
│   ├── doodle-cream/
│   ├── blockframe/
│   ├── blockframe-dark/             # Variante oscura de BlockFrame
│   └── purple-gold-presentation/    # Plantilla Professional y sus variantes de color
└── .github/workflows/pages.yml      # Despliegue automático en GitHub Pages
```

## Principios de diseño

1. **Una página, una idea**: cada página cumple una única tarea clara y el título expresa la conclusión de forma directa.
2. **Tipografía suficientemente grande**: debe seguir siendo legible al grabar la pantalla, tras la compresión del vídeo y en móviles.
3. **Espacio en blanco generoso**: evita que la información toque los bordes y reserva espacio para subtítulos, avatares y controles de la plataforma.
4. **Primero la estructura**: completa antes la planificación de la historia y el esquema de páginas, y después coloca el contenido en la plantilla.
5. **Autorrevisión página a página**: antes de publicar, comprueba la lógica, los desbordamientos, el contraste y el ritmo de cambio de página.

## Despliegue

El repositorio ya tiene configurado GitHub Actions (`.github/workflows/pages.yml`). En **Settings → Pages** del repositorio, elige **GitHub Actions** como origen del despliegue; al hacer push a `main` se actualizará GitHub Pages automáticamente.

## Autoría y agradecimientos

Creado y mantenido por [Juanjuanjie (卷卷姐 juan)](https://space.bilibili.com/229150291).

El proyecto está adaptado a partir de [frontend-slides](https://github.com/zarazhangrui/frontend-slides) y [beautiful-html-templates](https://github.com/zarazhangrui/beautiful-html-templates) de [Zara Zhang](https://github.com/zarazhangrui). Consulta la declaración detallada en [`NOTICE.md`](./NOTICE.md).

## Licencia

[MIT](./LICENSE)
