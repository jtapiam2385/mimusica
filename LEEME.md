# Mi Música: cómo dejarla funcionando

Son dos pasos, se hacen una sola vez y no cuestan nada. Te recomiendo hacerlos desde el computador.

## Paso 1: publicar la app en GitHub Pages

1. Crea una cuenta gratis en https://github.com (si no tienes una).
2. Pulsa **New repository**. Ponle de nombre `mimusica`, márcalo como **Public** y pulsa **Create repository**.
3. Pulsa **uploading an existing file** y arrastra todos los archivos de esta carpeta (index.html, sw.js, manifest.webmanifest y los íconos). Luego pulsa **Commit changes**.
4. Ve a **Settings → Pages**. En *Branch* elige `main` y la carpeta `/ (root)`, y pulsa **Save**.
5. Espera 1 o 2 minutos. Tu app va a quedar en:
   `https://TU-USUARIO.github.io/mimusica/`

Para probarla antes de conectarla, agrega `?demo=1` al final de esa dirección.

## Paso 2: crear el ID de aplicación en Microsoft

1. Entra a https://entra.microsoft.com con tu cuenta Hotmail.
   - Desde agosto de 2024, Microsoft ya no deja registrar apps con una cuenta personal sola: hay que tener un directorio. Si te pide crear uno o crear una cuenta de Azure, créala. Es gratis, pero Azure puede pedirte una tarjeta solo para verificar tu identidad.
2. Ve a **Registros de aplicaciones → Nuevo registro**.
   - Nombre: `Mi Música`
   - Tipos de cuenta admitidos: **Solo cuentas personales de Microsoft**
   - URI de redirección: elige **Aplicación de página única (SPA)** y pega exactamente `https://TU-USUARIO.github.io/mimusica/`. Debe terminar en `/`. La app te muestra esta dirección para que la copies.
3. Pulsa **Registrar** y copia el **Id. de aplicación (cliente)**.
4. Abre tu app, pega ese ID, revisa que la carpeta sea `/Mi Plex center/Mi música` y pulsa **Conectar con Microsoft**.

La primera vez la app lee toda la biblioteca, lo que puede tardar unos minutos. Después solo revisa los cambios.

## Instalarla en el celular

Abre la dirección de la app en Chrome, toca el menú ⋮ y elige **Agregar a la pantalla principal** (o **Instalar app**).

## Cómo funcionan las alertas

- La app compara las carpetas de cada artista con su discografía en **MusicBrainz**, una base de datos musical abierta y gratuita.
- **Faltantes**: discos de estudio que existen y que no están en tu OneDrive.
- **Novedades**: discos lanzados en los últimos 180 días, o anunciados, que no tienes.
- **Por revisar**: artistas que no encontré con seguridad. Puedes elegir el correcto o marcarlos como "no revisar".
- En **Ajustes** puedes sumar EPs, discos en vivo, recopilatorios y otros, y cambiar cada cuánto se revisan las novedades.
- Con el menú ⋮ de un disco puedes marcarlo como "Ya lo tengo / ignorar".
- La primera revisión completa tarda unos 10 a 15 minutos, porque MusicBrainz permite solo una consulta por segundo. Sigue avanzando mientras usas la app y continúa donde quedó la próxima vez que la abras.
- Los avisos aparecen al abrir la app. Si activas los avisos, también llegan como notificación del celular mientras la app está abierta o en segundo plano.

## Cómo lee tu música

- La estructura es `Categoría / Artista / AAAA - Álbum / canciones`. Las subcarpetas `CD1`, `CD2` se juntan en un solo álbum.
- Los vinilos no tienen carpeta de artista. En ese caso el artista se toma de las etiquetas del archivo.
- OneDrive no entrega el número de pista ni la carátula, así que la app los lee de las etiquetas ID3 de cada MP3 al abrir un álbum.
- Las listas de reproducción se guardan en el dispositivo donde las creas.
