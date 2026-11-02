---
title: Composición avanzada e índices en LaTeX
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
  - "[[Física/Grado/1º/Produção de Relatórios/02 LaTeX, entorno y fundamentos|LaTeX, entorno y fundamentos]]"
fsrs_goal: Construye y referencia tablas, figuras y ecuaciones de varias líneas; genera índices y organiza un informe repartido en archivos; comprueba en Zuloc la capacidad, el balance entre carga, producción y atraso, y la comparación de escenarios de plantilla.
tags:
  - fisica
  - latex
  - figuras
  - tablas
  - fcul
  - curricular
---

```dataviewjs
await dv.view("Planes/Estudio/Scripts/study-session", { location: "start" })
```

# Composición avanzada e índices en LaTeX

Al insertar una tabla, una figura o un capítulo, cambia la paginación y puede cambiar la numeración de otros elementos. La solución consiste en declarar relaciones: una leyenda identifica un objeto, una etiqueta permite citarlo y un índice recoge la estructura. Una composición mantenible conserva esas relaciones aunque el documento crezca.[^cruzadas][^indices]

## Estructura lógica y objetos numerados

### Formato semántico

> [!definicion] Formato semántico
> Composición basada en identificar la función de un elemento —sección, ecuación, tabla o leyenda— y dejar que la clase y los paquetes determinen su presentación.[^indices]

`\textbf{Resultados}` cambia el aspecto de unas letras; `\section{Resultados}` crea una sección. El segundo caso permite numeración e índice. La distinción se extiende a los objetos: una imagen insertada tiene un contenido gráfico; una figura numerada añade una identidad que puede usarse desde la prosa.

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - referencias-cruzadas
---
> [!note] Pregunta
> ¿Qué caracteriza al formato semántico de un documento LaTeX?
===
> [!important] Respuesta
> Se declara la función de cada elemento y la clase o los paquetes determinan su presentación; `\section` crea una sección, mientras `\textbf` sólo cambia el aspecto.
```

### Leyenda

> [!definicion] Leyenda
> Texto introducido mediante `\caption{...}` que identifica una figura o tabla y fija su número dentro del contador correspondiente.[^cruzadas]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - referencias-cruzadas
---
> [!note] Pregunta
> ¿Qué función cumple `\caption` en una figura o tabla LaTeX?
===
> [!important] Respuesta
> Compone su leyenda y fija el número del objeto dentro del contador correspondiente.
```

### Etiqueta

> [!definicion] Etiqueta
> Clave interna creada con `\label{clave}` para recuperar el número de un elemento o la página donde se encuentra.[^cruzadas]

En figuras y tablas, `\label` se coloca después de `\caption`: necesita guardar el número que esa orden acaba de fijar. Claves como `fig:medidas`, `tab:periodos` y `eq:polinomio` facilitan identificar el objeto al editar. Las claves deben ser únicas y estables.

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - referencias-cruzadas
---
> [!note] Pregunta
> ¿Qué identifica la clave creada con `\label` en LaTeX?
===
> [!important] Respuesta
> Un elemento mediante un nombre interno único y estable, del que pueden recuperarse el número o la página.
```

### Referencia cruzada

> [!definicion] Referencia cruzada
> Mención que recupera automáticamente información de una etiqueta: `\ref{clave}` devuelve el número y `\pageref{clave}`, la página.[^cruzadas]

`A tabela~\ref{tab:periodos}` conserva el espacio entre «tabela» y su número sin permitir un salto de línea. Después de insertar un objeto nuevo, las compilaciones necesarias actualizan la numeración. Una referencia «??» pide comprobar la clave, su existencia y el registro, y recompilar si la información auxiliar está pendiente.[^cruzadas]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - referencias-cruzadas
---
> [!note] Pregunta
> ¿Qué información recupera una referencia cruzada con `\ref` y con `\pageref` en LaTeX?
===
> [!important] Respuesta
> `\ref` recupera el número del elemento etiquetado y `\pageref` la página donde se encuentra.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - referencias-cruzadas
---
> [!note] Pregunta
> ¿Qué se comprueba cuando una referencia LaTeX muestra «??»?
===
> [!important] Respuesta
> Que la etiqueta exista, que la clave coincida y que se hayan completado las pasadas necesarias; el registro distingue una referencia ausente de una actualización pendiente.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - referencias-cruzadas
---
> [!note] Pregunta
> ¿Por qué se escribe `tabela~\ref{tab:periodos}` con una tilde en el fuente LaTeX?
===
> [!important] Respuesta
> Para conservar un espacio entre la palabra y el número e impedir un salto de línea entre ambos.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - referencias-cruzadas
---
> [!note] Pregunta
> ¿Por qué se coloca \label después de \caption dentro de una figura LaTeX?
===
> [!important] Respuesta
> Porque \caption fija el número de la figura y \label debe guardar ese número para que \ref lo recupere.
```

#### Ejemplo — Una figura que cambia de número

Si la figura marcada `fig:medidas` era la segunda y se inserta una nueva antes de ella, la mención `\ref{fig:medidas}` pasa a recuperar el número actualizado. «Figura 2» escrito a mano permanece igual y puede señalar otro objeto. La etiqueta mantiene la identidad; el número expresa la posición en la secuencia.[^cruzadas]

### Objetos flotantes

> [!definicion] Flotante
> Objeto cuya colocación final puede ajustarse para componer la página. Los entornos `figure` y `table` permiten que LaTeX gestione esa colocación.[^tablas][^figuras]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - referencias-cruzadas
---
> [!note] Pregunta
> ¿Qué es un flotante en la composición de un documento LaTeX?
===
> [!important] Respuesta
> Un objeto cuya posición final puede ajustar LaTeX para componer la página; `figure` y `table` son contenedores flotantes.
```

| Opción | Preferencia o efecto |
|---|---|
| `h` | Cerca de la posición del fuente. |
| `t` | Parte superior de una página. |
| `b` | Parte inferior. |
| `p` | Página destinada a flotantes. |
| `!` | Relaja ciertas restricciones de colocación; no fija una posición. |

`[htbp]` ofrece alternativas. `[h!]` sigue siendo una petición, no una coordenada garantizada. Conviene que la prosa identifique la figura por número y explique su función, en lugar de depender de «la figura de abajo».[^tablas][^figuras]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - referencias-cruzadas
---
> [!note] Pregunta
> ¿Qué posiciones permiten las opciones `t`, `b` y `p` de un flotante LaTeX?
===
> [!important] Respuesta
> Parte superior, parte inferior y página de flotantes, respectivamente; son alternativas que LaTeX utiliza al componer las páginas.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - referencias-cruzadas
---
> [!note] Pregunta
> ¿Garantiza `[h!]` que un flotante de LaTeX aparezca exactamente donde está escrito en el fuente?
===
> [!important] Respuesta
> No. `h` pide una posición próxima y `!` relaja ciertas restricciones; la colocación sigue dependiendo de la composición de página.
```

## Tablas: datos, anchuras y agrupaciones

### tabular

> [!definicion] tabular
> Entorno que dispone contenido en filas y columnas, con una especificación del número, alineación y anchura de las columnas.[^tablas]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - tablas
---
> [!note] Pregunta
> ¿Qué construye el entorno `tabular` de LaTeX?
===
> [!important] Respuesta
> La disposición de contenido en filas y columnas, según la alineación y anchura declaradas para las columnas.
```

### table

> [!definicion] table
> Entorno flotante que puede contener una tabla y aportar leyenda, numeración y preferencias de colocación. No dibuja por sí mismo las celdas.[^tablas]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - tablas
---
> [!note] Pregunta
> ¿Qué aporta el entorno `table` de LaTeX a una tabla?
===
> [!important] Respuesta
> Un contenedor flotante donde pueden incorporarse leyenda, etiqueta y preferencias de colocación; la cuadrícula se construye mediante `tabular` u otro entorno.
```

En `\begin{tabular}{lcr}`, hay tres columnas: izquierda, centro y derecha. `&` separa celdas y `\\` termina una fila. Los tipos `l`, `c` y `r` usan la anchura natural del contenido; `p{4cm}` crea una columna de párrafos de anchura fija y permite que el texto ocupe varias líneas.[^tablas][^tablasexterna]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - tablas
---
> [!note] Pregunta
> ¿Cómo se distinguen las celdas y las filas dentro de `tabular` en LaTeX?
===
> [!important] Respuesta
> `&` separa celdas y `\\` termina la fila. Una fila ordinaria de $n$ columnas necesita $n-1$ separadores.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - tablas
---
> [!note] Pregunta
> ¿Qué diferencia una columna `p{4cm}` de las columnas `l`, `c` y `r` en LaTeX?
===
> [!important] Respuesta
> `p{4cm}` fija una anchura de párrafo y permite varias líneas; `l`, `c` y `r` usan la anchura natural y alinean a izquierda, centro y derecha.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - referencias-cruzadas
---
> [!note] Pregunta
> ¿Qué diferencia `tabular` de `table` al construir una tabla en LaTeX?
===
> [!important] Respuesta
> `tabular` organiza filas y columnas; `table` es el contenedor flotante que permite añadir leyenda, número y preferencias de colocación.
```

### Líneas y marco

> [!definicion] Línea divisoria de una tabla
> Línea que separa filas o columnas: `|` se declara en la especificación de columnas, `\hline` traza una línea horizontal completa y `\cline{a-b}` la limita a las columnas indicadas.[^tablas]

Por ejemplo, `{|l|c|r|}` rodea y separa tres columnas. La ficha 2 exige bordes en todas las celdas; en otros trabajos se eligen según la claridad de las comparaciones. `\fbox{...}` rodea una caja con un marco y `\framebox[5cm]{...}` permite dar una anchura al marco. Ninguno convierte su contenido en flotante.[^tablas]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - tablas
---
> [!note] Pregunta
> ¿Cómo se declaran líneas verticales y horizontales en un `tabular` LaTeX?
===
> [!important] Respuesta
> `|` en la especificación de columnas declara líneas verticales; `\hline` traza una horizontal completa y `\cline{a-b}` sólo entre las columnas indicadas.
```

#### Ejemplo — Tabla de la suma y marco exterior

**Tarea.** Construir la tabla docente de la suma con columnas 0–3 y filas 1–3, y distinguir la cuadrícula de un marco exterior.[^tablas]

```latex
\begin{tabular}{|l||c|c|c|c|}
\hline
soma & 0 & 1 & 2 & 3 \\ \hline\hline
1 & 1 & 2 & 3 & 4 \\ \hline
2 & 2 & 3 & 4 & 5 \\ \hline
3 & 3 & 4 & 5 & 6 \\ \hline
\end{tabular}
```

El resultado contiene cinco columnas porque incluye la de etiquetas. La entrada en la fila 2 y columna 3 es $2+3=5$; esa comprobación distingue los datos de las divisiones de celda. El doble `||` separa visualmente las etiquetas de fila.

La misma disposición numérica puede componerse dentro de una fórmula mediante `array`. Sus celdas se interpretan como matemáticas; la cabecera verbal se inserta con `\text`, de `amsmath`:

```latex
\begin{equation*}
\begin{array}{c|cccc}
\text{soma} & 0 & 1 & 2 & 3 \\ \hline
1 & 1 & 2 & 3 & 4 \\
2 & 2 & 3 & 4 & 5 \\
3 & 3 & 4 & 5 & 6
\end{array}
\end{equation*}
```

`tabular` permite construir una tabla de texto; `array` integra la disposición en el modo matemático. Los datos no cambian al elegir uno u otro.[^tablas][^ecuaciones]

Para comparar los marcos, el mismo contenido puede envolverse de estas dos formas:

```latex
\fbox{\begin{tabular}{c|cccc}
soma & 0 & 1 & 2 & 3 \\ \hline
1 & 1 & 2 & 3 & 4 \\
2 & 2 & 3 & 4 & 5 \\
3 & 3 & 4 & 5 & 6
\end{tabular}}
\qquad
\framebox[5cm]{\begin{tabular}{c|cccc}
soma & 0 & 1 & 2 & 3 \\ \hline
1 & 1 & 2 & 3 & 4 \\
2 & 2 & 3 & 4 & 5 \\
3 & 3 & 4 & 5 & 6
\end{tabular}}
```

`\fbox` ajusta el marco a la caja de contenido; `\framebox[5cm]` declara una anchura. Ninguna de las dos órdenes crea líneas entre celdas: las divisiones interiores siguen perteneciendo a `tabular`.

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - tablas
---
> [!note] Pregunta
> ¿Qué diferencia `\fbox{contenido}` de `\framebox[5cm]{contenido}` en LaTeX?
===
> [!important] Respuesta
> `\fbox` ajusta el marco a la caja de contenido; `\framebox` permite declarar una anchura, como 5 cm. Ambas crean un marco exterior.
```

#### Ejemplo — Tabla y referencia completas de la ficha 2

La tarea consiste en reproducir las cuatro columnas y cuatro filas, centrar tabla y contenido, sombrear y destacar el encabezado y colocar la leyenda debajo. Los valores siguientes son los datos del ejercicio de composición; no constituyen una verificación zoológica.[^ficha]

```latex
\documentclass[a4paper,11pt]{report}
\usepackage[T1]{fontenc}
\usepackage[utf8]{inputenc}
\usepackage[portuguese]{babel}
\usepackage[table]{xcolor}
\begin{document}
\chapter{Introdução}
Texto introdutório.
\chapter{Desenvolvimento}
\section{Subespécies}
As características fornecidas no exercício encontram-se
na tabela~\ref{tab:suricatas}.
\begin{table}[htbp]
  \centering
  \setlength{\tabcolsep}{5pt}
  \begin{tabular}{|c|c|c|c|}
    \hline
    \rowcolor{gray!25}
    \textbf{Característica} & \textbf{siricata} &
    \textbf{iona} & \textbf{majoriae} \\ \hline
    cor do pelo & beje amarelado & castanho amarelado & castanho escuro \\ \hline
    tamanho & 29 cm & 25 cm & 34 cm \\ \hline
    peso & 731 g & 698 g & 799 g \\ \hline
  \end{tabular}
  \caption{Características diferenciadoras entre subespécies de Suricata,
    segundo os dados do exercício.}
  \label{tab:suricatas}
\end{table}
\end{document}
```

El encabezado aporta la primera fila; las características, otras tres. Por tanto, «cuatro filas» incluye el encabezado. `\centering` centra el conjunto; las cuatro `c` centran las celdas. La leyenda sigue al `tabular`, y la etiqueta sigue a la leyenda. Al ser la primera tabla del capítulo 2 de `report`, su número ordinario es 2.1. La columna larga se revisa en el PDF: si desborda, se ajustan anchuras o formato conservando legibilidad.

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - tablas
---
> [!note] Pregunta
> ¿Cómo se sombrea una fila con la configuración `xcolor` del ejemplo de la ficha?
===
> [!important] Respuesta
> Se carga `\usepackage[table]{xcolor}` y se coloca `\rowcolor{color}` al comienzo de la fila.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - tablas
---
> [!note] Pregunta
> ¿Qué diferencia `\centering` de las columnas `c` al componer una tabla LaTeX?
===
> [!important] Respuesta
> `\centering` centra el conjunto en su contexto; `c` centra el contenido dentro de cada columna declarada así.
```

### Anchura total con tabularx

> [!definicion] Columna X
> Columna de párrafos del paquete `tabularx` cuya anchura se calcula para que la tabla alcance una anchura total declarada. Varias columnas `X` ordinarias comparten la anchura disponible.[^tablas]

```latex
% Preámbulo: \usepackage{tabularx}
\begin{tabularx}{\linewidth}{|X|X|}
  \hline
  Objetivo & Evidência necessária \\ \hline
  Comparar medidas & Valores e condições de obtenção \\ \hline
\end{tabularx}
```

`\linewidth` toma la anchura de la línea en el contexto actual. Reducir la tabla de 10 cm a 6 cm redistribuye el texto en más renglones: no modifica sus datos. Es una solución distinta de reducir toda la tabla como una imagen.[^tablas]

#### Ejemplo — Una misma tabla con 10 y 6 centímetros

**Tarea.** Comparar la anchura de las columnas de una tabla de suma sin cambiar sus entradas. El paquete `tabularx` debe estar cargado:

```latex
\begin{tabularx}{10cm}{|X|X|X|X|X|}
\hline
soma & 0 & 1 & 2 & 3 \\ \hline
0 & 0 & 1 & 2 & 3 \\
1 & 1 & 2 & 3 & 4 \\
2 & 2 & 3 & 4 & 5 \\ \hline
\end{tabularx}

\medskip
\begin{tabularx}{6cm}{|X|X|X|X|X|}
\hline
soma & 0 & 1 & 2 & 3 \\ \hline
0 & 0 & 1 & 2 & 3 \\
1 & 1 & 2 & 3 & 4 \\
2 & 2 & 3 & 4 & 5 \\ \hline
\end{tabularx}
```

Las columnas `X` de cada tabla comparten la anchura calculada. La segunda tabla resulta más estrecha, con los mismos tamaños de letra y los mismos datos. La fila 0 corresponde a la variante docente de `tabularx`; la primera tabla de suma anterior emplea filas 1–3.[^tablas]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - tablas
---
> [!note] Pregunta
> ¿Cómo controla `tabularx` la anchura de una tabla LaTeX mediante columnas `X`?
===
> [!important] Respuesta
> Se declara la anchura total y las columnas `X` ordinarias comparten automáticamente el espacio disponible, con redistribución del texto.
```

### Unión horizontal con multicolumn

> [!definicion] Celda que abarca columnas
> Celda construida mediante `\multicolumn{n}{formato}{contenido}` para ocupar $n$ columnas de una fila.[^tablasexterna]

```latex
\begin{tabular}{|c|c|c|}
\hline
\multicolumn{2}{|c|}{Grupo A} & Grupo B \\ \hline
1 & 2 & 3 \\ \hline
\end{tabular}
```

La primera celda consume dos de las tres columnas, por lo que sólo se añade un `&` antes de «Grupo B». `\multicolumn` pertenece a LaTeX: el paquete `multicol`, citado por error en ese punto del resumen, sirve para columnas de texto y no es necesario aquí.[^tablas][^tablasexterna]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - tablas
---
> [!note] Pregunta
> ¿Cómo se construye una celda que abarca varias columnas en LaTeX?
===
> [!important] Respuesta
> Con `\multicolumn{n}{formato}{contenido}`. Consume $n$ columnas de la fila y no requiere el paquete `multicol`.
```

### Unión vertical con multirow

> [!definicion] Celda que abarca filas
> Celda construida con `\multirow{n}{anchura}{contenido}`, del paquete `multirow`, para ocupar $n$ filas. `*` permite una anchura natural.[^tablas]

```latex
% Preámbulo: \usepackage{multirow}
\begin{tabular}{|c|c|}
\hline
\multirow{2}{*}{Condição A} & 1 \\ \cline{2-2}
                         & 2 \\ \hline
\end{tabular}
```

La segunda fila deja vacía su primera celda porque ya está ocupada. `\cline{2-2}` evita atravesar con una línea el texto que abarca ambas filas. Una cabecera compleja puede combinar `\multicolumn` y `\multirow`; conviene contar qué columnas consume cada celda antes de escribir separadores.[^tablas]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - tablas
---
> [!note] Pregunta
> ¿Cómo se construye una celda que abarca varias filas con `multirow` en LaTeX?
===
> [!important] Respuesta
> Se carga `multirow` y se usa `\multirow{n}{anchura}{contenido}`; `*` elige anchura natural. Las filas siguientes dejan vacías las posiciones ocupadas.
```

#### Ejemplo — Unir filas y columnas en la misma tabla

**Tarea.** Componer la tabla docente con dos columnas bajo un encabezado común, dos agrupaciones de filas y una columna de valores en nanómetros.[^tablas]

```latex
% Preámbulo: \usepackage{multirow}
\begin{tabular}{lcc}
\hline
\multicolumn{2}{c}{\multirow{2}{*}{Colunas mescladas}} & Outras \\
 & & nm \\ \hline
\multirow{2}{*}{Primeira} & A & 385 \\ \cline{2-3}
                        & B & 397 \\ \hline
\multirow{2}{*}{Segunda}  & C & 376 \\ \cline{2-3}
                        & D & 390 \\ \hline
\end{tabular}
```

El encabezado ocupa dos columnas y dos filas: la fila siguiente deja libres las dos primeras posiciones mediante `& &`. «Primeira» y «Segunda» abarcan dos filas cada una; las líneas parciales atraviesan sólo las columnas 2 y 3. Los números se conservan como datos del ejercicio de composición; la tabla no identifica por sí sola qué magnitud física se midió.

## Separación y escala de tablas

### Separación vertical: arraystretch

> [!definicion] Factor arraystretch
> Multiplicador de la separación vertical de referencia de las filas, modificado mediante `\renewcommand{\arraystretch}{factor}`.[^tablas]

Un valor `1.3` aumenta el espacio de referencia respecto al valor `1`. El cambio se limita a una tabla si se encierra en un grupo con ella.

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - tablas
---
> [!note] Pregunta
> ¿Cómo se modifica la separación vertical de referencia de las filas de una tabla LaTeX?
===
> [!important] Respuesta
> Cambiando `\arraystretch` mediante `\renewcommand`, por ejemplo a `1.3`; un grupo limita el cambio a la tabla contenida.
```

### Separación lateral: tabcolsep

> [!definicion] Longitud tabcolsep
> Separación lateral de referencia entre el contenido y los bordes de columna de un `tabular`; se modifica como longitud.[^tablas]

```latex
{
\renewcommand{\arraystretch}{1.3}
\setlength{\tabcolsep}{8pt}
\begin{tabular}{cc}
A & B \\
1 & 2
\end{tabular}
}
```

`\tabcolsep` se modifica con `\setlength`, no con `\renewcommand` como aparece en un ejemplo del resumen. El grupo limita ambos cambios a esta tabla. Para limitar una tabla demasiado ancha puede usarse `adjustbox`, cargado en el preámbulo, con `\begin{adjustbox}{max width=\linewidth}...\end{adjustbox}`. La reducción disminuye también el tamaño de las letras: hay que comprobar el resultado a tamaño de lectura.[^tablas]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - tablas
---
> [!note] Pregunta
> ¿Cómo se cambia la separación lateral controlada por `\tabcolsep` en LaTeX?
===
> [!important] Respuesta
> Con `\setlength{\tabcolsep}{longitud}`, por ejemplo `8pt`; es una longitud, no una macro que se redefina con `\renewcommand`.
```

### Escala con adjustbox

> [!definicion] Escalado de una tabla
> Cambio de tamaño del conjunto de la tabla, incluido su texto, para ajustarlo a una anchura de salida.[^tablas]

```latex
% Preámbulo: \usepackage{adjustbox}
\begin{adjustbox}{width=\textwidth}
  \begin{tabular}{cc}
    Método & Resultado \\
    A & 12
  \end{tabular}
