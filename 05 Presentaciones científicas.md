---
title: Presentaciones científicas
asignatura: Produção de Relatórios
rama:
  - Comunicación científica
tipo:
  - procedimiento
  - teoría
nivel: universitario-introductorio
estado: revisado
capa: curricular
requiere:
  - "[[Física/Grado/1º/Produção de Relatórios/01 Informes y escritura científica|Informes y escritura científica]]"
  - "[[Física/Grado/1º/Produção de Relatórios/02 LaTeX, entorno y fundamentos|LaTeX, entorno y fundamentos]]"
fsrs_goal: Convierte un argumento científico en una secuencia oral con evidencia legible y fuentes, construye sus marcos Beamer y diagnostica cuándo usar fragile o dividir el contenido en varias diapositivas.
tags:
  - fisica
  - presentaciones
  - comunicacion-cientifica
  - fcul
  - curricular
---

```dataviewjs
await dv.view("Planes/Estudio/Scripts/study-session", { location: "start" })
```

# Presentaciones científicas

En una exposición oral, el público necesita seguir una secuencia sin detenerse a releer páginas. Las diapositivas seleccionan la evidencia que debe verse mientras la voz construye el argumento. El problema comunicativo precede a la herramienta: Beamer puede componer un marco correctamente aunque su título, su densidad o sus datos dificulten entender el resultado.[^harvard][^docente]

## Del informe a una secuencia oral

### Presentación científica

> [!definicion] Presentación científica
> Exposición planificada de una pregunta, un procedimiento, una evidencia y su interpretación para un público y un tiempo determinados, con apoyo visual que facilite comprender y evaluar el argumento.[^harvard]

El recorrido puede organizarse como problema → método indispensable → evidencia → interpretación → límite. Se elige qué necesita el público para comprender la conclusión. Un informe conserva detalles para consulta; la presentación hace visible el recorrido que debe poder seguirse durante la exposición.

```anki
deck: Física::Produção de Relatórios::Presentaciones
tags:
  - presentaciones
  - comunicacion-cientifica
---
> [!note] Pregunta
> ¿Qué organiza una presentación científica para un público y un tiempo determinados?
===
> [!important] Respuesta
> Una pregunta, el procedimiento necesario, la evidencia y su interpretación, con apoyo visual que permita seguir y evaluar el argumento.
```

### Afirmación y evidencia

> [!definicion] Estructura de afirmación y evidencia
> Diseño en el que un título expresa la idea central del marco y el contenido visual aporta la evidencia que permite examinarla.[^cmu]

«Resultados» nombra una categoría, pero no señala qué resultado importa. «El período medido aumenta entre las condiciones comparadas» dirige la atención hacia una relación concreta, siempre que los datos y su análisis la sostengan. El título no debe afirmar causalidad, exactitud o universalidad si el trabajo sólo ha establecido una comparación limitada.

```anki
deck: Física::Produção de Relatórios::Presentaciones
tags:
  - presentaciones
  - comunicacion-cientifica
---
> [!note] Pregunta
> ¿Qué limita la fuerza de la afirmación escrita en el título de una diapositiva científica?
===
> [!important] Respuesta
> El alcance de la evidencia y de su análisis: una comparación limitada no permite afirmar causalidad, exactitud o universalidad.
```

```anki
deck: Física::Produção de Relatórios::Presentaciones
tags:
  - presentaciones
  - comunicacion-cientifica
---
> [!note] Pregunta
> ¿Cómo se relacionan título y contenido visual en una estructura de afirmación y evidencia?
===
> [!important] Respuesta
> El título formula la idea central defendible y la representación aporta la evidencia con la que el público puede examinarla.
```

#### Ejemplo — Transformar veinte medidas en apoyo visual

La tarea es comunicar una tendencia durante una intervención breve. Una tabla de veinte filas conserva los valores, pero obliga a buscarlos uno a uno. Si la conclusión depende de una relación entre variables, una gráfica con ejes y unidades permite inspeccionar esa pauta; si depende de un valor preciso, puede bastar destacar ese valor y su incertidumbre.

