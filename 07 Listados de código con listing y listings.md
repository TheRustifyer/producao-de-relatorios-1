---
title: Listados de código con listing y listings
aliases:
  - Paquete Listing
  - Paquete listings
  - Listados de código con LaTeX
asignatura: Produção de Relatórios
rama:
  - Comunicación científica
  - Composición de documentos
tipo:
  - procedimiento
  - teoría
nivel: universitario-introductorio
estado: revisado
capa: curricular
requiere:
  - "[[Física/Grado/1º/Produção de Relatórios/03 Composición avanzada e índices en LaTeX|Composición avanzada e índices en LaTeX]]"
fsrs_goal: Construye listados con lenguaje, sangría, marco y números de línea; distingue listing de listings y código mostrado de ejecutado, y verifica la correspondencia entre archivo externo, PDF y resultados.
tags:
  - fisica
  - latex
  - listings
  - codigo
  - fcul
  - curricular
---

```dataviewjs
await dv.view("Planes/Estudio/Scripts/study-session", { location: "start" })
```

# Listados de código con listing y listings

Al copiar código a un informe, conserva sus sangrías, saltos de línea, comentarios y caracteres especiales. También explica qué hizo el programa dentro del procedimiento. El capítulo 5 del resumen docente trabaja con el paquete plural **`listings`** y sus órdenes `\lstset` y `lstlisting`.[^docente]

## Del programa a su representación

### Listado de código

> [!definicion] Listado de código
> Representación de un fragmento de programa que conserva sus caracteres y estructura y permite identificarlo y comentarlo dentro de un documento.[^docente]

Una lista de números puede ser el resultado de un cálculo; un listado muestra el texto del programa. Para evaluar el método, mira tanto qué operaciones aparecen en el código como qué resultado produjo al ejecutarlo con las entradas declaradas.

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - listings
---
> [!note] Pregunta
> ¿Qué representa un listado de código dentro de un informe?
===
> [!important] Respuesta
> El texto de un programa conservando caracteres y estructura, para poder identificar y analizar sus operaciones; se distingue de la salida obtenida al ejecutarlo.
```

### Composición y ejecución

> [!definicion] Composición de código
> Tratamiento del programa como contenido que debe imprimirse, con sus espacios y estilos, sin ejecutarlo como un programa del lenguaje mostrado.[^listings]

LaTeX procesa las órdenes de composición. `language=Python` le indica cómo reconocer y presentar las palabras del lenguaje; no ejecuta Python ni comprueba el algoritmo. Por eso, incluso un programa con errores de sintaxis puede quedar bien compuesto en el PDF. Ejecuta y revisa el programa por separado, y comprueba que el listado conserve fielmente el código.

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - listings
---
> [!note] Pregunta
> ¿Qué hace la composición de código en LaTeX con el programa mostrado?
===
> [!important] Respuesta
> Lo trata como contenido que debe imprimirse con sus espacios y estilos, sin ejecutarlo como un programa del lenguaje representado.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - listings
---
> [!note] Pregunta
> ¿Compilar en LaTeX un listado con `language=Python` verifica que el programa funciona?
===
> [!important] Respuesta
> No. Sólo compone su representación; el programa debe ejecutarse y sus resultados comprobarse por separado.
```

### Verbatim

> [!definicion] Representación literal
> Disposición del texto sin interpretar sus caracteres como órdenes de LaTeX. El entorno básico `verbatim` permite mostrar literalmente fragmentos.[^verbatim]

Usa `verbatim` para mostrar una orden o un fragmento breve tal como está escrito, sin reconocimiento del lenguaje. `listings` ofrece además opciones para elegir lenguaje, aplicar estilos, numerar líneas y ajustar la composición.

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - listings
---
> [!note] Pregunta
> ¿Qué significa mostrar un fragmento literalmente mediante `verbatim` en LaTeX?
===
> [!important] Respuesta
> Conservar sus caracteres sin interpretarlos como órdenes de LaTeX; un bloque básico no añade el reconocimiento sintáctico y las opciones de `listings`.
```

## Identificar el paquete por sus órdenes

### listings: paquete desarrollado en el curso

> [!definicion] Paquete listings
> Extensión que proporciona `lstlisting` para código incrustado, `\lstinputlisting` para código externo y `\lstset` para configurar su presentación.[^docente][^listings]

Se carga en el preámbulo mediante `\usepackage{listings}`. La grafía importa: **`lstlisting`**, en singular, es el entorno. `lstlistings` y `\lst{language=Python}`, impresos en un punto del resumen, son erratas; los ejemplos posteriores y la documentación muestran `lstlisting` y `\lstset{language=Python}`.[^docente][^listings]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - listings
---
> [!note] Pregunta
> ¿Qué órdenes permiten identificar el paquete plural `listings` en un fuente LaTeX?
===
> [!important] Respuesta
> `lstlisting` para código incrustado, `\lstinputlisting` para archivos externos y `\lstset` para configurar la presentación.
```

