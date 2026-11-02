---
title: LaTeX, entorno y fundamentos
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
  - "[[Física/Grado/1º/Produção de Relatórios/01 Informes y escritura científica|Informes y escritura científica]]"
fsrs_goal: Distingue sistema, distribución y editor; construye y depura un documento article o report con estructura, tres tipos de listas y fórmulas, justificando agrupación, modo y órdenes elegidas.
tags:
  - fisica
  - latex
  - informes
  - fcul
  - curricular
---

```dataviewjs
await dv.view("Planes/Estudio/Scripts/study-session", { location: "start" })
```

# LaTeX, entorno y fundamentos

Un informe contiene funciones distintas: título, sección, lista, nota y fórmula. LaTeX permite declarar esas funciones en un archivo de texto y obtener un documento compuesto a partir de ellas. Aprenderlo exige relacionar tres niveles: lo que se quiere comunicar, las órdenes que describen su estructura y el resultado que produce la compilación.[^cap1][^texto]

## Herramientas y ciclo de composición

### TeX

> [!definicion] TeX
> Sistema de composición tipográfica creado por Donald Knuth que procesa instrucciones para construir páginas de texto y matemáticas.[^cap1]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - compilacion
---
> [!note] Pregunta
> ¿Qué función cumple TeX en la preparación de un documento?
===
> [!important] Respuesta
> Procesa instrucciones para construir tipográficamente las páginas, incluido el texto matemático.
```

### LaTeX

> [!definicion] LaTeX
> Sistema de preparación de documentos basado en macros de TeX, desarrollado inicialmente por Leslie Lamport. Proporciona órdenes de estructura y composición como secciones, ecuaciones y referencias.[^latex]

Una macro permite invocar mediante un nombre una operación de composición. Así, `\section{Objetivo}` identifica una sección sin que el autor tenga que determinar de nuevo su numeración, tamaño y separación. La estructura declarada puede utilizarse después para generar un índice.[^texto]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - compilacion
---
> [!note] Pregunta
> ¿Qué aporta LaTeX sobre el sistema TeX?
===
> [!important] Respuesta
> Macros y estructuras que permiten declarar funciones del contenido, como secciones, ecuaciones y referencias, y componer el documento.
```

### Macro

> [!definicion] Macro
> Conjunto de instrucciones que puede invocarse mediante un nombre para realizar una operación de composición.[^latex]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - compilacion
---
> [!note] Pregunta
> ¿Qué permite hacer una macro en un sistema de composición como LaTeX?
===
> [!important] Respuesta
> Invocar mediante un nombre un conjunto de instrucciones, sin reescribirlas cada vez que se necesita la operación.
```



Las diapositivas llaman «editor» a LaTeX en una explicación introductoria. La distinción técnica útil es entre el sistema de composición, el programa que procesa el documento y la aplicación donde se escribe.[^cap1]

### Editor

> [!definicion] Editor
> Aplicación con la que se crea y modifica el archivo fuente. Puede integrar resaltado, visor y botones que ejecutan programas externos.[^cap1]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - compilacion
---
> [!note] Pregunta
> ¿Qué se modifica mediante un editor como Texmaker?
===
> [!important] Respuesta
> El archivo fuente. El editor puede ejecutar los programas de composición instalados y mostrar su salida si están configurados.
```

### Distribución TeX

> [!definicion] Distribución TeX
> Instalación que reúne programas de composición, clases, paquetes y archivos necesarios para procesar documentos.[^cap1]

En las diapositivas de 2026 se propone **Texmaker** como editor y **TeX Live** como distribución. El resumen de 2025 menciona también MiKTeX y MacTeX. Son recomendaciones de ediciones distintas: el principio estable consiste en disponer del editor y de un sistema TeX operativo, y configurar el primero para encontrar los programas del segundo. «TexLife» en el capítulo I es una errata por TeX Live.[^cap1][^instalacion]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - compilacion
---
> [!note] Pregunta
> ¿Qué diferencia hay entre TeX Live, LaTeX y Texmaker?
===
> [!important] Respuesta
> TeX Live es una distribución de programas y paquetes; LaTeX, un sistema de preparación de documentos sobre TeX; Texmaker, un editor del archivo fuente.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Qué aporta una distribución TeX que no aporta por sí solo un editor de texto?
===
> [!important] Respuesta
> Los programas y archivos de composición necesarios para procesar el fuente LaTeX y producir el documento final.
```

### Archivo fuente

> [!definicion] Archivo fuente
> Archivo de texto, habitualmente `.tex`, que contiene prosa y órdenes de LaTeX y constituye el origen editable del documento.[^instalacion]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - compilacion
---
> [!note] Pregunta
> ¿Qué contiene el archivo fuente `.tex` de un documento LaTeX?
===
> [!important] Respuesta
> La prosa y las órdenes editables con las que se construye el documento compuesto.
```

### Compilación

> [!definicion] Compilación
> Procesamiento del fuente y sus dependencias para producir el documento compuesto y los archivos auxiliares que requiere su construcción.[^instalacion][^estructuraexterna]

Con `pdflatex`, la salida de lectura se produce directamente como PDF. La ruta tradicional procesa el fuente para obtener un DVI (*device independent*), que puede convertirse en PostScript con `dvips` o en PDF mediante herramientas de conversión. No es necesario recorrer todos esos formatos para producir un PDF.[^instalacion]

El resumen menciona `xdvi` para visualizar DVI y `gv` para PostScript. Son utilidades de una ruta de composición concreta; el visor PDF corresponde a otra salida. Una instalación se comprueba guardando un documento mínimo, ejecutando el procesador elegido desde el editor y verificando que aparece su salida. El programa seleccionado y el formato esperado deben corresponderse.[^instalacion]

| Extensión | Función | Decisión que permite tomar |
|---|---|---|
| `.tex` | Contenido y órdenes editables. | Aquí se corrige el trabajo. |
| `.pdf` | Documento compuesto. | Aquí se inspecciona lo que recibirá el lector. |
| `.log` | Registro de procesamiento, errores y avisos. | Permite localizar la causa de un fallo. |
| `.aux` | Información auxiliar, incluidas etiquetas y citas. | Explica por qué las referencias pueden necesitar otra pasada. |
| `.toc` | Entradas del índice de contenido. | Se actualiza desde la estructura del documento. |
| `.dvi` | Salida intermedia de la ruta tradicional. | Se visualiza o convierte según esa ruta. |
| `.ps` | PostScript producido, por ejemplo, desde DVI. | Forma parte de una ruta de salida distinta del PDF directo. |

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - compilacion
---
> [!note] Pregunta
> ¿Para qué sirve el archivo `.aux` al compilar un documento LaTeX?
===
> [!important] Respuesta
> Guarda información auxiliar, incluidas etiquetas y citas, que se utiliza en pasadas posteriores.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - compilacion
---
> [!note] Pregunta
> ¿Qué contiene el archivo `.toc` de un documento LaTeX?
===
> [!important] Respuesta
> Las entradas del índice de contenido, obtenidas de la estructura declarada del documento.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - compilacion
---
> [!note] Pregunta
> ¿En qué consiste compilar un documento LaTeX?
===
> [!important] Respuesta
> En procesar el fuente y sus dependencias para producir el documento compuesto y los archivos auxiliares necesarios.
```

> [!procedimiento] Ciclo de trabajo
> Guardar el fuente → compilar → leer el registro si hay fallos → revisar el PDF → corregir el fuente → recompilar. Tras modificar títulos, etiquetas o índices, se repite la compilación hasta que desaparezcan los avisos de actualización.[^estructuraexterna][^instalacion]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - compilacion
---
> [!note] Pregunta
> ¿Qué ciclo de trabajo permite revisar un documento LaTeX tras editarlo?
===
> [!important] Respuesta
> Guardar, compilar, leer el registro, inspeccionar el PDF, corregir el fuente y recompilar hasta resolver errores y actualizaciones pendientes.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - compilacion
---
> [!note] Pregunta
> ¿Cómo se comprueba que un editor y una instalación TeX están conectados correctamente?
===
> [!important] Respuesta
> Guardando un documento mínimo, ejecutando desde el editor el procesador elegido y comprobando que produce el formato de salida esperado.
```