La tabla completa permanece disponible en el informe. La exposición explica las condiciones de medida y cómo se obtuvo el resultado mostrado. La transformación conserva el contenido necesario para evaluar la afirmación, en lugar de transferir al público toda la tarea de análisis.[^cmu][^harvard]

```anki
deck: Física::Produção de Relatórios::Presentaciones
tags:
  - presentaciones
  - comunicacion-cientifica
---
> [!note] Pregunta
> ¿Qué orienta elegir entre una gráfica y un valor destacado en una diapositiva científica?
===
> [!important] Respuesta
> La evidencia necesaria para la conclusión: una relación entre variables favorece una gráfica; una decisión sobre un valor preciso puede requerir destacarlo con su incertidumbre.
```

### Jerarquía visual

> [!definicion] Jerarquía visual
> Organización de tamaño, posición, contraste y etiquetas que establece el orden de lectura de una diapositiva y la relación entre sus elementos.[^harvard]

El lector debe identificar título, evidencia y atribución. Se mantiene una apariencia coherente y se comprueba la legibilidad a distancia. Las gráficas conservan nombres de magnitudes, unidades y significado de símbolos. Un efecto visual tiene función si explica una secuencia o una comparación; el exceso de texto y adornos compite con la explicación oral.[^harvard]

```anki
deck: Física::Produção de Relatórios::Presentaciones
tags:
  - presentaciones
  - comunicacion-cientifica
---
> [!note] Pregunta
> ¿Qué se comprueba para que una gráfica sea interpretable durante una exposición oral?
===
> [!important] Respuesta
> Magnitudes, ejes, unidades, significado de símbolos y fuentes, además de contraste y legibilidad a la distancia de lectura del público.
```

```anki
deck: Física::Produção de Relatórios::Presentaciones
tags:
  - presentaciones
  - comunicacion-cientifica
---
> [!note] Pregunta
> ¿Qué establece la jerarquía visual de una diapositiva?
===
> [!important] Respuesta
> El orden de lectura y la relación entre sus elementos mediante tamaño, posición, contraste y etiquetas, para reconocer título, evidencia y atribución.
```

```anki
deck: Física::Produção de Relatórios::Presentaciones
tags:
  - presentaciones
  - comunicacion-cientifica
---
> [!note] Pregunta
> ¿Qué debe aportar una diapositiva científica además de repetir lo que dice el ponente?
===
> [!important] Respuesta
> Evidencia o una relación visual que ayude a comprender y evaluar el mensaje oral, con etiquetas y fuentes legibles.
```

## Tiempo, público y atribución

### Guion y ensayo

> [!definicion] Guion de exposición
> Secuencia de mensajes y transiciones que organiza qué debe comprender el público y cómo se llega a la conclusión.[^harvard]

El ensayo comprueba si la cantidad de contenido corresponde al tiempo. Se registra dónde una figura necesita más explicación o una transición exige contexto. Si sobra material, se prioriza la evidencia indispensable para la conclusión y se reserva el detalle para preguntas o apoyo complementario. El número de diapositivas por minuto sólo orienta; una ecuación que requiere interpretación y una portada no consumen la misma atención.

```anki
deck: Física::Produção de Relatórios::Presentaciones
tags:
  - presentaciones
  - comunicacion-cientifica
---
> [!note] Pregunta
> ¿Qué contiene un guion de exposición científica?
===
> [!important] Respuesta
> La secuencia de mensajes y transiciones que permite al público comprender cómo se llega desde la pregunta hasta la conclusión.
```

```anki
deck: Física::Produção de Relatórios::Presentaciones
tags:
  - presentaciones
  - comunicacion-cientifica
---
> [!note] Pregunta
> ¿Qué se comprueba durante el ensayo de una presentación?
===
> [!important] Respuesta
> Si el contenido cabe en el tiempo y si figuras y transiciones reciben la explicación necesaria; se prioriza la evidencia indispensable para la conclusión.
```

#### Ejemplo — Corregir una transición ausente

Después de presentar el montaje, aparece una gráfica con una variable transformada que aún no se ha definido. El público puede leer los ejes, pero desconoce por qué se eligieron. La reparación consiste en explicar la transformación y la pregunta que permite examinar antes de interpretar la tendencia. Añadir más cifras a la gráfica no resuelve ese salto del argumento.

