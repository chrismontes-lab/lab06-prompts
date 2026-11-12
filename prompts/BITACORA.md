# Bitacora de prompts

Laboratorio 06: Fundamentos de Ingenieria de Prompts.

Herramienta de IA usada: ChatGPT

## Ejercicio 2: Tokens y ventana de contexto

| Texto | Caracteres | Tokens |
|-------|------------|--------|
| Los estudiantes programan en Java. | 34 | 7 |
| The students program in Java. | 29 | 2 |
| desafortunadamente | 18 | 4 |

**Observación:**

En el mismo chat, la IA recordó correctamente el nombre de la aplicación y la tecnología utilizada. Al realizar la pregunta en un chat nuevo, también respondió TiendaTec y Java Swing. Esto podría deberse a que la función de memoria conserva información entre conversaciones.

## Ejercicio 3: Temperatura

| Temperatura | % de BiblioTec | Nombres en los 5 intentos |
|-------------|----------------|---------------------------|
| 0 | 100.0% | BiblioTec, BiblioTec, BiblioTec, BiblioTec, BiblioTec |
| 0.5 | 65.3% | BiblioTec, LibroYa, BiblioTec, BiblioTec, LibroYa |
| 1 | 44.5% | BiblioTec, LibroYa, BiblioTec, PrestaLibro, LibroYa |
| 1.8 | 32.2% | LibroYa, BiblioTec, LibroYa, PrestaLibro, BiblioTec |

**Observación:**

Al aumentar la temperatura, disminuye la probabilidad de elegir BiblioTec y aparecen más alternativas en los resultados. El simulador no genera nombres nuevos porque solamente selecciona opciones de la lista definida en el código.

Al ejecutar nuevamente la temperatura 1.8, los porcentajes se mantuvieron iguales, pero los nombres seleccionados fueron diferentes. Esto demuestra que puede existir variabilidad al elegir entre varias opciones.

## Ejercicio 4: Prompt vago vs estructurado

| Criterio | Prompt vago | Prompt estructurado |
|----------|-------------|----------------------|
| Menciona el objetivo del sistema | Sí | Sí |
| Menciona a los usuarios principales | Sí | Sí |
| Tiene exactamente 3 funcionalidades | No | Sí |
| Está en 3 párrafos | Sí | Sí |
| Lo usaría en un informe real | Sí | Sí |

**Observación:**

El prompt vago produjo una respuesta clara, pero no especificó la cantidad de funcionalidades ni los detalles que debía incluir. En cambio, el prompt estructurado permitió obtener una respuesta más precisa, organizada y acorde con lo solicitado.

## Ejercicio 5: Anatomía de un prompt

- **Nivel 1:** La IA generó un programa para gestionar productos, incluyendo registro, consulta y búsqueda. Aunque la instrucción era general, eligió por su cuenta las funcionalidades y la estructura del programa.

- **Nivel 2:** Al agregar el rol de desarrollador Java, la IA adoptó una actitud más profesional y preguntó qué tipo de programa necesitaba desarrollar antes de generar el código. Esto demuestra que el rol influye en la forma de responder.

- **Nivel 3:** Al agregar el contexto de una tienda, la IA desarrolló un sistema más específico. Incluyó el registro, búsqueda, actualización y eliminación de productos, además de organizar el programa mediante tres clases.

- **Nivel 4:** Al especificar los atributos de la clase Producto, la IA generó una estructura más definida y acorde con los requisitos. El programa mantuvo las funcionalidades anteriores, pero ahora utilizó exactamente los datos solicitados.

- **Nivel 5:** Al indicar el formato de presentación, la IA organizó la respuesta de manera más clara. Primero explicó la estructura de la clase Producto y después presentó el código Java, facilitando la comprensión del programa.

- **Nivel 5 + Ejemplo:** Al proporcionar ejemplos de los métodos, la IA siguió el estilo indicado para los getters y setters. Esto permitió obtener un código más uniforme y organizado.

| Componente | Texto de mi prompt |
|------------|--------------------|
| Rol | Actua como desarrollador Java. |
| Instrucción | Crea un programa en Java usando una clase Producto con los atributos codigo, nombre, precio y stock. |
| Contexto | Para gestionar los productos de una tienda. |
| Ejemplo | Usa este estilo para los metodos: getPrecio(), setPrecio(double precio). |
| Formato | Explica primero la estructura de la clase y luego presenta el codigo Java. |