### listing: paquete singular de contraste

> [!definicion] Paquete listing
> Extensión distinta que ofrece un entorno `listing` no flotante con leyenda, etiqueta, referencia e índice de listados. No aporta las órdenes `\lst...` del paquete plural.[^listing]

El entorno singular permite añadir un número al bloque, pero el contenido también debe mostrarse de forma literal. Este ejemplo se compila por separado de los del paquete plural:

```latex
\documentclass{article}
\usepackage{listing}
\begin{document}
O listado~\ref{lst:singular} mostra uma repetição.
\begin{listing}
  \caption{Repetição ilustrativa}
  \label{lst:singular}
\begin{verbatim}
for valor in [1, 2, 3]:
    print(valor)
\end{verbatim}
\end{listing}
\listoflistings
\end{document}
```

`listing` organiza leyenda y número; `verbatim` conserva el texto. La etiqueta sigue a la leyenda y las compilaciones estabilizan la referencia. El bloque no usa el mecanismo de colocación flotante de `figure` o `table`.[^listing]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - listings
---
> [!note] Pregunta
> ¿Dónde se coloca `\label` respecto a `\caption` en el entorno del paquete singular `listing`?
===
> [!important] Respuesta
> Después de `\caption`, para guardar el número que la leyenda acaba de fijar.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - listings
---
> [!note] Pregunta
> ¿Qué aporta el paquete singular `listing` a un fragmento literal?
===
> [!important] Respuesta
> Un contenedor no flotante con leyenda, número, etiqueta, referencia e índice de listados; el contenido literal puede componerse mediante `verbatim`.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - listings
---
> [!note] Pregunta
> ¿Qué orden imprime el índice de listados del paquete singular `listing`?
===
> [!important] Respuesta
> `\listoflistings`, después de que las compilaciones hayan registrado sus entradas.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - listings
---
> [!note] Pregunta
> ¿Por qué `listing` y `listings` no son nombres intercambiables en LaTeX?
===
> [!important] Respuesta
> `listing` aporta un entorno numerado con leyenda y referencias; `listings` ofrece `lstlisting` y `\lstinputlisting` para componer código y archivos externos.
```

## Configuración de listings

### Configuración general y local

> [!definicion] Configuración de listado
> Selección de opciones con `\lstset{...}` para establecer valores generales o con los corchetes de un listado para modificar ese caso concreto.[^docente][^listings]

Una configuración común facilita que varios fragmentos conserven el mismo estilo. La selección local evita cambiar todos los listados cuando sólo uno utiliza otro lenguaje.

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - listings
---
> [!note] Pregunta
> ¿Qué diferencia configurar `listings` con `\lstset` de usar opciones en un listado concreto?
===
> [!important] Respuesta
> `\lstset` establece valores generales en su alcance; los corchetes del listado permiten modificar ese caso sin cambiar los demás.
```

```latex
% En el preámbulo
\usepackage{listings}
\lstset{
  basicstyle=\ttfamily\small,
  keepspaces=true,
  breaklines=true,
  showstringspaces=false,
  numbers=left,
  numberstyle=\tiny,
  stepnumber=1,
  numbersep=5pt,
  frame=single
}
```

### Lenguaje

> [!definicion] Lenguaje del listado
> Opción `language=...` que indica qué reglas de reconocimiento sintáctico se aplican al texto para componerlo.[^docente]