### Fuentes en diapositivas

> [!definicion] Atribución visual
> Identificación legible del origen de los datos, imágenes o ideas empleados en una diapositiva, situada junto al elemento o en una posición que permita reconocer la relación.[^harvard]

La selección de una imagen mantiene la responsabilidad sobre su uso y procedencia. Una referencia abreviada puede acompañarla y una diapositiva de referencias proporcionar los datos completos. Se comprueba que el público pueda distinguir evidencia propia y material ajeno; los permisos y la integridad se desarrollan en [[Física/Grado/1º/Produção de Relatórios/06 Ética y uso académico de las TIC|ética y uso académico de las TIC]].

```anki
deck: Física::Produção de Relatórios::Presentaciones
tags:
  - presentaciones
  - comunicacion-cientifica
---
> [!note] Pregunta
> ¿Qué debe permitir reconocer la atribución visual de una diapositiva?
===
> [!important] Respuesta
> El origen de los datos, imágenes o ideas y su relación con el elemento mostrado, distinguiendo evidencia propia de material ajeno mediante referencias legibles.
```

## Estructura de una presentación Beamer

### Clase beamer

> [!definicion] Beamer
> Clase de LaTeX que proporciona estructuras de composición para presentaciones y permite reutilizar gran parte de los comandos de texto, listas, figuras, tablas y matemáticas.[^docente]

El documento conserva preámbulo y cuerpo. `\documentclass[11pt]{beamer}` selecciona la clase y un tamaño base, como en el resumen docente. Los paquetes que se cargan deben responder al contenido previsto, por ejemplo lengua o imágenes.

```anki
deck: Física::Produção de Relatórios::Presentaciones
tags:
  - latex
  - beamer
---
> [!note] Pregunta
> ¿Qué permite la clase `beamer` de LaTeX?
===
> [!important] Respuesta
> Componer presentaciones mediante marcos y reutilizar gran parte de las órdenes habituales de texto, listas, tablas, imágenes y matemáticas.
```

### Marco y diapositiva

> [!definicion] Frame o marco
> Unidad de contenido delimitada por `\begin{frame}` y `\end{frame}`. Puede producir una o varias diapositivas del PDF, según sus opciones y su forma de presentación.[^docente][^beamer]

Un marco simple produce normalmente una diapositiva. La opción `allowframebreaks`, desarrollada más abajo, puede repartirlo en varias. Por eso el número de entornos `frame` no determina siempre el número de páginas del PDF.

```anki
deck: Física::Produção de Relatórios::Presentaciones
tags:
  - latex
  - beamer
---
> [!note] Pregunta
> ¿Por qué un marco Beamer no equivale siempre a una diapositiva del PDF?
===
> [!important] Respuesta
> Porque `frame` delimita una unidad de contenido que, según sus opciones y presentación, puede generar varias páginas.
```

### Título de marco

> [!definicion] Título de marco
> Encabezado de una unidad de presentación, declarado mediante `\begin{frame}{Título}` o mediante `\frametitle{Título}` en su interior.[^docente]

El título declara una idea que organiza el contenido. La orden sólo fija la composición; el autor decide qué afirmación resulta pertinente y defendible.

```latex
\begin{frame}{Título no argumento}
  Conteúdo do primeiro marco.
\end{frame}
\begin{frame}
  \frametitle{Título declarado dentro do marco}
  Conteúdo do segundo marco.
\end{frame}
```

Ambas formas producen un encabezado del marco. En la segunda, la orden `\frametitle` permite localizar por separado la declaración del título y el contenido.[^docente]

```anki
deck: Física::Produção de Relatórios::Presentaciones
tags:
  - latex
  - beamer
---
> [!note] Pregunta
> ¿Cómo se declara el título de un marco Beamer?
===
> [!important] Respuesta
> Con `\begin{frame}{Título}` o con `\frametitle{Título}` dentro del marco.
```

