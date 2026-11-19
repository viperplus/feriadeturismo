# Feria de Turismo 3D — ESRN RURAL Virtual

Muestra virtual en 3D: seis puestos de trabajos, murales de los cursos, el
video de la Feria de Laguna Blanca y un **Paseo de los Corredores** con 9 salones,
uno por corredor turístico de Río Negro, con las sedes que lo integran y un espacio
preparado para el video/foto de cada expo. Se recorre en primera persona, con ficha
de cada salón y foto para descargar.

Fuente de los corredores y sedes: <https://viperplus.github.io/mapacorredsores/> (Wikiparajes).

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
| `E` | ficha del puesto o del corredor |
| `F` | guardar foto en PNG |
| `Esc` | pausa |

En celular o tablet aparecen botones táctiles para caminar y mirar con el dedo.

---

## Archivos

| Archivo | Para qué |
|---|---|
| `index.html` | dirección raíz: redirige a la feria |
| `visita_virtual.html` | la feria entera (escena, estilos y lógica) |
| `video_galeria.mp4` | video de la pared del salón (Laguna Blanca) |
| `three.min.js` | motor 3D (Three.js r128) |

---

## Los 9 corredores y sus sedes

Al fondo del salón principal hay un vano que lleva al **Paseo de los Corredores**.
Cada salón tiene el cartel del corredor, las placas con sus sedes, un resumen y,
apretando `E`, la ficha completa (patrimonio, fiestas, identidad, flora, fauna,
emprendimientos y opciones sustentable/sostenible).

| # | Corredor | Sedes |
|---|---|---|
| 1 | Lago Pellegrini | Lago Pellegrini |
| 2 | Valle Verde y Peñas Blancas | Valle Verde, Peñas Blancas |
| 3 | Meseta Norte y Transición | Cerro Policía, Aguada Guzmán, Naupahuen, Mencué, Laguna Blanca, Blancura Centro, Colan Conhué |
| 4 | Precordillera y Cuenca del Limay | Corralito, Villa Llanquín, El Manso |
| 5 | Suroeste (La Trochita) | Río Chico, Mamuel Choique |
| 6 | Somuncura Centro-Oeste y Línea Sur | El Caín, Aguada de Guerra, Comicó, Yaminué, Rincón Treneta |
| 7 | Chelforó (Valle Medio Oriental) | Chelforó |
| 8 | Vertiente Oriental, Los Berros y Costa Marítima | Cona Niyeu, Arroyo Los Berros, Sierra Paileman, Aguada Cecilio |
| 9 | Litoral Atlántico (Nodo Único) | El Cóndor |

### Cómo agregar el video/foto de cada expo

Cada salón ya tiene su marco en la pared con el cartel *"Espacio preparado"*.
Cuando lleguen los archivos:

1. Copiar el video (o la foto) a esta carpeta, al lado de `visita_virtual.html`.
2. En `visita_virtual.html`, buscar `EXPO_SLOTS` (dentro del bloque
   `ALA DE CORREDORES TURÍSTICOS`). Hay 9 entradas, una por corredor, con
   `file:''` e `id:''`.
3. Completar `file:'nombre-del-archivo.mp4'` en la del corredor correspondiente.
   El cartel de "próximamente" se reemplaza solo por el reproductor, igual que
   el video de Laguna Blanca. Si es una foto, convertirla a mp4 (o avisar para
   adaptar el marco a imagen).
4. Subir los archivos con `git add . && git commit -m " videos de expo " && git push`.

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

---

Trabajo de aula — ESRN RURAL · Río Negro · Feria de Laguna Blanca
