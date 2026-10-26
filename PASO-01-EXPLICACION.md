# Paso 01: estructura que puedes defender

## Qué aprendemos hoy

Aprendemos a traducir el diseño a un árbol de HTML, distinguir contenido de apariencia y reconocer componentes y partes mediante BEM. Al terminar podrás localizar el padre correcto antes de intentar mover un elemento.

## Lee la cabecera desde fuera hacia dentro

1. `header.site-header` identifica la cabecera de la página.
2. `div.container.site-header__inner` agrupa sus tres zonas. Más adelante será el contenedor Flex que las distribuya.
3. `a.site-header__brand` representa la marca como enlace al inicio.
4. `nav.main-nav` identifica la navegación. Dentro hay una lista de cinco opciones.
5. `div.site-header__actions` agrupa las dos acciones de acceso.

La marca, el nav y el grupo de acciones son tres hijos directos de `site-header__inner`. Los enlaces de navegación están dentro de los `li` y de la lista: no son hijos directos de ese contenedor exterior. Si queremos distribuirlos entre sí, su responsable inmediato será `main-nav__list`.

## Clases y BEM

| Nombre | Interpretación |
|---|---|
| `.site-header` | Bloque de cabecera |
| `.site-header__inner` | Elemento interior del bloque |
| `.site-header__brand` | Elemento de marca |
| `.site-header__actions` | Elemento que agrupa acciones |
| `.main-nav` | Bloque de navegación con responsabilidad propia |
| `.main-nav__list` | Lista del bloque de navegación |
| `.main-nav__item` | Opción de esa lista |
| `.main-nav__link` | Enlace del bloque |
| `.button` | Base de un componente |
| `.button--primary` | Variante principal del botón |
| `.button--text` | Variante con aspecto de texto |
| `.container` | Clase compartida de ancho y alineación que crearemos después |

El HTML `class="container site-header__inner"` asigna dos clases a un elemento. La primera compartirá reglas de ancho; la segunda tendrá la distribución propia de la cabecera. La especificidad no aumenta por el mero hecho de que el atributo HTML tenga más clases: depende del selector CSS escrito.

`class="button button--primary"` conserva la base del componente y agrega su variante. `--primary` no tiene ningún poder visual por sí solo. Necesita una regla CSS. Cambiar el orden de las clases en el atributo no decide qué declaración CSS gana.

## Estructura y significado

- `head` contiene metadatos y referencias; `header` contiene la cabecera visible.
- `lang="en"` corresponde al idioma del contenido del diseño. Las explicaciones de estudio están en español.
- `main` contiene la parte principal de esta página.
- `section` agrupa contenido temático. Las secciones con título relacionan `aria-labelledby` con el ID de su encabezado.
- `div` agrupa para el layout sin añadir una región temática propia.
- `h1` es el título principal del documento; `h2` presenta secciones.
- `span` permite identificar una parte del título sin crear otro encabezado. Aquí selecciona Future para su resaltado.
- `ul` y `li` expresan que las opciones de navegación forman una lista.
- `id` identifica un destino único; `class` puede reutilizarse en varios elementos.
- `href="#courses"` busca el elemento cuyo ID sea `courses`.
- `type="button"` indica un botón de acción, no un botón de envío. Todavía debemos implementar su comportamiento si el alcance lo exige.
- Los comentarios `<!-- ... -->` documentan el HTML y no se muestran como contenido.

## Ejercicios de cambios en vivo

Haz un cambio por vez y explica antes el efecto esperado:

1. Cambia LOGIN por ACCESS. Localiza el contenido de texto, no el nombre de clase.
2. Mueve el `li` de About para que aparezca primero. Debes mover el nodo completo, incluyendo apertura y cierre.
3. Añade una sexta opción Scholarships y una sección de prueba con ID `scholarships`; comprueba el salto del enlace. Retira ambos al terminar para recuperar el diseño original.
4. Cambia el ID de courses a programmes sin tocar el href. Comprueba qué relación se rompió y arréglala en ambos extremos.
5. Quita `button` del atributo de SIGN UP. En esta etapa no hay diferencia visual porque aún no existen estilos. Explica qué estructura base dejaría de aplicarse cuando construyamos CSS.
6. Quita la clase de `main-nav__list`. Explica por qué la lista sigue existiendo, aunque después pierda el estilo que selecciona esa clase.
7. Explica por qué una clase llamada `main-nav__list` no pone automáticamente sus opciones en una fila.
8. Localiza qué padre distribuirá los tres grupos de la cabecera y cuál distribuirá los cinco elementos del menú.

## Preguntas para responder sin copiar

1. ¿Qué diferencia hay entre `head` y `header`?
2. ¿Por qué el contenedor exterior y la lista de navegación necesitarán reglas de distribución diferentes?
3. ¿Qué significa la clase `site-header__actions`?
4. ¿Por qué conservamos `button` cuando añadimos `button--primary`?
5. ¿Dónde cambiarías el texto de una opción? ¿Y su destino?
6. ¿Por qué el texto Future utiliza un span dentro del h1?
7. ¿Por qué el ancho 1728px del Figma no debe convertirse en un ancho fijo de toda la página?
8. ¿Qué hace el viewport y qué parte del responsive todavía debemos construir?

## Cómo comprobar que puedes avanzar

Debes poder escribir la cabecera siguiendo sus responsabilidades, señalar padre e hijo, modificar el texto de una opción, mover un li entero y enlazar correctamente un href con un ID. Después empezaremos con Sass y la maquetación de la cabecera, sin memorizar coordenadas del Figma.