```anki
deck: Física::Produção de Relatórios::Presentaciones
tags:
  - latex
  - beamer
---
> [!note] Pregunta
> ¿Qué función cumplen `\documentclass{beamer}` y `\begin{frame}...\end{frame}`?
===
> [!important] Respuesta
> La primera selecciona la clase para presentaciones; `frame` delimita una unidad de contenido que puede generar una o varias diapositivas.
```

### Portada y datos de autor

> [!definicion] Portada Beamer
> Marco que presenta los datos declarados con `\title`, `\author`, `\institute` y `\date`, mediante `\titlepage`.[^docente][^beamer]

Los datos se configuran en el preámbulo y se imprimen en un marco. `\institute` pertenece a Beamer y permite identificar la institución; esa disponibilidad no se traslada automáticamente a `article` o `report`.

```anki
deck: Física::Produção de Relatórios::Presentaciones
tags:
  - latex
  - beamer
---
> [!note] Pregunta
> ¿Cómo se compone una portada con datos de autor en Beamer?
===
> [!important] Respuesta
> Se declaran `\title`, `\author`, `\institute` y `\date`, y se coloca `\titlepage` dentro de un marco.
```

### Secciones e índice

> [!definicion] Sección de presentación
> División lógica de la secuencia creada con `\section{...}`. Puede recogerse en un marco con `\tableofcontents`.[^docente]

La sección organiza varios marcos; su título no constituye automáticamente una explicación oral ni una diapositiva propia. El índice anticipa las partes de una exposición suficientemente extensa como para necesitar esa orientación. Debe corresponder al recorrido real.

```anki
deck: Física::Produção de Relatórios::Presentaciones
tags:
  - latex
  - beamer
---
> [!note] Pregunta
> ¿Qué diferencia una sección de un marco en Beamer?
===
> [!important] Respuesta
> `\section` organiza lógicamente la secuencia y puede agrupar varios marcos; no crea por sí sola una diapositiva explicativa.
```

```anki
deck: Física::Produção de Relatórios::Presentaciones
tags:
  - latex
  - beamer
---
> [!note] Pregunta
> ¿Cómo se muestra el índice de secciones en una presentación Beamer?
===
> [!important] Respuesta
> Con `\tableofcontents` dentro de un marco, tras declarar las secciones pertinentes y recompilar para estabilizarlo.
```

#### Ejemplo — Presentación mínima completa

El objetivo es producir una portada, un índice y dos marcos con funciones diferentes. Los datos de la tabla son **ficticios** y sólo sirven para practicar composición y lectura; no describen un experimento real.

```latex
\documentclass[11pt]{beamer}
\usepackage[T1]{fontenc}
\usepackage[utf8]{inputenc}
\usepackage[portuguese]{babel}
\usetheme{CambridgeUS}
\usecolortheme{dolphin}
\title{Da pergunta ao resultado}
\author{Nome do autor}
\institute{Faculdade de Ciências}
\date{Outubro de 2026}
\begin{document}
\begin{frame}
  \titlepage
\end{frame}
\begin{frame}{Percurso da apresentação}
  \tableofcontents
\end{frame}
\section{Pergunta e método}
\begin{frame}{As repetições avaliam a dispersão das medidas}
  \begin{itemize}
    \item Mesma condição de medição.
    \item Registo de cada repetição.
    \item Comparação dos valores obtidos.
  \end{itemize}
\end{frame}
\section{Resultados}
\begin{frame}{Os valores fictícios variam entre 1,40 e 1,44 segundos}
  \centering
  \begin{tabular}{cc}
    Repetição & Período (s) \\
    1 & 1,40 \\
    2 & 1,44 \\
    3 & 1,42
  \end{tabular}

  \medskip
  \small Dados fictícios para praticar composição.
\end{frame}
\end{document}
```

La portada identifica; el índice orienta; el primer marco explica una decisión; el segundo muestra tres valores legibles. El PDF debe revisarse tras las compilaciones que estabilicen el índice. En un trabajo real, se sustituye la tabla ilustrativa por evidencia suficiente, y se añade su interpretación y conclusión.

## Apariencia y opciones de marcos

### Tema de presentación

