# Feria de Turismo 3D — ESRN RURAL Virtual

## El proyecto

La FERIA DE TURISMO de la ESRN RURAL Virtual muestra el trabajo de los estudiantes de la escuela rural de Río Negro. Se recorre en primera persona una plaza central abierta con nueve pabellones, uno por corredor turístico, y un gazebo con el cartel FERIA DE TURISMO / ESRN Rural Virtual. El video de la Feria de Laguna Blanca y el cartel SEDE LAGUNA BLANCA / ESRN Rural Virtual están en el pabellón del corredor 3 (Meseta Norte y Transición), junto a esa sede.

Cada salón expone solo material real: videos, fotos, flyers, audios y fichas de texto, enmarcados en la pared con su etiqueta de sede y de proyecto. Los videos se reproducen dentro del marco, arrancan silenciados al acercarse y recuperan sonido con un clic. Las fichas se arman con los textos de `materiales.js`: usan el color del corredor,
no tienen viñetas y muestran el resumen completo sin cortes. Los resúmenes de las fichas se basan en la sesión «Resúmenes Feria de Turismo 2026» ("Para explicarlo en la feria"), con redacción revisada para su lectura en cartel. Al abrirlas se abre un visor con pestañas, la imagen completa y texto con scroll donde se lee la data organizada de los 14 proyectos —con los títulos y los
nombres de los estudiantes tal como se entregó— y el texto original del expediente
queda en un desplegable. El inventario cubre 14 sedes, de Aguada Guzmán a Villa Llanquín, y respeta los corredores del mapa de Wikiparajes: no hay sedes ni proyectos inventados.

La escena eligió una feria rural cálida: paredes crema y adobe, madera, guirnaldas, iluminación solo hemisférica y solar. Funciona en GitHub Pages y también por HTTP local; tiene controles táctiles, guardado de foto en PNG y diagnóstico con `?debug=1`. Los originales entregados por los estudiantes no se modificaron: en `material/` hay copias convertidas y comprimidas para que se vean en cualquier navegador.

Muestra virtual en 3D: una **plaza central** con 9 pabellones alrededor, uno por
corredor turístico, con las sedes y el material real de los estudiantes. En el centro
hay un gazebo con el cartel de la feria. Laguna Blanca y su video están en el
pabellón del corredor 3.
Se recorre en primera persona y se puede descargar una foto.

En cada salón, el material de los estudiantes se expone como en una galería: **un
cuadro enmarcado por cada video, cada foto y cada texto**, con su etiqueta de sede.
Los videos se ven y se reproducen **directamente en la pared**, con el mismo marco de
madera, cartelito y lupa de play que la pantalla de Laguna Blanca. El marco adopta la
proporción real de cada grabación: los 10 videos verticales son altos y angostos y los
2 horizontales son anchos, sin deformaciones. Videos, fotos y fichas están a la
altura de los ojos (centros entre 1,7 y 2,6 m), para no mirar hacia abajo.
Se encienden en silencio al acercarse
(solo el más cercano a la vez) y con un clic se les da sonido: no abre ninguna ventana.
Las fotos están en cuadros más grandes en la pared del fondo, completas y sin recortes,
con la imagen original en alta resolución (las infografías se leen desde la pared);
al hacer clic en una foto o en una ficha sí se abre su reproductor.

