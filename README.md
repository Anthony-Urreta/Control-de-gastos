# Control financiero: divisas y bolívares

Panel para registrar entradas y salidas y medir la pérdida por la variación diaria del dólar BCV. Los datos viven en `data.json`, dentro de tu repositorio de GitHub, y el panel los lee y los guarda desde el navegador.

## Archivos

- `index.html`: el panel completo, en un solo archivo.
- `data.json`: los datos (movimientos, tasas y divisa base). Empieza vacío. Tiene el mismo formato que «Descargar respaldo».
- `README.md`: esta guía.

## Antes de empezar: ¿repositorio público o privado?

Lo que guardes en `data.json` son las finanzas del negocio.

- **Privado (recomendado).** Nadie más ve los datos. El panel se abre desde tu computadora con doble clic en `index.html`, o desde cualquier copia publicada, y lee y guarda con tu token. GitHub Pages gratis no publica repositorios privados.
- **Público con GitHub Pages.** El panel queda en una dirección web, `https://tu-usuario.github.io/tu-repo/`, que abres desde el teléfono. Pero **cualquiera que tenga el enlace, o que encuentre el repositorio, puede leer `data.json`**.
- **Opción mixta.** Usa un repositorio público solo con `index.html` para tener la página en GitHub Pages, y uno privado solo con `data.json`. En «Conexión con GitHub» escribe el repositorio privado: la página pública no muestra nada sin tu token.

## Puesta en marcha

1. **Crea el repositorio.** En GitHub, pulsa **New repository**. Ponle un nombre, por ejemplo `control-financiero`, y elige si será Private o Public.
2. **Sube los archivos.** En el repositorio, pulsa **Add file → Upload files**. Arrastra `index.html`, `data.json` y `README.md`, que vienen sueltos dentro de este zip, y pulsa **Commit changes**.
3. **Publica con GitHub Pages (opcional, solo si el repositorio es público).**
   - Entra en **Settings → Pages**.
   - En «Source», elige **Deploy from a branch**, la rama **main** y la carpeta **/ (root)**, y pulsa **Save**.
   - En uno o dos minutos aparece la dirección de tu panel.
4. **Crea un token solo para este repositorio.**
   - Ve a tu foto de perfil → **Settings → Developer settings → Personal access tokens → Fine-grained tokens → Generate new token**.
   - En «Repository access», elige **Only select repositories** y marca tu repositorio.
   - En «Repository permissions», cambia **Contents** a **Read and write**.
   - Ponle una fecha de vencimiento y pulsa **Generate token**. Copia el token, que empieza con `github_pat_`.
5. **Conecta el panel.**
   - Abre el panel y pulsa **Conectar GitHub** en la barra superior.
   - Completa usuario, repositorio, rama (`main`), archivo (`data.json`) y el token, y pulsa **Probar y conectar**.
   - Si abres el panel desde GitHub Pages, usuario y repositorio se completan solos.

La conexión y el token quedan guardados solo en ese navegador. En cada teléfono o computadora nuevo tienes que conectar una vez.

## Cómo pasar tus datos actuales

**Opción A, desde el panel:**
1. En el panel anterior, abre **Más → Descargar respaldo**.
2. En el panel nuevo, ya conectado, abre **Más → Restaurar respaldo** y elige ese archivo.
3. Pulsa **Guardar en GitHub**.

**Opción B, directo en GitHub:**
1. Renombra el archivo de respaldo a `data.json`.
2. Súbelo al repositorio con **Add file → Upload files**. Reemplaza el que está.

## Uso diario

- **Estado de sincronización.** El botón de la barra muestra cómo están tus datos:
  - **GitHub al día**: lo que ves es lo que está guardado.
  - **Guardar en GitHub**, en amarillo: hiciste cambios en este dispositivo. Púlsalo para publicarlos.
  - **Conectar GitHub**: el panel aún no tiene repositorio configurado.
- **Al abrir.** Si no tienes cambios pendientes, el panel trae solo la última versión de GitHub. Si tienes cambios sin publicar, los conserva y te avisa.
- **Si cierras sin guardar.** Si hay cambios sin publicar, el navegador te pregunta antes de cerrar la página.
- **Si alguien guardó antes que tú.** Cuando otro dispositivo guardó desde que trajiste los datos, el panel te avisa antes de reemplazar esa versión.
- **Más → Traer datos de GitHub** reemplaza los datos de este dispositivo por los publicados.
- **Historial.** Cada guardado queda como un commit con fecha y hora. En GitHub puedes ver el historial de `data.json` y recuperar cualquier versión anterior.

## Problemas frecuentes

- **«GitHub respondió 401».** El token venció o está mal copiado. Crea uno nuevo y vuelve a conectar.
- **«GitHub respondió 403».** El token no tiene **Contents: Read and write**, o no incluye este repositorio.
- **«GitHub respondió 404».** Revisa usuario, repositorio, rama y nombre del archivo. Si el repositorio es privado, hace falta el token.
- **«Se agotó el límite de consultas».** Sin token, GitHub permite 60 consultas por hora. Agrega el token.
- **Cambios que tardan en verse en la página pública.** GitHub Pages tarda uno o dos minutos en publicar cada cambio. Con la conexión configurada, el panel lee directo de GitHub y los ve al instante.

## Seguridad

- **El token es como una llave.** Si lo pierdes o alguien lo ve, bórralo en GitHub (Settings → Developer settings) y crea otro.
- **No guardes el token en el repositorio** ni lo envíes por chat.
- **Usa «Desconectar» en dispositivos prestados.** Está en Más → Conexión con GitHub y borra el token de ese navegador.
