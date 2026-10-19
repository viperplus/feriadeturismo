# Feria de Turismo 3D — ESRN RURAL Virtual

Muestra virtual en 3D: seis puestos de trabajos, maquetas, murales de los cursos y el
video de la Feria de Laguna Blanca. Se recorre en primera persona, con ficha de cada
puesto y foto para descargar.

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

---

Trabajo de aula — ESRN RURAL · Río Negro · Feria de Laguna Blanca