`\lstset{language=Python}` selecciona Python para los listados posteriores. `[language=Java]` en un listado cambia ese fragmento. Los estilos pueden distinguir palabras reservadas, comentarios y cadenas; su función es ayudar a leer las categorías del lenguaje, no aportar evidencia de que el programa funciona.[^listings]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - listings
---
> [!note] Pregunta
> ¿Qué selecciona `language=Python` o `language=Java` en `listings`?
===
> [!important] Respuesta
> Las reglas de reconocimiento sintáctico para componer el código y distinguir categorías del lenguaje; no ejecuta ni corrige el programa.
```

### Sangría, espacios y líneas largas

> [!definicion] Conservación de espacios
> Presentación que mantiene la separación y sangría del programa, por ejemplo mediante `keepspaces=true`, para representar fielmente su organización.[^listings]

`basicstyle=\ttfamily\small` compone el listado en letra monoespaciada y pequeña. `showstringspaces=false` oculta las marcas que señalarían espacios dentro de cadenas. Con `breaklines=true`, las líneas largas pueden partirse en el PDF; ese ajuste no cambia el archivo del programa, así que el lector todavía debe poder distinguir dónde termina cada línea real.[^listings]

En Python, cambiar la sangría puede alterar los bloques o volver inválido el programa. Por eso, al reconstruir los ejemplos del resumen, se conserva una indentación válida aunque en la representación original se haya perdido.[^docente]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - listings
---
> [!note] Pregunta
> ¿Qué protege `keepspaces=true` al mostrar código con `listings`?
===
> [!important] Respuesta
> La conservación de espacios y sangrías del código, necesarios para representar fielmente su organización.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - listings
---
> [!note] Pregunta
> ¿Qué aspecto selecciona `basicstyle=\ttfamily\small` para un listado?
===
> [!important] Respuesta
> Tipografía monoespaciada de tamaño pequeño para el código; las opciones de composición no modifican su ejecución.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - listings
---
> [!note] Pregunta
> ¿Qué efecto tiene `showstringspaces=false` en un listado LaTeX?
===
> [!important] Respuesta
> Evita mostrar marcas visibles de espacio dentro de las cadenas de texto.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - listings
---
> [!note] Pregunta
> ¿Modifica `breaklines=true` las líneas reales del archivo del programa?
===
> [!important] Respuesta
> No. Permite saltos visuales al componer líneas largas; la estructura del programa original debe seguir siendo reconocible.
```

### Numeración de líneas

> [!definicion] Numeración de líneas
> Marcadores de posición que permiten localizar partes de un listado sin introducir esos números en el programa.[^docente]

Con `numbers=left, numberstyle=\tiny, stepnumber=1, numbersep=5pt` aparece un número pequeño a la izquierda de cada línea, separado cinco puntos del código. `stepnumber` determina cada cuántas líneas se muestra un número. Así puedes señalar una operación concreta desde el texto.

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - listings
---
> [!note] Pregunta
> ¿Para qué se numeran las líneas de un listado dentro de un informe?
===
> [!important] Respuesta
> Para localizar operaciones y comentarlas desde la prosa sin introducir esos números dentro del programa.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - listings
---
> [!note] Pregunta
> ¿Qué controlan `numbers=left` y `numberstyle=\tiny` en `listings`?
===
> [!important] Respuesta
> La colocación de los números a la izquierda y su estilo tipográfico diminuto, respectivamente.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - listings
---
> [!note] Pregunta
> ¿Qué cambia `stepnumber` en la numeración de un listado?
===
> [!important] Respuesta
> El intervalo entre los números mostrados; `stepnumber=1` numera cada línea.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - listings
---
> [!note] Pregunta
> ¿Qué controla `numbersep=5pt` en un listado LaTeX?
===
> [!important] Respuesta
> La distancia de cinco puntos entre los números de línea y el código.
```

### Marco del listado

> [!definicion] Marco de código
> Borde de composición seleccionado con la opción `frame`, para delimitar visualmente el bloque.[^docente]

`frame=single` rodea el listado con un borde sencillo. El material también usa `frame=trBL`: `t`, `r`, `B` y `L` nombran los lados superior, derecho, inferior e izquierdo; las mayúsculas piden un borde doble en esos lados. Elige un marco si ayuda a separar el código del texto sin estorbar la lectura.[^docente]

```latex
\begin{lstlisting}[language=Python,frame=trBL]
def inicio():
    for i in range(10):
        print("hello world!")
