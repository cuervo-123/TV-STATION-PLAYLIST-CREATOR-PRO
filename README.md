# TV-STATION-PLAYLIST-CREATOR-PRO
Create Your IPTV M3U,JSON,M3U8  PLAYLIST EASY ALL IN ONE PLACE EXPORT AND IMPORT 


# Mi TV Station — Cargador M3U + Auto‑Aleatorio (con temporizador)

**Marca:** GLOBALTV4YOU · **Autor:** cuervodatabase

> App web ligera para cargar playlists IPTV (`.m3u` / `.m3u8`), reproducir con fallback **HLS.js**, gestionar **Favoritos/Playlists/Categorías**, y **cambiar de canal automáticamente** cada *N* segundos (configurable por el usuario).

---

## ✨ Funciones principales

* **Importar `.m3u` / `.m3u8`** desde archivo local.
* **Reproducción HLS**: usa **HLS.js** cuando el navegador no soporta HLS nativo.
* **Listado de canales con búsqueda** (filtra por nombre o grupo).
* **Selección múltiple** de canales para reproducción aleatoria.
* **Aleatorio inmediato** (un clic): escoge un canal al azar entre tu selección actual.
* **Auto‑Aleatorio con temporizador externo** (segundos):

  * Campo numérico para fijar intervalo (**mín. 5s**).
  * **▶️ Iniciar Auto‑Aleatorio** / **⏹️ Detener Auto‑Aleatorio**.
* **Favoritos**: agregar canal actual, reproducir, eliminar y exportar a `.m3u`.
* **Playlists personalizadas** (localStorage): guardar, cargar, eliminar y exportar.
* **Categorías**: crear y añadir selección de canales; clic para reproducir.
* **Exportación a `.m3u`** de selección, favoritos y playlists.

> Todo se guarda **localmente** en tu navegador (`localStorage`). No se requiere servidor.

---

## 🚀 Empezar

### 1) Abrir localmente

* Abre `index.html` en un navegador moderno **o**
* Sirve con un server local (recomendado):

  ```bash
  # Python 3
  python -m http.server 8080
  # abrir http://localhost:8080
  ```

### 2) Cargar una lista

1. Haz clic en **“Elegir archivo”** y selecciona un `.m3u` o `.m3u8`.
2. Verás los canales en la lista (nombre + grupo si existe).
3. Selecciona uno o **varios** canales (Ctrl/⌘ o Shift).

### 3) Reproducir

* Pulsa **📺 Reproducir seleccionado** para el canal marcado.
* Si la URL termina en `.m3u8`, la app usará **HLS.js** según lo necesite el navegador.

### 4) Modos aleatorios

* **Aleatorio inmediato:** pulsa **▶️ Aleatorio inmediato**. Elegirá 1 al azar **entre tu selección** actual.
* **Auto‑Aleatorio con temporizador:**

  1. Escribe los **segundos** en el campo (mínimo `5`).
  2. Pulsa **▶️ Iniciar Auto‑Aleatorio**.
  3. Cuando quieras, usa **⏹️ Detener Auto‑Aleatorio**.

> El auto‑aleatorio **solo usa los canales seleccionados**. Si no seleccionas nada, te pedirá que elijas canales.

### 5) Favoritos / Playlists / Categorías

* **Favoritos**: cuando estés reproduciendo un canal, pulsa **⭐ Agregar a Favoritos**. Adminístralos desde su panel (reproducir, eliminar, exportar).
* **Playlists**:

  * Selecciona canales → nómbralos → **💾 Guardar selección**.
  * Carga con **📂 Cargar**, elimina con **🗑️ Eliminar**, exporta con **⬇️ Exportar (.m3u)**.
* **Categorías**:

  * **📝 Crear** una categoría, luego **🔀 Añadir selección** para incluir los canales marcados.
  * Clic en un ítem de la categoría para reproducirlo.

---

## 🧩 Notas sobre formato M3U

