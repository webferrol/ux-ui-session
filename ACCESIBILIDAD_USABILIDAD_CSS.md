# Usabilidad en CSS

## Content table


## Properties

### scroll-behavior

- Value: smooth


```css
/*
✔ https://caniuse.com/?search=scroll-behavior

La propiedad CSS scroll-behavior especifica el comportamiento del desplazamiento para un elemento con desplazamiento

❤ smooth
La caja se desplaza suavemente, utilizando una función de tiempo definida por el agente de usuario (user-agent) sobre un período de tiempo también definido por éste. Los agentes de usuario seguirán las convenciones de su propia plataforma, en caso de que existan.*/

html {
    scroll-behavior: smooth;
}
```


## Values

### Value balance

- Property: text-wrap


```css
/*
✔ https://caniuse.com/?search=balance

La propiedad CSS controla cómo se envuelve el texto dentro de un elemento. Los diferentes valores proporcionan

❤ balance
El texto está envuelto de una manera que mejor equilibre el número de caracteres en cada línea, mejorando la calidad del diseño y la legibilidad. Debido a que contar caracteres y equilibrarlos en varias líneas es computacionalmente costoso, este valor solo es compatible con bloques de texto que abarcan un número limitado de líneas ( la implementación de Chrome usa seis líneas envueltas o menos ), lo que significa que es útil para casos como encabezados o citas.*/

h1,
blockquote {
    text-wrap: balance;
}
```

## @media

### prefers-color-scheme

```css
/*
✔ dark mode / light mode

Por ejemplo, una de las características más recurrentes en interfaces de usuario es la posibilidad de elegir un dark mode o dark theme, es decir, un sistema que permita al usuario seleccionar un tema claro (generalmente con fondo blanco) o un tema oscuro (generalmente con fondo negro).

Aunque podemos hacer esto de forma manual, existe una regla @media especial denominada prefers-color-scheme donde podemos detectar si el usuario tiene preferencia por uno de estos dos valores (establecido en las opciones del sistema operativo) y actuar en consecuencia. Los valores que es posible indicar son light o dark:
*/

@media (prefers-color-scheme: dark) {
  :root {
    --background-color: #333;
    --foreground-color: #eee;
  }
}

@media (prefers-color-scheme: light) {
  :root {
    --background-color: #eee;
    --foreground-color: #111;
  }
}

body {
  background-color: var(--background-color);
  color: var(--foreground-color);
}
```

### prefers-reduced-motion


```css
/*
✔ https://caniuse.com/?search=scroll-behavior

La propiedad CSS scroll-behavior especifica el comportamiento del desplazamiento para un elemento con desplazamiento

❤ smooth
La caja se desplaza suavemente, utilizando una función de tiempo definida por el agente de usuario (user-agent) sobre un período de tiempo también definido por éste. Los agentes de usuario seguirán las convenciones de su propia plataforma, en caso de que existan.*/

html {
    scroll-behavior: smooth;
}

/*
✔ Movimiento reducido

Las interfaces modernas en la actualidad suelen apostar por diseños con animaciones y transiciones que hacen más agradables los cambios de estado y acciones específicas en una web. Sin embargo, por cuestiones de accesibilidad estas animaciones también pueden suponer molestias a usuarios que son especialmente sensibles a este tipo de estímulos

One set of options to turn these animations off is rather cryptically hidden under:
 
Control Panel > System and Security > System > Advanced System Settings > Performance settings > Visual effects

The first option, “Animate controls and elements inside windows”*/

.motion-title {
    width: fit-content;
    position: absolute;
    top: 0;
    
    font-family: system-ui, -apple-system, sans-serif;
    
    animation-name: var(--preferred-animation, title);
    animation-duration: 5s;
    animation-delay: 1s;
    animation-iteration-count: infinite;
    animation-direction: alternate;
}

@keyframes title {
    0% {
        left: 0;
        opacity: 1;
    }
    25% {
        top: 50vh;
    }
    50% {
        top: 0;
    }
    100% {
        left: 100%;
        transform: translateX(-100%);
        opacity: .2;
    }
}

@media (prefers-reduced-motion: reduce) {
    :root {
        --preferred-animation: soft;
    }
}
```