```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - compilacion
---
> [!note] Pregunta
> ¿Dónde se busca la causa de un error de compilación de LaTeX?
===
> [!important] Respuesta
> En el registro `.log`; se corrige el fuente y se recompila, comprobando también el PDF resultante.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - compilacion
---
> [!note] Pregunta
> ¿Por qué pueden necesitarse varias compilaciones tras cambiar referencias o índices en LaTeX?
===
> [!important] Respuesta
> Porque una pasada escribe la información auxiliar y otra la incorpora; los cambios pueden exigir nuevas actualizaciones.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - compilacion
---
> [!note] Pregunta
> ¿Qué diferencia la salida de `pdflatex` de la ruta tradicional LaTeX → DVI?
===
> [!important] Respuesta
> `pdflatex` produce PDF directamente; la ruta tradicional produce DVI, que puede convertirse después en PostScript o PDF.
```

## Anatomía del documento y lenguaje de órdenes

### Preámbulo

> [!definicion] Preámbulo
> Parte anterior a `\begin{document}` en la que se eligen clase, opciones y paquetes y se establece la configuración general.[^texto]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Qué se configura en el preámbulo de un documento LaTeX?
===
> [!important] Respuesta
> La clase, sus opciones, los paquetes y la configuración general, antes de `\begin{document}`.
```

### Cuerpo del documento

> [!definicion] Cuerpo del documento
> Contenido situado entre `\begin{document}` y `\end{document}`. Lo escrito después del cierre queda fuera del procesamiento del documento.[^texto]

#### Ejemplo — Primer documento completo

El objetivo es producir una página con una sección, un párrafo y una fórmula. Este ejemplo utiliza `pdflatex` y un archivo guardado como UTF-8:

```latex
\documentclass[a4paper,11pt]{article}
\usepackage[T1]{fontenc}
\usepackage[utf8]{inputenc}
\usepackage[portuguese]{babel}
\usepackage{amsmath,amssymb}

\begin{document}
\section{Objetivo}
O polinómio $p(x)=x^2-1$ tem duas raízes reais.
\begin{equation}
  p(x)=(x-1)(x+1)
\end{equation}
\end{document}
```

La sección debe aparecer numerada y la igualdad, en una línea propia. La identidad se comprueba al desarrollar el producto. La compilación comprueba la sintaxis; la expansión algebraica comprueba el contenido matemático. Son dos revisiones necesarias y distintas.

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Por qué compilar una fórmula LaTeX sin errores no demuestra que sea matemáticamente correcta?
===
> [!important] Respuesta
> Porque el procesador interpreta la sintaxis de composición; la igualdad, sus condiciones y su significado requieren una comprobación matemática independiente.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Qué límites tiene el cuerpo de un documento LaTeX?
===
> [!important] Respuesta
> Empieza en `\begin{document}` y termina en `\end{document}`. El contenido posterior al cierre no se incorpora al documento.
```

## Órdenes, argumentos y grupos

### Órdenes

> [!definicion] Orden de LaTeX
> Instrucción iniciada por una barra inversa. Puede tener un nombre de letras, como `\section`, o estar formada por una barra y un símbolo, como `\%`. Sus argumentos determinan sobre qué actúa.[^texto][^estructuraexterna]

Las mayúsculas importan: `\large`, `\Large` y `\LARGE` son órdenes diferentes. Cambiar la capitalización puede producir otro tamaño o un nombre que el sistema no reconoce.[^texto]

Después de una orden cuyo nombre está formado por letras, un espacio separa el nombre del texto, pero normalmente no se imprime. Para escribir «LaTeX permite», sirve `\LaTeX{} permite`: el grupo vacío termina la orden y deja que el espacio siguiente se conserve.[^texto]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Cómo se reconoce una orden en el fuente LaTeX?
===
> [!important] Respuesta
> Por la barra inversa inicial seguida de un nombre de letras o de un símbolo. Los nombres distinguen mayúsculas y minúsculas.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Para qué sirve el grupo vacío en `\LaTeX{} permite`?
===
> [!important] Respuesta
> Termina la orden para que el espacio siguiente se conserve y separe «LaTeX» de «permite».
```

### Argumentos

> [!definicion] Argumento
> Contenido que una orden recibe para determinar su actuación. La sintaxis de cada orden establece los argumentos obligatorios y los opcionales.[^texto][^estructuraexterna]

En `\documentclass[a4paper,11pt]{article}`, `article` es el argumento obligatorio entre llaves; las opciones de papel y tamaño van entre corchetes. En `\textbf{Resultado}`, el argumento determina qué texto se compone en negrita.

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Cómo se distinguen el argumento obligatorio y las opciones en `\documentclass[a4paper,11pt]{article}`?
===
> [!important] Respuesta
> `{article}` elige obligatoriamente la clase; `[a4paper,11pt]` contiene opciones de esa clase.
```

### Grupos

> [!definicion] Grupo
> Región delimitada, habitualmente con `{...}`, que permite limitar el alcance de declaraciones y cambios locales.[^texto]

En `{\bfseries Texto} normal`, la declaración afecta a «Texto» y el cierre devuelve el estilo anterior antes de «normal». Las llaves de un argumento delimitan lo que recibe una orden; las de este grupo delimitan una región de composición.

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Para qué se agrupa `{\bfseries Texto}` entre llaves en un fuente LaTeX?
===
> [!important] Respuesta
> Para limitar la declaración de negrita al grupo; después del cierre se recupera el estilo anterior.
```

### Entornos

> [!definicion] Entorno
> Construcción delimitada por `\begin{nombre}` y `\end{nombre}` que aplica una estructura o unas reglas a su contenido.[^texto]

Los cierres deben respetar el orden de apertura. Si se abre una lista dentro de otra, se cierra primero la interior. Un paquete aporta funcionalidades; un entorno usa una estructura dentro del cuerpo. `\usepackage` y `\begin` cumplen, por tanto, funciones diferentes.

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Cómo se delimita un entorno LaTeX y cómo se cierran los entornos anidados?
===
> [!important] Respuesta
> Con `\begin{nombre}` y `\end{nombre}`. Se cierra primero el entorno interior y después el exterior.
```

### Caracteres especiales y comentarios

> [!definicion] Carácter especial
> Carácter al que LaTeX asigna una función sintáctica y cuya impresión literal requiere una orden apropiada.[^texto][^estructuraexterna]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Por qué algunos caracteres requieren una orden para imprimirse literalmente en LaTeX?
===
> [!important] Respuesta
> Porque tienen una función sintáctica reservada; la orden distingue el símbolo literal de esa función.
```

| Carácter | Función habitual | Impresión literal en texto |
|---|---|---|
| `%` | Comenta hasta el final de la línea. | `\%` |
| `$` | Delimita modo matemático. | `\$` |
| `&` | Separa columnas de una alineación. | `\&` |
| `#` | Parámetro en definiciones de macros. | `\#` |
| `_` | Subíndice matemático. | `\_` |
| `{` y `}` | Agrupan contenido o argumentos. | `\{` y `\}` |
| `\` | Introduce una orden. | `\textbackslash{}` |
| `~` | Espacio que impide un salto de línea. | `\textasciitilde{}` |
| `^` | Superíndice matemático. | `\textasciicircum{}` |

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Cómo se imprimen una barra inversa, una tilde y un circunflejo literales en texto LaTeX?
===
> [!important] Respuesta
> Con `\textbackslash{}`, `\textasciitilde{}` y `\textasciicircum{}`, respectivamente.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Qué función cumple `~` entre dos fragmentos del fuente LaTeX?
===
> [!important] Respuesta
> Introduce un espacio que impide separar ambos fragmentos por un salto de línea.
```

Por ejemplo, `A eficiência foi 95\%.` imprime el porcentaje. Escribir `95%` comenta el resto de esa línea del fuente; puede desaparecer texto o incluso una orden de cierre. El comentario es útil para anotar el fuente sin incorporarlo al PDF.[^estructuraexterna]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Cómo se imprimen literalmente `%`, `&`, `$`, `#`, `_` y las llaves en texto LaTeX?
===
> [!important] Respuesta
> Anteponiendo una barra inversa: `\%`, `\&`, `\$`, `\#`, `\_`, `\{` y `\}`.
```

### Comentarios

> [!definicion] Comentario
> Fragmento del fuente que empieza con `%` y se extiende hasta el final de esa línea; queda excluido del documento compuesto.[^texto][^estructuraexterna]

Un comentario puede explicar en el fuente por qué se eligió una opción o se dejó pendiente un dato. Una orden situada después de `%` en la misma línea también queda comentada.

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Qué parte del fuente ignora LaTeX después de encontrar un `%` sin escapar?
===
> [!important] Respuesta
> Todo lo que queda de esa línea, incluidos el texto y las órdenes que aparezcan después del símbolo.
```

