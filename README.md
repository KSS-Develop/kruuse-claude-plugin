# Kruuse para Claude

![Kruuse](assets/logo.png)

Plugin de [Kruuse Chile](https://kruuse.cl/cl) para Claude. Kruuse vende maquinaria y herramientas para taller, carpintería, metalmecánica, jardín y construcción de marcas como Scheppach, Holzstar, Metallkraft, Optimum y Unicraft, con despacho a todo Chile.

Con este plugin, Claude puede:

- Buscar productos por nombre, modelo, marca o SKU.
- Mostrar la ficha técnica, los manuales y las variantes (por ejemplo voltaje o presión).
- Entregar el precio vigente en pesos chilenos con IVA y si hay stock local o es un producto a pedido con su plazo.
- Armar un carro y entregar un enlace que lo abre en kruuse.cl, donde se elige el despacho y se paga.

## Instalación

En Claude, agrégalo desde el directorio de plugins. En Claude Code:

```
/plugin install kruuse --marketplace KSS-Develop/kruuse-claude-plugin
```

## Qué contiene

- `.mcp.json`: el conector remoto de Kruuse, `https://kruuse.cl/api/ucp/mcp` (Model Context Protocol sobre HTTPS, sin inicio de sesión). Implementa el catálogo y el carro del [Universal Commerce Protocol](https://ucp.dev).
- `skills/comprar-en-kruuse`: instrucciones para que Claude busque, compare y arme el carro de forma correcta.

El plugin no ejecuta código en el equipo de la persona.

## Datos que envía y guarda

- Las búsquedas y los identificadores de producto que Claude consulta se envían al conector de Kruuse (`kruuse.cl`), que responde con datos públicos del catálogo. No hay inicio de sesión ni datos de cuenta.
- Al armar un carro se envían sólo las variantes y cantidades elegidas. El carro no recibe datos personales desde Claude.
- Si la persona abre el carro en kruuse.cl e ingresa ahí sus datos de contacto o despacho pero no termina la compra, el carro se vacía a los 30 días y esos datos se borran.
- El plugin no procesa pagos ni recibe datos de tarjeta: el pago se hace en el checkout de kruuse.cl.
- No envía datos a ningún otro servicio.

Política de privacidad: https://kruuse.cl/cl/politica-de-privacidad

## Límites

Los precios no incluyen despacho y no reservan stock. El pago, el despacho y la boleta o factura se completan en kruuse.cl. No consulta pedidos ya hechos. Las fichas están en español.

## Soporte

https://kruuse.cl/cl/contacto
