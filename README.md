# Natalí Elisei · SUP

Dossier deportivo y simulador de sponsoreo. Sitio estático para https://toraindiasup.com.ar, alojado en el proyecto Netlify `toraindia`.

## Archivos

- `site/index.html`: contenido, diseño y comportamiento.
- `site/assets/`: imágenes optimizadas WebP.
- `site/compartir-natali-v1.jpg`: portada para compartir.
- `site/favicon.svg`, `site/favicon-32.png`, `site/apple-touch-icon.png`: ícono NE de la pestaña.
- `netlify.toml`: carpeta de publicación.

## Conectar el proyecto existente en Netlify

1. Abrir el proyecto `toraindia`.
2. Ir a Project configuration → Build & deploy → Continuous deployment → Repository.
3. Seleccionar Link repository y autorizar el repositorio de GitHub.
4. Elegir la rama `main`, dejar el comando de compilación vacío y usar `site` como directorio de publicación.
5. Guardar y comprobar el despliegue. Mantener el dominio actual.

Los cambios publicados en main disparan un nuevo despliegue cuando la conexión está activa. No crear un segundo proyecto de Netlify.

## Editar los textos

Todos los bloques de texto están señalizados con un comentario `<!-- TEXTO: ... -->` para poder encontrarlos sin leer HTML.

1. Abrir `site/index.html` en GitHub y tocar el lápiz (Edit this file).
2. Buscar con Ctrl+F (Cmd+F en Mac) la palabra `TEXTO:` para ir saltando de bloque en bloque, o buscar el bloque puntual: por ejemplo `TEXTO: perfil`.
3. Cambiar únicamente lo que está **entre** las etiquetas. En `<p>Seleccionada Nacional...</p>` se edita el medio; los `<p>` y `</p>` quedan como están.
4. Bajar hasta el final y tocar **Commit changes**.
5. Netlify publica solo. El cambio se ve en menos de un minuto.

### Bloques disponibles

| Marcador | Qué cambia |
| --- | --- |
| `portada · linea de arriba` | Ubicación y "Dossier 2026" |
| `portada · titulo y presentacion` | Nombre, bajada y párrafo de presentación |
| `portada · botones` | Los dos botones de la portada |
| `cinta de logros que se desliza` | La banda celeste con los logros |
| `perfil · texto y datos` | Biografía y los datos de la ficha |
| `trayectoria · titulo` | Encabezado de resultados |
| `trayectoria · resultados año por año` | Cada fila de la línea de tiempo |
| `frase destacada sobre la foto` | La cita grande sobre la foto |
| `disciplinas · las tarjetas` | Sprint, Técnico, Maratón |
| `compromiso · texto y numeros` | Sección "Más que competir" |
| `clinicas · bajada que explica que es una clinica` | El párrafo de arriba de la sección |
| `clinicas · las sedes` | Ciudad y provincia o país de cada clínica |
| `clinicas · que gana una marca` | El recuadro de activación para sponsors |
| `clinicas · invitacion a las escuelas` | El cierre con el botón de WhatsApp |
| `clinicas · pie de cada video` | El texto debajo de cada clip |
| `categorias de sponsors que busca` | Las etiquetas de rubros |
| `sponsors · marcas que la acompañan` | Sección de sponsors |
| `temporada · titulo y numeros` | Encabezado y los cuatro contadores |
| `temporada · las 8 fechas` | Mes, año, competencia, sede y estado |
| `simulador · texto de arriba` | Texto del simulador de logo |
| `video · titulo y bajada` | Encabezado de la sección del video |
| `contacto · titulo y texto` | Cierre y datos de contacto |
| `pie de pagina` | La línea final |

### Recomendaciones

- Escribir acentos y ñ con normalidad.
- No borrar los `<` ni los `>`. Si se rompe algo, GitHub guarda todas las versiones: entrar en History y volver a la anterior.
- Las imágenes se conservan junto al HTML, en `site/assets/`.
- Para sumar un sponsor: dejar el logo en `site/assets/` como `sponsor-<marca>.webp`, con fondo transparente y unos 600x240, y copiar una tarjeta de `partner-grid` cambiando el archivo y el nombre.
- **Al reemplazar una imagen hay que cambiarle el nombre** (por ejemplo `anio-2022-aloha.webp` en lugar de `anio-2022.webp`) y actualizar la referencia en el HTML. La carpeta `assets/` se sirve con caché de un año e `immutable`: si se pisa un archivo conservando el nombre, los navegadores siguen mostrando la versión vieja y no vuelven a pedirla.
- Al cambiar el texto que se ve al compartir el link, WhatsApp y las redes pueden tardar en actualizarlo por su propia caché.

### Sumar una sede de clínicas

El mapa es un SVG dibujado a partir del contorno real de Argentina y Uruguay, y cada punto se calcula desde la latitud y la longitud de la ciudad. Agregar un renglón a la lista **no** dibuja el punto: hay que pedir que recalculen el mapa con la sede nueva.

### Videos

Los tres videos del sitio usan `preload="none"` y una imagen de portada (`assets/portada-*.webp`). Así la página no descarga ningún MP4 hasta que alguien toca play: son 14 MB entre los tres. **Si se agrega un video hay que agregarle su portada**, si no queda un rectángulo negro y conviene volver al preload.

## Contenido pendiente

Del Campeonato Argentino ASA y del circuito FAC todavía no están todas las sedes. Se van sumando al bloque `TEXTO: temporada · las 8 fechas` a medida que las confirman, y hay que mover los contadores de `TEXTO: temporada · titulo y numeros` cuando cambia la cantidad de fechas. El Mundial ICF 2027 espera sede y fecha.

La sección **Testimonios se sacó** por ahora: los tres textos eran de ejemplo. Para volver a ponerla está entera en el historial de git, en el commit anterior al que la quitó.

Los logos de sponsors viven en `site/assets/sponsor-*.webp` y cada tarjeta enlaza al Instagram de la marca. Al copiar un link de Instagram hay que borrarle el `?stkn=...`: es un token de compartir atado a la sesion de quien lo copio y no corresponde publicarlo.

Los textos de la sección Clínicas son un borrador: la definición de qué es una clínica y el recuadro "Qué gana una marca" los escribí yo, no salieron de Natalí. Conviene que los repase antes de mandar el link. Faltan además los años de cada sede y, si los tiene, cuánta gente pasó por las clínicas.

Falta el bloque de alcance (seguidores, alcance mensual, público en competencia), que es el dato que primero pide una marca.