\end{lstlisting}
```

En el PDF, `t` y `r` producen borde sencillo arriba y a la derecha; `B` y `L`, borde doble abajo y a la izquierda. La comparación con `frame=single` permite verificar que la capitalización determina qué lados se duplican.[^listings]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - listings
---
> [!note] Pregunta
> ¿Qué selecciona la opción `frame` de `listings`?
===
> [!important] Respuesta
> El borde de composición del bloque; `frame=single` dibuja un marco sencillo.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - listings
---
> [!note] Pregunta
> ¿Qué bordes produce `frame=trBL` en `listings`?
===
> [!important] Respuesta
> Superior y derecho sencillos, inferior e izquierdo dobles; las mayúsculas indican los lados duplicados.
```

## Código incrustado y código externo

### lstlisting

> [!definicion] Código incrustado
> Copia del programa escrita entre `\begin{lstlisting}` y `\end{lstlisting}` dentro del propio fuente LaTeX.[^listings]

#### Ejemplo — Python completo y listado referenciable

La tarea es mostrar una función que imprime diez veces una cadena y ejecutarla una vez. El listado conserva la sangría que distingue cuerpo de función y cuerpo del bucle:

```latex
\documentclass{article}
\usepackage{listings}
\lstset{basicstyle=\ttfamily\small,keepspaces=true,
        showstringspaces=false,numbers=left,numberstyle=\tiny,
        stepnumber=1,numbersep=5pt,frame=single}
\begin{document}
O listado~\ref{lst:python} define e chama uma função.
\begin{lstlisting}[language=Python,
  caption={Dez mensagens numa chamada},label={lst:python}]
def inicio():
    for i in range(10):
        print("hello world!")

inicio()
\end{lstlisting}
\end{document}
```

Definir la función no la ejecuta: `inicio()` es la llamada que la pone en marcha. En Python, el bucle recorre diez valores y produce diez líneas. Si compilas el documento LaTeX, en cambio, solo verás el código impreso. Son dos operaciones distintas.

La definición crea la función y la llamada la ejecuta. `range(10)` recorre los enteros del 0 al 9 y se detiene antes del extremo final. La sangría indica qué instrucciones pertenecen a cada bloque.[^python]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - listings
---
> [!note] Pregunta
> ¿Qué función sintáctica cumple la sangría en los bloques del ejemplo Python?
===
> [!important] Respuesta
> Determina qué instrucciones pertenecen a la función y al bucle; volver al nivel exterior termina la pertenencia al bloque interior.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - listings
---
> [!note] Pregunta
> ¿Qué caracteriza el código incrustado mediante `lstlisting` en LaTeX?
===
> [!important] Respuesta
> El programa se copia entre la apertura y el cierre del entorno dentro del propio `.tex`; esa copia debe conservarse coherente con la versión ejecutada.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - listings
---
> [!note] Pregunta
> ¿Basta definir una función Python con `def inicio():` para que se ejecute su cuerpo?
===
> [!important] Respuesta
> No. Se necesita invocarla, por ejemplo mediante `inicio()`; la definición establece qué hará cuando se llame.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - listings
---
> [!note] Pregunta
> ¿Qué enteros recorre `range(n)` de Python si $n$ es un entero positivo?
===
> [!important] Respuesta
> Los enteros desde 0 hasta $n-1$; el extremo $n$ queda excluido.
```

#### Ejemplo — Java y revisión de índices de bucle

El objetivo es mostrar dos bucles y seleccionar los pares en que los índices coinciden. La forma válida de declarar la entrada del programa usa `String[] args`, y el bucle interior actualiza `j`:

```java
public class Inicio {
    public static void main(String[] args) {
        for (int i = 0; i < 10; i++) {
            for (int j = 0; j < 8; j++) {
                if (i == j) {
                    System.out.println(i);
                }
            }
        }
    }
}
```

Para cada `i`, el bucle interior examina `j` de 0 a 7. La igualdad se cumple una vez para cada `i` de 0 a 7, de modo que la salida son esos ocho enteros en líneas separadas. Se corrigen así las formas `args[0]` y la actualización del índice exterior que aparecen en ejemplos del resumen; la corrección del algoritmo se explica, además de mostrar un código con buen aspecto.[^docente]

La firma `public static void main(String[] args)` corresponde al punto de entrada usado en este ejemplo clásico de aplicación Java; `args` es un array de cadenas, no una expresión `args[0]` dentro de la declaración.[^java]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - listings
---
> [!note] Pregunta
> ¿Cómo se declara el parámetro del `main` clásico utilizado en el ejemplo Java?
===
> [!important] Respuesta
> Como array de cadenas en `public static void main(String[] args)`; `args[0]` no es la declaración válida de ese parámetro.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - listings
---
> [!note] Pregunta
> ¿Qué se comprueba en el control de un bucle interior con índice `j`, anidado dentro de otro con índice `i`?
===
> [!important] Respuesta
> Que inicialización, condición y actualización controlen el índice previsto; en el ejemplo independiente, el interior comprueba y actualiza `j`, sin modificar por error `i`.
```