La muestra se reorganizó como una **feria rural cálida**: paredes crema y adobe,
madera y guirnaldas de colores. Los muros tienen una textura cálida crema→adobe,
los mostradores un mantel con dobladillo y una maceta ligera, y las fotos se piden
con mayor nitidez. Se eliminaron por completo la antesala y el recorrido
recto tipo pasillo de clínica, junto con los puestos, murales y afiches inventados
(inscripción, gastronomía, artesanías, trekking, "Mapa de Rio Negro", "Fiesta de la
Manzana", etc.) y sus 25 puntos de interés falsos. Tampoco quedan azules fríos ni
neones: la paleta es crema, adobe, madera y terracota, con un acento apagado distinto
por corredor. El arranque está directamente en
la plaza: los 9 pabellones tienen el frente abierto y miran al centro, con mostrador,
banco, cartelería de madera y **solo el material real** de `materiales.js`.
Los huecos entre pabellones están cerrados para que no parezcan callejones. Los
videos se reparten hasta 3 por pared y las fotos y fichas van de a 5 por fila, con
el excedente en la pared derecha: ningún cuadro queda apretado ni chico.

No se agregaron luces ni sombras nuevas: la iluminación es solo hemisférica y solar
(2 luces, sin luces puntuales) y un solo video se reproduce a la vez. La plaza es a
cielo abierto: no hay techo, lucernarios ni pinos. Los carteles de sede quedan por
encima del nivel del paso, para no tapar la entrada a los pabellones. En el gazebo, la guirnalda pasa por encima del cartel y los cuatro postes tienen
colisión. La pantalla de Laguna Blanca quedó dentro del pabellón del corredor 3,
entre 0,75 y 3,15 m. La galería de
fotos/fichas no ofrece pestañas de video: los videos se escuchan y se ven en la
pared, sin modal. Los videos están dentro de los pabellones y miran al
visitante; las fotos caben enteras en la pared de 8 m y conservan su proporción real.

Los salones se incorporaron por etapas para cuidar el rendimiento: primero la
estructura, carteles y fichas; después los posters con el material. Fuente de los
corredores: <https://viperplus.github.io/mapacorredsores/> (Wikiparajes).

Los originales entregados por los estudiantes no se modificaron: en `material/`
hay copias convertidas y comprimidas (MP4 H.264, JPG) para que se vean en cualquier
navegador y en móviles.

La versión de la escena queda marcada en `BUILD`, `version.txt` y el badge visible.
Todos los assets locales se piden con `?v=BUILD` para evitar mezclas por caché. Si el
autoplay es rechazado (por ejemplo en iOS), se reintenta solo: los videos arrancan
siempre silenciados y con un clic se activa el sonido. Hay aviso y recuperación si se
pierde el contexto WebGL, se liberan los decodificadores y las texturas al cerrar
ventanas y se valida la configuración guardada. Para diagnosticar, agregá `?debug=1`
al final de la URL de la escena.

---

## Cómo verla

**Online:** entrá al enlace de GitHub Pages y listo, no hay que instalar nada.

**En la compu (archivo local):** los navegadores no permiten reproducir video ni
cargar la escena 3D abriendo el archivo con doble clic. Hay que servirla por HTTP:

- Doble clic en `abrir_feria.vbs` (Windows), o
- en una terminal dentro de la carpeta: `python servir_feria.py`

y después abrir <http://127.0.0.1:8766/visita_virtual.html>

---

## Controles

| Tecla | Qué hace |
|---|---|
| `W A S D` / flechas | caminar |
| Mouse | mirar (clic para capturar el puntero) |
| `Shift` | correr |
| `Espacio` | saltar |
| `E` | ficha del puesto |
| `F` | guardar foto en PNG |
| `Esc` | pausa |

En celular o tablet aparecen botones táctiles para caminar y mirar con el dedo.

---

## Archivos

| Archivo | Para qué |
|---|---|
| `index.html` | dirección raíz: redirige a la feria |
| `visita_virtual.html` | la feria entera (escena, estilos y lógica) |
| `materiales.js` | inventario de las 14 sedes con material: poster, texto y archivos |
| `material/posters/` | posters de las sedes (respaldo de los cuadros) |
| `material/wall/` | imágenes enmarcadas que se ven en la pared, con etiqueta |
| `material/videos/` | videos de los estudiantes (MP4 H.264 comprimidos) |
| `material/fotos/` | fotos y flyers en JPG |
| `material/audio/` | audios de los proyectos |
| `video_galeria.mp4` | video de la pared del salón |
| `three.min.js` | motor 3D (Three.js r128) |

Si `three.min.js` faltara, el código cae solo a una copia desde un CDN, así que la
feria también anda con solo conexión a internet.

---

## Publicar en GitHub Pages

Los archivos de esta carpeta están listos para subir tal cual.

### Opción A — desde la web de GitHub (la más simple)

1. Entrá a <https://github.com/new>
2. Nombre del repositorio: `feria-turismo` → **Public** → *Create repository*
3. *Add file* → *Upload files* → arrastrá todos los archivos de esta carpeta
4. *Commit changes*

### Opción B — con git desde la terminal

```bash
cd feria-turismo
git init
git add .
git commit -m "Feria de turismo 3D"
git branch -M main
git remote add origin https://github.com/TU-USUARIO/feria-turismo.git
git push -u origin main
```

### Activar Pages

1. En el repositorio: **Settings** → **Pages**
2. *Source:* **Deploy from a branch**
3. *Branch:* **main** / **/ (root)** → **Save**
4. Esperá uno o dos minutos

Tu feria queda en: **`https://TU-USUARIO.github.io/feria-turismo/`**

### Actualizarla después

Editás los archivos, y en la carpeta:

```bash
git add .
git commit -m "Descripción del cambio"
git push
```

Se vuelve a publicar sola en 1 o 2 minutos.

---

## Si algo falla

| Síntoma | Qué revisar |
|---|---|
| Pantalla negra / no arranca | ¿El navegador soporta WebGL? Probá Chrome, Edge o Firefox actualizados. |
| "No se pudo cargar Three.js" | Faltan `three.min.js` y no hay internet para el respaldo. |
| No hay audio | Los navegadores lo recién habilitan después del primer clic en **ENTRAR**. |
| El video no se ve | Que exista `video_galeria.mp4` junto al HTML. |
| Un cuadro no muestra su material | Que estén `materiales.js` y la carpeta `material/` completos. |
| Se ve todo pero los cuadros quedan vacíos | Probá con `Ctrl+F5` para renovar la caché del navegador. |

---

Trabajo de aula — ESRN RURAL · Río Negro · Feria de Laguna Blanca