\end{adjustbox}
```

`width=\textwidth` fuerza esa anchura, incluso si amplía una tabla pequeña. La variante `max width=\linewidth` limita el máximo sin exigir ese crecimiento. Se decide entre redistribuir texto mediante columnas de párrafo y escalar el conjunto según lo que conserve mejor la legibilidad.[^tablas][^adjustbox]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - tablas
---
> [!note] Pregunta
> ¿Qué diferencia `width=...` de `max width=...` al escalar con `adjustbox`?
===
> [!important] Respuesta
> `width` fuerza la anchura indicada; `max width` establece un máximo y evita ampliar un contenido que ya cabe.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - tablas
---
> [!note] Pregunta
> ¿Qué diferencia escalar toda una tabla de redistribuir su texto con columnas de párrafo?
===
> [!important] Respuesta
> El escalado cambia también las letras; las columnas de párrafo cambian los saltos de línea sin reducir necesariamente el tamaño tipográfico.
```

### Importación desde hojas de cálculo

> [!definicion] Exportación de tabla a LaTeX
> Conversión de celdas de una hoja de cálculo en código de composición que debe integrarse y revisarse en el documento.[^tablas]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - tablas
---
> [!note] Pregunta
> ¿Qué se obtiene al exportar celdas de una hoja de cálculo a LaTeX?
===
> [!important] Respuesta
> Código de composición de una tabla; la conversión no valida sus datos ni decide su pertinencia para el informe.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - tablas
---
> [!note] Pregunta
> ¿Qué paquete necesita una tabla exportada que utiliza `\toprule`, `\midrule` y `\bottomrule`?
===
> [!important] Respuesta
> `booktabs`; las órdenes generadas determinan las dependencias que deben cargarse antes de compilar.
```

El material propone Excel2LaTeX: se obtiene el complemento, se abre en Excel y se utiliza su función de exportación para generar el código de las celdas seleccionadas. La interfaz depende de la instalación. El código obtenido se copia al fuente y se identifican sus dependencias, como `xcolor` para colores o `booktabs` para `\toprule`, `\midrule` y `\bottomrule`. Después se comprueban valores, unidades, caracteres especiales, anchura y legibilidad. Exportar automatiza la transcripción; no valida los datos ni decide qué comparación necesita el informe.[^tablas]

> [!procedimiento] De la hoja de cálculo al documento
> 1. Obtener el complemento Excel2LaTeX y abrirlo en Excel según su instalación.
> 2. Seleccionar las celdas pertinentes y generar su código LaTeX.
> 3. Insertar el código en el documento y cargar los paquetes que utilice.
> 4. Compilar y comparar el PDF con las celdas originales: valores, unidades, cabeceras y signos.
> 5. Ajustar anchura y separación sin alterar los datos.[^tablas]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - tablas
---
> [!note] Pregunta
> ¿Qué requiere integrar en un documento LaTeX una tabla exportada con Excel2LaTeX?
===
> [!important] Respuesta
> Insertar el código, cargar sus dependencias y comprobar datos, unidades, caracteres, anchura y legibilidad en el PDF frente a la hoja original.
```

## Figuras y composición de bloques

### Inclusión y escala con graphicx

> [!definicion] Inclusión gráfica
> Inserción de un archivo mediante `\includegraphics`, del paquete `graphicx`, con opciones de tamaño o escala.[^figuras]

En una ruta con `pdflatex` se usan habitualmente PDF, PNG o JPEG. `\includegraphics[width=.65\linewidth]{medidas.pdf}` asigna una anchura relativa; `scale=.5` aplica un factor de escala; `\scalebox{.5}{...}` escala el contenido que encierra. La ruta y el nombre deben corresponder al archivo real.[^figuras]

```latex
% Preámbulo: \usepackage{graphicx}
\begin{figure}[htbp]
  \centering
  \includegraphics[width=.65\linewidth]{medidas.pdf}
  \caption{Magnitud medida frente al tiempo; unidades indicadas en los ejes.}
  \label{fig:medidas}
\end{figure}
```

Este fragmento requiere aportar `medidas.pdf`. El bloque incluye la imagen; la leyenda identifica la evidencia y la prosa que la cita interpreta el resultado. Una figura legible conserva los rótulos al tamaño final del PDF.

Las variantes `\includegraphics[scale=.5]{medidas.pdf}` y `\scalebox{.5}{\includegraphics{medidas.pdf}}` aplican un factor de escala. `width=.65\linewidth` fija una anchura relativa al contexto; el mismo factor `.5` puede producir anchuras distintas si los archivos originales tienen tamaños diferentes.[^figuras]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - figuras
---
> [!note] Pregunta
> ¿Cómo se incluye una imagen mediante `graphicx` en LaTeX?
===
> [!important] Respuesta
> Se carga `graphicx` y se usa `\includegraphics[opciones]{archivo}`; el nombre y la ruta deben corresponder a un archivo disponible.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - figuras
---
> [!note] Pregunta
> ¿Qué diferencia `width=.65\linewidth` de `scale=.5` al incluir una imagen LaTeX?
===
> [!important] Respuesta
> La primera fija una anchura relativa a la línea disponible; la segunda multiplica las dimensiones originales por un factor.
```

### Subfiguras

> [!definicion] Subfigura
> Panel identificado dentro de una figura común, con una anchura y una leyenda propias. `subcaption` proporciona el entorno `subfigure`.[^figuras]

```latex
% Preámbulo: \usepackage{graphicx,subcaption}
\begin{figure}[htbp]
  \centering
  \begin{subfigure}[b]{.46\linewidth}
    \includegraphics[width=\linewidth]{caso-a.pdf}
    \caption{Condição A}
  \end{subfigure}\hfill
  \begin{subfigure}[b]{.46\linewidth}
    \includegraphics[width=\linewidth]{caso-b.pdf}
    \caption{Condição B}
  \end{subfigure}
  \caption{Comparação entre as duas condições.}
  \label{fig:comparacao}
\end{figure}
```

Las anchuras y separaciones deben caber en la línea. Para tres paneles puede asignarse `.30\linewidth` a cada uno con separaciones que respeten ese límite. El entorno `subfigure` de `subcaption` no debe confundirse con el antiguo paquete llamado `subfigure`; los ejemplos usan una única solución coherente.[^figuras]

#### Ejemplo — Tres paneles con leyendas propias

**Tarea.** Disponer tres imágenes, cada una identificada por su condición, y una leyenda común. Los tres archivos indicados deben estar disponibles.

```latex
% Preámbulo: \usepackage{graphicx,subcaption}
\begin{figure}[htbp]
\centering
\begin{subfigure}{.30\linewidth}
  \includegraphics[width=\linewidth]{caso-a.pdf}
  \caption{Condição A}
\end{subfigure}\hfill
\begin{subfigure}{.30\linewidth}
  \includegraphics[width=\linewidth]{caso-b.pdf}
  \caption{Condição B}
\end{subfigure}\hfill
\begin{subfigure}{.30\linewidth}
  \includegraphics[width=\linewidth]{caso-c.pdf}
  \caption{Condição C}
\end{subfigure}
\caption{Comparação das três condições.}
\label{fig:tres-condicoes}
\end{figure}
```

Las cajas consumen el 90 % de la anchura exterior y dejan espacio para la separación. Dentro de cada `subfigure`, `\linewidth` es la anchura de ese panel. Las leyendas individuales identifican las condiciones; la común formula la comparación.[^figuras]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - figuras
---
> [!note] Pregunta
> ¿Qué aporta una subfigura dentro de una figura LaTeX?
===
> [!important] Respuesta
> Un panel con anchura y leyenda propias dentro de una figura común; `subcaption` proporciona el entorno `subfigure`.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - figuras
---
> [!note] Pregunta
> ¿Qué condición de anchura debe comprobarse al colocar varias subfiguras en una línea?
===
> [!important] Respuesta
> Que sus anchuras y las separaciones entre ellas quepan en la anchura disponible; dentro de cada panel, `\linewidth` es local.
```

### Minipage

> [!definicion] Minipage
> Caja de texto de anchura declarada que permite componer un bloque con párrafos y otros elementos dentro de una página.[^bloques]

```latex
\begin{minipage}[t]{.45\linewidth}
  \textbf{Método}\par
  Descrição do procedimento.
\end{minipage}\hfill
\begin{minipage}[t]{.45\linewidth}
  \textbf{Resultado}\par
  Síntese da observação.
\end{minipage}
```

`[t]` alinea las cajas por arriba; pueden usarse `[c]` o `[b]` para otras alineaciones. La anchura es obligatoria y `\linewidth` dentro de la caja se refiere a su anchura local. La sintaxis ampliada permite declarar altura y alineación interna: `\begin{minipage}[c][3cm][c]{5cm}`. Es útil para un encabezado con logotipo y texto, sin convertir ambos elementos en flotantes independientes.[^bloques]

#### Ejemplo — Encabezado con imagen y texto

**Tarea.** Reservar dos cajas de altura 3 cm para un logotipo y el título de una ficha. Se carga `graphicx` y se aporta `logo.pdf`:

```latex
\begin{minipage}[c][3cm][c]{3cm}
  \includegraphics[height=1.5cm]{logo.pdf}
\end{minipage}\hfill
\begin{minipage}[c][3cm][c]{8.5cm}
  \begin{flushright}
    Ficha de \LaTeX\\
    Modo Texto
  \end{flushright}
\end{minipage}
```

El primer `[c]` determina la alineación de la caja respecto a los elementos vecinos; `[3cm]` fija la altura y el siguiente `[c]` centra verticalmente su contenido. Las anchuras obligatorias son 3 y 8,5 cm. La suma de anchuras y separaciones debe caber en la línea. Las dimensiones declaradas permiten comparar el resultado con el encabezado docente.[^bloques]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - composicion
---
> [!note] Pregunta
> ¿Qué construye una `minipage` de LaTeX y qué dimensión es obligatoria?
===
> [!important] Respuesta
> Una caja que puede contener párrafos y otros elementos; debe declararse su anchura.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - composicion
---
> [!note] Pregunta
> ¿Qué indican los argumentos de `\begin{minipage}[c][3cm][c]{5cm}`?
===
> [!important] Respuesta
> Alineación exterior central, altura 3 cm, alineación interior central y anchura 5 cm, en ese orden.
```

#### Anchura relativa expresada en em

> [!definicion] Unidad em
> Unidad de longitud determinada por la fuente actual. Permite expresar dimensiones relativas a su escala tipográfica, en lugar de fijarlas en centímetros.[^unidades]

El ejemplo docente `\begin{minipage}{10em}...\end{minipage}` utiliza diez veces esa longitud como anchura de la caja. Cambiar la fuente puede cambiar la anchura física resultante. La asociación histórica con la letra M no debe interpretarse como una medición universal del glifo en cualquier fuente.[^bloques][^unidades]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - composicion
---
> [!note] Pregunta
> ¿Por qué una anchura de `10em` en LaTeX no representa una longitud física universal?
===
> [!important] Respuesta
> Porque `em` depende de la fuente actual; diez veces esa unidad puede cambiar de anchura al cambiar la fuente.
```

### Quote

> [!definicion] Bloque quote
> Entorno de composición de una cita o fragmento separado del párrafo principal mediante márgenes.[^bloques]

`\begin{quote}...\end{quote}` cambia la disposición del fragmento. La atribución se escribe junto a la cita con el sistema bibliográfico correspondiente; el entorno sólo compone el texto. Separación visual y reconocimiento de autoría cumplen funciones distintas.

```latex
Texto que introduce una cita atribuida:
\begin{quote}
  Fragmento citado literalmente.
\end{quote}
```