Para componerlo se sitúa el texto dentro de `lstlisting` con `[language=Java]`. La elección del lenguaje de resaltado no realiza esas correcciones.

### lstinputlisting

> [!definicion] Código externo incluido
> Programa leído de un archivo mediante `\lstinputlisting[opciones]{ruta}` durante la compilación del documento.[^listings]

```latex
\lstinputlisting[language=Python,
  caption={Análise das medidas},label={lst:analisis}]{analisis.py}
```

El archivo `analisis.py` tiene que estar en esa ruta cuando compiles. LaTeX incorpora entonces su contenido, de modo que no necesitas mantener una copia aparte en el archivo `.tex`. La orden no ejecuta el programa ni actualiza las cifras escritas en el informe. Es una opción adicional del paquete; el resumen docente se centra sobre todo en el código incrustado.

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - listings
---
> [!note] Pregunta
> ¿Qué diferencia práctica hay entre `lstlisting` y `\lstinputlisting`?
===
> [!important] Respuesta
> `lstlisting` contiene una copia del código en el `.tex`; `\lstinputlisting` lee un archivo externo durante la compilación, por lo que ese archivo debe estar disponible.
```

### Leyenda y referencia

> [!definicion] Identificación de listado
> Asociación entre un fragmento, una leyenda que indica su función y una clave que permite citarlo desde la prosa.[^listings]

`caption={...}` describe la operación relevante y `label={lst:analisis}` establece la clave. `listado~\ref{lst:analisis}` recupera el número. Una leyenda como «Python» sólo nombra el lenguaje; «Cálculo de la media de las medidas» explica qué debe examinarse.

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - listings
---
> [!note] Pregunta
> ¿Cómo se identifica y cita un listado con `listings` dentro de un informe?
===
> [!important] Respuesta
> `caption` describe su función, `label` asigna una clave y `\ref{clave}` recupera su número desde la prosa.
```

## Código, resultados y entrega verificable

### Correspondencia de versiones

> [!definicion] Correspondencia entre código y resultado
> Relación comprobable entre la versión del programa mostrada, sus entradas, la ejecución realizada y los resultados comunicados.[^integridad]

Para que otra persona pueda repetir el análisis, indica las dependencias y las condiciones relevantes y conserva las entradas que utilizaste. Si el código es de otra persona, cítala y respeta sus condiciones de uso. Antes de compartirlo, quita o protege la información personal y las credenciales.[^integridad]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - listings
---
> [!note] Pregunta
> ¿Qué permite verificar la correspondencia entre un código mostrado y un resultado comunicado?
===
> [!important] Respuesta
> Identificar la versión, las entradas, las dependencias y la ejecución de la que proceden los resultados, y comprobar que el PDF muestra ese mismo programa.
```

#### Ejemplo — Archivo actualizado y PDF antiguo

Se corrige `analisis.py`, pero se entrega un PDF compilado antes. El listado visible no corresponde a la versión corregida. Hay que recompilar y comprobar el fragmento, y además ejecutar el análisis pertinente y revisar cifras y conclusiones. La inclusión externa sincroniza lo que se muestra al compilar; sus límites de validez no incluyen actualizar automáticamente el razonamiento redactado.

> [!procedimiento] Comprobación de un listado
> 1. Identificar qué parte del método debe mostrar.
> 2. Elegir código incrustado o archivo externo según su mantenimiento.
> 3. Conservar caracteres, sangría y lenguaje correcto.
> 4. Añadir leyenda y referencia que permitan comentarlo.
> 5. Comprobar ejecución y resultados por separado de la composición.
> 6. Revisar PDF, versión y atribución antes de entregar.[^docente][^listings][^integridad]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - listings
---
> [!note] Pregunta
> ¿Qué comprobaciones independientes exige entregar un listado y sus resultados?
===
> [!important] Respuesta
> Fidelidad de la composición, sintaxis y ejecución del programa, corrección del procedimiento y correspondencia de versión, entradas y cifras comunicadas.
```