## Clases, paquetes y lengua

### Clase de documento

> [!definicion] Clase
> Conjunto de reglas que determina la estructura disponible y decisiones generales de composición de un tipo de documento.[^texto]

| Clase | Uso presentado en el material |
|---|---|
| `article` | Artículos, trabajos breves o de seminario. |
| `report` | Informes extensos y proyectos organizados por capítulos. |
| `book` | Libros. |
| `letter` | Cartas. |
| `beamer` | Presentaciones. |
| `exam` | Hojas de ejercicios o pruebas. |
| `sciposter` | Pósteres. |
| `moderncv` | Currículos. |

La lista docente escribe `slide` para transparencias; la clase estándar correspondiente se llama **`slides`**. La clase de presentación desarrollada con ejemplos específicos es `beamer`.[^texto][^clases]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Qué determina la clase de un documento LaTeX y cómo se selecciona?
===
> [!important] Respuesta
> Su estructura disponible y reglas generales de composición; se selecciona con `\documentclass[opciones]{clase}`.
```

#### Opciones de clase

Las opciones más comunes de las clases estándar son `10pt`, `11pt` o `12pt` para el tamaño base; `a4paper` o `letterpaper` para papel; `twocolumn` para dos columnas; `twoside` para composición a doble cara; `landscape` para orientación apaisada y `fleqn` para ecuaciones alineadas a la izquierda. **`fleqn`** es la grafía correcta, frente a `flenq` en el material portugués. La disponibilidad de opciones depende de la clase.[^texto]

Por ejemplo, `\documentclass[12pt,twoside,a4paper]{article}` pide un artículo de tamaño base 12 puntos, preparado a doble cara sobre papel A4. La clase estándar `article` usa 10 puntos y papel carta cuando esas opciones no se cambian; declararlas hace explícita la elección.[^texto]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Qué tamaño base y papel utiliza la clase estándar `article` si no se modifican esas opciones?
===
> [!important] Respuesta
> 10 puntos y papel carta (`letterpaper`); conviene declarar explícitamente otros requisitos, como A4 y 12 puntos.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Cómo se pide en una clase estándar de LaTeX papel A4, tamaño base 12 puntos y composición a doble cara?
===
> [!important] Respuesta
> Con las opciones `[a4paper,12pt,twoside]` de `\documentclass`.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Qué opciones de clase LaTeX seleccionan dos columnas, orientación apaisada y ecuaciones a la izquierda, respectivamente?
===
> [!important] Respuesta
> `twocolumn`, `landscape` y `fleqn`, si la clase utilizada admite esas opciones.
```

### Paquete

> [!definicion] Paquete
> Extensión cargada con `\usepackage[opciones]{nombre}` que añade órdenes o modifica capacidades de composición.[^texto]

Se carga una funcionalidad cuando se necesita: `amsmath` amplía la composición matemática, `amssymb` aporta símbolos, `graphicx` permite incorporar imágenes y `eurosym` proporciona `\euro`. Después de `\usepackage{eurosym}`, `10~\euro` compone una cantidad seguida del símbolo monetario sin separar ambos por un salto de línea.[^texto]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Qué es un paquete LaTeX y dónde se carga?
===
> [!important] Respuesta
> Una extensión de funcionalidad; se carga en el preámbulo con `\usepackage[opciones]{nombre}`.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Qué se necesita para usar `\euro` según el ejemplo docente?
===
> [!important] Respuesta
> Cargar `eurosym` en el preámbulo. `10~\euro` compone la cantidad y el símbolo sin un salto de línea entre ambos.
```

## Lengua, codificación y acentos

### Lengua del documento

> [!definicion] Configuración de lengua
> Selección de reglas lingüísticas de composición, como nombres automáticos y partición de palabras. En el material se realiza con `\usepackage[portuguese]{babel}`.[^texto]

Con esa configuración, los rótulos automáticos y la separación de palabras siguen las reglas portuguesas. Si una palabra necesita una partición particular, `\hyphenation{com-po-si-ção}` declara puntos de corte permitidos; los guiones de la declaración indican posiciones posibles y no se imprimen dentro de la palabra.[^texto]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Qué configura `\usepackage[portuguese]{babel}`?
===
> [!important] Respuesta
> Las reglas lingüísticas de composición, incluidos los nombres automáticos y la partición de palabras en portugués.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Cómo se declaran puntos de partición de una palabra con `\hyphenation`?
===
> [!important] Respuesta
> Escribiendo la palabra con guiones en los cortes permitidos, por ejemplo `\hyphenation{com-po-si-ção}`.
```

### Codificación de entrada

> [!definicion] Codificación de entrada
> Regla que relaciona los bytes del archivo con los caracteres escritos. La configuración de entrada debe corresponder a la codificación con que se guardó el fuente.[^texto][^estructuraexterna]

La **codificación de entrada** determina cómo se interpretan los caracteres guardados; la lengua seleccionada determina otras reglas de composición. Para un archivo UTF-8 procesado con `pdflatex`, se usa, si se declara, `\usepackage[utf8]{inputenc}`. No se seleccionan simultáneamente Latin1 y UTF-8 como si fuesen dos lenguas. Las instalaciones modernas de LaTeX usan UTF-8 como entrada predeterminada.[^texto][^estructuraexterna]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Por qué la opción de `inputenc` debe corresponder a la codificación del archivo?
===
> [!important] Respuesta
> Porque determina cómo se interpretan sus bytes como caracteres. Un fuente UTF-8 debe interpretarse como UTF-8, sin combinarlo con Latin1.
```

### Acentos y cedilla

> [!definicion] Orden de acento
> Orden que compone una marca diacrítica sobre el carácter indicado, o debajo en el caso de la cedilla.[^texto]

Los acentos pueden escribirse directamente en el archivo UTF-8 o con órdenes: `caf\'e`, ``\`a``, `c\^amara`, `c\~ao`, `ca\c{c}a` y `f\'{\i}sica`. Estas formas permiten reconocer fuentes antiguos; con una configuración correcta, «café», «câmara» y «física» se escriben con normalidad.[^texto]

La orden `\i` aporta una i sin punto para que el acento ocupe su lugar en `\'{\i}`.[^texto]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Para qué se utiliza `\i` al escribir `f\'{\i}sica` en LaTeX?
===
> [!important] Respuesta
> Aporta una i sin punto sobre la que se coloca el acento agudo.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Qué órdenes permiten reconocer acentos agudo, grave, circunflejo, tilde y cedilla en un fuente LaTeX?
===
> [!important] Respuesta
> Las órdenes de acento aplicadas al carácter: por ejemplo `caf\'e` para agudo, ``\`a`` para grave, `c\^amara` para circunflejo, `c\~ao` para tilde y `ca\c{c}a` para cedilla.
```

## Estructura y composición del texto

### Secciones y capítulos

El seccionado describe la relación jerárquica entre los títulos. Una sección puede contener subsecciones; en `report`, un capítulo puede contener varias secciones.[^texto]

#### Secciones

> [!definicion] Seccionado
> Jerarquía de divisiones lógicas que LaTeX numera y utiliza para organizar la navegación del documento.[^texto]

En `article`, la secuencia es `\section`, `\subsection`, `\subsubsection`, `\paragraph` y `\subparagraph`. Los últimos dos nombres también designan niveles de encabezado: no son la forma ordinaria de terminar un párrafo de prosa. `report` incorpora `\chapter` y permite agrupar capítulos mediante `\part`.[^texto]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Qué diferencia hay entre `\paragraph{Título}` y un nuevo párrafo de prosa en LaTeX?
===
> [!important] Respuesta
> `\paragraph` crea un nivel de encabezado; un párrafo de prosa se separa con una línea en blanco o `\par`.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Qué jerarquía de seccionado proporciona `article` en LaTeX?
===
> [!important] Respuesta
> `\section`, `\subsection`, `\subsubsection`, `\paragraph` y `\subparagraph`, con el título como argumento.
```

#### Capítulos

> [!definicion] Capítulo
> División estructural de clases como `report`, introducida con `\chapter{título}`, a la que pueden subordinarse secciones.[^texto]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Qué cambio estructural permite `report` frente a `article` al organizar un informe LaTeX?
===
> [!important] Respuesta
> Permite introducir capítulos con `\chapter`; las secciones pueden quedar subordinadas a ellos y numerarse por capítulo.
```