Este fragmento es una plantilla de composición: en una entrega se reemplaza por la cita real y su referencia. El cambio de márgenes permite identificar el bloque, pero no aporta el nombre del autor ni la localización de la fuente.[^bloques]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - composicion
---
> [!note] Pregunta
> ¿Qué aporta `quote` a una cita en LaTeX y qué debe añadirse aparte?
===
> [!important] Respuesta
> La separa tipográficamente mediante márgenes; la atribución y la referencia bibliográfica deben incorporarse por su propio mecanismo.
```

### Verbatim y presentación de código

> [!definicion] Verbatim
> Entorno que muestra literalmente el contenido, conservando caracteres que normalmente serían interpretados como órdenes.[^bloques]

Sirve para enseñar el propio código LaTeX o un fragmento técnico. El entorno básico existe sin cargar paquetes; el paquete `verbatim` amplía sus posibilidades. La presentación de programas con lenguaje, numeración y leyendas se desarrolla mediante [[Física/Grado/1º/Produção de Relatórios/07 Listados de código con listing y listings|listings]]. Mostrar código no lo ejecuta ni comprueba su resultado.

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - composicion
---
> [!note] Pregunta
> ¿Qué hace el entorno `verbatim` con las órdenes escritas en su interior?
===
> [!important] Respuesta
> Las muestra literalmente en vez de ejecutarlas como órdenes de composición. El entorno básico no requiere cargar un paquete.
```

### Columnas de texto

> [!definicion] Composición en columnas
> Distribución del texto en varias columnas, globalmente mediante la opción `twocolumn` o localmente mediante `multicols`, del paquete `multicol`.[^columnas]

```latex
% Preámbulo: \usepackage{multicol}
\begin{multicols}{2}
Primeiro parágrafo com texto suficiente para ocupar várias linhas.

Segundo parágrafo do bloco.
\end{multicols}
```

El argumento puede cambiarse a `3` para tres columnas. Se comprueba que el ancho disponible permite leer las fórmulas, tablas y figuras previstas. `multicols`, `\multicolumn` y `minipage` resuelven problemas diferentes: flujo de prosa, unión de celdas y caja de anchura fijada, respectivamente.

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - composicion
---
> [!note] Pregunta
> ¿Cómo se elige entre `multicols`, `\multicolumn` y `minipage` en LaTeX?
===
> [!important] Respuesta
> `multicols` distribuye prosa en columnas; `\multicolumn` une celdas de una tabla; `minipage` crea una caja de anchura declarada.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - composicion
---
> [!note] Pregunta
> ¿Qué diferencia la opción de clase `twocolumn` del entorno `multicols`?
===
> [!important] Respuesta
> `twocolumn` selecciona globalmente dos columnas; `multicols` permite distribuir un bloque concreto en el número de columnas indicado.
```

```latex
% Preámbulo: \usepackage{multicol}
\begin{multicols}{3}
1\\ 2\\ 3\\ 4\\ 5\\ 6
\end{multicols}
```

En el ejemplo breve y equilibrado de la fuente, la lectura baja por cada columna y continúa por la siguiente: 1–2, 3–4 y 5–6. Con prosa extensa, las líneas y el equilibrio dependen del contenido y de la anchura disponible.[^columnas]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - composicion
---
> [!note] Pregunta
> ¿Cómo se distribuye localmente la prosa en tres columnas con LaTeX?
===
> [!important] Respuesta
> Se carga `multicol` y se coloca el texto en `\begin{multicols}{3}...\end{multicols}`.
```

## Ecuaciones de varias líneas y matrices

La elección del entorno depende de qué constituye una unidad matemática: una relación larga, una cadena de transformaciones o varias ecuaciones independientes. Los ejemplos siguientes requieren `\usepackage{amsmath}` en el preámbulo. Las letras de los ejemplos algebraicos representan variables reales y las igualdades expresan las relaciones que se desea componer; no son datos de un experimento. $S$ nombra una suma, $p$ un polinomio y las letras con subíndice identifican sus términos o variables.[^ecuaciones]

### equation y numeración

> [!definicion] Ecuación numerada
> Expresión compuesta con `equation`, que asigna un número al conjunto. `equation*` omite ese número; una etiqueta permite citar una ecuación numerada.[^ecuaciones]

```latex
\begin{equation}
  p(x)=x^2-1
  \label{eq:polinomio}
\end{equation}
A equação~\ref{eq:polinomio} define o polinómio.
```

Una etiqueta en una ecuación sin número no crea uno. El entorno `equation` solo no organiza varias líneas separadas por `\\`; necesita una estructura interior apropiada o ser sustituido por otro entorno.[^ecuaciones]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - ecuaciones
---
> [!note] Pregunta
> ¿Basta insertar `\\` dentro de `equation` para construir una derivación de varias líneas?
===
> [!important] Respuesta
> No. Se necesita una estructura apropiada, como `split` dentro de `equation`, o un entorno multilineal adecuado.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - ecuaciones
---
> [!note] Pregunta
> ¿Cómo se obtiene una ecuación numerada y referenciable en LaTeX?
===
> [!important] Respuesta
> Se utiliza `equation` y se coloca una etiqueta dentro; `\ref` recupera su número. `equation*` no produce ese número.
```

### multline: una expresión larga

> [!definicion] multline
> Entorno para partir una única expresión en varias líneas sin exigir un punto común de alineación. La primera y la última se disponen hacia extremos opuestos.[^ecuaciones]

```latex
\begin{multline}
  S=a_1+a_2+a_3+a_4+a_5+a_6\\
    +a_7+a_8+a_9+a_{10}
\end{multline}
```

La suma conserva todos sus términos; el salto responde a la anchura. No se insertan signos de igualdad nuevos si la segunda línea sólo continúa el mismo miembro.

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - ecuaciones
---
> [!note] Pregunta
> ¿Cuándo se elige `multline` para componer matemáticas en LaTeX?
===
> [!important] Respuesta
> Para una expresión larga repartida en varias líneas sin exigir un punto común de alineación.
```

### split: una cadena con un solo número

> [!definicion] split
> Estructura de alineación situada dentro de una ecuación para repartirla en varias líneas conservando un único número.[^ecuaciones]

```latex
\begin{equation}
\begin{split}
  (x+y)(x-y) &= x^2-xy+xy-y^2\\
             &= x^2-y^2
\end{split}
\label{eq:producto}
\end{equation}
```

`&` marca el punto común, aquí antes de `=`. La primera igualdad desarrolla el producto y la segunda cancela términos opuestos. El conjunto expresa una única derivación válida para $x,y\in\mathbb R$ y recibe una sola referencia.

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - ecuaciones
---
> [!note] Pregunta
> ¿Cómo se decide qué símbolos quedan alineados verticalmente en un `split` de LaTeX?
===
> [!important] Respuesta
> Situando las marcas `&` en la posición que deba compartirse entre filas, por ejemplo antes de `=` o antes de una continuación con `+`.
```

#### Ejemplo — Alinear una continuación o una igualdad

**Tarea.** Componer $a=b+c-d+e-f$ en dos líneas y decidir qué relación debe resultar visible.[^ecuaciones]

```latex
\begin{equation}
\begin{split}
 a=b &+c-d\\
     &+e-f
\end{split}
\end{equation}

\begin{equation}
\begin{split}
 a &= b+c-d\\
   &\quad +e-f
\end{split}
\end{equation}
```

En la primera versión, las marcas se sitúan antes de los signos `+` de ambas líneas. En la segunda, la primera marca precede al signo `=` y la continuación recibe sangría. La segunda línea prolonga el mismo miembro; no afirma una igualdad distinta.

Una derivación completa puede conservar también un único número:

```latex
\begin{equation}
\begin{split}
 f(x,y) &= \frac{1}{6}(2x^2+3xy+xy)\\
        &= \frac{1}{3}(x^2+2xy)\\
        &= \frac{x^2+2xy}{3}.
\end{split}
\end{equation}
```

Para $x,y\in\mathbb R$, la segunda igualdad agrupa $3xy+xy=4xy$ y extrae un factor 2; la última reúne los términos bajo el mismo denominador. Las tres líneas describen la misma función.[^ecuaciones]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - ecuaciones
---
> [!note] Pregunta
> ¿Qué aporta `split` dentro de `equation` en LaTeX?
===
> [!important] Respuesta
> Reparte una misma ecuación o derivación en varias líneas alineadas, conservando un único número para el conjunto.
```

### gather: ecuaciones sin alineación común

> [!definicion] gather
> Entorno que agrupa ecuaciones centradas sin alinearlas entre sí. Cada fila puede recibir un número; `gather*` elimina la numeración.[^ecuaciones]

```latex
\begin{gather}
  a_1=b_1+c_1\\
  a_2=b_2+c_2-d_2
\end{gather}
```

Es adecuado si no se desea destacar una columna de igualdades. Se elige por la relación visual entre ecuaciones, no simplemente porque haya dos líneas.

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - ecuaciones
---
> [!note] Pregunta
> ¿Cómo dispone `gather` varias ecuaciones en LaTeX?
===
> [!important] Respuesta
> Las centra sin alinearlas entre sí; cada fila puede numerarse y la variante `gather*` omite los números.
```

### align: ecuaciones alineadas

> [!definicion] align
> Entorno de ecuaciones cuyas filas se alinean en las marcas `&`. Cada fila numerada puede tener su propia etiqueta; `align*` omite los números.[^ecuaciones]

```latex
\begin{align}
  a_1 &= b_1+c_1 \label{eq:primera}\\
  a_2 &= b_2+c_2-d_2 \label{eq:segunda}
\end{align}
```

Para varias parejas de columnas se añaden marcas: `a_{11} &= b_{11} & a_{12} &= b_{12}`. Cada pareja sitúa una parte a la derecha y otra a la izquierda del punto de alineación. `\notag` o `\nonumber` suprime el número de una fila concreta. El material contiene también `eqnarray`; los entornos de `amsmath` evitan sus problemas de espaciado y proporcionan el control necesario.[^ecuaciones][^ams]

```latex
\begin{align}
 a_{11} &= b_{11} & a_{12} &= b_{12}\\
 a_{21} &= b_{21} & a_{22} &= b_{22}+c_{22} \notag
\end{align}
```

Hay dos parejas de columnas y dos filas. Cada pareja alinea su signo de igualdad; `\notag` suprime sólo el número de la segunda fila.[^ecuaciones]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - ecuaciones
---
> [!note] Pregunta
> ¿Qué relación visual establece el entorno `align` de LaTeX?
===
> [!important] Respuesta
> Alinea las filas en las marcas `&`, con numeración independiente por fila; pueden disponerse varias parejas de columnas.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - ecuaciones
---
> [!note] Pregunta
> ¿Cómo se suprime el número de una fila concreta dentro de `align` en LaTeX?
===
> [!important] Respuesta
> Añadiendo `\notag` o `\nonumber` a esa fila; `align*` suprime la numeración del conjunto.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - referencias-cruzadas
---
> [!note] Pregunta
> ¿Cómo se elige entre `equation` con `split` y `align` para varias líneas matemáticas?
===
> [!important] Respuesta
> `equation` con `split` trata la derivación como una unidad con un número; `align` permite numerar y referenciar filas por separado.
```

### flalign: extensión horizontal

> [!definicion] flalign
> Variante de alineación que distribuye ampliamente las columnas, hasta los márgenes disponibles. Se usa cuando esa distribución facilita comparar expresiones separadas.[^ams]

```latex
\begin{flalign*}
  a &= b+c &&\\
  d &= e-f &&
\end{flalign*}
```

