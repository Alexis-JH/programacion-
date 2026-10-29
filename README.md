# Planificador de Alexis Macalupu con kardex

## Propósito
Autor: Alexis Jheampiers Macalupu Coronel (curso ET505, Semana 9, trabajo individual).

Mejora del Planificador de materiales de la semana 7. El planificador original calcula el costo de un pedido en céntimos enteros y comprueba que no supere el presupuesto de S/ 220.00 (taller de manualidades ficticio para 22 estudiantes de 4.° grado, S/ 10 por estudiante). En la semana 9 se añade un **kardex** de existencias físicas: materiales con código estable, búsqueda, cambio de nombre por código, entradas y salidas, historial, persistencia en el navegador y exportación a CSV.

El presupuesto (dinero, en céntimos) y la existencia (unidades físicas) son datos distintos y no se mezclan. Todos los datos son ficticios.

## Archivos
- `index.html`: estructura de la página. Contiene el planificador (S7) y, debajo, la sección del kardex (`<section id="kardex">`, ids `k-*`). Enlaza `styles.css`, `app.js` y `kardex.js`.
- `styles.css`: apariencia. Conserva las reglas de S7 y añade al final la personalización de S9 (color verde, tamaño de la etiqueta del kardex, tabla y selector).
- `app.js`: lógica del planificador de S7 (`calcularTotal`, `validarPedido`, mensajes). No se modificó en S9.
- `kardex.js`: lógica nueva del kardex. Reglas sin acceso a pantalla (`saldoDe`, `agregarMovimiento`, `siguienteCodigo`, `exportarCSV`) y, después, la interfaz con `localStorage`.
- `README.md`: este documento.

El orden de carga en `index.html` es `app.js` y luego `kardex.js`. No comparten variables: `kardex.js` solo depende de los ids `k-*` de su propia sección.

## Ejecutar y usar
**Local:** conserve juntos los cinco archivos y abra `index.html` en Chrome o Edge. No requiere instalar nada ni internet.

**Publicado:** abra el enlace de GitHub Pages indicado abajo.

Uso del kardex:
1. Escriba el nombre de un material ficticio y pulse **Crear material**. Recibe un código estable (`MAT-001`, `MAT-002`, ...).
2. Use **Buscar por nombre o código** para filtrar y elija el material en la lista. Si la búsqueda no tiene coincidencias, no hay material seleccionado y no se actúa sobre la selección anterior.
3. Elija **ENTRADA** o **SALIDA**, escriba una cantidad entera positiva y pulse **Registrar movimiento**. Existencia = entradas − salidas. Una salida mayor a la existencia se rechaza sin guardar nada.
4. **Cambiar nombre** modifica el material por su código; el historial y los demás materiales no cambian.
5. **Eliminar sin movimientos o inactivar**: si el material no tiene movimientos se elimina previa confirmación (se puede cancelar); si tiene movimientos se inactiva y su historial se conserva.
6. **Exportar CSV** descarga `movimientos-materiales.csv` (separador `;`, UTF-8 con BOM) para abrirlo en Excel.

## Publicación
Repositorio: [PEGAR AQUÍ la URL de mi repositorio de GitHub]

Sitio GitHub Pages: [PEGAR AQUÍ la URL que GitHub Pages muestra]

## Integración de los fragmentos (S9)
| Fragmento | Dónde se integró | Adaptación propia |
|---|---|---|
| `kardex.html` | `index.html`, después de la sección «Preparar un pedido» y fuera de su formulario (sin formularios anidados) | `novalidate` en sus dos formularios para mostrar los mensajes propios; etiqueta «Nombre del material ficticio» |
| `kardex.js` | Archivo nuevo, enlazado con `<script src="kardex.js">` después de `app.js` | Código legible `MAT-001` como id estable (función `siguienteCodigo`) en lugar de un UUID largo; corregido el texto «Use al menos 3 caracteres.» |
| `personalizacion.css` | Final de `styles.css` | El selector `#conv-form` (otro proyecto) se cambió por `#formulario`, el formulario del planificador; se añadieron reglas para el `select` y el mensaje del kardex |

Además se reemplazó el texto de S7 «Su reto de programación / avisos de pendiente» por «Cómo usar el planificador», porque los tres TODO ya estaban completados.

## Personalización
- Etiqueta HTML: «Nombre del material ficticio» (`label.etiqueta-kardex`).
- Tamaño CSS de esa etiqueta: `font-size: 1.25rem`, en negrita.
- Paleta RGB: verde `rgb(22,101,52)` para botones y etiqueta, sobre texto blanco (contraste alto).

## Aportes y ayuda recibida
- Aporte propio: proyecto S7 (cálculo, validación, presupuesto de S/ 220.00) y elección de la personalización.
- Fragmentos suministrados por la asignatura: `kardex.html`, `kardex.js`, `personalizacion.css`.
- Ayuda de IA: asistente Claude (Anthropic), 28/10/2026, para integrar los fragmentos, proponer las adaptaciones indicadas arriba, ejecutar las pruebas en un navegador automatizado y preparar el borrador del informe. El detalle de consultas, errores corregidos y pruebas está en el PDF entregado en MAXEDRA (el PDF no se publica aquí).

## Límites
- Los datos se guardan en `localStorage`: solo existen en este navegador y en este origen. No hay base de datos compartida ni varios usuarios.
- El CSV es una copia de los movimientos en el momento de exportar; no se sincroniza con Excel.
- Si el navegador bloquea el almacenamiento, el kardex avisa y no sobrescribe datos.
- Los datos son ficticios; no se guardan datos personales ni claves.
