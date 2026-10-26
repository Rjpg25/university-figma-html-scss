# Lectura del diseño real

## Datos observados en el archivo

Hay un único frame de página visible en el canvas principal: `Homepage`, de **1728 × 4690**. El archivo también contiene componentes y recursos internos; no son páginas adicionales de la web. No se encontró una composición móvil independiente de esta página.

| Dato | Valor observado |
|---|---|
| Marca | Mrs. College Guide |
| Tipografía de esta página | Poppins |
| Pesos utilizados | Regular (400), Medium (500), SemiBold (600) |
| Color principal del texto y del footer | #36384E |
| Dorado de botones y enlaces | Aproximadamente #E5B300, redondeando canales a 8 bits |
| Ancho del frame | 1728 px |
| Alto del frame | 4690 px |
| Ancho del contenido de la cabecera | 1482 px |
| Alto de la cabecera en el frame | 154 px |
| Tamaño de la marca | 24 px |
| Tamaño de los enlaces de navegación | 16 px |
| Tamaño de los títulos habituales de sección | 32 px |
| Tamaño de los títulos de tarjetas | 26 px |
| Tamaño de los párrafos principales | 20 px |
| Título hero | Find Your Future Today! |
| Tamaños observados en el título hero | 58 px en varias palabras, 64 px en Future |

Los colores se reconstruyeron desde los valores del archivo. Las dimensiones son medidas de la composición de referencia: no son una instrucción para fijar el ancho o la altura completos de la página en CSS.

## Orden vertical observado

| Orden | Bloque | Contenido | Herramienta que practicaremos |
|---|---|---|---|
| 1 | Cabecera | Marca, cinco enlaces, LOGIN, SIGN UP | Flexbox, BEM, adaptación por ancho |
| 2 | Hero | Campus, título con palabra resaltada, subtítulo | Fondo/imagen, capas, centrado, tamaños fluidos |
| 3 | Introducción | Párrafo y GET STARTED | Contenedor, ancho de lectura, espaciado |
| 4 | Búsqueda | Find a course, Find a university, Find an open day | Grid del conjunto y Flex dentro de tarjetas |
| 5 | Universidades | Stanford, Stallion, Covenant | Grid responsive, imágenes, componentes |
| 6 | Cursos | User experience design, Computer science, Business management | Reutilización y variantes |
| 7 | Ayuda | Imagen y We're here to help; READ FAQS y ASK A QUESTION | Dos columnas, Flex de acciones, apilamiento |
| 8 | Newsletter y pie | Formulario, consentimiento, suscripción, redes, enlaces, copyright | Formularios, Flex/Grid y acceso por teclado |

El menú incluye News, pero en este frame no se observa un bloque de noticias independiente. El bloque final es un newsletter. Los destinos de los enlaces se decidirán según el alcance pedido por el profesor.

## Cómo adaptaremos la composición

Estas son propuestas de implementación para estudiar, no medidas móviles extraídas del Figma:

- Contenedor con ancho fluido y un límite máximo inspirado en la referencia.
- Cabecera que cambia su distribución cuando los grupos dejan de caber.
- Tarjetas en una columna en espacios estrechos y más columnas cuando caben.
- Bloque de ayuda apilado en móvil y en dos columnas en escritorio.
- Formularios y grupos de botones que puedan envolver o apilarse.
- Alturas que crezcan con el contenido, en lugar de copiar el alto de 4690px a la página.

## Recorrido de aprendizaje

1. HTML, árbol de cajas y nombres BEM.
2. Preparar Sass, fuentes locales, variables, reset y contenedor.
3. Cabecera con Flexbox y adaptación de sus grupos.
4. Hero, imágenes, recorte, superposición y título fluido.
5. Introducción y tarjetas con Grid; distribución interna con Flex.
6. Bloque de ayuda, newsletter y footer.
7. Pruebas responsive, diagnóstico con DevTools y auditoría con cambios en vivo.

En cada etapa repetiremos: objetivo → elemento responsable → propiedad → efecto al modificarla → comprobación.