* Se leen atributos comunes `#EXTINF` como:

  * `tvg-logo="…"`
  * `group-title="…"`
* Ejemplo:

  ```m3u
  #EXTM3U
  #EXTINF:-1 tvg-logo="https://logo.example/logo.png" group-title="News",My News Channel
  https://example.com/stream/playlist.m3u8
  ```

---

## 🧪 Resolución de problemas

* **HTTPS vs HTTP:** Si sirves la página en **HTTPS**, muchos navegadores bloquean streams **HTTP** (contenido mixto). Usa URLs HTTPS o prueba sirviendo la app por HTTP local.
* **CORS:** Algunos servidores no permiten uso desde otros orígenes. Si no exponen encabezados CORS, el navegador bloqueará la petición.
* **Smart TV: solo audio / sin video:** Algunos navegadores de TV tienen soporte limitado de MSE. Prueba en desktop (Chrome/Edge/Firefox) o usa un dispositivo externo.
* **.m3u8 no reproduce:** Verifica que **HLS.js** se cargó y que el manifiesto es accesible. Streams con DRM o geobloqueos no funcionarán.
* **Listas gigantes:** `.m3u` muy grandes pueden sentirse lentas en el DOM. Considera dividir por categorías o preprocesar del lado del servidor.

---

## 🧱 Branding GLOBALTV4YOU

* **Título y nombre:** Cambia el `<title>` y el `<h1>` si quieres que diga “GLOBALTV4YOU”.
* **Logotipo:** Añade tu logo en la cabecera, por ejemplo:

  ```html
  <header>
    <img src="./logo-globaltv4you.png" alt="GLOBALTV4YOU" style="height:40px;vertical-align:middle"/>
    <h1 style="display:inline-block;margin-left:8px">GLOBALTV4YOU — Mi TV Station</h1>
  </header>
  ```
* **Colores de marca:** Edita las variables CSS del tema:

  ```css
  :root{
    --bg:#0f1115;   /* Fondo */
    --fg:#e6e8eb;   /* Texto */
    --accent:#00ffd5; /* Acento (cámbialo por tu color de marca) */
  }
  ```
* **Metadatos y SEO:**

  ```html
  <meta name="description" content="GLOBALTV4YOU — App IPTV con playlists M3U, HLS.js y auto‑aleatorio configurable."/>
  <meta property="og:title" content="GLOBALTV4YOU — Mi TV Station"/>
  <meta property="og:description" content="Cargador M3U/M3U8, favoritos, playlists, categorías y auto‑aleatorio con temporizador."/>
  <meta property="og:type" content="website"/>
  <meta property="og:image" content="https://tusitio.com/logo-globaltv4you.png"/>
  ```

---

## 📦 Publicar en GitHub Pages

1. Crea un repo y sube `index.html` y tus assets (logo, etc.).
2. *Settings → Pages* → **Deploy from a branch** → selecciona rama y carpeta raíz.
3. Abre la URL publicada.

---

## 🗺️ Roadmap sugerido

* Guardar/recuperar el **intervalo** del temporizador en `localStorage`.
* Modo **Pausa/Continuar** y **cuenta regresiva** visual.
* Importar/Exportar **JSON** completo (con favoritos y categorías).
* Vista de logos/miniaturas con *lazy loading* para listas grandes.

---

## 📝 Cambios

* **v2 (actual)** — Temporizador **externo** de Auto‑Aleatorio (numérico, ≥5s) + botones Iniciar/Detener.
* **v1** — Carga M3U/HLS, búsqueda, aleatorio inmediato, favoritos, playlists, categorías, exportar.

---

## 🔒 Datos y privacidad

* Se usa solo `localStorage` del navegador:

  * `playlist_<nombre>` — playlists guardadas
  * `favoritos` — lista de favoritos
  * `cat_<nombre>` — listas por categoría
* Borra el almacenamiento del navegador para reiniciar la app.

---

## 📄 Licencia

MIT (puedes añadir tu archivo `LICENSE`).
