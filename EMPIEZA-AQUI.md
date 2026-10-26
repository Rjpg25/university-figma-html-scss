# University · Paso 01

Este material está preparado a partir de tu archivo `07-University.fig`. La primera etapa consiste en entender la composición y construir un HTML que podamos explicar. Los estilos se desarrollarán en las siguientes etapas.

## Qué tienes

- `index.html`: estructura inicial, con la cabecera completa y las secciones identificadas. Las tarjetas y el formulario todavía no están construidos.
- `scss/styles.scss`: fuente inicial de Sass, preparada para el siguiente paso.
- `css/styles.css`: salida CSS vacía en esta etapa; no hay maquetación visual todavía.
- `assets/images`: nueve imágenes originales utilizadas por el diseño, con nombres descriptivos.
- `assets/fonts`: Poppins en pesos 400, 500 y 600 para las siguientes etapas, junto con su licencia. Todavía no se aplican al HTML.
- `LECTURA-DEL-FIGMA.md`: datos medidos y decisiones de implementación que debemos distinguir.
- `PASO-01-EXPLICACION.md`: explicación del HTML y primeras preguntas de auditoría.

## Trabaja en VS Code

1. Extrae la carpeta y ábrela con Archivo → Abrir carpeta.
2. Abre `index.html` en el navegador. Puedes usar Live Server si ya lo tienes.
3. Compara el HTML con el árbol de secciones del diseño.
4. Usa F12 para inspeccionar la marca, la navegación y sus padres.
5. Haz los ejercicios de `PASO-01-EXPLICACION.md`.

El resultado actual muestra listas, títulos, párrafos y botones con los estilos iniciales del navegador. Es el resultado previsto del paso de estructura. El objetivo visual de la primera etapa no es reproducir la captura terminada.

## Sobre los enlaces y botones

El Figma muestra sus rótulos y apariencia, pero no especifica rutas de destino ni formularios de autenticación. Para esta práctica asignamos anclas internas: Universities → universidades; Courses → cursos; About → introducción. Community apunta provisionalmente al bloque de ayuda y News al newsletter. Son destinos de entrenamiento, no rutas extraídas del archivo.

LOGIN y SIGN UP se representan como botones `type="button"` para practicar acciones de interfaz futuras. En esta etapa todavía no tienen comportamiento. Si el profesor exige páginas de autenticación, pasaremos a enlaces que apunten a esas páginas. La etiqueta depende del comportamiento requerido.

## Sass, cuando lleguemos al paso 02

Los comandos se ejecutan desde esta carpeta, uno por uno. Node.js y npm deben estar instalados:

```powershell
npm install --save-dev sass
```

```powershell
npx sass scss/styles.scss css/styles.css
```

```powershell
npx sass --watch scss/styles.scss:css/styles.css
```

Si PowerShell bloquea `npx.ps1` o `npm.ps1`, puedes usar `npx.cmd` y `npm.cmd` con los mismos argumentos o la terminal Símbolo del sistema de VS Code.

El HTML enlaza CSS compilado. Cuando practiquemos Sass, editaremos SCSS y compilaremos la salida; no mantendremos dos versiones de los mismos estilos editadas a mano.
