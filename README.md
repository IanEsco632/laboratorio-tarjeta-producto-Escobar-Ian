# Práctica de laboratorio · `<tarjeta-producto>`

Programación Integrativa de Componentes Web · Unidad 1: Web Components

| Dato | Completa |
|---|---|
| Emprendimiento | Frut & Fresh Drinks |
| Estudiantes (Apellido Nombre) | Escobar Rivadeneira Ian Alfredo <br> Sandoval Espinosa José María <br> Alcaciega Tigse Diego Alejandro <br>|
| NRC | 36642 |
| Fecha | 14 de octubre de 2026 |
| Enlace del repositorio | [https://github.com/IanEsco632/laboratorio-tarjeta-producto-Escobar-Ian.git] |

## Propuesta del emprendimiento

- Nombre del emprendimiento: Frut & Fresh Drinks
- Problema que resuelve: Falta de opciones de bebidas naturales, refrescantes y de calidad rápida para estudiantes y profesionales que buscan hidratarse de forma saludable durante el día.
- Cliente al que se dirige: Jóvenes y adultos de la comunidad universitaria y público general que valoran lo natural y refrescante.

## Cómo abrir el proyecto

1. Abre la carpeta en Visual Studio Code.
2. Clic derecho sobre `index.html` → **Open with Live Server**. Los módulos no cargan con `file://`.
3. Abre las herramientas del navegador (F12) y deja visible la pestaña **Consola**.

## Registro de los pasos

### Paso 1 · index.html y el módulo

- Etiqueta que registramos: `<tarjeta-producto>`
- ¿Por qué el nombre debe llevar guion?: Porque la especificación de Web Components de W3C exige que todos los elementos personalizados (Custom Elements) lleven obligatoriamente un guion medio para diferenciarse de las etiquetas HTML nativas.
- Ruta del módulo y cómo lo importa la página: Ruta `./componentes/tarjeta-producto.js` y la página lo importa mediante `<script type="module" src="./componentes/tarjeta-producto.js">`.

### Paso 2 · Plantilla, Shadow DOM y slots

- Slots con nombre que tiene la plantilla: `slot="foto"` y `slot="nombre"`.
- Texto de respaldo del slot sin nombre: `Sin descripción`
- ¿Qué pasaría si no usáramos `cloneNode(true)`?: El único nodo de la plantilla se movería físicamente de un elemento a otro en el DOM en lugar de clonarse, haciendo que solo la última tarjeta muestre el contenido y las anteriores queden vacías.

### Paso 3 · Atributo precio y estilos

- Método que reacciona cuando cambia `precio`: `attributeChangedCallback(nombre, anterior, valor)`
- Color de marca (`--color-marca`) y dónde lo definimos: Se definió como `#10b981` en el archivo `estilos.css` a nivel del selector `tarjeta-producto`.
- Valor de respaldo que usa el componente si la página no define la variable: `#10b981` (dentro de las funciones `var(--color-marca, #10b981)` en el Shadow DOM).

### Paso 4 · Tres productos del emprendimiento

| # | Producto | Precio |
|---|---|---|
| 1 | Jugo Natural de Naranja | $2.50 |
| 2 | Batido de Mora con Leche | $3.00 |
| 3 | Refresco de Maracuyá | $2.25 |

### Paso 5 · Repositorio del equipo

| Integrante | Qué hizo en este laboratorio |
|---|---|
| Escobar Rivadeneira Ian Alfredo | Diseño del componente `tarjeta-producto.js`, estructura del Shadow DOM, slots y lógica de atributos reactivos. |
| [Compañero 2] | Configuración del repositorio en GitHub, subida de archivos y pruebas en Live Server. |
| [Compañero 3] | Maquetación y redacción de la propuesta del emprendimiento en el README.md. |
| [Compañero 4] | Verificación de consola, pruebas con `setAttribute` y captura de pantalla final. |

## Verificación

Marca con una `x` lo que ya comprobaste en el navegador.

- [x] La etiqueta tiene guion.
- [x] La página solo cambia lo que el componente expone con `var()`.
- [x] `setAttribute` cambia el precio en pantalla.
- [x] La consola no muestra errores.

Prueba que usamos en la consola:

```js
document.querySelector("tarjeta-producto").setAttribute("precio", "25");