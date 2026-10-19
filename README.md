# BRASA · Aplicación de pedidos v2

Demostración comercial por Vexel Graphics. Navegación diseñada para móvil, carta interactiva, carrito persistente y gestión local de pedidos. Identidad cálida en crema, naranja y verde oliva.

**Página:** https://tatorux.github.io/brasa-restaurante/

## Recorridos
- Carta con búsqueda, categorías y favoritos.
- Personalización: acompañamiento, extras, cantidad y notas.
- Carrito con entrega en mesa, recogida o domicilio de ejemplo ($4.500 COP).
- Checkout con datos de prueba, validación y total desglosado.
- Historial, detalle del pedido, repetición y simulación de estados.
- Club: cada 5 pedidos entregados habilita 15% de descuento en productos; reglas ilustrativas, sin valor real.
- Perfil, exportación/importación JSON con validación y confirmación.
- Administración en `#admin`: estados y disponibilidad de productos.

## Archivos
`index.html`, `style.css`, `app.js`: entrada, interfaz y lógica. `icon.svg` y `app.webmanifest`: identidad y modo de visualización standalone en navegadores compatibles. Las imágenes WebP están en la raíz. No requiere compilación. Puede abrirse con un servidor estático o GitHub Pages.

## Personalización
Productos y adicionales en `products`, tarifa demo en `delivery()`, colores en `:root`, identidad en `shell()`. Mantener los identificadores al cambiar textos. Los precios siempre deben volver a validarse en servidor en la versión operativa.

## Datos y límites
Guarda en `localStorage` bajo `brasa-v2`, separado de la primera versión. No requiere contraseña y no tiene usuarios reales. No procesa pagos, no envía pedidos, no manda WhatsApp y no comparte registros entre dispositivos. Usa datos ficticios. Las pestañas del mismo navegador reciben actualizaciones locales; esto no sustituye una base de datos.

Los registros de la versión inicial (`brasa-orders`) no se migran: pertenecen a otra estructura de demostración. El nuevo historial comienza vacío.

## Para producción
Autenticación, roles, base de datos compartida, validación de catálogo/precios/descuentos en servidor, transacciones de inventario, idempotencia de pedidos, manejo de fallos y respaldos, cumplimiento de tratamiento de datos y proveedores de mensajes/pagos configurados por el negocio. El panel demo abierto no se debe usar para operar datos reales.

## Validación v2
Node: sintaxis, cálculo del carrito, domicilio, recompensas y su restitución al cancelar, filtros, búsquedas vacías, renderizado de pantallas y existencia de recursos. Inspección final de la página publicada en navegador. La maqueta tiene reglas responsive para móvil, tableta y escritorio; no equivale a una prueba en todos los dispositivos físicos.