#### Partes

> [!definicion] Parte
> División de nivel superior introducida con `\part{título}`; puede agrupar capítulos dentro de una obra extensa.[^texto]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Qué función cumple `\part` en un informe LaTeX extenso?
===
> [!important] Respuesta
> Introduce una división de nivel superior que puede agrupar varios capítulos.
```

#### Ejemplo — De artículo a informe, como en la ficha 2

Al convertir un documento `article` en `report` y situar sus secciones dentro de `\chapter{Introdução}`, cambia la estructura: las secciones se subordinan al capítulo y suelen numerarse 1.1, 1.2, etc. Un nuevo capítulo *Desenvolvimento* inicia el siguiente conjunto de secciones.[^ficha]

```latex
\documentclass[a4paper,11pt]{report}
\usepackage[T1]{fontenc}
\usepackage[utf8]{inputenc}
\usepackage[portuguese]{babel}
\begin{document}
\chapter{Introdução}
\section{Alimentação}
Texto introdutório.
\chapter{Desenvolvimento}
\section{Onde avistar suricatas no habitat selvagem?}
Texto da secção.
\end{document}
```

Se comprueba la numeración en el PDF después de compilar. Cambiar sólo el aspecto de un título no produce esta jerarquía.



### Párrafo y salto de línea

> [!definicion] Párrafo en el fuente
> Bloque de texto separado del siguiente por una línea en blanco o por `\par`. Un salto simple de línea en el fuente suele equivaler a un espacio.[^estructuraexterna]

`\\` y `\newline` fuerzan un salto de línea en contextos apropiados, pero no crean por sí mismos un nuevo párrafo. La línea en blanco expresa una unidad de discurso nueva. `\noindent` suprime la sangría inicial del párrafo al que se aplica; no modifica su significado.[^texto]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Cómo se suprime la sangría inicial de un párrafo concreto en LaTeX?
===
> [!important] Respuesta
> Anteponiendo `\noindent` a ese párrafo.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Cómo se distingue un párrafo nuevo de un salto de línea en el fuente LaTeX?
===
> [!important] Respuesta
> Una línea en blanco o `\par` inicia un párrafo; `\\` o `\newline` sólo fuerza un cambio de línea en un contexto apropiado.
```

### Alineación

> [!definicion] Alineación de párrafos
> Disposición de las líneas respecto a los márgenes. `center`, `flushleft` y `flushright` permiten centrar o alinear a izquierda o derecha un bloque.[^texto]

```latex
\begin{flushright}
Lisboa, outubro de 2026
\end{flushright}
\begin{center}
Texto centralizado
\end{center}
\begin{flushleft}
Texto alinhado à esquerda
\end{flushleft}
```

La alineación se elige por la función del bloque. Una fecha puede alinearse a la derecha; el desarrollo ordinario conserva un patrón uniforme que facilite la lectura.

Los tres bloques producen una fecha a la derecha, texto centrado y texto alineado a la izquierda, respectivamente.[^texto]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Qué entornos permiten centrar un bloque de texto LaTeX o alinearlo a izquierda y derecha?
===
> [!important] Respuesta
> `center`, `flushleft` y `flushright`, respectivamente; el texto se coloca entre la apertura y el cierre del entorno elegido.
```

### Estilos y agrupación

> [!definicion] Estilo tipográfico
> Cambio de forma o énfasis de un fragmento sin alterar su nivel estructural.[^texto]

`\textbf{...}` produce negrita; `\textit{...}`, cursiva; `\emph{...}`, énfasis contextual; `\texttt{...}`, tipo monoespaciado; `\textsc{...}`, versalitas, y `\underline{...}`, subrayado. Las órdenes `\uuline` y `\sout` requieren `ulem`; `\usepackage[normalem]{ulem}` conserva el comportamiento habitual de `\emph`.[^texto]

Las versalitas son letras con forma de mayúscula y distinta altura según su función; `\textsc` no equivale a convertir todos los caracteres a mayúsculas del mismo tamaño. `\textbullet` imprime una viñeta aislada; para una lista de elementos se usa `itemize`.[^texto]

El material usa también declaraciones antiguas como `\bf` o `\tt`. Es preferible reconocer su función y escribir formas actuales como `{\bfseries Texto}` y `\texttt{código}`. Las llaves impiden que una declaración se extienda al contenido posterior.

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Qué cambia un estilo tipográfico en LaTeX?
===
> [!important] Respuesta
> La forma o el énfasis de un fragmento, sin convertirlo por sí solo en una sección u otro nivel estructural.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Cómo se delimita un fragmento en negrita o cursiva con órdenes de argumento en LaTeX?
===
> [!important] Respuesta
> Se escribe `\textbf{fragmento}` para negrita y `\textit{fragmento}` para cursiva.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Qué diferencia `\emph` de pedir directamente cursiva con `\textit`?
===
> [!important] Respuesta
> `\emph` pide énfasis según el contexto tipográfico; `\textit` selecciona directamente la forma cursiva.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Qué aspecto solicita `\texttt{código}` en LaTeX?
===
> [!important] Respuesta
> Un tipo monoespaciado, en el que cada carácter ocupa la misma anchura.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Qué solicita `\textsc` en LaTeX?
===
> [!important] Respuesta
> Versalitas: letras con forma de mayúscula y alturas diferenciadas, sin convertir todo el fragmento a mayúsculas ordinarias.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Qué órdenes componen subrayado, doble subrayado y tachado en LaTeX?
===
> [!important] Respuesta
> `\underline`, `\uuline` y `\sout`; las dos últimas requieren `ulem`, que puede cargarse con `normalem` para conservar el énfasis habitual.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Cómo se imprime una viñeta aislada en LaTeX?
===
> [!important] Respuesta
> Con `\textbullet`. Para organizar varios elementos como lista se utiliza `itemize`.
```

### Tamaño de letra

> [!definicion] Tamaño relativo
> Tamaño seleccionado respecto al tamaño base de la clase, mediante una declaración cuyo alcance conviene limitar con un grupo.[^texto]

La secuencia creciente es `\tiny`, `\scriptsize`, `\footnotesize`, `\small`, `\normalsize`, `\large`, `\Large`, `\LARGE`, `\huge` y `\Huge`. Por ejemplo, `{\Large Aviso}` limita el cambio a «Aviso». El tamaño de un título estructural se gobierna normalmente desde la clase; aumentar una línea no la convierte en sección.

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Cuál es la secuencia creciente de tamaños relativos desde `\tiny` hasta `\Huge` en LaTeX?
===
> [!important] Respuesta
> `\tiny`, `\scriptsize`, `\footnotesize`, `\small`, `\normalsize`, `\large`, `\Large`, `\LARGE`, `\huge`, `\Huge`.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Cómo se aplica un tamaño relativo a un fragmento LaTeX y se recupera después el tamaño anterior?
===
> [!important] Respuesta
> Encerrando la declaración y el texto en un grupo, como `{\Large Aviso}`. El cierre restaura el estado anterior; `\normalsize` selecciona explícitamente el tamaño normal.
```

### Color

> [!definicion] Color de texto
> Propiedad visual aplicable a un fragmento mediante `\textcolor{color}{texto}`, con un paquete como `color` o `xcolor`.[^texto]

Con `\usepackage{xcolor}`, `\textcolor{blue}{Resultado}` muestra un texto azul. El nombre debe existir en el sistema de colores cargado. La selección de color debe conservar legibilidad y una función reconocible, como distinguir una advertencia del argumento ordinario.

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Cómo se aplica color a un fragmento de texto LaTeX?
===
> [!important] Respuesta
> Se carga `color` o `xcolor` y se usa `\textcolor{color}{fragmento}`, con un nombre definido en el sistema cargado.
```

### Espacios explícitos

> [!definicion] Espaciado explícito
> Inserción de una separación tipográfica mediante una orden, en lugar de repetir espacios del teclado.[^texto]

