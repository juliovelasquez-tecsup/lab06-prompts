# Bitacora de prompts

Laboratorio 06: Fundamentos de Ingenieria de Prompts.

Herramienta de IA usada: Claude

## Ejercicio 2: Tokens y ventana de contexto
| Texto | Caracteres | Tokens |
|-------|------------|--------|
| Los estudiantes programan en Java. |34|7|
| The students program in Java. |30|7|
| desafortunadamente |18|4|

**Para el caso 4 me respondió lo esperado, sin embargo, para el caso 5 la IA menciona que no tiene forma de saber el nombre de mi proyecto. Esto se debe por que no cuneta con la opción de memoria activada.**

## Ejercicio 3: Temperatura
| Temperatura | % de BiblioTec | Nombres en los 5 intentos |
|-------------|----------------|---------------------------|
| 0 |100 |Bliotect, LibroYa, PrestaLibro, LectoGo, PaginaLibre, NubeDeTinta|
| 0.5 |65.3|Bliotect, LibroYa, PrestaLibro, LectoGo, PaginaLibre, NubeDeTinta|
| 1 |44.5|Bliotect, LibroYa, PrestaLibro, LectoGo, PaginaLibre, NubeDeTinta|
| 1.8 |32.2|Bliotect, LibroYa, PrestaLibro, LectoGo, PaginaLibre, NubeDeTinta|


## Ejercicio 4: Prompt vago vs estructurado
| Criterio | Prompt vago | Prompt estructurado |
|----------|-------------|---------------------|
| Menciona el objetivo del sistema |Si|Si|
| Menciona a los usuarios principales |Si|Si|
| Tiene exactamente 3 funcionalidades |No|Si|
| Esta en 3 parrafos |No|Si|
| Lo usaria en un informe real |No|Si|


## Ejercicio 5: Anatomia de un prompt
| Componente | Texto de mi prompt |
|------------|--------------------|
| Rol |Java Senior Developer |
| Instruccion |Create a Java program|
| Contexto |Managing products on a virtual storel|
| Ejemplo |Using a Product class with the attributes Code, Name, Price, Stock|
| Formato |Methods: getPrice(), setPrice(double price)|
