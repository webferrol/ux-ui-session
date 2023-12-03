# Usabilidad en HTML

## Content table

## Validadores HTML

El [validador W3C](https://validator.w3.org/) es una __herramienta__ proporcionada por la organización internacional que establece los estandares y pautas de la __World Wide Web__ y se encarga de validar y verificar la calidad del código los lenguajes de marcados utilizados en las páginas web.

## Comentarios

Utilice comentarios para otros desarroladores y programadores.

```html
<!-- Encabezado de la página -->
```

## Estructura indentada

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Título de página</title>
  <link rel="shortcut icon" href="favicon.ico" type="image/x-icon">
</head>
<body>
  
</body>
</html>
```

## Etiquetas

### meta

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

## Atributos

### label

Nos permite asociar un contenido a un control de formulario

```html
<label for="name">Nombre</label>
<input name="nombre" id="name" placeholder="Xurxo">
```

### role

Se describe para definir la función de un __elemento__.

### rel

En los enlaces para que los **motores de búsqueda** no rastreen la dirección podemos poner en el _atributo_ **rel** el valor "nofollow".

### alt

En las imágenes es conveniente utilizar el atributo **alt** para poner un "texto alternativo" en caso de que la imagen no se pueda cargar y que utilizarán los __lectores de pantalla__ cuando quieran referirse a ella.

```html
<a href="https://www.webferrol.com/admin" rel="nofollow">Acceso</a>
```

## ARIA

## Atributos aria

### aria-disabled 

[MDN](https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Attributes/aria-disabled)

    The aria-disabled state indicates that the element is perceivable but disabled, so it is not editable or otherwise operable.


```html
<button aria-disabled="true" tab-index="-1">Cerrar</button>
```

### aria-label

Para aquellos __elementos__ que no tienen contenido visible.

```html
<button aria-label="Close" onclick="myDialog.close()">X</button>
```
