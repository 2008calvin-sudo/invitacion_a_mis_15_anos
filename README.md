# 💌 Invitación XV Años · María de los Ángeles González

Invitación interactiva y responsiva (celular y pantalla completa) con sobre de terciopelo, tarjeta tipo carrusel, video de fondo y música. Es una página estática: **HTML + CSS + JavaScript en un solo archivo**, sin instalar nada.

## 📁 Estructura

```
invitacion/
├── index.html          ← toda la página (HTML, CSS y JS)
├── README.md
└── media/
    ├── video_fondo.mp4     Video del bosque encantado (siempre en silencio)
    ├── musica.mp3          Canción (empieza al tocar el sello)
    ├── sobre_cerrado.jpg   Sobre de terciopelo cerrado con sello dorado
    ├── sobre_abierto.jpg   Sobre abierto con la tarjeta
    └── quinceanera.jpg     Foto de la quinceañera
```

> Para cambiar una imagen, el video o la música, **reemplaza el archivo manteniendo el mismo nombre**. Si usas otro nombre, edita la ruta en `index.html` (están marcadas con `► reemplaza`).

## ▶️ Cómo verla

Abre `index.html` con doble clic en Chrome, Firefox, Edge o Safari. Mantén la carpeta `media/` junto al archivo.

## ✨ Cómo funciona

1. **Bienvenida:** letras doradas que aparecen en secuencia — "Te Invito a mis **15 Años**, una noche mágica". Dura unos 6 segundos y se puede saltar con un toque.
2. **Sobre cerrado** al centro con un botón pulsante sobre el sello dorado ("Haz clic para abrir").
3. Al tocar el sello: destellos dorados, el sobre cerrado se funde con el sobre abierto, **empieza la canción** y después sube la tarjeta.
4. **Tarjeta con 3 secciones** (desliza, usa las flechas, los puntos o el teclado ← →):
   - **Bienvenida:** foto y nombre de la quinceañera.
   - **Detalles:** padre, fecha, hora, lugar, botón de Google Maps y confirmación por WhatsApp.
   - **Galería:** imágenes con miniaturas; al tocar una se amplía.
5. **Video de fondo:**
   - *Pantalla ancha:* no aparece hasta que se abre la invitación; entonces surge a la izquierda (completo, sin zoom) y la tarjeta queda a la derecha.
   - *Celular:* el video está detrás del sobre y arranca al tocar el sello.
6. Botón del parlante (arriba a la derecha) para silenciar o activar la canción.

## ✏️ Qué debes personalizar

Todo está en el bloque `CONFIG` al inicio del `<script>` de `index.html`:

| Campo | Qué es | Valor actual |
|---|---|---|
| `fecha` | Fecha del evento | `'00 de Mes de 2026'` ⚠️ **pendiente** |
| `hora` | Hora | `'7:30 PM'` |
| `lugar` | Lugar | `'Colegio Médico'` |
| `mapsUrl` | Enlace de Google Maps | búsqueda "Colegio Médico" ⚠️ pega el enlace exacto |
| `whatsapp` | Número que recibe las confirmaciones, con código de país y **sin** `+` ni espacios (Argentina: `549` + área + número) | `'5490000000000'` ⚠️ **de ejemplo** |
| `mensaje` | Texto prellenado del WhatsApp | ver archivo |

Los textos de **Padre / padrinos** y **nombre** están directamente en el HTML (busca `Juan González` y `María de los Ángeles González`).

La galería se edita en la lista `GALLERY` (agrega más rutas de imágenes).

## 🎛️ Ajustes finos

| Qué | Dónde | Valor |
|---|---|---|
| Volumen de la canción | `music.volume` | `0.8` (de 0 a 1) |
| Segundo del video donde empieza y vuelve a empezar el bucle | `START_TIME` | `3.5` |
| Qué tan difuminado está el fondo en pantalla ancha | `#bgBlur` → `blur(7px)` | más px = más difuminado |
| Posición del video a la izquierda (pantalla ancha) | `#bg` → `object-position` | `27%` (0% pegado a la izquierda, 50% centro) |
| Posición de la tarjeta a la derecha (pantalla ancha) | `.card{left:…}` | `73%` |
| Duración de la bienvenida (ms) | `setTimeout(endIntro, 6000)` | `6000` (textos en el bloque `<div id="intro">`) |
| Velocidad de apertura del sobre | `transition` de `.env img` y el `3400` de `openEnvelope` | mayor número = más lento |
| Posición del botón del sello | `#seal` → `left`, `top`, `width` | solo si cambias `sobre_cerrado.jpg` |

## 🌐 Publicarla en internet

Sube **`index.html` y la carpeta `media/` juntos** a cualquier hosting estático (Netlify Drop, GitHub Pages, Vercel, Cloudflare Pages, etc.) y comparte el enlace.

Consejos:
- `musica.mp3` pesa ~5,6 MB y el video ~6,6 MB. Para que cargue más rápido en celular, puedes comprimir la canción (128 kbps es suficiente).
- Los navegadores **no permiten sonido automático**: por eso la música empieza al tocar el sello. Es normal.
- Las tipografías (Cinzel, Cormorant Garamond y Great Vibes) se cargan desde Google Fonts; sin internet se usa una fuente de respaldo.

## 🎨 Estilo

Paleta borgoña/terciopelo con dorado y destellos mágicos de bosque encantado. Los colores están como variables al inicio del CSS (`--wine`, `--velvet`, `--gold`, …).
