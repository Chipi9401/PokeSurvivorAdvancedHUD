# PokéSurvivor – Zoom + Stats
 
Userscript de [Tampermonkey](https://www.tampermonkey.net/) para **[PokéSurvivor](https://pokesurvivor.com)** (fan game *bullet-heaven* en el navegador, repositorio original: [JPTER78/pokesurvivor](https://github.com/JPTER78/pokesurvivor)).
 
Añade zoom con la rueda del ratón, un panel de estadísticas, ayudas visuales sobre el mapa, un buscador en la colección y varias mejoras de comodidad. Todo se activa y desactiva desde un menú propio.
 
> **Proyecto no oficial.** No tiene relación con el autor de PokéSurvivor, ni con Nintendo, Game Freak o The Pokémon Company. Es un script de cliente que solo cambia cómo ves y manejas el juego en tu navegador.
 
**Instalación rápida:** [Greasy Fork](https://greasyfork.org/scripts/TU_ID) · [copia en GitHub](./pokesurvivor-zoom-stats.user) · [siempre la última versión](#siempre-la-última-versión-cargador-require) (ver [instrucciones](#instalación))
 
> [!WARNING]
> **Aviso para usuarios de Brave**
>
> Los escudos de Brave hacen que algunas partes del script no funcionen, como el zoom y el minimapa. La única solución es desactivarlos desde la barra de URL; el juego no tiene anuncios, por lo que no debería haber problemas con popups ni similares.
 
---
 
## Funciones
 
### 🔍 Zoom y cámara
 
- **Zoom con la rueda del ratón:** más o menos campo de visión (de 0,7× a 3×), con el personaje siempre centrado.
- **Integrado en la cámara del juego:** la carga del terreno y la aparición de enemigos se adaptan al zoom.
- **Se recuerda:** el valor se guarda entre sesiones. `Inicio` lo restablece.
### 📊 Panel de estadísticas
 
- **Barras:** vida y experiencia.
- **Rendimiento:** FPS (en color) y campo de visión actual.
- **Datos del jugador:** nivel, ataque, velocidad, reducción de daño, regeneración, probabilidad de crítico, recarga y ataque activo.
- **Datos de la partida:** derrotas, monedas, tiempo de run, DPS (últimos 5 s), derrotas por minuto y mejor ataque contra tu objetivo.
- **Opcionales:** imán, bonus de XP y monedas, jefes derrotados, daño total, tickets, vínculos y objeto equipado.
- **Arrastrable:** se mueve por su título y con doble clic vuelve a su sitio. `F8` lo oculta.
### 🗺️ Sobre el mapa
 
- **Barra de vida de enemigos:** más grande, en tres tamaños (normal, grande o enorme).
- **Eficacia de tipo:** anillo bajo cada enemigo según lo eficaz que sea tu ataque activo contra él.
- **Apoyos resaltados:** curanderos, escudos e invocadores.
- **Vida de los jefes:** en número y porcentaje.
- **Avisos de ataque:** zonas y rayos más visibles, con un anillo que se cierra al detonar.
- **Círculo del imán:** desactivado por defecto.
- **Flechas en el borde de la pantalla:** hacia jefes (`B`), duende del tesoro (`$`), altares (`A`), manantiales (`+`), cofres (`C`) y grietas (`R`).
- **Minimapa arrastrable:** donde poder ver dónde se encuentran tus aliados en todo momento.
### ⚡ Comodidad
 
- **Pausa automática:** al salir de la pestaña o ventana (no en cooperativo).
- **Cambiar de ataque:** `Mayús` + rueda.
- **Avisos con sonido:** cuando aparece un shiny, el duende del tesoro o una grieta.
- **Título de la pestaña:** muestra tu vida y el tiempo de la partida.
- **Guardado:** exportar e importar como archivo JSON.
### 📖 Colección
 
- **Barra de búsqueda:** por nombre, tipo o número de Pokédex, sin distinguir tildes ni mayúsculas.
- **Resultados por generación:** botones con los resultados de cada una y salto automático a una que tenga.
- **Atajos:** `/` enfoca la barra, `Enter` abre el primer resultado y `Esc` limpia la búsqueda.
- **Qué se busca:** el nombre y el tipo solo entre los Pokémon que ya tienes; el número, entre todos.
### 🎯 Opcional (desactivado por defecto)
 
- **Cambio automático de ataque:** elige el hueco más eficaz contra el enemigo al que apuntas. Nunca actúa en cooperativo.
---
 
## Instalación
 
### 1. Instala un gestor de userscripts
 
| Navegador | Extensión |
|---|---|
| Chrome / Edge / Brave | [Tampermonkey](https://www.tampermonkey.net/) |
| Firefox | [Tampermonkey](https://www.tampermonkey.net/) |
| Safari | [Tampermonkey](https://www.tampermonkey.net/) |
 
> **Chrome y Edge recientes:** puede que tengas que habilitar los scripts de usuario para la extensión. Abre `chrome://extensions` (o `edge://extensions`), entra en los **Detalles** de Tampermonkey y activa **«Permitir scripts de usuario»**; si no aparece esa opción, activa el **Modo desarrollador** de la página de extensiones.
 
### 2. Instala el script
 
Elige **una** de estas formas.
 
**Método principal: Greasy Fork**
 
1. Abre la página del script en Greasy Fork: **<https://greasyfork.org/scripts/TU_ID>**
2. Pulsa el botón verde **Instalar este script**.
3. Tampermonkey mostrará una pantalla de instalación: pulsa **Instalar**.
Desde Greasy Fork, Tampermonkey puede avisarte cuando haya versiones nuevas.
 
#### Siempre la última versión: cargador `@require`
 
**Recomendado si quieres tener siempre la última versión**, sin esperar a que Tampermonkey compruebe actualizaciones. En lugar de instalar el código, instalas un pequeño «cargador» que descarga la versión más reciente de este repositorio cada vez que abres el juego.
 
1. Abre el panel de Tampermonkey → **Crear un script nuevo**.
2. Borra todo el contenido y pega **solo** esta cabecera, sin nada de código debajo:
```js
   // ==UserScript==
   // @name         PokéSurvivor – Zoom FOV + Stats
   // @namespace    chipi
   // @version      1.0
   // @description  Cargador: ejecuta siempre la última versión de PokeSurvivorAdvancedHUD
   // @match        https://pokesurvivor.com/*
   // @match        https://jpter78.github.io/pokesurvivor/*
   // @run-at       document-start
   // @grant        none
   // @require      https://raw.githubusercontent.com/Chipi9401/PokeSurvivorAdvancedHUD/refs/heads/main/pokesurvivor-zoom-stats.user
   // ==/UserScript==
```
 
3. Guarda con `Ctrl + S`.
4. Abre el **Panel de control** de Tampermonkey → pestaña **Configuración** y cambia el **Modo de configuración** (*Config mode*) a **Avanzado** (*Advanced*).
5. Baja hasta la sección **Externos** (*Externals*) y pon el **Intervalo de actualización** (*Update interval*) en **Siempre** (*Always*).
A partir de ahora, cada vez que cargues el juego Tampermonkey descargará el código más reciente del repositorio antes de ejecutarlo. Para actualizar no tienes que hacer nada.
 
- El archivo del repositorio se llama `pokesurvivor-zoom-stats.user` (sin `.js`): la URL de `@require` debe coincidir exactamente con ese nombre.
- GitHub guarda en caché los archivos unos minutos: una versión recién publicada puede tardar un poco en llegar.
- Este método ejecuta lo que haya en la rama `main` en cada carga. Si prefieres una versión fija que no cambie sola, usa Greasy Fork o la copia manual de abajo.
- Si has hecho un *fork*, cambia la URL de `@require` por la de tu repositorio.
**Copia de seguridad: desde GitHub**
 
Si Greasy Fork no está disponible o prefieres una copia fija:
 
1. Abre el archivo [`pokesurvivor-zoom-stats.user`](./pokesurvivor-zoom-stats.user) en este repositorio y copia **todo** su contenido (botón **Raw**, `Ctrl + A`, `Ctrl + C`).
2. Abre el panel de Tampermonkey → **Crear un script nuevo**.
3. Borra el contenido de ejemplo y pega el código completo.
4. Guarda con `Ctrl + S`.
> Instala el script **solo por una vía**. Si ya lo tienes desde Greasy Fork, el cargador o la copia de GitHub, **desinstala el otro** antes de añadir uno nuevo, o se ejecutarán dos copias a la vez.
 
### 3. Juega
 
Entra en **<https://pokesurvivor.com>** (o en la versión de GitHub Pages) y recarga con **`Ctrl + F5`**. Verás un botón **⚙** abajo a la derecha y, al empezar una partida, el panel de estadísticas.
 
El script se ejecuta solo en estas direcciones:
 
```
https://pokesurvivor.com/*
https://jpter78.github.io/pokesurvivor/*
```
 
---
 
## Controles
 
| Acción | Control |
|---|---|
| Zoom (ver más / menos) | Rueda del ratón (abajo = ver más) |
| Restablecer zoom | `Inicio` |
| Cambiar de ataque | `Mayús` + rueda |
| Mostrar u ocultar el panel | `F8` |
| Mover el panel | Arrastrar su título |
| Panel a su posición original | Doble clic en su título |
| Abrir las opciones | Botón **⚙** |
| Buscar en la colección | `/` |
 
---
 
## El menú ⚙
 
Cuatro pestañas, con un pie fijo donde están **★ Recomendado** y **Reset**.
 
| Pestaña | Contenido |
|---|---|
| **Panel** | Qué mostrar: panel, FPS, campo de visión, barras de vida y de experiencia. |
| **Estadísticas** | Qué estadísticas del jugador salen en el panel (con *Todo* y *Nada*). |
| **Mundo** | Tamaño de la barra de vida de enemigos y las ayudas sobre el mapa. |
| **Extras** | Pausa al salir, Mayús + rueda, avisos, título, cambio automático de ataque, y exportar o importar el guardado. |
 
Tus elecciones se guardan en el navegador (`localStorage`).
 
---
 
## Exportar e importar el guardado
 
El progreso del juego vive en el `localStorage` del navegador, así que se pierde si borras los datos del sitio. En **⚙ → Extras → Guardado**:
 
- **Exportar** descarga un `.json` con todo el guardado.
- **Importar** lo restaura (sobrescribe el guardado actual de ese navegador y recarga la página).
Importa siempre **desde el menú principal**, no durante una partida. Los guardados no se comparten entre `pokesurvivor.com` y la versión de GitHub Pages, porque son sitios distintos para el navegador.
 
---
 
## Juego limpio
 
- Los anillos, flechas, DPS y demás son **información**: no modifican el juego ni el progreso.
- El **cambio automático de ataque** es lo único que actúa por ti. Está desactivado por defecto, no funciona en cooperativo y solo cambia si el nuevo ataque es claramente mejor. En solitario cuenta para el ranking, así que úsalo según tu criterio.
- El script no toca vida, daño ni velocidad, ni envía nada a ningún servidor.
---
 
## Solución de problemas
 
**No aparece el botón ⚙ ni el panel**
- Comprueba que Tampermonkey está activo y que el script aparece **activado** en su panel.
- En Chrome o Edge, revisa que los scripts de usuario estén permitidos (ver arriba).
- Recarga con `Ctrl + F5`.
**El zoom no hace nada**
- Mueve la rueda con el ratón sobre la partida (no sobre un menú con scroll).
- Si usas **Brave**, desactiva los escudos para el sitio (ver el aviso de arriba).
- Abre la consola (`F12`) y busca errores del script.
**El cargador no trae la última versión**
- Comprueba que el **Modo de configuración** de Tampermonkey está en *Avanzado* y que el **Intervalo de actualización** de *Externos* está en *Siempre*.
- Espera unos minutos: GitHub cachea los archivos.
- Revisa que la URL de `@require` coincide exactamente con el nombre del archivo (`pokesurvivor-zoom-stats.user`).
**El panel dice «Esperando partida…»**
- Es normal en los menús. Aparecerá al empezar una partida.
**Faltan las flechas a altares, manantiales, cofres o grietas**
- Estas ayudas buscan los objetos del juego por nombre y dependen de la estructura interna del juego. Escribe `__PS.pois()` en la consola: si devuelve una lista vacía, ese dato no se ha podido localizar. Abre un *issue* y adjunta el archivo `interact.js` del juego para ajustarlo.
**El DPS se queda en 0**
- Depende del contador de daño del jugador del juego. Si no se actualiza, abre un *issue*.
**Algo dejó de funcionar tras una actualización del juego**
- El script se engancha a nombres internos del juego (`G.Camera`, `G.Player`, `G.Enemy`, `G.Hazards`…). Si el autor los cambia, puede que haya que adaptarlo.
---
 
## Desarrollo
 
- Un único archivo, sin dependencias ni paso de compilación: `pokesurvivor-zoom-stats.user`.
- Se ejecuta en `document-start` y captura las clases del juego (`Camera`, `Player`, `Enemy`, `Hazards`) en el momento en que se definen.
- La interfaz propia (botón, menú, panel y capa de dibujo) va dentro de un **Shadow DOM**, para no chocar con el CSS del juego.
- Para depurar desde la consola: `__PS.player()`, `__PS.pois()` y `__PS.hazards()`.
---
 
## Licencia
 
Código bajo licencia [MIT](./LICENSE). Los sprites, nombres y marcas de Pokémon pertenecen a sus dueños y no se incluyen aquí.