## Práctica con soluciones razonadas

#### Ejercicio 1 — Elegir una fuente de código

> [!ejemplo] Enunciado
> El análisis está guardado en `datos.py` y se revisará varias veces. Debe mostrarse sin mantener otra copia. ¿Qué orden corresponde y qué comprobaciones exige?

> [!resolucion]- Resolución
> Se usa `\lstinputlisting[language=Python,caption={Análise de dados},label={lst:datos}]{datos.py}`. Se comprueba la ruta y se recompila después del cambio. La ejecución y los resultados se revisan por separado; la inclusión no garantiza que la cifra del texto proceda de esa versión.

#### Ejercicio 2 — Reconocer el paquete

> [!ejemplo] Enunciado
> Una plantilla carga `listing` y usa `listing` con `\caption`. Otra carga `listings` y usa `\lstinputlisting`. ¿Qué hace cada una y qué error ocurriría al intercambiar sólo sus nombres?

> [!resolucion]- Resolución
> La primera aporta un contenedor numerado no flotante; la segunda compone el código y lee un archivo externo. El error frecuente consiste en atribuir `\lstinputlisting` al paquete singular: sus órdenes no son intercambiables. Hay que elegir el paquete y conservar su sintaxis correspondiente.

#### Ejercicio 3 — Separar tres verificaciones

> [!ejemplo] Enunciado
> Un código Python con sangría incorrecta aparece legible en el PDF y se afirma que «compila, por tanto calcula bien». Identifica las comprobaciones que se han confundido.

> [!resolucion]- Resolución
> La compilación LaTeX sólo demuestra que se pudo componer el documento. La sintaxis de Python requiere su propio intérprete y una sangría válida; la corrección del resultado exige comprobar el procedimiento y sus entradas. Finalmente se verifica que el listado del PDF coincide con el programa evaluado. Son evidencias distintas.

Un listado bien presentado deja que el lector examine el cálculo que produjo los resultados. Para saber qué demuestra, hay que compararlo con la evidencia; al compartirlo, también deben respetarse [[Física/Grado/1º/Produção de Relatórios/06 Ética y uso académico de las TIC|la integridad, la atribución y la privacidad]].

## 📚 Fuentes

### Material base aportado

[^docente]: Eugénia Graça — *Resumo de LaTeX*, julio de 2025, archivo `PR - Resumo - 2025 - 2026.pdf`, pp. físicas 73–75 (impresas 65–67); *LaTeX Summary*, archivo `PR - Resumo - INGLES - 2025 - 2026.pdf`, pp. físicas 66–68, como contraste. Paquete plural, lenguajes Python/Java, entorno, marco y números. Se corrigen las erratas de entorno, configuración y sintaxis de programas junto a los ejemplos.
[^verbatim]: Eugénia Graça — *Resumo de LaTeX*, p. física 40 (impresa 32); *Capítulo II — Modo Texto*, julio de 2026, archivo `cap2 - PR -2026-2027.pdf`, p. física 72, diapositiva 70 de 99. Representación literal.

### Ampliación externa