> [!definicion] Tema Beamer
> Conjunto de decisiones de apariencia y navegación seleccionado mediante `\usetheme{nombre}`.[^docente]

El resumen ejemplifica `CambridgeUS` y enumera temas como `Madrid`, `Berlin`, `Berkeley`, `Warsaw`, `Singapore` y `Copenhagen`. El nombre debe corresponder a un tema instalado y distinguir mayúsculas. Cambiar el tema conserva las secciones y el contenido, pero puede modificar el espacio útil y la navegación; se revisan los marcos afectados.

El capítulo de presentaciones recoge este catálogo. Se conservan sus nombres válidos y se corrigen «Cambridge» a `CambridgeUS` y «Berlim» a `Berlin`:[^cap5][^beamer]

| Tema | Tema | Tema | Tema |
|---|---|---|---|
| `Antibes` | `Darmstadt` | `JuanLesPins` | `PaloAlto` |
| `Bergen` | `Dresden` | `Luebeck` | `Pittsburgh` |
| `Berkeley` | `Frankfurt` | `Madrid` | `Rochester` |
| `Berlin` | `Goettingen` | `Malmoe` | `Singapore` |
| `CambridgeUS` | `Hannover` | `Marburg` | `Szeged` |
| `Copenhagen` | `Ilmenau` | `Montpellier` | `Warsaw` |

```anki
deck: Física::Produção de Relatórios::Presentaciones
tags:
  - latex
  - beamer
---
> [!note] Pregunta
> ¿Qué selecciona `\usetheme{nombre}` en Beamer y qué debe comprobarse al cambiarlo?
===
> [!important] Respuesta
> La apariencia y navegación de la presentación; se comprueba que el nombre exista y que los marcos conserven espacio y legibilidad.
```

### Tema de color

> [!definicion] Tema de color
> Configuración cromática seleccionada con `\usecolortheme{nombre}`, independiente de la estructura del argumento.[^docente]

Entre los nombres del material están `albatross`, `beaver`, `beetle`, `crane`, `dolphin`, `dove`, `fly`, `lily`, `orchid`, `rose`, `seagull`, `seahorse`, `whale` y `wolverine`. La elección se comprueba con el proyector o una escala equivalente de lectura: un color disponible no garantiza un contraste adecuado.

```anki
deck: Física::Produção de Relatórios::Presentaciones
tags:
  - latex
  - beamer
---
> [!note] Pregunta
> ¿Qué diferencia `\usecolortheme` de `\usetheme` en Beamer?
===
> [!important] Respuesta
> `\usecolortheme` selecciona la configuración cromática; `\usetheme` gobierna el tema general de apariencia y navegación.
```

### allowframebreaks

> [!definicion] División automática de marco
> Opción `allowframebreaks` que permite distribuir el contenido de un marco en varias diapositivas y señalar su continuación.[^docente]

```latex
\begin{frame}[allowframebreaks]{Referências}
  Texto ou bibliografia que pode ocupar várias páginas.
\end{frame}
```

Es útil para material que admite continuidad, como una bibliografía extensa. Si un resultado necesita varios razonamientos distintos, dividirlo en marcos con mensajes propios proporciona más control que confiar en una ruptura automática. La opción no decide qué parte debe comprenderse antes.

Una línea corta no necesita dividirse por el hecho de activar la opción. Cuando se quiere comprobar de manera reproducible que un mismo marco puede producir dos páginas, se introduce un corte explícito con `\framebreak`:[^beamer]

```latex
\begin{frame}[allowframebreaks]{Duas partes do mesmo marco}
  Primeira parte: identificar os dados e a sua origem.
  \framebreak
  Segunda parte: interpretar os dados com as condições declaradas.
\end{frame}
```

El resultado esperado son dos diapositivas de continuación. Un marco de contenido suficientemente largo puede dividirse automáticamente; el corte explícito de este ejemplo permite comprobar la diferencia entre contar marcos y contar páginas sin depender de una cantidad aproximada de texto.

