# 🚚 DAMM Delivery System - TeamFedora-ProjectDamm

## Resumen del proyecto

Nuestro proyecto consiste en un sistema formado por **dos aplicaciones Android** y un **servidor central**.

- **App Cliente** (para bares y restaurantes): permite hacer pedidos de bebidas, elegir cantidades y seleccionar el horario preferido para la entrega.
- **App Repartidor**: muestra los pedidos activos sobre un mapa, con cada parada marcada, y permite abrir Google Maps para seguir la ruta óptima.
- **Servidor central**: almacena los pedidos en una base de datos y sincroniza la información entre ambas apps en tiempo real.

### Características clave

- **Sin APIs externas** para la lógica de negocio: la comunicación entre cliente, servidor y repartidor es directa mediante un protocolo propio.
- **Telemetría cifrada** de extremo a extremo (AES-256, TLS/ECDH) para garantizar la seguridad de los datos.
- **Mapas integrados** en la app del repartidor que marcan cada parada y permiten navegar paso a paso con Google Maps.
- **Optimización automática** de rutas y carga del camión para lograr repartos más rápidos, ordenados y eficientes.
- **Gestión de horarios** de reparto seleccionados por el cliente, respetados automáticamente por el sistema.

## Arquitectura

<img width="1536" height="1024" alt="IMGINTERHACK" src="https://github.com/user-attachments/assets/af96581c-d3a7-456b-ad0d-4466df07eee2" />


- La base de datos reside en el servidor y es el único punto central de verdad.
- No se utilizan APIs REST públicas; la comunicación se realiza mediante sockets seguros o colas internas con telemetría cifrada.

## Funcionalidades

### App Cliente
- Catálogo de bebidas con precios.
- Selección de cantidades y horario de entrega.
- Seguimiento del estado del pedido.

### App Repartidor
- Mapa interactivo con todas las paradas pendientes.
- Marcadores personalizados por cliente.
- Botón de navegación que abre Google Maps con la ruta óptima (orden automático de paradas).
- Confirmación de entregas realizadas.

### Servidor
- Registro seguro de pedidos y usuarios.
- Lógica de optimización de rutas (por horario y proximidad geográfica).
- Panel web básico de administración.

## Seguridad y eficiencia

- Todo el tráfico entre apps y servidor está cifrado (telemetría incluida).
- Autenticación de dispositivos mediante credenciales únicas.
- La optimización de rutas reduce distancia recorrida → menor consumo y emisiones.

### Proyecto presentado en INTERHACK para DAMM.
