# Usabilidad en CSS (+ experiencia de usuario)

## dark mode / light mode

Ejemplo sacado de __chatgpt__. Para ver el código completo descárgate la carpeta **dark-light-mode**

```js
// Verifica el estado actual del modo en localStorage (si existe)
const savedMode = localStorage.getItem('darkMode');
const prefersDarkMode = window.matchMedia('(prefers-color-scheme: dark)').matches;
console.log(prefersDarkMode)

// Configura el modo inicial según la preferencia del usuario y localStorage
const initialMode = savedMode === 'enabled' || (savedMode !== 'disabled' && prefersDarkMode);
setMode(initialMode);

// Función para alternar entre modos
function toggleMode() {
    const isDarkMode = document.body.classList.toggle('dark-mode');
    localStorage.setItem('darkMode', isDarkMode ? 'enabled' : 'disabled');
}

// Función para establecer el modo y actualizar localStorage
function setMode(isDarkMode) {
    document.body.classList.toggle('dark-mode', isDarkMode);
    localStorage.setItem('darkMode', isDarkMode ? 'enabled' : 'disabled');
}
```