```anki
deck: Física::Produção de Relatórios::Presentaciones
tags:
  - latex
  - beamer
---
> [!note] Pregunta
> ¿Qué permite `allowframebreaks` en un marco Beamer?
===
> [!important] Respuesta
> Distribuir su contenido en varias diapositivas de continuación cuando lo requiere su extensión; `\framebreak` puede imponer un corte explícito dentro de ese marco.
```

### fragile para contenido literal

> [!definicion] Marco frágil
> Marco declarado con `[fragile]` para permitir contenido literal, como `verbatim`, cuyo tratamiento requiere una lectura especial del cuerpo.[^docente]

```latex
\begin{frame}[fragile]{Uma ordem escrita como código}
\begin{verbatim}
\section{Resultados}
\end{verbatim}
\end{frame}
```

Se muestra la orden en lugar de ejecutarla como seccionado de la presentación. El cierre `\end{frame}` se mantiene en su propia línea. El mismo cuidado corresponde al incluir listados de programa: el contenido literal cambia la manera de procesar el marco, aunque su apariencia parezca un bloque de texto sencillo.

```anki
deck: Física::Produção de Relatórios::Presentaciones
tags:
  - latex
  - beamer
---
> [!note] Pregunta
> ¿Cómo debe colocarse el cierre `\end{frame}` en el marco `fragile` del ejemplo Beamer?
===
> [!important] Respuesta
> En su propia línea, para que se reconozca correctamente al procesar el contenido literal.
```

```anki
deck: Física::Produção de Relatórios::Presentaciones
tags:
  - latex
  - beamer
---
> [!note] Pregunta
> ¿Por qué un marco Beamer con `verbatim` necesita normalmente `[fragile]`?
===
> [!important] Respuesta
> Porque su contenido literal necesita un tratamiento especial de lectura; `[fragile]` permite procesarlo sin interpretarlo como el contenido ordinario de un marco.
```

## Aplicación — Las cinco diapositivas del trabajo Zuloc

El trabajo integrado de Zuloc incluye un informe y una presentación de **cinco diapositivas**. La secuencia está fijada por el enunciado y cada página debe cumplir una función concreta:[^zuloc]

| Diapositiva | Contenido exigido | Comprobación |
|---:|---|---|
| 1 | Portada con el título del trabajo. | Identifica la entrega y su autoría. |
| 2 | Tabla Modelo de B. | Los datos corresponden a la versión B utilizada en el informe. |
| 3 | Gráfico de B. | Representa los resultados de esa misma versión, con ejes y unidades legibles. |
| 4 | Número de trabajadores elegido y justificación. | Explica por qué mediante cifras y recursos visuales, sin texto corrido. |
| 5 | Imagen relativa al tema y sitio del que se obtuvo. | Permite identificar tanto la imagen como su procedencia. |

El fondo no puede ser completamente blanco. Todas las diapositivas llevan título; en la portada se utiliza el título del trabajo. Una configuración posible, ajustable al contraste requerido, es:[^zuloc][^beamer]

```latex
% Preámbulo Beamer
\setbeamercolor{background canvas}{bg=blue!5}
```

Un tema de color puede modificar títulos o bloques sin modificar el fondo completo. Se inspecciona el PDF para verificar qué superficies cambió la configuración y si el contraste permite leer tablas, ejes y referencias.

### Contar la salida y distribuir las fuentes

La comprobación de las cinco diapositivas se realiza sobre el PDF final. Cinco entornos `frame` pueden generar más páginas si se introducen divisiones o presentaciones sucesivas del contenido. La atribución se integra junto a la evidencia o la imagen correspondiente, conservando la secuencia de cinco páginas exigida.[^zuloc][^beamer]

```anki
deck: Física::Produção de Relatórios::Presentaciones
tags:
  - latex
  - beamer
---
> [!note] Pregunta
> ¿Cómo se verifica un límite exacto de diapositivas en una presentación Beamer?
===
> [!important] Respuesta
> Contando las páginas reales del PDF final, porque las opciones de un marco pueden producir más de una página.
```

```anki
deck: Física::Produção de Relatórios::Presentaciones
tags:
  - latex
  - beamer
---
> [!note] Pregunta
> ¿Cómo se fija explícitamente el fondo de las diapositivas en Beamer?
===
> [!important] Respuesta
> Mediante `\setbeamercolor{background canvas}{bg=color}`; un tema de color no garantiza cambiar ese fondo. Se comprueba el resultado y el contraste en el PDF.
```

