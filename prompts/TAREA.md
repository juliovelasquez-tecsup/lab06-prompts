# Tarea: Mi prompt profesional

Laboratorio 06: Fundamentos de Ingenieria de Prompts.

Herramienta de IA usada: (escribe aqui cual usaste)

## Funcionalidad elegida

**Calculo de notas de un curso.** Un programa de consola en Java que registra las notas de varios estudiantes, calcula el promedio ponderado de cada uno y le asigna una condicion (Aprobado o Desaprobado).

Elegi esta funcionalidad porque es sencilla, tiene reglas claras (pesos y nota minima) y permite verificar el resultado a mano.

## Version 1: prompt basico

```text
Hazme un programa para calcular notas.
```

**Que cambie:** nada, es el punto de partida.

**Que paso con la respuesta:** la IA tuvo que adivinar casi todo. No dijo el lenguaje, ni de que notas hablaba, ni como se calcula el promedio. Respondio con un ejemplo generico (un promedio simple de unas pocas notas) y sin explicacion de su estructura.

**Que faltaba:** lenguaje, reglas del calculo, tipo de programa y formato de la respuesta.

## Version 2

```text
Actua como desarrollador Java. Crea un programa de consola en Java
para calcular el promedio final de un estudiante. El promedio se calcula
con tres notas: practica (30 %), parcial (30 %) y final (40 %).
El estudiante aprueba si su promedio es mayor o igual a 10.5.
```

**Que cambie:** agregue un **rol** (desarrollador Java), el **contexto** (tres notas con sus pesos y la nota minima) y una **instruccion** mas concreta (programa de consola, promedio final).

**Por que:** en la version 1 la IA invento las reglas. Al dar los pesos y la nota minima, ya no tiene que suponer nada sobre el calculo.

**Que mejoro en la respuesta:** el programa ya esta en Java y usa los pesos correctos. Aun asi, trabaja con un solo estudiante, mezcla todo en el `main`, no valida que las notas esten entre 0 y 20 y entrego el codigo sin explicar su estructura.

**Que faltaba:** manejar varios estudiantes, ordenar el codigo, validar datos, fijar un formato de salida y mostrar un ejemplo del estilo esperado.

## Version 3: prompt final

```text
Actua como desarrollador Java con experiencia en ensenar programacion
a estudiantes de primeros ciclos.

Crea un programa de consola en Java que registre las notas de varios
estudiantes y calcule su promedio final y su condicion.

Contexto:
- Cada estudiante tiene nombre y tres notas en escala de 0 a 20:
  practica (30 %), parcial (30 %) y final (40 %).
- El estudiante esta Aprobado si su promedio es mayor o igual a 10.5;
  en caso contrario, esta Desaprobado.
- El programa pide cuantos estudiantes se van a registrar y luego
  los datos de cada uno.

Restricciones:
- No uses librerias externas; solo la libreria estandar de Java.
- Valida que cada nota este entre 0 y 20 y vuelve a pedirla si no lo esta.
- Usa una clase Estudiante con los metodos getPromedio() y getCondicion().
- No incluyas interfaz grafica ni archivos ni base de datos.

Ejemplo del estilo de salida:
Ana Torres | Promedio: 13.40 | Condicion: Aprobado

Formato de la respuesta:
1. Explica primero la estructura del programa en maximo 5 lineas.
2. Luego presenta el codigo completo en un solo bloque de codigo Java.
3. Termina con una tabla de 3 casos de prueba con las columnas
   Notas ingresadas, Promedio esperado y Condicion.
```

**Que cambie:** agregue un **ejemplo** de la salida, un **formato** de respuesta (explicacion, codigo, tabla de pruebas) y una lista de **restricciones** (sin librerias externas, validacion, clase `Estudiante`, sin GUI ni archivos).

**Por que:** en la version 2 la salida y la estructura del codigo dependian de lo que la IA decidiera. Con el ejemplo y el formato dejo de adivinar como presentarlo, y con las restricciones evito que complique el programa.

**Que mejoro en la respuesta:** explica la estructura antes del codigo, usa la clase `Estudiante`, valida las notas, imprime exactamente con el estilo del ejemplo y entrega una tabla de pruebas que puedo comprobar con una calculadora.

## Componentes del prompt final

| Componente | Texto de mi prompt |
|------------|--------------------|
| Rol | Actua como desarrollador Java con experiencia en ensenar programacion a estudiantes de primeros ciclos. |
| Instruccion | Crea un programa de consola en Java que registre las notas de varios estudiantes y calcule su promedio final y su condicion. |
| Contexto | Cada estudiante tiene nombre y tres notas en escala de 0 a 20: practica (30 %), parcial (30 %) y final (40 %). Aprobado si el promedio es mayor o igual a 10.5. |
| Ejemplo | Ana Torres \| Promedio: 13.40 \| Condicion: Aprobado |
| Formato | Explica primero la estructura en maximo 5 lineas, luego el codigo completo en un solo bloque y termina con una tabla de 3 casos de prueba. |
| Restricciones | No uses librerias externas. Valida las notas entre 0 y 20. Sin interfaz grafica, archivos ni base de datos. |

## Evaluacion del resultado

| Criterio | Si / No |
|----------|---------|
| El codigo compila y se ejecuta sin errores | Si |
| Calcula bien el promedio ponderado (30 %, 30 %, 40 %) | Si |
| No usa librerias externas | Si |
| Valida que las notas esten entre 0 y 20 | Si |
| Explica la estructura antes del codigo | Si |
| La salida respeta el estilo del ejemplo | Si |
| Incluye la tabla de 3 casos de prueba | Si |

## Errores que evite

1. **Ser demasiado general.** La version 1 ("Hazme un programa para calcular notas") era tan general que la IA adivino el lenguaje y las reglas. En la version 3 indique el rol, la tarea exacta, los pesos de cada nota y la condicion de aprobacion, asi que no hubo nada importante que adivinar.
2. **No indicar el formato.** En la version 2 el codigo llego sin explicacion y con una salida que la IA eligio sola. En la version 3 pedi el orden exacto de la respuesta (explicacion, codigo, tabla de pruebas) y di un ejemplo de la salida por consola.