En matemáticas, `\,`, `\:`, `\;`, `\quad` y `\qquad` proporcionan separaciones de anchura creciente; `\!` reduce espacio. `\hspace{1cm}` y `\vspace{3mm}` introducen separaciones horizontales y verticales con una dimensión. El material incluye las órdenes de TeX `\hskip` y `\vskip`; las formas con argumento entre llaves hacen más visible el alcance al leer el fuente.[^texto]

Los nombres `\thinspace`, `\medspace` y `\thickspace` corresponden a las separaciones fina, media y gruesa. En una fórmula, `a\,b`, `a\:b` y `a\;b` permiten comparar esos tres intervalos. El espacio negativo aproxima dos signos: `\int\!\int_D` reduce la separación entre integrales respecto a `\int\int_D`. El ejemplo compara composición; no establece un valor para la integral.[^texto]

Estas órdenes ajustan composición. No se usan para reconstruir a mano columnas, listas o alineaciones que ya tienen entornos propios.

```latex
Texto\hskip 1.5mm separado horizontalmente.\par
\vskip 3cm
Parágrafo após a separação vertical.
```

`\hskip` actúa entre fragmentos de una línea; después de `\par`, `\vskip` introduce la separación vertical antes del párrafo siguiente.[^texto]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Qué órdenes introducen espacios matemáticos fino, medio y grueso en LaTeX?
===
> [!important] Respuesta
> `\,`, `\:` y `\;`, equivalentes a `\thinspace`, `\medspace` y `\thickspace`; `\quad` y `\qquad` dan separaciones mayores.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Qué hace `\!` entre dos signos matemáticos en LaTeX?
===
> [!important] Respuesta
> Introduce un espacio negativo y aproxima los signos, como en `\int\!\int_D`.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Cómo se solicita una separación horizontal o vertical de dimensión explícita en LaTeX?
===
> [!important] Respuesta
> Con `\hspace{dimensión}` o `\vspace{dimensión}`; el material muestra también las formas de TeX `\hskip` y `\vskip` seguidas de una longitud.
```

### Notas al pie

> [!definicion] Nota al pie
> Aclaración vinculada a un punto de la prosa mediante una llamada y compuesta al pie de la página. Se introduce con `\footnote{texto}`.[^notas]

```latex
A tabela usa dados da ficha.\footnote{Os valores servem ao exercício de composição.}
```

La llamada se sitúa junto a la afirmación que aclara. Una bibliografía, en cambio, identifica fuentes citadas y necesita su mecanismo de referencias.

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Cómo se introduce una nota al pie en LaTeX?
===
> [!important] Respuesta
> Mediante `\footnote{texto}` en el lugar de la llamada; LaTeX compone el contenido al pie de la página.
```

## Listas y relaciones entre elementos

### Lista sin orden: itemize

> [!definicion] Lista con viñetas
> Conjunto de elementos paralelos cuyo orden no expresa una secuencia ni una clasificación. Se construye con `itemize` y una orden `\item` por elemento.[^texto]

```latex
\begin{itemize}
  \item Instrumento de medida.
  \item Registo de dados.
\end{itemize}
```

La ficha 2 pide transformar la subsección *Alimentação* en una lista simple. Se conserva el contenido de la subsección y se marca cada elemento; no se inventan datos alimentarios para completar el ejercicio.[^ficha]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Cuándo se elige `itemize` y cómo se marca cada elemento en LaTeX?
===
> [!important] Respuesta
> Cuando los elementos son paralelos y su orden no expresa una secuencia; cada uno comienza con `\item`.
```

### Lista ordenada: enumerate

> [!definicion] Lista numerada
> Serie de elementos cuyo orden permite expresar pasos, prioridades o una clasificación. Se construye con `enumerate`.[^texto]

```latex
\begin{enumerate}
  \item Preparar o instrumento.
  \item Registar a observação.
\end{enumerate}
```

La ficha pide una lista de parques ordenada por una densidad. La numeración expresa esa relación sólo si los datos justifican el orden. Los nombres y valores concretos de la *Folha 2 — Resultado* no están entre los materiales aportados.[^ficha]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Qué relación entre los elementos justifica elegir `enumerate` en LaTeX?
===
> [!important] Respuesta
> Una secuencia, prioridad o clasificación expresada por el orden; LaTeX genera automáticamente los números de los elementos.
```

### Lista de términos: description

> [!definicion] Lista descriptiva
> Asociación entre una etiqueta y su explicación, mediante `\item[etiqueta]` dentro de `description`.[^texto]

```latex
\begin{description}
  \item[Objetivo] Comparar resultados.
  \item[Método] Explicar a recolha de dados.
\end{description}
```

Transformar una lista numerada en descriptiva conserva las explicaciones, pero sustituye el papel del número por una etiqueta informativa. Esa es la distinción que ejercita la ficha.[^ficha]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Cómo se asocia una etiqueta con su explicación en una lista `description` de LaTeX?
===
> [!important] Respuesta
> Con `\item[etiqueta] explicación` dentro del entorno `description`.
```

### Listas anidadas

> [!definicion] Anidación de listas
> Inserción de una lista dentro de un elemento de otra para representar una dependencia jerárquica.[^texto]

```latex
\begin{enumerate}
  \item Preparação
    \begin{itemize}
      \item Verificar o instrumento.
      \item Identificar o registo.
    \end{itemize}
  \item Medição
\end{enumerate}
```

La anidación básica no requiere paquetes. El paquete `enumerate`, usado en el material, permite personalizar etiquetas, por ejemplo `\begin{enumerate}[A.]`. Se distingue así construir una jerarquía de modificar su marcador.[^texto]

#### Ejemplo — Jerarquía con marcadores distintos

**Tarea.** Organizar una preparación como apartado A y, dentro de ella, dos comprobaciones identificadas por números romanos. Se carga `\usepackage{enumerate}` en el preámbulo:

```latex
\begin{enumerate}[A.]
  \item Preparação
    \begin{enumerate}[i)]
      \item Verificar o instrumento.
      \item Identificar o registo.
    \end{enumerate}
  \item Medição
\end{enumerate}
```

El PDF debe mostrar A y B en el nivel exterior e i) y ii) dentro de A. La lista interior termina antes de comenzar B: esa posición del cierre determina la pertenencia de los elementos.

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Qué relación representa una lista anidada en LaTeX?
===
> [!important] Respuesta
> Una dependencia jerárquica: la lista interior se coloca dentro del elemento al que pertenece y se cierra antes de continuar la exterior.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Cómo se personaliza una lista numerada con etiquetas A., B., C. mediante el paquete `enumerate`?
===
> [!important] Respuesta
> Se carga `enumerate` y se abre la lista con `\begin{enumerate}[A.]`; esa opción modifica el marcador, sin crear la anidación.
```

## Fundamentos de escritura matemática

### Modo en línea y modo destacado

> [!definicion] Modo matemático
> Reglas de composición específicas para símbolos, índices, relaciones y expresiones matemáticas. En línea se delimita con `$...$`; una expresión destacada ocupa una línea propia y puede numerarse con `equation`.[^matematica]

La expresión breve $p(x)=x^2-1$ cabe en una oración. La identidad que gobierna un desarrollo puede destacarse:

$$
p(x)=(x-1)(x+1).
$$

En un fuente LaTeX se puede escribir `\begin{equation}...\end{equation}` para una fórmula numerada y `equation*` con `amsmath` para omitir el número. El modo matemático aplica reglas propias: las letras representan normalmente variables y los espacios del teclado no se conservan como en la prosa.[^matematica]

Los entornos `math` y `displaymath` corresponden, respectivamente, a una expresión en línea y a una expresión destacada sin número. Por ejemplo, `\begin{math}x^2\end{math}` se integra en la oración. El material muestra también dólares dobles para destacar fórmulas; en fuentes LaTeX se prefieren los entornos específicos, que expresan de forma más clara la estructura. Dentro de una fórmula, `\boxed{x=2}` de `amsmath` dibuja un recuadro alrededor del resultado.[^matematica]

```latex
Uma solução é \begin{math}x=2\end{math}.
\begin{displaymath}
  \boxed{x=2}
\end{displaymath}
```

La primera igualdad aparece en la frase. La segunda queda destacada y recuadrada, sin número:

