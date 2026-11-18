<p align="center">
  <img src="img/logo.png" alt="kysbebe" width="180">
</p>

<h1 align="center">Videos de recompensas para OBS</h1>
<p align="center">por <a href="https://github.com/kysbebe"><b>kysbebe</b></a></p>

Cuando alguien canjea una recompensa de **puntos de canal en Twitch**, aparece su video en **un lugar y con un tamaño al azar** de la pantalla. Todo funciona con **una sola fuente de OBS**, y se configura desde un **panel visual**, sin programar.

<p align="center"><img src="docs/vista_panel.png" alt="Panel de configuración" width="820"></p>

## Qué hace

- 🎬 **Un video por recompensa:** "Duck Dance" → `videos/duckdance.mp4`. Mayúsculas, tildes y espacios no importan.
- 🎲 **Lugar y tamaño al azar:** elegís en qué zonas de la pantalla puede salir (arriba a la izquierda, centro, abajo a la derecha…) y entre qué tamaños.
- 🖱️ **Panel visual (`configurar.html`):** arrastrás videos, elegís zonas en una pantallita, ajustás tamaño y volumen, y probás en OBS con un botón. Todo se guarda solo.
- 🟩 **Quita el fondo verde** de videos de pantalla verde.
- 🔊 **Volumen por video**, y el sonido entra al mezclador de OBS.
- 🛡️ **Anti-spam:** máximo de videos a la vez; el resto espera su turno.
- ⚡ OBS toma los cambios del panel en 2 segundos, sin actualizar la fuente.

## Qué necesitás

- Windows y **OBS Studio 28 o más nuevo** → [obsproject.com/download](https://obsproject.com/download)
- **Streamer.bot** (gratis) → [streamer.bot/downloads](https://streamer.bot/downloads)
- Un canal de Twitch con **puntos de canal** (afiliado o partner)
- **Chrome** o **Edge** para abrir el panel

## Instalación

📄 **La guía completa paso a paso, con capturas, está en [docs/Guia-videos-de-recompensas.pdf](docs/Guia-videos-de-recompensas.pdf).**

Resumen:

1. **Descargá este repositorio:** botón verde **Code › Download ZIP**, y extraelo en una carpeta fija.
2. **Streamer.bot:** conectá tu cuenta **Broadcaster** de Twitch (Platforms › Twitch › Accounts).
3. **Streamer.bot › Servers/Clients › WebSocket Server:** Auto Start **On**, `127.0.0.1`, puerto **8080**, Authentication **desmarcado**, **Start Server**.
4. **OBS › Herramientas › Ajustes del servidor WebSocket:** que el puerto sea **4455** (nunca 8080) y Enable Authentication desmarcado.
5. **OBS › Fuentes › + › Navegador:** Archivo local = `widget.html`, **1920 × 1080**, marcá **Controlar audio mediante OBS**. Para escucharlo vos, activá los auriculares de la fuente en el mezclador.
6. Abrí **`configurar.html`** con Chrome o Edge, elegí esta carpeta y agregá tus videos.

## Problemas comunes

| Qué pasa | Qué hacer |
|---|---|
| El widget se ve vacío | Es normal: es transparente. Probá con **▶ Probar en OBS**. |
| "Sin conexión con Streamer.bot" | WebSocket Server de Streamer.bot en **Running**, puerto 8080. El de OBS en **4455**. |
| Conectado pero no pasa nada al canjear | La cuenta **Broadcaster** tiene que estar conectada en Streamer.bot. |
| "No hay video para…" | Asigná la recompensa en el panel desde **Últimos canjes recibidos**. |
| El video no se ve | Puede estar en HEVC/H.265: convertilo a H.264. |

Más en la [guía en PDF](docs/Guia-videos-de-recompensas.pdf).

## Seguridad y privacidad

- Todo funciona **en tu PC**: no se envía nada a internet. El widget solo se conecta a Streamer.bot en tu propia computadora.
- `config.js` se lee como **datos**, no se ejecuta como código en el panel, y el widget valida todos los valores (tamaños, volumen, nombres de archivo) antes de usarlos.
- El widget **solo** abre archivos de la carpeta `videos/`: no acepta rutas a otras carpetas.
- Las páginas tienen una **política de seguridad de contenido (CSP)** que bloquea scripts externos.

## Licencia

**Uso personal gratuito. Prohibido vender, redistribuir versiones modificadas, quitar la firma o usar este material para entrenar IA.** Leé las condiciones completas en [LICENSE.md](LICENSE.md).

---

<p align="center">Hecho por <a href="https://github.com/kysbebe"><b>kysbebe</b></a> 🐰</p>