[^listings]: CTAN — [Listings](https://ctan.org/pkg/listings), y archivos del paquete instalado en TeX Live 2026, `listings.sty` y `lstmisc.sty`. Entornos, archivo externo y opciones de composición. [The Listings Package: manual](https://ctan.math.illinois.edu/macros/latex/contrib/listings/listings.pdf), versión 1.11b, 14 de noviembre de 2025, §2.7, p. 20, confirma los bordes de `frame=trBL`: sencillos arriba y a la derecha, dobles abajo y a la izquierda. `lstinputlisting` amplía el caso de código incrustado desarrollado en el resumen.
[^listing]: CTAN — [Listing](https://ctan.org/pkg/listing), contrastado con la documentación incluida al final de `listing.sty`, versión 1.2, de Hebley y Kuhlmann, en TeX Live 2026. Entorno no flotante, caption/label/ref y listoflistings. No se presupone que el título histórico «Pacote Listing» identifique el paquete singular: los ejemplos docentes disponibles utilizan el plural.
[^integridad]: Universidade de Lisboa — [Código de Conduta e de Boas Práticas](https://www.ulisboa.pt/sites/default/files/documents/page/2023/codigodecondutaedeboaspraticasdauniversidadedelisboa.pdf), 2015, art. 8 del anexo III, p. física 7 del PDF compilado. Fidelidad de resultados, autoría y uso de creaciones y archivos; aplicación a la correspondencia entre programa y resultado.
[^python]: Python Software Foundation — [More Control Flow Tools](https://docs.python.org/3/tutorial/controlflow.html), §§4.2–4.3 y 4.8. Sangría, iteración, extremo excluido de `range` y diferencia entre definir y llamar una función.
[^java]: Oracle — [A Closer Look at the “Hello World!” Application](https://docs.oracle.com/javase/tutorial/getStarted/application/index.html), apartado *The main Method*, tutorial de JDK 8. Contraste de la firma clásica utilizada en el ejemplo, sin presentarla como catálogo completo de formas admitidas por versiones posteriores.

## 🧑‍🏫 Prompt para tutor conversacional

Haz de tutor de primer curso universitario. Plantea una pregunta cada vez y espera el intento del estudiante antes de continuar.

Empieza por preguntar qué ve el lector en un listado. Aclara que muestra el texto del programa, pero no lo ejecuta.

El material del curso trabaja con el paquete plural listings. Repasa cómo se carga con usepackage{listings}, cómo lstset reúne opciones, cómo lstlisting muestra código dentro del documento y cómo lstinputlisting incorpora un archivo externo. Lstlistings y lst{language=...} son erratas del material.

Compara ese paquete con el entorno del paquete singular listing: no es flotante y admite caption, label después de caption, ref y listoflistings, pero no ofrece las órdenes que empiezan por lst.

Pregunta para qué sirve cada opción: language elige el lenguaje que se reconoce, basicstyle pone el código en letra monoespaciada, keepspaces conserva los espacios, breaklines parte visualmente las líneas largas y showstringspaces decide si se marcan los espacios dentro de cadenas.

Repasa también la numeración: numbers=left coloca los números a la izquierda, numberstyle=tiny los hace pequeños, stepnumber=1 los muestra en cada línea y numbersep=5pt los separa del código. Un marco solo delimita el bloque; ninguna de estas opciones cambia el programa.

En Python, una función llamada inicio que contiene un bucle for range(10) solo imprime sus diez líneas cuando se llama a inicio(). Pídele que señale qué hace la definición y qué hace la llamada.

En Java, la entrada del ejemplo usa main(String[] args). Dos bucles recorren i de 0 a 9 y j de 0 a 7; al imprimir cuando i==j, producen los valores de 0 a 7.

Haz que distinga tres revisiones: si el programa respeta la sintaxis de su lenguaje, si LaTeX compone correctamente el listado y si el resultado del programa es correcto.

Si se usa un archivo externo, comprueba que esté disponible en la ruta indicada y vuelve a compilar después de cambiarlo. La inclusión no ejecuta el programa ni actualiza por sí sola las cifras redactadas en el informe.

Usa tres casos de diagnóstico: un PDF que sigue mostrando una versión antigua, una orden lst escrita con el paquete singular y una sangría de Python incorrecta.

Da pistas y vuelve a preguntar más adelante para reforzar la recuperación. Pasa después a un análisis real: revisad qué versión del programa se usó, con qué entradas y dependencias, quién lo escribió y si contiene datos privados. No supongas que el estudiante dispone de información que no se ha aportado.

```dataviewjs
await dv.view("Planes/Estudio/Scripts/study-session", { location: "end" })
```
