# El Eco de las Mareas — Estado del proyecto
### Documento de referencia para retomar el trabajo en cualquier momento

## Repositorio
- **GitHub:** https://github.com/colladoalan/Ecos-de-las-mareas (público)
- **Sitio publicado:** https://colladoalan.github.io/Ecos-de-las-mareas/
- **Archivo principal:** `El Eco de las Mareas.html` (= `index.html`, mismo contenido)

## Flujo de trabajo establecido
1. Todos los cambios se hacen acá en el chat — nada se sube solo.
2. **Solo subo a git cuando el usuario lo pide explícitamente** ("subilo", "dale", etc.) — nunca por mi cuenta.
3. Antes de cada push, reviso primero si hay cambios remotos nuevos (`git fetch` + comparar) por si alguien subió algo directo desde github.com, para no pisarlo.
4. Las imágenes del sitio usan **URLs absolutas a GitHub** (`https://raw.githubusercontent.com/colladoalan/Ecos-de-las-mareas/main/assets/...`), no rutas relativas — así funcionan sin depender de tener la carpeta `assets/` al lado del HTML.
5. Cuando reemplazo una imagen con el mismo nombre de archivo, sumo/subo el número de versión en el query string (`?v=2`, `?v=3`...) para evitar problemas de caché del navegador.

## Estructura del sitio (`El Eco de las Mareas.html`)
- **Botón "Tráiler"** (arriba del todo del panel lateral) → galería de planos ya generados, organizada por escena, con:
  - Modo edición (arrastrar para reordenar, click para renombrar, crear/borrar planos y escenas, exportar cambios para pegarme en el chat).
  - Lightbox con flechas de navegación, botón de comentarios y botón de descarga en tamaño completo.
- **Grupos desplegables** en el menú lateral: Personajes, Escenografías, Embarcación, Producción del tráiler.
- **Sistema de comentarios (Giscus)** ya configurado y funcionando — usa GitHub Discussions del mismo repo. Login con cuenta de GitHub requerido para comentar (no para leer).

## Documentos del proyecto (fichas y prompts)
- **Personajes:** Clara, Tomás, Mateo (15 años — confirmado, no 17), Sofía, Dr. Vicente Olivera, Alfi (mascota/asistente, puede transformarse manteniendo ojos ámbar + estrías azules), Dron doméstico (Mini Dron Auxiliar, reemplazó a los "drones pajarito").
- **Embarcación:** `ficha_benteveo.md` — velero moderno de fibra de vidrio (NO madera), basado en un Beneteau First 30 real (solo de referencia interna, nunca nombrar la marca en prompts). Nombre "Benteveo" pintado en el espejo de popa, logo de pájaro origami en la vela mayor (blanca, prolija, no desteñida), matrícula 620772, timón único en bañera abierta (no timonera cerrada).
- **Escenografías** (separadas en archivos individuales): Nodo Ancla 7 (módulos circulares + brazo ramificado, dos puertos — carga grande y marina chica), Costa de Mar del Plata (Playa Bristol, Hotel Provincial y Casino, sin acantilados), Casa Martínez, Puerto de Mar del Plata, El mar/tormenta (viento fuerte, poca lluvia).
- **Prompts de producción:** `prompts_imagenes_el_eco_de_las_mareas.md`, `prompts_dobles_por_plano.md` (imagen+video, 27 planos), `planos_video_por_escena.md`. Estructura actual: Escenas 01 a 08 (se unificaron 04+05 en una sola Escena 04, y se renumeraron las siguientes para que quede cronológico sin saltos).
- **Storyboard oficial:** `storyboard_el_eco_de_las_mareas.html` (usa numeración por CLIP del guion original — todavía no está unificada con el sistema de Escenas de los prompts; es una inconsistencia conocida y pendiente).

## Pendientes conocidos (sin resolver)
- Unificar la numeración CLIP (storyboard) vs Escena (prompts) en un solo sistema.
- El mecanismo de Alfi tiene dos versiones en danza: pulso de luz bioluminiscente vs frecuencia acústica por los transductores del Benteveo — falta decidir cuál es la definitiva.
- No hay ficha del antagonista (Vortex Corp) — el usuario confirmó que no es prioridad para un tráiler.
- Instrumental de a bordo: en algunas imágenes generadas aparece la marca real "B&G" — hay que evitarla en próximas generaciones (usar un nombre inventado).

## Token de GitHub
El usuario generó un Personal Access Token fine-grained (scope: solo este repo, permiso Contents: Read and write) para que yo pueda pushear. Si expira o se revoca, hay que pedirle uno nuevo con los mismos pasos: Settings → Developer settings → Fine-grained tokens → Only this repo → Contents: Read and write.