$$
\boxed{x=2}.
$$

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Cómo se elige entre `equation` y `equation*` en LaTeX?
===
> [!important] Respuesta
> `equation` numera la expresión; `equation*`, disponible con `amsmath`, la destaca sin número.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Cuándo conviene componer una fórmula en línea y cuándo en modo destacado?
===
> [!important] Respuesta
> En línea si acompaña una oración breve; destacada si necesita inspección propia o gobierna un desarrollo. La numeración se elige según la necesidad de referenciarla.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Qué reglas cambian al entrar en modo matemático en LaTeX?
===
> [!important] Respuesta
> Se componen símbolos, variables, índices y relaciones con reglas matemáticas; las letras y espacios dejan de interpretarse como prosa ordinaria.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Qué diferencia de presentación existe entre los entornos LaTeX `math` y `displaymath`?
===
> [!important] Respuesta
> `math` integra una fórmula en la línea de texto; `displaymath` la destaca en una línea propia sin numerarla.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Cómo se recuadra una expresión matemática mediante `amsmath`?
===
> [!important] Respuesta
> Con `\boxed{expresión}` dentro del modo matemático.
```

### Subíndices y superíndices

Los índices inferiores y superiores forman parte de la expresión a la que se adjuntan. Las llaves delimitan todos los símbolos que deben ocupar una misma posición de índice.[^matematica]

#### Subíndices

> [!definicion] Subíndice en LaTeX
> Contenido matemático colocado como índice inferior mediante `_`; si contiene varios símbolos se agrupa entre llaves.[^matematica]

`a_i` y `a_{ij}` producen $a_i$ y $a_{ij}$. En `a_ij`, sólo `i` forma el subíndice. La agrupación debe corresponder al índice que se desea comunicar.

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Cómo se representa el subíndice formado por dos letras en $a_{ij}$ con LaTeX?
===
> [!important] Respuesta
> Con `a_{ij}`; las llaves hacen que ambas letras formen el subíndice.
```

#### Superíndices

> [!definicion] Superíndice en LaTeX
> Contenido matemático colocado como índice superior mediante `^`; puede representar un exponente según el significado declarado.[^matematica]

`x_1` produce $x_1$; `x_{12}` produce $x_{12}$; `x^{n+1}` produce $x^{n+1}$. Sin llaves, `x^12` eleva sólo el `1` y deja el `2` fuera del exponente. Se comprueba la agrupación interpretando el resultado, no sólo verificando que compile.

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Por qué debe escribirse `x^{12}` para representar $x^{12}$ en LaTeX?
===
> [!important] Respuesta
> Porque las llaves agrupan los dos dígitos como exponente; en `x^12` sólo el `1` queda elevado.
```

### Símbolos, relaciones y operadores

Una fórmula combina letras, relaciones y operadores con funciones tipográficas diferentes. Las órdenes permiten conservar esas diferencias al componerla.[^matematica]

#### Símbolos y relaciones

> [!definicion] Orden de símbolo matemático
> Nombre que produce un símbolo dentro del modo matemático; distingue su función de la escritura literal de una palabra.[^matematica]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Qué función cumple una orden de símbolo matemático en LaTeX?
===
> [!important] Respuesta
> Produce un símbolo con la función tipográfica correspondiente; la orden no establece por sí sola su significado o dominio.
```

| Función | Fuente LaTeX | Lectura |
|---|---|---|
| Letras griegas | `\alpha`, `\beta`, `\gamma`, `\Sigma`, `\sigma` | $\alpha$, $\beta$, $\gamma$, $\Sigma$, $\sigma$; las mayúsculas importan. |
| Relaciones | `\leq`, `\geq`, `\neq` | $\leq$, $\geq$, $\neq$. |
| Conjuntos | `\emptyset`, `\in`, `\subset` | $\emptyset$, $\in$, $\subset$. |
| Cuantificadores | `\forall`, `\exists` | $\forall$, $\exists$. |
| Flechas | `\rightarrow`, `\to` | $\rightarrow$, $\to$. |
| Operaciones | `\cdot`, `\div` | $\cdot$, $\div$. |
| Vector y continuidad | `\vec{a}`, `\ldots`, `\cdots` | $\vec a$, $\ldots$, $\cdots$. |

Las órdenes distinguen las categorías tipográficas: `\Sigma` produce una letra griega mayúscula; `\sum` produce el operador de suma. En una descripción simbólica, `\forall x` expresa un cuantificador, pero el dominio de $x$ debe declararse en el argumento matemático.[^matematica]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Qué órdenes LaTeX componen el conjunto vacío, la pertenencia y la inclusión?
===
> [!important] Respuesta
> `\emptyset`, `\in` y `\subset`, respectivamente; el significado de inclusión sigue la convención matemática declarada.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Cómo se componen los cuantificadores universal y existencial en LaTeX, y qué información debe acompañarlos?
===
> [!important] Respuesta
> Con `\forall` y `\exists`; debe declararse el dominio de la variable cuantificada.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Cómo se compone una flecha hacia la derecha en modo matemático LaTeX?
===
> [!important] Respuesta
> Con `\rightarrow` o su forma equivalente `\to`.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Qué órdenes LaTeX componen el punto de multiplicación y el signo de división?
===
> [!important] Respuesta
> `\cdot` y `\div`, respectivamente.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Cómo se añade una flecha de vector a una letra en LaTeX?
===
> [!important] Respuesta
> Mediante `\vec{letra}`, por ejemplo `\vec{a}`.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Qué diferencia de posición existe entre `\ldots` y `\cdots` en una fórmula LaTeX?
===
> [!important] Respuesta
> `\ldots` produce puntos bajos y `\cdots` puntos centrados, según los elementos de la expresión.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Qué diferencia tipográfica existe entre `\Sigma` y `\sum` en LaTeX?
===
> [!important] Respuesta
> `\Sigma` compone una letra griega mayúscula; `\sum` compone el operador sumatorio, al que pueden añadirse cotas.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Qué órdenes LaTeX representan las relaciones menor o igual, mayor o igual y distinto?
===
> [!important] Respuesta
> `\leq`, `\geq` y `\neq`, dentro del modo matemático.
```

#### Operadores con nombre

> [!definicion] Operador matemático con nombre
> Operación cuyo nombre se compone mediante una orden específica para darle la forma y el espaciado de operador.[^matematica]

Los operadores con nombre se componen mediante `\sin`, `\cos`, `\tan`, `\log`, `\liminf` o `\bmod`, por ejemplo `$\sin(x)$`. Escribir `$sin(x)$` compone tres letras como variables. El significado del símbolo se fija siempre en la explicación matemática: elegir una orden no establece un dominio ni demuestra una relación.[^matematica]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Por qué se escribe `\sin(x)` en vez de `sin(x)` en modo matemático LaTeX?
===
> [!important] Respuesta
> Para componer «sin» como nombre de un operador, con su forma y espaciado; sin la orden se componen tres letras como variables.
```

### Texto dentro de fórmulas

> [!definicion] Texto matemático insertado
> Fragmento de lenguaje ordinario dentro de una expresión, compuesto con `\text{...}` de `amsmath`; `\mbox{...}` permite también incorporar una caja de texto.[^matematica]

```latex
\begin{equation*}
  x_1=7 \quad \text{e} \quad x_2=-7
\end{equation*}
```

La palabra portuguesa «e» queda como texto. Sin esa orden, la letra se interpretaría tipográficamente como variable.

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Cómo se introduce una palabra como texto dentro de una fórmula con `amsmath`?
===
> [!important] Respuesta
> Con `\text{palabra}`. `\mbox{...}` permite también insertar una caja de texto; los espacios de separación se añaden según corresponda.
```

### Fracciones

> [!definicion] Fracción en LaTeX
> `\frac{numerador}{denominador}` construye una fracción con dos argumentos agrupados independientemente.[^matematica]

Por ejemplo, `\frac{x^2}{k+1}` representa $x^2/(k+1)$ y exige $k\ne-1$ si se interpreta como cociente real. `\dfrac` o `\displaystyle\frac` fuerzan el tamaño destacado de la fracción; dentro de una línea pueden aumentar la separación entre renglones.[^matematica]

Una fracción también puede ocupar un exponente: `x^{\frac{2}{k+1}}` agrupa todo el cociente en el índice superior. Por ejemplo, para $x>0$ y $k\ne-1$ reales se obtiene:

$$
x^{\frac{2}{k+1}}.
$$

El cierre de `\frac` termina su denominador; la última llave cierra el exponente completo. Esta lectura permite comprobar las dos agrupaciones.[^matematica]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Cómo se compone una fracción en LaTeX y qué agrupa cada argumento?
===
> [!important] Respuesta
> Con `\frac{numerador}{denominador}`; cada par de llaves agrupa por separado uno de los dos componentes.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Qué cambia `\dfrac` respecto a `\frac` en una fórmula en línea?
===
> [!important] Respuesta
> Fuerza el tamaño destacado de la fracción, como `\displaystyle\frac`, y puede aumentar la separación entre renglones.
```

