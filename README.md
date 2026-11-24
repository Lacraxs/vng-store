# VNG Store

Tienda online de **VNG Store**, joyería de diseño propio ([@vngstore75](https://www.instagram.com/vngstore75/) · [@vngstore5](https://www.tiktok.com/@vngstore5)).

## Qué incluye

- **Inicio de sesión obligatorio** con carrusel 3D de las piezas de fondo.
- **Portada** con el logo, fondo de mármol en movimiento y cursor personalizado.
- **Colección** en rueda 3D (ratón, arrastrar o flechas).
- **Productos**: todas las piezas, con ficha, detalles, cuidados y tallas.
- **Carrito y pago**, preparado para Stripe.
- **Mi pedido**: la clienta sigue su pedido (Recibido → Pagado → Enviado → En reparto → Entregado).
- **Atención al cliente**: formulario de consultas.
- **Panel de la vendedora** (privado, con permisos y contraseña): pedidos, productos (añadir, precio, stock), clientes, mensajes y ajustes.
- Idiomas: español e inglés.

## Estructura

```
index.html   la web completa (HTML, CSS y JS)
img/         fotos de producto, logo y textura de mármol
```

## Importante

Esta versión está hecha para funcionar como **artifact de Claude**: el guardado de pedidos, los permisos del panel, la subida de fotos y los emails usan las capacidades de Claude (`claude.use("db")`, `"user"`, `"assets"`, `"mcp"`).

Si abres `index.html` fuera de Claude (GitHub Pages, un hosting…), la tienda se ve y funciona, pero los datos se guardan solo en el navegador de cada persona y el panel queda bloqueado. Para una tienda real hace falta un pequeño servidor que:

1. Guarde pedidos, productos y consultas en una base de datos.
2. Cree el pago con **Stripe Checkout** y reciba el aviso `checkout.session.completed` para marcar el pedido como **Pagado**.
3. Envíe los emails (confirmación de compra y pedido entregado) desde el correo de la tienda.
4. Proteja el panel con login y contraseña en el servidor.

La configuración de Stripe está al principio del script, en `STRIPE` (`checkoutEndpoint` o `paymentLinks`).

## Créditos

Programación y diseño: **Lacrax & Jerix**.
