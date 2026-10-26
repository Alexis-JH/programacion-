# Planificador de Alexis Macalupu — materiales educativos

## Autor y propósito
Autor: Alexis Jheampiers Macalupu Coronel (curso ET505, Semana 7, trabajo individual).
Sistema: Planificador de Alexis Macalupu.
Actividad educativa (ficticia): taller de manualidades para 22 estudiantes de 4.° grado de primaria. El sistema organiza el pedido de un material, calcula su costo en céntimos enteros y comprueba que no supere el presupuesto. Todos los datos son ficticios.

## Ejecutar
Descargue y conserve juntos index.html, styles.css y app.js. Abra index.html en Chrome o Edge. Edite app.js, guarde y recargue. No necesita instalar paquetes ni conectarse a internet.

## Responsabilidades
- index.html: estructura y entradas.
- styles.css: apariencia.
- app.js: objeto limites, cálculo y validación sin acceso a pantalla; luego lectura y acciones de interfaz.

## Pendientes obligatorios (completados)
- TODO 1: calcularTotal(pedido) devuelve pedido.cantidad * Math.round(pedido.precio * 100), es decir, cantidad por precio convertido a céntimos enteros.
- TODO 2: validarPedido(pedido) devuelve "El total supera el presupuesto." si total > limites.presupuestoCentimos; si cumple devuelve "" (cadena vacía). No lee ni modifica la pantalla.
- TODO 3: el botón Comprobar pedido llama a const error = validarPedido(pedido); Confirmar simulación usa la misma función, por lo que ambos botones comparten una sola validación.

## Mi personalización
- Nombre del sistema: "Planificador de Alexis Macalupu" (en <title> y <h1> de index.html).
- Actividad: taller de manualidades para 22 estudiantes de 4.° grado. Material de ejemplo: cartulinas (placeholder "Ejemplo: cartulinas").
- Presupuesto propio: S/ 220.00, es decir limites.presupuestoCentimos:22000. Es distinto de S/150, está entre S/50 y S/300 y es múltiplo de S/10. Justificación: se asignan S/10 por estudiante y son 22 estudiantes (22 x 10 = 220).
- El texto visible de index.html dice S/ 220.00 y coincide con app.js. Se mantienen maxCantidad:30 y maxPrecio:50.

## Pruebas
Se ejecutaron cinco pruebas en el navegador, con ambos botones (Comprobar pedido y Confirmar simulación); los resultados y capturas están en el informe PDF:
1. Válido: Cartulinas, 10 unidades a S/5.00 → total S/ 50.00, saldo S/ 170.00.
2. Inválido: material vacío, y cantidad 2.5 → error rojo; no se confirma.
3. Límite: 10 unidades a S/22.00 (presupuesto/10) → total S/ 220.00, saldo S/ 0.00; se acepta.
4. Exceso: 10 unidades a S/22.01 → total S/ 220.10, exceso S/ 0.10; error rojo.
5. Se confirma un pedido válido, se intenta uno inválido y la ficha válida se conserva; luego Limpiar la elimina.

## Mi aporte y ayuda recibida
Modificaciones: completé los tres TODO en app.js, cambié limites.presupuestoCentimos a 22000, y personalicé index.html (título, encabezado, descripción de la actividad, presupuesto visible y ejemplo de material). Conservé mostrarMensaje y mostrarError sin cambios.
Error detectado y corregido: tras el TODO 1 y antes del TODO 2 la validación seguía devolviendo el aviso de pendiente; se resolvió con el TODO 2. Para el exceso se usa 22.01 (no 0.01), como indica la guía.
Ayuda recibida: utilicé el asistente de IA Claude (Anthropic) para aplicar los cambios de la guía paso a paso, proponer la personalización, ejecutar las pruebas en un navegador automatizado y armar el borrador del informe. También consulté las guías de MAXEDRA (cambios exactos y GitHub). Soy responsable de entender y explicar cada parte en la exposición individual.

## Repositorio individual y GitHub Pages
Cada alumno crea su propio repositorio. En la web de GitHub use New repository y después Add file > Upload files para subir estos cuatro archivos en la raíz; no suba el ZIP sin extraer. Guarde los cambios con Commit changes.
Para publicar: Settings > Pages > Deploy from a branch > main > /(root) > Save. GitHub Free permite Pages con repositorios públicos. Espere la publicación y abra la URL que GitHub muestre; compruebe ambos botones y actualice al subir cambios. Si aparece 404, compruebe index.html en la raíz y la rama seleccionada.
No suba contraseñas, datos reales de alumnos ni informes personales. El informe se entrega en MAXEDRA. GitHub Pages es opcional esta semana. Ejecute su copia local y conserve los archivos originales para sustentar. En MAXEDRA entregue únicamente un PDF; no adjunte código, ZIP, Word ni imágenes por separado.

Repositorio: (pendiente: pegar aquí el enlace de mi repositorio cuando lo cree)
Sitio: (pendiente: pegar aquí el enlace que GitHub Pages muestre, si lo publico)

Fuente: https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site

## Entrega y evaluación

Trabajo individual. El único PDF reúne explicación, personalización, capturas del código y del sistema, cinco pruebas y aportes documentados en README. Plazo: 17/10/2026 a las 20:00, Perú. Durante la práctica cada estudiante sube su plantilla a su propio GitHub; esto no reemplaza el PDF.

Rúbrica: organización y reutilización 5; personalización funcional 5; pruebas e informe coherente 5; exposición individual del trabajo 5. Las consultas del taller resuelven dudas y no sustituyen la exposición del cuarto criterio.

## Evolución propuesta
Semana 7: cálculo, validación y organización. Semana 8: crear y listar registros. Semana 9: buscar, modificar y eliminar. Semana 10: integración y comprobación individual. Las ampliaciones requieren las consignas de esas semanas; no se exigen en esta entrega.


## Mensajes visibles y pruebas de error

Esta versión muestra errores en rojo y resultados válidos en verde. Comprobar indica «Pedido no válido»; Confirmar indica «No se pudo confirmar». Si ya había un pedido válido, lo conserva y lo aclara. Los tres TODO siguen pendientes para el estudiante; los avisos de pendiente no son pruebas aprobadas. Complete esos cambios siguiendo la guía.

Busque las marcas TODO 1, TODO 2 y TODO 3; las líneas indicadas en la guía son orientativas. Mantenga las funciones mostrarMensaje y mostrarError, que ya están preparadas. Después de cambiar const error=null, conserve las líneas que siguen aunque difieran de la versión anterior de la guía.

Ejemplo con presupuesto S/150: 10 unidades a S/15.00 se aceptan. Para probar exceso, escriba S/15.01 como precio unitario: total S/150.10, exceso S/0.10. No reemplace el precio por S/0.01. Con otro presupuesto, use 10 unidades a presupuesto/10 y después aumente ese precio en S/0.01. Pruebe ambos botones.

Si ya avanzó, conserve su carpeta anterior y trabaje con una copia. Traslade sus tres cambios y su personalización a esta versión; no sobrescriba su trabajo sin conservarlo. La modalidad, la rúbrica y la entrega de un PDF siguen vigentes.
