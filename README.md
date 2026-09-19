# Terminal portuario · gemelo digital STS

Simulador 3D de una grúa pórtico STS (ship-to-shore): telemetría en vivo, tensión de
cables, momento y capacidad, pendulación, fatiga, viento, interbloqueos y piloto
automático de descarga buque → camión. Todo vive en `index.html`, sin instalación
ni servidor: basta abrir el archivo.

## Uso en celular y tablet

- **Mando táctil**: barra inferior con carro (◀ ▶), izaje (▲ ▼), pórtico (« »),
  AUTO, LOCK/UNLOCK, 20/40 pies y PARO de emergencia. Se mantiene pulsado el botón
  para mover el eje, igual que con el teclado.
- **Pestañas** (solo en pantallas angostas): *Vista* deja el 3D a pantalla completa,
  *Telemetría* y *Control* muestran los paneles laterales.
- **Cámara**: un dedo orbita, dos dedos acercan y desplazan. Los botones de cámara
  del encabezado quedan como iconos deslizables.
- **Paneles ocultables**: los iconos del encabezado muestran u ocultan telemetría,
  control, alineación, CCTV y registro. La elección se recuerda en el navegador.
- **Ventanas flotantes**: las de alineación y CCTV se arrastran por su barra de
  título, se minimizan y se cierran; su posición también se recuerda.
- **Pantalla completa**: en iOS/Android se puede usar «Añadir a pantalla de inicio»
  (hay manifest e iconos) y la app abre sin barras del navegador.
- **Rendimiento**: en móvil se reduce la resolución de render, el antialias y la
  calidad de sombras para mantener la fluidez.

## Atajos de teclado (escritorio)

`A`/`D` carro · `W`/`S` izaje · `Q`/`E` pórtico · `P` piloto automático ·
`Espacio` lock/unlock · `T` 20/40 pies · `X` parada de emergencia · `1`–`6` cámaras.

## Publicar para abrirlo desde el celular

El repositorio incluye `.github/workflows/pages.yml`, que publica el sitio en
GitHub Pages con cada push a `main`. Para activarlo, una sola vez:

1. En GitHub: **Settings → Pages → Build and deployment → Source: GitHub Actions**.
2. Fusionar esta rama en `main`.
3. Abrir en el celular `https://shakdows.github.io/aduanas/`.

Si prefieres no usar Actions, en esa misma pantalla se puede elegir
**Deploy from a branch → main / (root)**, que sirve el `index.html` igual.

## Archivos

| Archivo | Para qué sirve |
| --- | --- |
| `index.html` | La aplicación completa (3D, física, interfaz). |
| `manifest.webmanifest` | Permite instalarla como app en celular y tablet. |
| `icon.svg`, `icon-180.png`, `icon-192.png`, `icon-512.png` | Iconos de la app. |
| `.github/workflows/pages.yml` | Publicación automática en GitHub Pages. |

Las librerías (Three.js, Tailwind, Font Awesome, fuentes) se cargan desde CDN, así
que la primera carga necesita internet.
