# Proyecto Malcriado Store

## Descripción

Este proyecto consiste en una página web de merchandising inspirada en el álbum “Malcriado” de Lasso, desarrollada como práctica de Front-End utilizando HTML5 y CSS3.

La estructura general del sitio fue organizada mediante etiquetas semánticas como `<html>`, `<head>`, `<body>`, `<header>`, `<nav>`, `<main>`, `<section>`, `<article>` y `<footer>`, permitiendo una correcta organización y accesibilidad del contenido.

## Estructura y etiquetas utilizadas

Dentro del documento se utilizaron etiquetas como `<meta>` para configurar la codificación UTF-8 y el diseño responsive, `<link>` para conectar Google Fonts y el archivo CSS externo, y `<title>` para definir el nombre de cada página en el navegador.

La navegación del sitio fue desarrollada utilizando enlaces `<a>` junto con listas `<ul>` y `<li>`, permitiendo acceder a la página principal y a la sección de contacto. Además, se utilizaron etiquetas `<div>` para agrupar distintos elementos de la interfaz, como el logo y las secciones de contenido.

La página principal incluye títulos y textos mediante etiquetas `<h1>`, `<h2>`, `<h3>` y `<p>`, además de imágenes de productos implementadas con `<img>`. La sección de productos fue diseñada mediante cards responsivas utilizando Flexbox, donde cada tarjeta contiene información del producto y botones interactivos creados con la etiqueta `<button>`.

## Formulario de contacto

El proyecto también incorpora un formulario de contacto funcional desarrollado con las etiquetas `<form>`, `<label>`, `<input>` y `<textarea>`, permitiendo que los usuarios envíen mensajes mediante Formspree utilizando el método POST.

Los campos del formulario incluyen correo electrónico y mensaje, junto con un botón de envío implementado con `<button type="submit">`.

## Diseño visual y estilos

En cuanto al diseño visual, se utilizó un archivo CSS externo (`styles.css`) para aplicar estilos personalizados en el `<header>`, `<footer>`, formularios, botones, listas de navegación y tarjetas de productos.

También se implementaron propiedades CSS como:

- `background-color`
- `border-radius`
- `box-shadow`
- `padding`
- `margin`
- `gap`
- `object-fit`
- `font-size`

Además, se incorporaron tipografías externas de Google Fonts.

## Responsive Design

El sitio cuenta con diseño responsive mediante Flexbox y Media Queries, permitiendo adaptar la estructura de navegación, las cards de productos y el formulario de contacto a diferentes tamaños de pantalla y dispositivos móviles.

## Autor

Proyecto realizado por Natalia Fernanda Hiporre para el curso Talento Tech – Comisión 26123 de Front-End JS, con el objetivo de reforzar conocimientos de maquetación web, diseño responsivo y desarrollo de interfaces utilizando HTML5 y CSS3.

## Actualización: Incorporación de JavaScript y Datos Dinámicos

Para la segunda etapa del curso, el proyecto evolucionó sumando lógica de programación, persistencia de datos y una arquitectura de archivos modular basada en componentes interconectados.

### Nueva Estructura de Archivos y Carpetas

- **`data/`**: Contiene el archivo `productos.json`, el cual centraliza toda la información estructurada del catálogo (id, nombre, precio y rutas de imágenes para Gorra, Playera, Sudadera y Totebag).
- **`js/`**: Carpeta que organiza la lógica del negocio mediante módulos de JavaScript:
  - `index.js`: Script principal de la página de inicio. Se encarga de hacer la petición asrincrónica para traer el catálogo y construir la interfaz de la tienda.
  - `carrito.js`: Controlador encargado de renderizar dinámicamente las tarjetas dentro de la página del carrito de compras.
  - `contacto.js`: Script dedicado a inicializar y mantener actualizado el estado del contador en la vista de contacto.
  - `funcionesCarrito.js`: Contiene las funciones core para interactuar con los elementos del array (agregar, eliminar usando `splice()` o vaciar).
  - `storage.js`: Administra la persistencia de datos interactuando directamente con el `localStorage` mediante `JSON.stringify()` y `JSON.parse()`.
  - `ui.js`: Módulo reutilizable para el manejo visual de la interfaz (alertas y manipulación de texto del contador).

### Funcionalidades Técnicas Implementadas

- **Consumo Asincrónico de Datos**: Uso de `fetch()` en `index.js` para consumir de forma dinámica el catálogo desde `./data/productos.json` procesando las respuestas con promesas (`.then()` y `.catch()`).
- **Inyección Dinámica en el DOM**: Creación en tiempo real de componentes estructurales utilizando métodos nativos de JavaScript como `document.createElement()`, asignación de clases dinámicas (`classList.add()`) y ensamblado de nodos con `appendChild()` para pintar las tarjetas en los contenedores `#contenedor-tarjetas` y `#contenedor-carrito`.
- **Manejo de Eventos y Ciclo de Vida**: Uso de los escuchadores `addEventListener("click")` en los botones de compra y control preciso del ciclo de vida de la aplicación mediante el evento global `DOMContentLoaded` para garantizar que el contador refleje el estado real del carrito en todas las vistas del sitio desde el arranque.
