# Licores PAZ

Sitio web de una licorera, hecho con HTML y CSS.

Repositorio: https://github.com/pazzz200/Licorera_PAZ_HTML

## 1. El proyecto

Licores PAZ es una licorera que vende cervezas, aguardiente, ron, whisky y mucha variedad de licores, con entrega a domicilio.

- Para quien es: personas mayores de 18 años que quieren ver los productos y los precios.
- Que necesita el cliente: una pagina sencilla para mostrar productos, precios, horarios y como llegar, y un formulario para recibir pedidos.

## 2. Estructura

Archivos y carpetas del proyecto:

- index.html: la pagina de inicio
- precios.html: la pagina de precios y el formulario
- README.md: este documento
- css/styles.css: los estilos de las dos paginas
- images: el logo y las fotos
- capturas: las capturas de este README

Etiquetas que use:

- header: la parte de arriba, con el logo y el menu.
- nav: el menu con los enlaces.
- main: el contenido principal de cada pagina.
- section: cada bloque de la pagina (productos, horarios, opiniones).
- article: cada tarjeta de producto.
- footer: la parte de abajo.

## 3. Sistema visual

Hice un diseño minimalista con fondo negro, porque el logo es dorado con negro y asi combina.

- Fondo: negro #000
- Texto: blanco suave #eee
- Enlaces y boton: blanco #fff
- Texto secundario: gris #aaa
- Lineas: gris oscuro #333
- Fuente: Arial, Helvetica, sans-serif

Pendiente: pasar estos valores a variables en :root.

## 4. Especificidad

La especificidad se cuenta asi: (IDs, clases, etiquetas). Gana la regla que tenga el numero mas alto.

### Conflicto 1: color del menu

- a vale (0,0,1) y pone color #fff
- nav a vale (0,0,2) y pone color #aaa

Gana nav a porque tiene 2 etiquetas. Por eso el menu se ve gris.

### Conflicto 2: alto de las fotos de los productos

- img vale (0,0,1) y pone height auto
- article img vale (0,0,2) y pone height 180px

Gana article img. Por eso las tres fotos quedan del mismo alto.

### Conflicto 3: ultima fila de la tabla

- td vale (0,0,1) y pone text-align left
- tfoot td vale (0,0,2) y pone text-align center

Gana tfoot td. Por eso el texto de "Domicilio gratis" queda centrado.

Pendiente: un conflicto por orden (empate) y las capturas del inspector.

## 5. Herencia

- Se hereda: color. Lo puse solo en el body y todos los textos salen blancos.
- No se hereda: border-bottom. Cada section tiene una linea abajo, pero los parrafos de adentro no.

## 6. Modelo de cajas

Uso box-sizing: border-box, entonces el ancho ya incluye el padding y el borde.

Ancho de un campo del formulario en computador:

- El main mide 800 px y tiene 20 px de padding a cada lado, entonces adentro quedan 760 px.
- El input tiene width 100%, o sea 760 px.
- Contenido 742 + padding 16 + borde 2 = 760 px.

Margenes que se solapan: entre los dos parrafos de "Bienvenido" cada uno tiene 16 px de margen, pero el espacio entre ellos es de 16 px y no de 32 px, porque los margenes se juntan.

## 7. Selectores

Pendiente: todavia no uso una pseudoclase estructural como :nth-child.

## 8. Responsive

- Las dos paginas tienen la etiqueta meta viewport.
- Las imagenes tienen max-width 100% para que no se salgan de la pantalla.
- Las tarjetas tienen min-width 200px, entonces en pantallas pequeñas bajan una debajo de otra.

Pendiente: agregar el @media para celular.

## 9. Problemas y soluciones

El CSS no funcionaba. El archivo styles.css estaba suelto y el HTML lo buscaba en css/styles.css. Lo arregle creando la carpeta css y moviendo el archivo ahi.

El logo se veia re grande. Movi el logo al header, pero la regla del CSS decia #presentacion img y ya no le aplicaba. Lo arregle cambiando el selector a header img con width 180px.

## 10. Evidencias

Captura 1: la pagina antes de que funcionara el CSS.

![Captura 1](capturas/captura%201.jpeg)

Captura 2: inicio con el logo y el menu.

![Captura 2](capturas/captura%202.jpeg)

Captura 3: pagina de precios.

![Captura 3](capturas/captura%203.jpeg)

Captura 4: productos, horarios y opiniones.

![Captura 4](capturas/captura%204.jpeg)