#### Ejemplo — Una fracción continuada

**Tarea.** Componer la expresión $x=a_0+1/(a_1+1/a_2)$ de manera que puedan distinguirse sus dos cocientes. Para coeficientes reales se exige $a_2\ne0$ y $a_1+1/a_2\ne0$.

```latex
\begin{equation}
  x=a_0+\dfrac{1}{a_1+\dfrac{1}{a_2}}
\end{equation}
```

Cada denominador pertenece al `\dfrac` que abre inmediatamente antes. Por ejemplo, $a_0=1$, $a_1=2$ y $a_2=2$ dan $x=1+1/(2+1/2)=7/5$. Esta sustitución comprueba la agrupación y las condiciones; la compilación permite inspeccionar la legibilidad.[^matematica]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Qué condición matemática debe comprobarse en cada cociente de una fracción continuada?
===
> [!important] Respuesta
> Que cada denominador, incluidas las expresiones completas de los denominadores exteriores, sea distinto de cero.
```

### Raíces

> [!definicion] Raíz en LaTeX
> `\sqrt{radicando}` compone una raíz cuadrada y `\sqrt[n]{radicando}` una raíz de índice $n$.[^matematica]

`\sqrt[3]{x}` representa la raíz cúbica de $x$. Para una raíz cuadrada real, el radicando debe ser no negativo: la orden de composición no impone esa condición al contenido matemático.

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Qué condición debe cumplir el radicando de una raíz cuadrada interpretada como número real?
===
> [!important] Respuesta
> Debe ser no negativo; escribir `\sqrt{...}` correctamente no comprueba esa condición.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Cómo se elige el índice de una raíz en LaTeX?
===
> [!important] Respuesta
> Se usa `\sqrt[n]{radicando}` para índice $n$; sin el argumento opcional, `\sqrt{radicando}` compone una raíz cuadrada.
```

### Delimitadores ajustables

> [!definicion] Delimitadores ajustables
> Par de delimitadores cuya altura se adapta a su contenido mediante `\left` y `\right`.[^matematica]

La elección resulta útil cuando una fracción necesita paréntesis más altos que una letra:

```latex
\begin{equation*}
  1+\left(\frac{1}{1-x^2}\right)^3
\end{equation*}
```

En este ejemplo algebraico, $x\in\mathbb R\setminus\{-1,1\}$. Las llaves de LaTeX agrupan; los paréntesis impresos explicitan cómo debe interpretarse la potencia. El par `\left` y `\right` debe estar completo, aunque uno de sus delimitadores se haga invisible con un punto.[^matematica]

Los tamaños también pueden elegirse manualmente con `\big`, `\Big`, `\bigg` y `\Bigg`, como `\bigl(x\bigr)` y `\Biggl(\frac{1}{1-x^2}\Biggr)`. Las variantes terminadas en `l` y `r` identifican los lados izquierdo y derecho. Esta elección fija un tamaño; `\left` y `\right` lo ajustan al contenido.[^cap3]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Cómo se ajusta automáticamente la altura de un par de delimitadores en LaTeX?
===
> [!important] Respuesta
> Con `\left` y `\right`. Debe existir el par completo; un punto permite que uno de los delimitadores sea invisible.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Qué diferencia la selección manual `\big`, `\Big`, `\bigg`, `\Bigg` de `\left` y `\right` en LaTeX?
===
> [!important] Respuesta
> Las primeras fijan tamaños de delimitador elegidos por el autor; `\left` y `\right` ajustan el tamaño al contenido.
```

### Integrales

> [!definicion] Composición de una integral
> `\int_{a}^{b} f(x)\,\mathrm{d}x` dispone el signo integral, los límites y el integrando. Los límites se expresan mediante subíndice y superíndice.[^matematica]

Para $a,b\in\mathbb R$, el ejemplo elemental

$$
\int_a^b 1\,\mathrm{d}x=b-a
$$

permite identificar cada parte: límites $a,b$, integrando $1$, variable $x$ y diferencial. El espacio fino `\,` separa el diferencial. La identidad se comprueba evaluando la primitiva $x$ en ambos extremos.

> [!advertencia] Corrección del ejemplo de la fuente
> El resumen imprime una integral gaussiana con exponente positivo y un valor finito sin declarar hipótesis. Esa igualdad no se utiliza como resultado: una fórmula que compila puede contener un error matemático. La composición de integrales se practica aquí con una integral definida elemental.[^matematica]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Cómo se componen los límites y el diferencial de una integral definida en LaTeX?
===
> [!important] Respuesta
> Por ejemplo, con `\int_{a}^{b} f(x)\,\mathrm{d}x`: los índices son los límites y el espacio fino separa el diferencial.
```

### Sumatorios

> [!definicion] Composición de un sumatorio
> `\sum_{k=1}^{n}` dispone el signo de suma e identifica su índice $k$ y sus cotas $1,n$.[^matematica]

Un ejemplo finito permite verificar cada término:

$$
\sum_{k=1}^{3} k=1+2+3=6.
$$

El fuente es `\sum_{k=1}^{3} k`. La colocación de las cotas cambia entre modo en línea y destacado; `\displaystyle` permite modificar esa presentación.[^matematica]

El resumen asocia por error $\sum_{k=1}^{n}1/(k+2)$ con $\pi^2/6$ al tomar un límite. Esa serie diverge: quitar un número finito de términos a la serie armónica no cambia su divergencia. La suma finita anterior permite comprobar tanto la composición como el resultado.[^matematica][^armonica]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Cómo se compone un sumatorio que recorre los enteros de 1 a $n$ en LaTeX?
===
> [!important] Respuesta
> Con `\sum_{k=1}^{n}` seguido del sumando; $k$ identifica el índice y las expresiones inferior y superior fijan las cotas.
```

### Límites

> [!definicion] Composición de un límite
> `\lim_{n\to\infty}` identifica la operación de límite, la variable $n$ y la tendencia indicada.[^matematica]

Para un ejemplo con $n$ entero positivo se escribe `\lim_{n\to\infty}\frac{1}{n}=0`. La expresión resultante es:

$$
\lim_{n\to\infty}\frac{1}{n}=0.
$$

El subíndice declara qué variable cambia y hacia dónde; esa información no debe confundirse con una cota superior de un sumatorio.

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Cómo se indica en LaTeX que un límite corresponde a $n$ tendiendo a infinito?
===
> [!important] Respuesta
> Con `\lim_{n\to\infty}` seguido de la expresión; el subíndice identifica la variable y su tendencia.
```

### Combinaciones

> [!definicion] Coeficiente binomial
> Para $n\in\mathbb N_0$ y $k\in\{0,\ldots,n\}$, el número de selecciones de $k$ elementos entre $n$ sin atender al orden se expresa por $\binom nk=n!/[k!(n-k)!]$ y se compone con `\binom{n}{k}`.[^matematica]

```latex
\begin{equation*}
  \binom{n}{k}=\frac{n!}{k!(n-k)!}
\end{equation*}
```

