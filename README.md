# Licores PAZ

Sitio web de una licorera, hecho con HTML y CSS.

Repositorio: https://github.com/pazzz200/Licorera_PAZ_HTML

## 1. El proyecto

**Licores PAZ** es una licorera que vende cervezas, aguardiente, ron, whisky y mucha variedad de licores, con entrega a domicilio.

- **Para quién es:** personas mayores de 18 años que quieren ver los productos y los precios.
- **Qué necesita el cliente:** una página sencilla para mostrar productos, precios, horarios y cómo llegar, y un formulario para recibir pedidos.

## 2. Estructura

```
Licorera_PAZ_HTML/
├── index.html      ← inicio
├── precios.html    ← precios y formulario
├── README.md
├── css/styles.css  ← estilos de las dos páginas
├── images/         ← logo y fotos
└── capturas/       ← capturas de este README
```

Etiquetas que usé:

- `header`: la parte de arriba, con el logo y el menú.
- `nav`: el menú con los enlaces.
- `main`: el contenido principal de cada página.
- `section`: cada bloque de la página (productos, horarios, opiniones…).
- `article`: cada tarjeta de producto.
- `footer`: la parte de abajo.

## 3. Sistema visual

Hice un diseño minimalista con fondo negro, porque el logo es dorado con negro y así combina.

- **Fondo:** negro `#000`.
- **Texto:** blanco suave `#eee`.
- **Enlaces y botón:** blanco `#fff`.
- **Texto secundario:** gris `#aaa`.
- **Líneas:** gris oscuro `#333`.
- **Fuente:** `Arial, Helvetica, sans-serif`.

Pendiente: pasar estos valores a variables en `:root`.

## 4. Especificidad

La especificidad se cuenta así: (IDs, clases, etiquetas). Gana la regla que tenga el número más alto.

### Conflicto 1: color del menú

```
a       → (0,0,1)   color: #fff
nav a   → (0,0,2)   color: #aaa
```

Gana `nav a` porque tiene 2 etiquetas. Por eso el menú se ve gris.

### Conflicto 2: alto de las fotos de los productos

```
img           → (0,0,1)   height: auto
article img   → (0,0,2)   height: 180px
```

Gana `article img`. Por eso las tres fotos quedan del mismo alto.

### Conflicto 3: última fila de la tabla

```
td         → (0,0,1)   text-align: left
tfoot td   → (0,0,2)   text-align: center
```

Gana `tfoot td`. Por eso el texto de "Domicilio gratis" queda centrado.

Pendiente: un conflicto por orden (empate) y las capturas del inspector.

## 5. Herencia

- **Se hereda:** `color`. Lo puse solo en el `body` y todos los textos salen blancos.
- **No se hereda:** `border-bottom`. Cada `section` tiene una línea abajo, pero los párrafos de adentro no.

## 6. Modelo de cajas

Uso `box-sizing: border-box`, entonces el ancho ya incluye el padding y el borde.

Ancho de un campo del formulario en computador:

- `main` mide 800 px y tiene 20 px de padding a cada lado, entonces adentro quedan **760 px**.
- El `input` tiene `width: 100%`, o sea 760 px.
- Contenido 742 + padding 16 + borde 2 = **760 px**.

Márgenes que se solapan: entre los dos párrafos de "Bienvenido" cada uno tiene 16 px de margen, pero el espacio entre ellos es de 16 px y no de 32 px, porque los márgenes se juntan.

## 7. Selectores

Pendiente: todavía no uso una pseudoclase estructural como `:nth-child`.

## 8. Responsive

- Las dos páginas tienen la etiqueta `meta viewport`.
- Las imágenes tienen `max-width: 100%` para que no se salgan de la pantalla.
- Las tarjetas tienen `min-width: 200px`, entonces en pantallas pequeñas bajan una debajo de otra.

Pendiente: agregar el `@media` para celular.

## 9. Problemas y soluciones

**El CSS no funcionaba.** El archivo `styles.css` estaba suelto y el HTML lo buscaba en `css/styles.css`. Lo arreglé creando la carpeta `css/` y moviendo el archivo ahí.

**El logo se veía gigante.** Moví el logo al `header`, pero la regla del CSS decía `#presentacion img` y ya no le aplicaba. Lo arreglé cambiando el selector a `header img` con `width: 180px`.

## 10. Evidencias

**Captura 1:** la página antes de que funcionara el CSS.

![Captura 1](capturas/captura%201.jpeg)

**Captura 2:** inicio con el logo y el menú.

![Captura 2](capturas/captura%202.jpeg)

**Captura 3:** página de precios.

![Captura 3](capturas/captura%203.jpeg)

**Captura 4:** productos, horarios y opiniones.

![Captura 4](capturas/captura%204.jpeg)

Pendiente: capturas a 360 px de ancho.