Las marcas finales permiten disponer la alineación en la anchura disponible. Se compara el resultado con `align*`: si la separación amplia no ayuda, `align` conserva una composición más compacta. Es una ampliación de contraste de `amsmath`, no un requisito adicional del esquema docente.

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - ecuaciones
---
> [!note] Pregunta
> ¿Qué diferencia de disposición ofrece `flalign` respecto a una alineación compacta en LaTeX?
===
> [!important] Respuesta
> Distribuye ampliamente las columnas hasta los márgenes disponibles; se elige si esa extensión ayuda a comparar las expresiones.
```

### array: alineación matemática general

> [!definicion] array
> Entorno de filas y columnas dentro del modo matemático, con una especificación de alineación semejante a la de una tabla.[^ecuaciones]

```latex
\begin{equation*}
\left\{\begin{array}{ll}
  x+y=3 & \text{primeira condição}\\
  x-y=1 & \text{segunda condição}
\end{array}\right.
\end{equation*}
```

`\left\{` abre una llave visible y `\right.` cierra el par de delimitadores sin dibujar el segundo. A diferencia de `tabular`, `array` compone sus celdas como matemáticas; las palabras necesitan `\text`.

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - ecuaciones
---
> [!note] Pregunta
> ¿Cómo se cierra un par `\left` y `\right` cuando sólo se desea una llave visible a la izquierda?
===
> [!important] Respuesta
> Se utiliza `\left\{` para abrir y `\right.` para cerrar con un delimitador invisible.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - ecuaciones
---
> [!note] Pregunta
> ¿Qué diferencia `array` de `tabular` al disponer filas y columnas en LaTeX?
===
> [!important] Respuesta
> `array` funciona dentro del modo matemático y compone sus celdas como matemáticas; las palabras deben insertarse como texto.
```

### cases: condiciones y funciones por tramos

> [!definicion] cases
> Entorno de `amsmath` que organiza expresiones con una llave izquierda y una segunda columna para sus condiciones.[^ecuaciones]

Para el valor absoluto de un número real se tiene:

$$
|x|=\begin{cases}
x,&x\ge0,\\
-x,&x<0.
\end{cases}
$$

```latex
\begin{equation}
  |x|=\begin{cases}
    x  & \text{se } x\ge0,\\
    -x & \text{se } x<0.
  \end{cases}
\end{equation}
```

Las condiciones cubren todos los reales y no se solapan. Una función por tramos requiere esa lectura de dominio; una llave correctamente dibujada no corrige condiciones contradictorias.

En el ejemplo de condiciones del material aparece un «5» aislado en una fila que debería expresar cuándo se aplica una fórmula. Esa fila no especifica una condición interpretable. El ejemplo del valor absoluto emplea condiciones explícitas y comprueba que cada real recibe un solo valor.[^ecuaciones]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - ecuaciones
---
> [!note] Pregunta
> ¿Qué estructura compone `cases` de `amsmath`?
===
> [!important] Respuesta
> Expresiones bajo una llave izquierda con una segunda columna para sus condiciones; se utiliza dentro del modo matemático.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - ecuaciones
---
> [!note] Pregunta
> ¿Qué debe comprobarse en las condiciones de una función real definida por tramos?
===
> [!important] Respuesta
> Que cubran el dominio declarado y asignen un único valor a cada argumento; una composición tipográfica correcta no garantiza esa coherencia.
```

### Matrices y delimitadores

> [!definicion] Entorno de matriz
> Disposición matemática rectangular cuyas columnas se separan con `&` y filas con `\\`; los entornos de `amsmath` añaden delimitadores según el nombre elegido.[^matrices]

| Entorno | Delimitador |
|---|---|
| `matrix` | Ninguno. |
| `pmatrix` | Paréntesis. |
| `bmatrix` | Corchetes. |
| `Bmatrix` | Llaves. |
| `vmatrix` | Barras simples. |
| `Vmatrix` | Barras dobles. |

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - matrices
---
> [!note] Pregunta
> ¿Cómo se separan filas y columnas en los entornos matriciales de `amsmath`?
===
> [!important] Respuesta
> `&` separa columnas y `\\` separa filas. El nombre del entorno determina los delimitadores.
```

```latex
\begin{equation*}
  A=\begin{pmatrix}
    1 & 2 & 3\\
    4 & 5 & 6\\
    7 & 8 & 9
  \end{pmatrix}
\end{equation*}
```

La matriz tiene tres filas y tres columnas; cada fila contiene dos separadores. Las barras simples se usan a menudo para determinantes y las dobles para normas, pero el entorno sólo imprime delimitadores: la operación y su significado deben declararse en el argumento matemático.

Las [[Matemáticas/Álgebra lineal/Matrices|matrices]] permiten organizar estos números por filas y columnas. Para comparar únicamente los delimitadores se conserva el mismo contenido en todos los ejemplos siguientes.[^matrices]

### matrix: sin delimitadores

> [!definicion] Entorno matrix
> Variante matricial de `amsmath` que dispone las entradas sin añadir delimitadores.[^matrices]

`\begin{matrix}1&2\\3&4\end{matrix}`, dentro del modo matemático, compone:

$$
\begin{matrix}1&2\\3&4\end{matrix}.
$$

Las entradas quedan alineadas sin añadir un contorno. Esta variante permite elegir después delimitadores externos si resultan necesarios.[^matrices]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - matrices
---
> [!note] Pregunta
> ¿Qué delimitadores añade el entorno `matrix` de `amsmath`?
===
> [!important] Respuesta
> Ninguno; sólo dispone las entradas en filas y columnas.
```

### pmatrix: paréntesis

> [!definicion] Entorno pmatrix
> Variante matricial de `amsmath` que encierra las entradas entre paréntesis.[^matrices]

`\begin{pmatrix}1&2\\3&4\end{pmatrix}` añade paréntesis a las mismas entradas:

$$
\begin{pmatrix}1&2\\3&4\end{pmatrix}.
$$

El orden sigue siendo $2\times2$; el cambio de entorno afecta a los delimitadores.[^matrices]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - matrices
---
> [!note] Pregunta
> ¿Qué entorno de `amsmath` compone una matriz entre paréntesis?
===
> [!important] Respuesta
> `pmatrix`, con `&` entre columnas y `\\` entre filas.
```

### bmatrix: corchetes

> [!definicion] Entorno bmatrix
> Variante matricial de `amsmath` que encierra las entradas entre corchetes.[^matrices]

`\begin{bmatrix}1&2\\3&4\end{bmatrix}` produce:

$$
\begin{bmatrix}1&2\\3&4\end{bmatrix}.
$$

Se elige cuando la convención adoptada para la matriz utiliza corchetes.[^matrices]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - matrices
---
> [!note] Pregunta
> ¿Qué entorno de `amsmath` compone una matriz entre corchetes?
===
> [!important] Respuesta
> `bmatrix`; la letra inicial minúscula distingue esta variante de `Bmatrix`.
```

### Bmatrix: llaves

> [!definicion] Entorno Bmatrix
> Variante matricial de `amsmath` que encierra las entradas entre llaves.[^matrices]

`\begin{Bmatrix}1&2\\3&4\end{Bmatrix}` produce:

$$
\begin{Bmatrix}1&2\\3&4\end{Bmatrix}.
$$

La `B` mayúscula es parte del nombre de la orden y selecciona llaves.[^matrices]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - matrices
---
> [!note] Pregunta
> ¿Qué entorno de `amsmath` compone una disposición matricial entre llaves?
===
> [!important] Respuesta
> `Bmatrix`, con `B` mayúscula.
```

### vmatrix: barras simples

> [!definicion] Entorno vmatrix
> Variante matricial de `amsmath` que encierra las entradas entre barras simples, sin efectuar una operación sobre ellas.[^matrices]

`\begin{vmatrix}1&2\\3&4\end{vmatrix}` produce:

$$
\begin{vmatrix}1&2\\3&4\end{vmatrix}.
$$

Si se declara que representa el determinante de esa matriz cuadrada, su valor es $1\cdot4-2\cdot3=-2$. El entorno imprime las barras y las entradas; el cálculo se realiza aparte.[^matrices]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - matrices
---
> [!note] Pregunta
> ¿Qué imprime `vmatrix` y qué debe declararse si sus barras representan un determinante?
===
> [!important] Respuesta
> Imprime barras simples alrededor de las entradas; debe declararse la interpretación como determinante, que el entorno no calcula.
```

### Vmatrix: barras dobles

> [!definicion] Entorno Vmatrix
> Variante matricial de `amsmath` que encierra las entradas entre barras dobles, sin definir por sí sola una norma.[^matrices]

`\begin{Vmatrix}1&2\\3&4\end{Vmatrix}` produce:

$$
\begin{Vmatrix}1&2\\3&4\end{Vmatrix}.
$$

Las barras dobles pueden utilizarse en una notación de norma, cuya definición debe indicarse. Elegir este entorno no determina por sí solo qué norma se utiliza.[^matrices]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - matrices
---
> [!note] Pregunta
> ¿Qué imprime `Vmatrix` de `amsmath`?
===
> [!important] Respuesta
> Barras dobles alrededor de las entradas; una interpretación como norma necesita su propia definición matemática.
```

### Puntos de continuación e índices finales

Para una matriz de $m$ filas y $n$ columnas, los índices finales deben corresponder a esas dimensiones. `\ldots`, `\vdots` y `\ddots` representan continuación horizontal, vertical y diagonal:

```latex
\begin{equation*}
 A=\begin{pmatrix}
 a_{11} & \ldots & a_{1n}\\
 \vdots & \ddots & \vdots\\
 a_{m1} & \ldots & a_{mn}
 \end{pmatrix}
\end{equation*}
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - matrices
---
> [!note] Pregunta
> ¿Cómo se indican continuaciones horizontal, vertical y diagonal en una matriz LaTeX?
===
> [!important] Respuesta
> Con `\ldots`, `\vdots` y `\ddots`, respectivamente; los índices finales deben corresponder a las dimensiones declaradas.
```

## Índices y navegación automática

### Índice de contenido

> [!definicion] Índice de contenido
> Relación de divisiones del documento generada a partir de las órdenes de seccionado, mediante `\tableofcontents`.[^indices]

La primera compilación registra entradas y otra las incorpora. Los cambios posteriores pueden alterar páginas y requerir nuevas pasadas. Los títulos escritos únicamente con formato manual no producen esas entradas. Las versiones con asterisco, como `\section*`, tampoco se incorporan automáticamente como una sección numerada ordinaria.[^indices]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - indices
---
> [!note] Pregunta
> ¿Aparece automáticamente una sección creada con `\section*` en el índice de contenido LaTeX?
===
> [!important] Respuesta
> No. Su incorporación debe declararse si se necesita, pues no genera la entrada ordinaria de una sección numerada.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - indices
---
> [!note] Pregunta
> ¿De dónde obtiene `\tableofcontents` las entradas del índice de contenido LaTeX?
===
> [!important] Respuesta
> De las órdenes de seccionado; los títulos escritos sólo con formato manual no aportan entradas. La información se registra y lee mediante compilaciones sucesivas.
```

### Índice de figuras

> [!definicion] Índice de figuras
> Relación generada mediante `\listoffigures` a partir de las leyendas de figuras.[^indices]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - indices
---
> [!note] Pregunta
> ¿Qué orden genera el índice de figuras en LaTeX y de dónde proceden sus entradas?
===
> [!important] Respuesta
> `\listoffigures`; sus entradas proceden de las leyendas de figuras.
```

### Índice de tablas

> [!definicion] Índice de tablas
> Relación generada mediante `\listoftables` a partir de las leyendas de tablas.[^indices]

Insertar sólo una imagen o un `tabular` sin su leyenda no aporta una entrada numerada a esos índices. Un título breve opcional, como `\caption[Comparação]{Explicação completa...}`, permite que el índice sea conciso mientras la figura conserva una leyenda explicativa.[^indices]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - indices
---
> [!note] Pregunta
> ¿Qué orden genera el índice de tablas en LaTeX y de dónde proceden sus entradas?
===
> [!important] Respuesta
> `\listoftables`; sus entradas proceden de las leyendas de tablas, no del contenido de un `tabular` aislado.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - indices
---
> [!note] Pregunta
> ¿Cómo se escribe una entrada breve para el índice sin acortar la leyenda de una figura LaTeX?
===
> [!important] Respuesta
> Mediante el argumento opcional de `\caption[entrada breve]{leyenda completa}`.
```

### Índice remisivo

> [!definicion] Índice remisivo
> Índice alfabético de términos y páginas de aparición, construido a partir de marcas `\index{...}` y procesado con una herramienta de indexación.[^remisivo]

```latex
% Preámbulo
\usepackage{makeidx}
\makeindex
% En el cuerpo
A compilação\index{compilação} produz o documento.
Uma figura\index{figuras!legendas} pode ter uma legenda.
% Donde debe imprimirse el índice
\printindex
```

La secuencia es LaTeX → `makeindex documento.idx` → LaTeX. El archivo `.idx` contiene las entradas sin ordenar, `.ind` el índice preparado para incorporar y `.ilg` el registro del proceso de indexación. Una marca `figuras!legendas` crea una subentrada. El índice de contenido organiza capítulos y secciones; el remisivo permite buscar términos dispersos.[^remisivo]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - indices
---
> [!note] Pregunta
> ¿Cómo se construye e incorpora un índice remisivo con MakeIndex en LaTeX?
===
> [!important] Respuesta
> Se carga `makeidx`, se activa `\makeindex`, se marcan términos con `\index`, se ejecuta LaTeX → MakeIndex → LaTeX y se coloca `\printindex` donde debe aparecer.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - indices
---
> [!note] Pregunta
> ¿Qué funciones cumplen `.idx`, `.ind` y `.ilg` al generar un índice remisivo?
===
> [!important] Respuesta
> `.idx` contiene entradas sin ordenar, `.ind` el índice preparado para incorporar y `.ilg` el registro del programa de indexación.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - indices
---
> [!note] Pregunta
> ¿Cómo se crea una subentrada en un índice remisivo LaTeX?
===
> [!important] Respuesta
> Separando entrada y subentrada con `!`, como `\index{figuras!legendas}`.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - referencias-cruzadas
---
> [!note] Pregunta
> ¿Qué distingue el índice de contenido del índice remisivo de un documento LaTeX?
===
> [!important] Respuesta
> El de contenido recoge el seccionado; el remisivo organiza términos marcados con `\index` y necesita procesar las entradas con una herramienta como MakeIndex.
```

## Página, portada y proyecto con varios archivos

### Portada

> [!definicion] Portada generada
> Composición de los datos declarados mediante `\title`, `\author` y `\date`, invocada con `\maketitle`.[^pagina]

```latex
% Preámbulo
\title{Relatório de medição}
\author{Nome do autor\\Faculdade de Ciências}
\date{Outubro de 2026}
% Cuerpo
\maketitle
```

Para una imagen en la portada, el material propone `titlepic` junto con `graphicx`: `\titlepic{\includegraphics[width=3cm]{logo.pdf}}`, antes de `\maketitle`. La orden `\institute` presentada en una diapositiva corresponde a clases como `beamer`; no está disponible por defecto en `article` o `report`. En estas clases se puede integrar la institución en los datos de autor o diseñar una portada propia.[^pagina]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - composicion
---
> [!note] Pregunta
> ¿Cómo se genera una portada básica a partir de metadatos en LaTeX?
===
> [!important] Respuesta
> Se declaran `\title`, `\author` y `\date`, y se invoca `\maketitle` en el cuerpo.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - composicion
---
> [!note] Pregunta
> ¿Cómo se añade una imagen a la portada mediante `titlepic`?
===
> [!important] Respuesta
> Se cargan `titlepic` y `graphicx`, se declara `\titlepic{\includegraphics[opciones]{archivo}}` antes de `\maketitle` y se aporta la imagen.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - composicion
---
> [!note] Pregunta
> ¿Está disponible `\institute` por defecto en `article` y `report`?
===
> [!important] Respuesta
> No. Puede integrarse la institución en los datos de autor o componerse una portada propia; `\institute` pertenece a clases como `beamer`.
```

### Paginación

> [!definicion] Esquema de paginación
> Regla que determina cómo se representa el contador de página: `arabic`, `roman`, `Roman`, `alph` o `Alph`, mediante `\pagenumbering{...}`.[^pagina]

Una pauta para preliminares y cuerpo es `\pagenumbering{roman}` antes de los índices y, después de `\clearpage`, `\pagenumbering{arabic}` para iniciar el cuerpo. Esa orden reinicia el contador; `\setcounter{page}{n}` permite fijarlo explícitamente. `\thispagestyle{empty}` oculta encabezados y pies de la página actual, incluido el número impreso, sin eliminar la página del documento.[^pagina]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - composicion
---
> [!note] Pregunta
> ¿Qué cambia `\pagenumbering{roman}` en un documento LaTeX?
===
> [!important] Respuesta
> Selecciona números romanos minúsculos y reinicia el contador de página. `arabic`, `Roman`, `alph` y `Alph` seleccionan otros esquemas.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - composicion
---
> [!note] Pregunta
> ¿Cómo se fija un valor concreto del contador de página en LaTeX?
===
> [!important] Respuesta
> Con `\setcounter{page}{n}`, donde $n$ es el valor deseado.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - composicion
---
> [!note] Pregunta
> ¿Qué efecto tiene `\thispagestyle{empty}` sobre la página actual en LaTeX?
===
> [!important] Respuesta
> Oculta sus encabezados y pies, incluido el número impreso, sin eliminar la página ni dejar de contarla.
```

### Encabezado y pie con fancyhdr

> [!definicion] Encabezado y pie personalizados
> Zonas repetidas de página cuya composición puede configurarse con `fancyhdr` en posiciones izquierda, central y derecha.[^pagina]

```latex
% Preámbulo
\usepackage{fancyhdr}
\pagestyle{fancy}
\fancyhf{}
\lhead{Produção de Relatórios}
\chead{}
\rhead{Medição}
\lfoot{}
\cfoot{}
\rfoot{Página \thepage}
\renewcommand{\headrulewidth}{0pt}
\renewcommand{\footrulewidth}{.4pt}
```

`\fancyhf{}` borra los campos previos. Las seis órdenes declaran cada zona y `\thepage` recupera el número actual. Las páginas de apertura de capítulos pueden usar un estilo diferente del ordinario; el PDF permite comprobar qué páginas reciben la configuración.[^pagina]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - composicion
---
> [!note] Pregunta
> ¿Por qué se revisan por separado las páginas de apertura de capítulo al configurar `fancyhdr`?
===
> [!important] Respuesta
> Porque pueden utilizar un estilo de página distinto del ordinario y no recibir automáticamente la misma configuración.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - composicion
---
> [!note] Pregunta
> ¿Qué zonas permite personalizar `fancyhdr` en una página LaTeX?
===
> [!important] Respuesta
> Izquierda, centro y derecha del encabezado y del pie, con `\lhead`, `\chead`, `\rhead`, `\lfoot`, `\cfoot` y `\rfoot`.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - composicion
---
> [!note] Pregunta
> ¿Cómo se sustituye una paginación previa por un pie derecho «Página n» con `fancyhdr`?
===
> [!important] Respuesta
> Se limpian los campos con `\fancyhf{}` y se declara `\rfoot{Página \thepage}`; `\thepage` recupera el número actual.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - composicion
---
> [!note] Pregunta
> ¿Cómo se controlan las líneas del encabezado y del pie con `fancyhdr`?
===
> [!important] Respuesta
> Redefiniendo `\headrulewidth` y `\footrulewidth` con un grosor; `0pt` suprime la línea correspondiente.
```

### Márgenes con geometry

> [!definicion] Geometría de página
> Distribución del área de texto y sus márgenes, configurada mediante `geometry`.[^pagina]

```latex
\usepackage[a4paper,left=3cm,right=2.5cm,
            top=2.5cm,bottom=2cm]{geometry}
```

Las dimensiones anteriores reproducen un ejemplo del capítulo II; no se presentan como norma universal de FCUL. Una entrega concreta puede fijar otros márgenes. Modificarlos cambia anchuras de línea, saltos y posición de flotantes; por eso la revisión se realiza sobre el documento completo.

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - composicion
---
> [!note] Pregunta
> ¿Cómo se declaran los cuatro márgenes mediante `geometry` en LaTeX?
===
> [!important] Respuesta
> Con las opciones `left`, `right`, `top` y `bottom`, cada una con su longitud, al cargar o configurar `geometry`.
```

### input

> [!definicion] Inserción con input
> Incorporación del contenido de otro fuente mediante `\input{ruta}`, sin imponer un cambio de página.[^archivos]

Una sección breve o un resumen pueden integrarse en el flujo del documento principal. La inserción conserva el contexto de numeración y configuración del lugar donde se realiza.

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - composicion
---
> [!note] Pregunta
> ¿Cómo incorpora `\input{ruta}` otro fuente en un documento LaTeX?
===
> [!important] Respuesta
> Inserta su contenido en el contexto actual sin imponer un cambio de página.
```

### include

> [!definicion] Inclusión con include
> Incorporación de una parte mediante `\include{ruta}`, con límites de página y gestión de información auxiliar propia de esa parte.[^archivos]

Esta separación resulta útil para capítulos de un informe extenso. El documento principal reúne la secuencia y los archivos aportan sus contenidos:

```latex
% Dentro del cuerpo del documento principal
\input{tex/resumo}
\tableofcontents
\include{tex/introducao}
\include{tex/resultados}
\include{tex/conclusao}
```

El documento principal conserva clase, paquetes y cuerpo general; los archivos incluidos contienen las partes correspondientes. Se compila el principal para que las etiquetas y la numeración compartan contexto. Los nombres deben corresponder a los archivos existentes; repartir el trabajo no elimina sus dependencias.

Por ejemplo, `tex/introducao.tex` puede comenzar con `\chapter{Introdução}` y contener sus secciones, sin repetir `\documentclass` ni otro `\begin{document}`. El documento principal proporciona ese marco común.[^archivos]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - composicion
---
> [!note] Pregunta
> ¿Qué aporta `\include` al incorporar una parte de un documento LaTeX?
===
> [!important] Respuesta
> Incorpora el fuente con límites de página y gestión auxiliar de esa parte, útil para capítulos de un proyecto extenso.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - composicion
---
> [!note] Pregunta
> ¿Qué archivo se compila en un proyecto LaTeX dividido mediante `\input` o `\include`?
===
> [!important] Respuesta
> El documento principal, que proporciona la clase, los paquetes y el contexto común de numeración y referencias.
```

## Aplicación — Componer y comprobar el informe Zuloc

El enunciado del laboratorio Zuloc reúne composición y análisis: exige un informe con portada, índices, introducción, caso de estudio, conclusión y bibliografía. Los índices de contenido, tablas y figuras son automáticos; cada tabla y gráfico lleva leyenda de LaTeX y debe poder identificarse desde la prosa.[^zuloc]

### Formato y estructura exigidos

La portada incluye nombre completo, número de alumno, título, licenciatura, turma e imagen alusiva. Queda sin paginación impresa, encabezado ni pie; los índices usan romanos y las páginas restantes, arábigos. El tamaño base es 12 puntos y los márgenes son 1,7 cm arriba y abajo, 1,6 cm a izquierda y derecha. Estas medidas pertenecen a este enunciado concreto.[^zuloc]

```latex
% Preámbulo de un documento de 12 puntos
\usepackage[a4paper,top=1.7cm,bottom=1.7cm,
            left=1.6cm,right=1.6cm]{geometry}
% Tras la portada y antes de los índices
\pagenumbering{roman}
\tableofcontents
\listoftables
\listoffigures
\clearpage
\pagenumbering{arabic}
```

La introducción pide investigar cambios de hábitos de consumo, incorporar una cita y comparar en dos columnas cómo se actuaba y cómo se actuará. Los ejemplos personales deben corresponder a la experiencia o intención real de su autor. El caso de estudio comienza con una introducción de hasta cinco líneas que incluya sus parámetros de capacidad individual y número de trabajadores.[^zuloc]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - latex
  - composicion
---
> [!note] Pregunta
> ¿Qué distingue la paginación de portada, índices y cuerpo en el informe Zuloc?
===
> [!important] Respuesta
> La portada no muestra número, encabezado ni pie; los índices usan numeración romana y el cuerpo arábiga. Los índices se generan automáticamente.
```

### Capacidad individual y capacidad de la plantilla

El caso simula la producción de embalajes reciclados. Un kilogramo de plástico permite obtener ocho embalajes; la unidad de cálculo de pedidos y producción es el embalaje, no el kilogramo.[^zuloc]

> [!definicion] Capacidad individual
> Número máximo de embalajes que produce un trabajador en un día, denotado por $q$. El enunciado fija $q=50+s$, donde $s$ es la suma de los dígitos del número de alumno.[^zuloc]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - informes
  - simulacion
---
> [!note] Pregunta
> ¿Cómo se obtiene la capacidad individual diaria $q$ en el caso Zuloc?
===
> [!important] Respuesta
> Se suma 50 a la suma de los dígitos del número de alumno. Su unidad es embalajes por trabajador y día.
```

### Número inicial de trabajadores

> [!definicion] Plantilla inicial de Zuloc
> Número $n$ de trabajadores fijado como el producto de tres dígitos no nulos del número de alumno.[^zuloc]

Si existen más de tres dígitos no nulos y su elección cambia el producto, el enunciado no especifica cómo seleccionarlos. Los parámetros personales deben quedar explícitos antes de calcular.

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - informes
  - simulacion
---
> [!note] Pregunta
> ¿Cómo fija el enunciado Zuloc el número inicial de trabajadores?
===
> [!important] Respuesta
> Como el producto de tres dígitos no nulos del número de alumno; si hay más de tres candidatos, la elección debe quedar aclarada porque puede cambiar el resultado.
```



### Capacidad diaria de la plantilla

> [!definicion] Capacidad diaria de la plantilla
> Máximo de embalajes que puede producir el conjunto de $n$ trabajadores durante un día:
> $$
> C=nq.
> $$
> Con $n$ y $q$ constantes, $C$ es constante y se expresa en embalajes por día.[^zuloc]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - informes
  - simulacion
---
> [!note] Pregunta
> ¿Cómo se calcula la capacidad diaria de la plantilla en el modelo Zuloc?
===
> [!important] Respuesta
> $C=nq$, con $n$ trabajadores y capacidad individual $q$. Permanece constante si esos parámetros no cambian.
```

### Pedidos y selección por intervalos

#### Probabilidad acumulada

> [!definicion] Probabilidad acumulada
> Para valores de demanda ordenados, suma de las probabilidades de todos los valores hasta el considerado. Establece los umbrales sucesivos de la selección por intervalos.[^zuloc]

Por ejemplo, las probabilidades 9 %, 14 % y 21 % producen acumuladas de 9 %, 23 % y 44 %. La probabilidad de un intervalo se recupera restando sus umbrales consecutivos.

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - informes
  - simulacion
---
> [!note] Pregunta
> ¿Cómo se obtienen los umbrales acumulados para simular una demanda discreta?
===
> [!important] Respuesta
> Sumando sucesivamente las probabilidades de los valores ordenados; la diferencia entre umbrales consecutivos es la probabilidad del intervalo.
```

#### Demanda diaria

> [!definicion] Demanda diaria
> Número de embalajes pedidos durante el día $t$, representado por $D_t$. El enunciado establece seis valores posibles y sus probabilidades.[^zuloc]

Una variable aleatoria uniforme $U_t$ permite asignar cada valor mediante probabilidades acumuladas. Adoptando $U_t\in[0,1]$, las pruebas sucesivas «menor o igual» del enunciado corresponden a estos intervalos:

| Intervalo de $U_t$ | $D_t$, embalajes | Probabilidad |
|---|---:|---:|
| $0\le U_t\le0{,}09$ | 5000 | 9 % |
| $0{,}09<U_t\le0{,}23$ | 5500 | 14 % |
| $0{,}23<U_t\le0{,}44$ | 6000 | 21 % |
| $0{,}44<U_t\le0{,}70$ | 6500 | 26 % |
| $0{,}70<U_t\le0{,}89$ | 7000 | 19 % |
| $0{,}89<U_t\le1$ | 7500 | 11 % |

Las probabilidades suman 100 %. Cada intervalo tiene longitud igual a la probabilidad asignada y los intervalos cubren $[0,1]$ sin solaparse. Por ejemplo, $U_t=0{,}09$ produce 5000. Cambiar la inclusión de los extremos no cambia las probabilidades de una uniforme continua, pero puede cambiar los resultados de una lista de números redondeados; se conserva la convención docente.[^zuloc]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - informes
  - simulacion
---
> [!note] Pregunta
> ¿Qué representa $D_t$ en la simulación Zuloc?
===
> [!important] Respuesta
> Los embalajes pedidos durante el día $t$, seleccionados entre los seis valores posibles con las probabilidades del enunciado.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - informes
  - simulacion
---
> [!note] Pregunta
> ¿Cómo se transforma un uniforme $U_t$ en una demanda discreta con probabilidades dadas?
===
> [!important] Respuesta
> Se divide el intervalo de la uniforme en tramos consecutivos cuyas longitudes son las probabilidades y se asigna a cada tramo su demanda; las fronteras siguen una convención explícita.
```

### Carga pendiente, producción y atraso

#### Carga por atender

El modelo conserva pedidos sin atender de un día al siguiente y no produce existencias por encima de los pedidos disponibles. Se fija inicialmente $B_0=0$.[^zuloc]

> [!definicion] Carga por atender
> Total disponible para producir en el día $t$, formado por pedidos nuevos y atraso anterior:[^zuloc]
> $$
> W_t=D_t+B_{t-1}.
> $$

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - informes
  - simulacion
---
> [!note] Pregunta
> ¿Cómo se obtiene la carga por atender $W_t$ en el modelo Zuloc?
===
> [!important] Respuesta
> $W_t=D_t+B_{t-1}$: pedidos nuevos del día más atraso del día anterior, con $B_0=0$ inicialmente.
```

#### Producción efectiva

> [!definicion] Producción efectiva
> Cantidad que puede atenderse sin superar la capacidad ni los pedidos disponibles:[^zuloc]
> $$
> Y_t=\min(W_t,C).
> $$

Así se cumplen simultáneamente $0\le Y_t\le C$ y $Y_t\le W_t$. Elegir el máximo violaría una de esas restricciones cuando capacidad y carga fueran distintas.

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - informes
  - simulacion
---
> [!note] Pregunta
> ¿Por qué la producción diaria de Zuloc es $Y_t=\min(W_t,C)$?
===
> [!important] Respuesta
> Porque no puede superar ni la carga por atender ni la capacidad diaria; el mínimo satisface ambas restricciones.
```

#### Atraso al final del día

> [!definicion] Atraso al final del día
> Pedidos que quedan sin producir después de atender la carga diaria:
> $$
> B_t=W_t-Y_t\ge0.
> $$
> Este valor pasa a formar parte de la carga del día siguiente.[^zuloc]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - informes
  - simulacion
---
> [!note] Pregunta
> ¿Cómo se calcula y se transmite el atraso en la simulación Zuloc?
===
> [!important] Respuesta
> $B_t=W_t-Y_t$, siempre no negativo; se suma a la nueva demanda al calcular la carga del día siguiente.
```

### Ocupación y comparación de plantillas

> [!definicion] Porcentaje de ocupación
> Parte de la capacidad diaria utilizada efectivamente, para $C>0$:
> $$
> O_t=100\frac{Y_t}{C}\,\%.
> $$
> Su valor queda entre 0 y 100 %.[^zuloc]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - informes
  - simulacion
---
> [!note] Pregunta
> ¿Cómo se calcula el porcentaje de ocupación de la plantilla en el modelo Zuloc?
===
> [!important] Respuesta
> $100Y_t/C$ por ciento, con $C>0$; compara producción efectiva y capacidad, y queda entre 0 y 100 %.
```

#### Ejemplo — Un atraso que se absorbe al día siguiente

**Tarea.** Comprobar dos días ilustrativos con $q=70$, $n=100$, pedidos de 7500 y 6500 embalajes y atraso inicial cero. Los parámetros son didácticos y no sustituyen los personales de una entrega.

La capacidad es $C=100\cdot70=7000$ embalajes diarios. El primer día se produce $\min(7500,7000)=7000$ y quedan 500 pendientes, con ocupación 100 %. El segundo día la carga es $6500+500=7000$: se atiende completa y el atraso vuelve a cero. En ambos días se verifica $Y_t+B_t=W_t$, que expresa la conservación de pedidos.[^zuloc]

La tabla de ocho columnas permite comprobar el recorrido completo de los dos días. Los aleatorios 0,95 y 0,50 son ilustrativos y generan los pedidos usados:

| Día | Nº aleatorio | Pedidos recibidos $D_t$ | Pedidos por producir $W_t$ | Capacidad diaria $C$ | Producidos $Y_t$ | Atraso $B_t$ | Ocupación |
|---:|---:|---:|---:|---:|---:|---:|---:|
| 1 | 0,95 | 7500 | 7500 | 7000 | 7000 | 500 | 100 % |
| 2 | 0,50 | 6500 | 7000 | 7000 | 7000 | 0 | 100 % |

La salida de A requiere la tabla y un gráfico de columnas. Las leyendas identifican cada representación y las referencias permiten relacionarlas con la interpretación. Para B se duplica la hoja, se denomina B, se sustituyen los aleatorios por la serie del Word y se ajusta el número de trabajadores; se prepara una introducción de hasta cinco líneas y se incorporan su tabla y gráfico de columnas. La falta de esa serie impide calcular aquí una versión B determinada.[^zuloc]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - informes
  - simulacion
---
> [!note] Pregunta
> ¿Qué pasos distinguen la preparación de B en el trabajo Zuloc?
===
> [!important] Respuesta
> Duplicar la hoja como B, sustituir sus aleatorios por la serie proporcionada, ajustar la plantilla y presentar la introducción, tabla y gráfico de columnas correspondientes.
```

El enunciado exige comparar el número elegido de trabajadores con $n-1$ y $n+1$, aportando resultados numéricos. Mantener la misma secuencia de pedidos permite atribuir las diferencias al cambio de capacidad. Sin costes y sin un umbral de servicio especificados, esos resultados no determinan un óptimo económico único.[^zuloc]

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - informes
  - simulacion
---
> [!note] Pregunta
> ¿Por qué comparar producción, atraso y ocupación no determina por sí solo una plantilla económicamente óptima?
===
> [!important] Respuesta
> Porque faltan criterios para valorar el coste de los trabajadores y del atraso o un umbral de servicio; los resultados describen compromisos, pero no fijan una elección única.
```

```anki
deck: Física::Produção de Relatórios::LaTeX
tags:
  - informes
  - simulacion
---
> [!note] Pregunta
> ¿Por qué conviene conservar los mismos pedidos al comparar $n-1$, $n$ y $n+1$ trabajadores en Zuloc?
===
> [!important] Respuesta
> Para que la comparación refleje el cambio de capacidad y no una demanda aleatoria diferente; se justifican las conclusiones con producción, atraso y ocupación numéricos.
```

### Límites del enunciado y de los datos disponibles

La tabla exige días 1–31 y la instrucción del gráfico menciona 30 días: ambos horizontes aparecen en el documento y son incompatibles si se supone una única serie completa. La parte B puede omitirse bajo una condición de corrección de A, pero la presentación exige tabla y gráfico de B. Además, no se ha aportado el Word que contiene sus números aleatorios. Estas condiciones impiden reconstruir una entrega B única a partir del material disponible.[^zuloc]

Las afirmaciones ambientales utilizadas para justificar el proyecto necesitan fuentes propias y actuales; los valores del ejercicio se distinguen de los datos empíricos que se afirmen sobre el mundo. La [[Física/Grado/1º/Produção de Relatórios/04 Búsqueda bibliográfica y referencias|búsqueda y atribución de fuentes]] permite sostener ese contexto.

## Práctica con soluciones razonadas

#### Ejercicio 1 — Un índice vacío

> [!ejemplo] Enunciado
> El PDF contiene títulos escritos en negrita y `\tableofcontents` está vacío. ¿Qué cambio debe hacerse y por qué puede necesitar otra compilación?

> [!resolucion]- Resolución
> Se sustituyen los títulos manuales por `\section` o el nivel apropiado. La compilación registra entradas auxiliares y otra pasada las lee. El error frecuente consiste en rellenar el índice a mano: los cambios de estructura o páginas dejan entonces referencias obsoletas.

#### Ejercicio 2 — Reparar una referencia de tabla

> [!ejemplo] Enunciado
> Una tabla tiene `\label{tab:datos}` antes de `\caption{Dados}` y la referencia devuelve otro número. Describe la reparación y la comprobación.

> [!resolucion]- Resolución
> Se coloca la etiqueta después de la leyenda para capturar el contador correcto. Se comprueba que la clave es única y coincide con `\ref`, se recompila y se compara la mención con la leyenda del PDF. Si persiste «??», el registro permite distinguir una clave ausente de una actualización pendiente.

#### Ejercicio 3 — Elegir entorno matemático

> [!ejemplo] Enunciado
> Escoge un entorno para una suma demasiado larga, una derivación con un solo número, tres ecuaciones alineadas y una función definida por condiciones. Justifica cada elección.

> [!resolucion]- Resolución
> `multline` parte una expresión sin punto común; `equation` con `split` conserva una derivación y un número; `align` ofrece filas alineadas con numeración independiente; `cases`, dentro de un modo matemático, relaciona expresiones y condiciones. Las condiciones de validez incluyen que la función por tramos tenga un dominio declarado y condiciones coherentes.

#### Ejercicio 4 — Transferir la tabla de la ficha

> [!ejemplo] Enunciado
> Partiendo del ejemplo de suricatas, explica cómo mantener el contenido si una columna desborda y cómo conservar la referencia al mover la tabla a otro capítulo.

> [!resolucion]- Resolución
> Se decide una anchura de párrafo `p{...}` o se usa `tabularx` para redistribuir texto; se revisan legibilidad y unidades antes de reducir toda la tabla. Se conserva la clave `tab:suricatas` y se cita con `\ref`; al moverla cambia su número, no la identidad de la etiqueta. Las compilaciones actualizan la referencia y el índice de tablas.

La estructura y las referencias cruzadas mantienen coherente el interior del informe. La [[Física/Grado/1º/Produção de Relatórios/04 Búsqueda bibliográfica y referencias|gestión bibliográfica]] resuelve la otra relación imprescindible: que cada afirmación apoyada en trabajos ajenos permita recuperar su fuente.

## 📚 Fuentes

### Material base aportado

[^cruzadas]: Eugénia Graça — *Resumo de LaTeX*, julio de 2025, archivo `PR - Resumo - 2025 - 2026.pdf`, pp. físicas 33–34 (impresas 25–26); *Capítulo II — Modo Texto*, julio de 2026, archivo `cap2 - PR -2026-2027.pdf`, pp. físicas 62–63, diapositivas 60–61. Leyendas, etiquetas y referencias. El capítulo II contiene 101 páginas físicas y 99 diapositivas numeradas, por dos repeticiones de contenido.
[^tablas]: Mismos materiales: resumen portugués, pp. físicas 24–35 (impresas 16–27); capítulo II, pp. físicas 46–66. Tablas, celdas, espacios, exportación y escala. Las erratas de `multicolumn` y `tabcolsep` se corrigen junto a sus procedimientos.
[^figuras]: Resumen portugués, pp. físicas 35–39 (impresas 27–31); capítulo II, pp. físicas 67–71. Gráficos, escala y subfiguras. El resumen inglés se consulta como contraste.
[^bloques]: Resumen portugués, pp. físicas 40–41 (impresas 32–33); capítulo II, pp. físicas 72–77. Verbatim, quote y minipage.
[^columnas]: Resumen portugués, pp. físicas 18–19 (impresas 10–11); capítulo II, pp. físicas 26–27. Dos y tres columnas de texto.
[^ecuaciones]: Eugénia Graça — *Resumo de LaTeX*, pp. físicas 59–65 (impresas 51–57), y *Capítulo III — Modo Matemático*, portada de julio de 2024, pp. físicas 18–32, diapositivas 17–30. Ecuaciones y sistemas. Se corrige el uso de varias líneas dentro de `equation` sin una estructura interior y la condición aislada «5». El capítulo III está identificado como `cap 3- PR 2021-2022 reduzido.pdf`; el año se toma de la portada.
[^matrices]: Eugénia Graça — *Resumo de LaTeX*, pp. físicas 65–67 (impresas 57–59), y capítulo III, pp. físicas 33–38, diapositivas 31–36; AMS, manual citado en la ampliación externa, §4.1. Matrices y puntos de continuación; índices finales ajustados a las dimensiones declaradas y variante `matrix` sin delimitadores.
[^indices]: Resumen portugués, p. física 42 (impresa 34); capítulo II, pp. físicas 87–88. Índices de contenido y objetos.
[^remisivo]: Resumen portugués, p. física 43 (impresa 35). Índice remisivo y archivos del proceso.
[^pagina]: Resumen portugués, pp. físicas 43–46 (impresas 35–38); capítulo II, pp. físicas 79–86. Portada, paginación, márgenes y fancyhdr.
[^archivos]: Resumen portugués, pp. físicas 47–48 (impresas 39–40); capítulo II, pp. físicas 93–94. División en archivos.
[^ficha]: Ficha 2 — Modo Texto, pp. físicas 2–3. Tabla de cuatro columnas y cuatro filas, encabezado gris, bordes, centrado, leyenda inferior y referencia. Se utiliza su enunciado; la hoja de resultado no fue aportada.
[^zuloc]: FCUL — *Enunciado do Trabalho — Laboratório Zuloc*, archivo `enunciado PR moodle.pdf`, 9 páginas físicas. P. 1: estructura, márgenes, tamaño y paginación; pp. 2–3: portada e introducción; pp. 4–7: parámetros, probabilidades, recurrencias y comparación; pp. 8–9: presentación. Las contradicciones entre 31 y 30 días y entre la omisión condicional y las diapositivas exigidas para B se conservan como límites del enunciado. Los ejemplos numéricos son ilustrativos y no reconstruyen datos personales ni la serie B ausente.

### Ampliación externa

[^tablasexterna]: LearnLaTeX — [Tables](https://www.learnlatex.org/en/lesson-08). Anchuras de párrafo y unión de celdas; [Cross-referencing](https://www.learnlatex.org/en/lesson-09) y [Structuring longer documents](https://www.learnlatex.org/en/lesson-13), contraste de automatización.
[^ams]: American Mathematical Society y LaTeX Project — [User’s Guide for the amsmath Package](https://ctan.math.illinois.edu/macros/latex/required/amsmath/amsldoc.pdf), §§3–4. Contraste para alineación, numeración, matrices y sustitución de `eqnarray`; `flalign` se incorpora como ampliación funcional.
[^adjustbox]: Martin Scharrer — [The adjustbox Package](https://ctan.math.illinois.edu/macros/latex/contrib/adjustbox/adjustbox.pdf), versión 1.3c, §4.3, p. 17. Diferencia entre fijar una anchura y limitar la anchura máxima sin ampliar un contenido que ya cumple el límite.
[^unidades]: LaTeX2e reference manual — [Units of length](https://latexref.xyz/Units-of-length.html). Unidades relativas a la fuente actual, especialmente `em`, y alcance de su asociación histórica con la anchura de M.

## 🧑‍🏫 Prompt para tutor conversacional

Tutoriza a nivel universitario introductorio con una pregunta cada vez, espera y ofrece pistas antes de resolver.

Examina función lógica frente a formato: section crea estructura; textbf cambia aspecto. Caption fija número, label guarda identidad, ref recupera número y pageref página; label va después de caption.

Figure/table son flotantes, y h/t/b/p/! expresan preferencias.

Tabular construye filas y columnas con &, doble barra y l/c/r/p; table aporta flotación y leyenda. Tabularx con X ajusta anchura; multicolumn une columnas sin multicol; multirow une filas y exige dejar celdas ocupadas vacías; arraystretch escala separación vertical y tabcolsep se modifica con setlength.

Graphicx incorpora PDF/PNG/JPEG; subcaption dispone paneles. Minipage crea cajas; quote compone citas y verbatim muestra literal. Multicols distribuye prosa.

Con amsmath, equation da un número, split parte una derivación dentro de equation, multline parte una expresión sin alineación, gather agrupa sin alinear, align alinea filas, flalign extiende horizontalmente, array y cases organizan condiciones; pmatrix/bmatrix/Bmatrix/vmatrix/Vmatrix eligen delimitador, no significado.

Tableofcontents recoge secciones, listoffigures y listoftables leyendas; el índice remisivo usa makeidx, makeindex, index y printindex, con idx→ind e ilg de registro.

Maketitle compone portada; pagenumbering elige esquema y reinicia contador, thispagestyle oculta campos; fancyhdr configura seis zonas y geometry márgenes. Input inserta y include añade límites de página.

Como aplicación, el informe Zuloc exige portada, índices automáticos, introducción, caso, conclusión y bibliografía, con 12 puntos y márgenes de 1,7 cm verticales y 1,6 cm horizontales. La portada queda sin número, encabezado ni pie; índices romanos y cuerpo arábigo. La introducción contrasta hábitos propios en columnas e incorpora una cita.

En la simulación, $q=50+$ suma de dígitos del número de alumno; $n$ es el producto de tres dígitos no nulos y $C=nq$. Los pedidos $D_t$ toman 5000, 5500, 6000, 6500, 7000 o 7500 con probabilidades 9, 14, 21, 26, 19 y 11 %. Con $B_0=0$, carga $W_t=D_t+B_{t-1}$, producción $Y_t=\min(W_t,C)$, atraso $B_t=W_t-Y_t$ y ocupación $100Y_t/C$ por ciento, para $C>0$. Comprueba que producción y atraso conservan la carga. Compara $n-1,n,n+1$ con los mismos pedidos y resultados numéricos. No inventes parámetros personales ni la serie B ausente; identifica las contradicciones 31/30 días y omisión de B frente a diapositivas obligatorias de B.

Propón reparar un índice vacío, una etiqueta adelantada y una tabla que desborda. Haz justificar numeración y condiciones de una función por tramos. Adapta dificultad con recuperación activa, repetición espaciada y transferencia; continúa con bibliografía.

```dataviewjs
await dv.view("Planes/Estudio/Scripts/study-session", { location: "end" })
```
