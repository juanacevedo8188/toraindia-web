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
| `disciplinas · las cuatro tarjetas` | Sprint, Técnico, Maratón, Formación |
| `compromiso · texto y numeros` | Sección "Más que competir" |
| `testimonios · cada bloque es una persona` | Frase, nombre y rol de cada testimonio |
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
- Al cambiar el texto que se ve al compartir el link, WhatsApp y las redes pueden tardar en actualizarlo por su propia caché.

## Contenido pendiente

El calendario de la temporada 2026/27 tiene **fechas inventadas** y lo avisa en pantalla. Hay que reemplazarlas por las reales antes de mandarle el link a una marca: bloque `TEXTO: temporada · las 8 fechas`. Si cambia la cantidad de fechas, actualizar también los cuatro contadores en `TEXTO: temporada · titulo y numeros`.

Los tres testimonios están **inventados** y lo avisan en pantalla. Hay que reemplazarlos por frases reales, con nombre y rol de quien las dice: bloque `TEXTO: testimonios`.

La sección Sponsors espera nombres y logos confirmados. No se deben interpretar las marcas visibles en las tablas de referencia como sponsors.

Falta el bloque de alcance (seguidores, alcance mensual, público en competencia), que es el dato que primero pide una marca.