### Justificación sin texto corrido

**Tarea.** Diseñar la cuarta diapositiva para que el público pueda evaluar la elección de $n$ trabajadores. Una tabla breve puede comparar $n-1$, $n$ y $n+1$ en capacidad, atraso y ocupación; las etiquetas y cifras hacen visible el compromiso que se explica oralmente. Los números se obtienen del modelo real y se vinculan a sus condiciones. La preferencia entre coste y servicio requiere un criterio explícito.[^zuloc]

La [[Física/Grado/1º/Produção de Relatórios/03 Composición avanzada e índices en LaTeX#Aplicación — Componer y comprobar el informe Zuloc|composición y comprobación del informe Zuloc]] desarrolla los parámetros y recurrencias que sostienen esa comparación. La diapositiva debe corresponder a los resultados del informe, conservando la identificación de la versión y los escenarios utilizados.

```anki
deck: Física::Produção de Relatórios::Presentaciones
tags:
  - presentaciones
  - comunicacion-cientifica
---
> [!note] Pregunta
> ¿Cómo puede justificarse una elección de plantilla sin texto corrido en una diapositiva científica?
===
> [!important] Respuesta
> Comparando escenarios mediante cifras, tabla o gráfica legibles, y explicando oralmente el criterio y las condiciones que relacionan esos resultados con la decisión.
```

### Ambigüedad de la versión B

El enunciado permite omitir B si la plantilla inicial ya resulta adecuada, pero exige su tabla y gráfico en las diapositivas 2 y 3. Ambas instrucciones permanecen en conflicto. Además, la serie aleatoria del Word utilizada en B no está entre los materiales disponibles. La preparación de la presentación requiere identificar qué versión de los resultados se considera válida; los datos ausentes no se sustituyen por una serie inventada.[^zuloc]

## Práctica con soluciones razonadas

#### Ejercicio 1 — Ajustar la fuerza del título

> [!ejemplo] Enunciado
> Una gráfica presenta dispersión y barras de incertidumbre, pero el título dice «El modelo confirma exactamente todos los datos». Propón una revisión defendible.

> [!resolucion]- Resolución
> Se formula una afirmación que corresponda al análisis: por ejemplo, «Los datos son compatibles con la tendencia prevista dentro de la incertidumbre», sólo si el contraste lo sostiene. La explicación identifica modelo, condiciones y límite de validez de la comparación. «Exactamente» es un error frecuente porque oculta la precisión efectiva de la evidencia.

#### Ejercicio 2 — Reconocer estructura y salida

> [!ejemplo] Enunciado
> Una presentación tiene tres entornos `frame`, uno con `allowframebreaks`. ¿Tiene necesariamente tres diapositivas? ¿Qué orden construye el índice?

> [!resolucion]- Resolución
> No: el marco con división automática puede generar varias páginas. El índice se compone con `\tableofcontents` dentro de un marco y utiliza las secciones declaradas. Se recompila para actualizarlo y se revisa el PDF para conocer la salida real.

#### Ejercicio 3 — Reparar código y reorganizar el mensaje

> [!ejemplo] Enunciado
> Un marco ordinario contiene `verbatim` y falla. Además, reúne método, resultados y conclusión en una lista de quince elementos. Propón una reparación técnica y otra comunicativa.

> [!resolucion]- Resolución
> Se añade `[fragile]` para permitir el contenido literal y se comprueban sus cierres. Después se separan los mensajes que necesitan evidencia e interpretación propias. La selección se ensaya con el tiempo disponible; reducir la letra hasta que quepa la lista no resuelve la dificultad de seguir el argumento.

Una presentación conserva la exigencia de atribuir y justificar lo que comunica. El uso de imágenes, datos y herramientas conduce a [[Física/Grado/1º/Produção de Relatórios/06 Ética y uso académico de las TIC|los principios de integridad académica]], que afectan tanto a una exposición como a su informe de apoyo.

## 📚 Fuentes

### Material base aportado

[^docente]: Eugénia Graça — *Resumo de LaTeX*, julio de 2025, archivo `PR - Resumo - 2025 - 2026.pdf`, pp. físicas 69–72 (impresas 61–64); *LaTeX Summary*, archivo `PR - Resumo - INGLES - 2025 - 2026.pdf`, pp. físicas 62–65, como contraste. Clase, marcos, tema, color, títulos, índice, allowframebreaks y fragile.
[^cap5]: Eugénia Graça — *Capítulo V — Apresentações*, portada de julio de 2024, archivo `cap 5 - PR.pdf`, 11 páginas físicas y 10 diapositivas numeradas por la repetición de la diapositiva 4. Pp. físicas 3–6: estructura; pp. 7–9: temas y colores; pp. 10–11: opciones e índice. Se corrigen localmente los nombres de temas mediante el manual oficial.
[^zuloc]: FCUL — *Enunciado do Trabalho — Laboratório Zuloc*, archivo `enunciado PR moodle.pdf`, p. física 9. Presentación de cinco diapositivas, contenido de cada página, fondo y títulos. P. 8: omisión condicional de B; la discrepancia se conserva como ambigüedad del enunciado.

### Ampliación externa

[^harvard]: Harvard Catalyst — [Slides](https://catalyst.harvard.edu/writing-communication-center/visualize-science/slides/). Función visual, claridad, legibilidad, fuentes y revisión de diapositivas.
[^cmu]: Carnegie Mellon University — [PowerPoint / Oral Presentation Slide Design](https://www.cmu.edu/student-success/other-resources/resource-descriptions/powerpoint-design.html). Estructura de afirmación y evidencia.
[^beamer]: Till Tantau, Joseph Wright y Vedran Miletić — [The Beamer Class: User Guide](https://ctan.math.illinois.edu/macros/latex/contrib/beamer/doc/beameruserguide.pdf), versión 3.78, agosto de 2026. Marcos, títulos, temas, fondo, contenido literal y división de páginas. Contraste de los nombres `CambridgeUS` y `Berlin` y del tratamiento de `allowframebreaks` y `fragile`.

## 🧑‍🏫 Prompt para tutor conversacional

Tutoriza a nivel universitario introductorio con una pregunta por turno y espera la respuesta.

Una presentación comunica pregunta→método esencial→evidencia→interpretación→límite.

El título debe expresar un mensaje defendible y la imagen, gráfica o tabla permitir evaluarlo; la voz explica decisiones y límites. La jerarquía visual ordena título, evidencia y atribución; comprueba ejes, unidades, contraste y lectura a distancia. El ensayo ajusta contenido al tiempo y al público.

Beamer es una clase LaTeX: documentclass[11pt]{beamer}; frame delimita contenido y puede producir una o varias diapositivas.

Title/author/institute/date preparan portada con titlepage; section organiza y tableofcontents recoge las partes.

Usetheme elige aspecto y usecolortheme colores; CambridgeUS y dolphin son ejemplos. `\frametitle` o argumento de frame fija título.

Allowframebreaks reparte un marco largo; fragile permite verbatim y código literal.

El trabajo Zuloc exige cinco páginas: portada, tabla B, gráfico B, elección de plantilla sin texto corrido e imagen con sitio de procedencia. El fondo no puede ser totalmente blanco y cada página lleva título. Cuenta páginas finales, no sólo marcos; conserva las fuentes junto a sus elementos. El informe permite omitir B bajo una condición, mientras la presentación exige B: identifica esa ambigüedad y la serie del Word no aportada, sin inventar resultados.

Usa tres valores ficticios de período 1,40; 1,44 y 1,42 segundos para elegir una representación, sin tratarlos como evidencia real.

Pide corregir un título excesivo, distinguir marco de diapositiva y reparar un verbatim sin fragile. Distingue errores técnicos, de evidencia, de secuencia y de legibilidad; practica con pistas, recuperación activa y repetición espaciada.

Continúa con autoría, privacidad y uso de materiales.

```dataviewjs
await dv.view("Planes/Estudio/Scripts/study-session", { location: "end" })
```