Para $n=4$ y $k=2$, la expresión da $6$. La fuente usa también `{n \choose k}`; `\binom` expresa con mayor claridad los dos argumentos. Los índices del resultado y del factorial deben coincidir: mezclar $r$ y $k$ sin una definición distinta altera la fórmula.

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - documento-cientifico
---
> [!note] Pregunta
> ¿Cómo se compone el coeficiente binomial con LaTeX y qué cuenta para $0\le k\le n$ enteros?
===
> [!important] Respuesta
> Se escribe `\binom{n}{k}` y cuenta selecciones de $k$ elementos entre $n$ sin atender al orden: $n!/[k!(n-k)!]$.
```

## Práctica y diagnóstico

#### Ejercicio 1 — Lista y fórmula en línea

> [!ejemplo] Enunciado
> Construye el cuerpo de un documento con dos pasos numerados y la expresión $p(x)=x^2-1$ dentro de una frase. Indica dónde empieza y termina el cuerpo.

> [!resolucion]- Resolución
> Se delimita con `\begin{document}` y `\end{document}`; los pasos se escriben como dos `\item` dentro de `enumerate`, y la frase contiene `$p(x)=x^2-1$`. Escribir los números a mano es un error frecuente: impide que la lista conserve automáticamente su orden y formato al insertar elementos.

#### Ejercicio 2 — Diagnosticar tres fallos distintos

> [!ejemplo] Enunciado
> a) Falta `\end{document}`. b) Se escribe `95% dos casos` en una línea. c) Se pretende representar $x^{12}$ mediante `$x^12$`. Explica qué se revisa en cada caso.

> [!resolucion]- Resolución
> a) El cuerpo carece de cierre; se restaura y se revisa el registro de compilación. b) `%` comenta el resto de la línea; se usa `95\% dos casos`. c) La sintaxis puede compilar, pero agrupa mal el exponente; se escribe `$x^{12}$`. Los casos distinguen estructura incompleta, interpretación especial de un carácter y significado matemático incorrectamente representado.

#### Ejercicio 3 — Elegir una lista por su función

> [!ejemplo] Enunciado
> Decide qué usar para instrumentos sin orden, un protocolo de medida y un vocabulario de términos con explicación. ¿Hace falta un paquete para anidar una lista?

> [!resolucion]- Resolución
> Instrumentos: `itemize`. Protocolo: `enumerate`, porque el orden guía la ejecución. Vocabulario: `description`, con etiquetas en `\item[...]`. La anidación básica está disponible sin paquetes; personalizar etiquetas mediante las opciones del paquete `enumerate` es otra decisión.

#### Ejercicio 4 — Transferir la ficha 2

> [!ejemplo] Enunciado
> Convierte el documento mínimo `article` en `report`, crea los capítulos *Introdução* y *Desenvolvimento* y justifica el cambio en la numeración de secciones. Después escribe una fracción con denominador $1-x^2$ y declara su dominio real.

> [!resolucion]- Resolución
> Se cambia la clase a `report`, se coloca `\chapter{Introdução}` antes de las secciones existentes y `\chapter{Desenvolvimento}` antes de las nuevas. Las secciones pasan a depender del número del capítulo. La fracción es `\frac{1}{1-x^2}`; exige $x\ne\pm1$. La revisión comprueba estructura y condiciones de validez matemática, además de la compilación.

El documento ya puede expresar texto y fórmulas elementales. Al crecer, aparecen relaciones entre objetos numerados, ecuaciones de varias líneas e índices. La [[Física/Grado/1º/Produção de Relatórios/03 Composición avanzada e índices en LaTeX|composición avanzada]] organiza esas dependencias para que la edición no obligue a corregir números a mano.

## 📚 Fuentes

### Material base aportado

[^cap1]: Eugénia Graça — Capítulo I, julio de 2026, pp. físicas 6–10. TeX, LaTeX, editor y distribución.
[^texto]: Eugénia Graça — *Resumo de LaTeX*, julio de 2025, pp. físicas 11–24 (impresas 3–16); *Capítulo II — Modo Texto*, julio de 2026, pp. físicas 4–45, diapositivas 4–43 de 99. Órdenes, clases, lengua, formato y listas. El resumen inglés se utiliza como contraste; confirma `fleqn`.
[^instalacion]: Eugénia Graça — *Resumo de LaTeX*, pp. físicas 77–78 (impresas 69–70). Archivos, rutas de composición e instalación; se distingue su recomendación de la del capítulo I de 2026.
[^notas]: Eugénia Graça — *Resumo de LaTeX*, p. física 42 (impresa 34); capítulo II, p. física 78, diapositiva 76. Notas al pie.
[^matematica]: Eugénia Graça — *Resumo de LaTeX*, pp. físicas 53–59 (impresas 45–51). Modo matemático, símbolos, fracciones, raíces, integrales, sumas, límites y combinaciones. Las igualdades erróneas se señalan localmente y no se adoptan.
[^cap3]: Eugénia Graça — *Capítulo III — Modo Matemático*, portada de julio de 2024, pp. físicas 4–18, diapositivas 4–16. Fuente identificada como `cap 3- PR 2021-2022 reduzido.pdf`; la edición se toma de la portada. Modos, delimitadores, fracciones y operaciones matemáticas.
[^ficha]: *Ficha 2 — Modo Texto*, pp. físicas 1–2. Conversión a `report` y tres tipos de listas. No se aportaron *Folha 1* ni *Folha 2 — Resultado*; los ejemplos son autónomos y no reconstruyen sus datos ausentes.

### Ampliación externa

[^latex]: LaTeX Project — [Introduction to LaTeX](https://www.latex-project.org/about/). Naturaleza del sistema y separación entre estructura y composición.
[^estructuraexterna]: LearnLaTeX — [Basic document structure](https://www.learnlatex.org/en/lesson-03) y [Mathematics](https://www.learnlatex.org/en/lesson-10). Contraste de estructura, caracteres y sintaxis matemática. La configuración de entrada evita combinar codificaciones incompatibles.
[^clases]: LaTeX Project — clases estándar del sistema LaTeX, `slides.cls` y `classes.dtx`, edición consultada de TeX Live 2026. El nombre de la clase es `slides`; los valores predeterminados de `article` incluyen `10pt` y `letterpaper`.
[^armonica]: OpenStax — [Calculus, volumen 2, §5.3: The Divergence and Integral Tests](https://openstax.org/books/calculus-volume-2/pages/5-3-the-divergence-and-integral-tests). Demostración de la divergencia de la serie armónica, utilizada para corregir la igualdad errónea del resumen.

## 🧑‍🏫 Prompt para tutor conversacional

Tutoriza Produção de Relatórios a nivel universitario introductorio. Formula una pregunta por turno y espera el intento antes de ofrecer pistas o soluciones. Distingue errores de sintaxis, agrupación, elección de estructura y significado matemático.

TeX compone; LaTeX proporciona macros y estructuras; TeX Live distribuye programas y paquetes; Texmaker edita. El fuente `.tex` se procesa a PDF; `.log` registra mensajes, `.aux` auxilia referencias y `.toc` contiene el índice. Existe la ruta tradicional DVI → PS/PDF.

El preámbulo configura clase y paquetes y el cuerpo queda entre begin y end de document.

Órdenes sensibles a mayúsculas, argumentos obligatorios en llaves y opcionales en corchetes; los grupos limitan declaraciones.

Revisa caracteres especiales y comentarios: `%` elimina el resto de la línea; `\%` imprime el porcentaje. Un grupo limita declaraciones, mientras un argumento entrega contenido a una orden. Una línea en blanco o `\par` inicia párrafo; `\\` fuerza un cambio de línea en un contexto apropiado.

`article` organiza secciones y `report` incorpora capítulos. Usa UTF-8 coherente y babel portuguese para lengua. Distingue párrafo de salto de línea, estilo de estructura y tres listas: itemize sin orden, enumerate ordenada, description etiqueta-explicación. Notas con footnote.

Las fórmulas en línea usan dólares o el entorno `math`; `displaymath` destaca sin número, `equation` numera y `equation*` con `amsmath` no. Subíndices y exponentes de varios símbolos requieren llaves. Examina `frac`, `dfrac`, `sqrt`, `left/right`, tamaños manuales de delimitadores, operadores, `text`, `int`, `sum`, `lim` y `binom`. La expresión $1/(1-x^2)$ exige $x\ne\pm1$; compilar no comprueba ese dominio.

Pide reparar x^12, porcentaje sin escapar y cierre de document ausente; adaptar article a report; escribir una lista y una fórmula. Distingue error de sintaxis, agrupación, procedimiento y significado.

Utiliza recuperación activa, repetición espaciada, pistas y transferencia; continúa con referencias cruzadas, tablas y composición de ecuaciones.

```dataviewjs
await dv.view("Planes/Estudio/Scripts/study-session", { location: "end" })
```
