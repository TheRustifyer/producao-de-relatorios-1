---
title: Informes y escritura científica
aliases:
  - Organización de informes científicos
asignatura: Produção de Relatórios
rama:
  - Comunicación científica
tipo:
  - procedimiento
  - teoría
nivel: universitario-introductorio
estado: revisado
capa: curricular
fsrs_goal: Construye la estructura de un informe breve o extenso, justifica la separación de método, resultados y discusión, y revisa un párrafo y sus representaciones para conservar una evidencia verificable.
tags:
  - fisica
  - informes
  - comunicacion-cientifica
  - fcul
  - curricular
---

```dataviewjs
await dv.view("Planes/Estudio/Scripts/study-session", { location: "start" })
```

# Informes y escritura científica

Quien lee un informe necesita reconstruir una investigación: qué se quiso averiguar, cómo se trabajó y qué resultados permiten responder. La estructura distribuye esas preguntas entre secciones; la escritura relaciona las afirmaciones con su evidencia. Estas buenas prácticas forman el primer bloque de *Produção de Relatórios* y se aplican tanto al escribir con Word como con LaTeX.[^cap1][^sheffield]

## Del trabajo realizado al argumento científico

### Informe científico

> [!definicion] Informe científico
> Documento que comunica un problema, el procedimiento seguido para abordarlo, los resultados obtenidos y las conclusiones que esos resultados permiten sostener. Permite localizar la evidencia y examinar el razonamiento.[^cap1][^sheffield]

El objetivo determina qué información resulta pertinente. Una cronología puede explicar una decisión importante —por ejemplo, por qué se repitió una medida—, pero la sucesión de tareas debe conducir a una respuesta reconocible. El lector ha de poder relacionar cada conclusión con los resultados que la sostienen.[^sheffield]

```anki
deck: Física::Produção de Relatórios::Informes
tags:
  - fisica
  - informe-cientifico
---
> [!note] Pregunta
> ¿Qué debe comunicar un informe científico para que el lector pueda examinar el trabajo?
===
> [!important] Respuesta
> El problema, el procedimiento, los resultados y las conclusiones que esos resultados sostienen, con una relación identificable entre evidencia y razonamiento.
```

### Elegir la estructura según el trabajo

El informe de un experimento suele separar las medidas de su interpretación; una revisión compara fuentes, y un proyecto puede dedicar capítulos al análisis, al diseño y a la implementación. El esquema dependerá de lo que haya que hacer para responder a la pregunta. Por eso, la pauta extensa de la profesora y la estructura breve de un informe experimental no son intercambiables: cada una da espacio a tareas distintas.[^estructura][^sheffield]

> [!procedimiento] Elección de estructura
> 1. Formular qué pregunta debe responder el informe.
> 2. Identificar cómo se obtiene la respuesta: medidas, comparación de fuentes o desarrollo de una solución.
> 3. Distribuir ese recorrido en secciones con funciones reconocibles.
> 4. Ajustar las secciones y su extensión al enunciado de la entrega.[^estructura][^sheffield]

#### Ejemplo — Convertir una actividad en una pregunta

**Tarea.** Imagina que acabas de medir el período de un péndulo. Propón un título informativo para cada caso: a) repites la medida manteniendo la longitud; b) comparas medidas tomadas con longitudes distintas.

«Práctica 1» dice cuál es la entrega, pero no qué estudiaste. Para el caso a), **«Medición repetida del período de un péndulo»** cuenta con claridad qué hiciste. Para el b), **«Variación del período medido con la longitud del péndulo»** deja ver qué relación comparaste.

Comprueba el título mirando los datos. Cinco medidas tomadas con la misma longitud muestran cuánto varían las repeticiones en esa condición; para averiguar cómo influye la longitud en el período, necesitas medir con longitudes distintas. ==El título debe decir qué hiciste realmente.==[^sheffield]

```anki
deck: Física::Produção de Relatórios::Informes
tags:
  - fisica
  - informe-cientifico
---
> [!note] Pregunta
> ¿Qué permiten estudiar las medidas repetidas del período de un péndulo tomadas a una sola longitud?
===
> [!important] Respuesta
> La variación entre repeticiones en esa condición. Para estudiar una dependencia del período con la longitud hacen falta medidas a distintas longitudes.
```

```anki
deck: Física::Produção de Relatórios::Informes
tags:
  - fisica
  - informe-cientifico
---
> [!note] Pregunta
> ¿Cómo se elige la estructura de un informe científico?
===
> [!important] Respuesta
> Se parte de la pregunta y de las operaciones necesarias para responderla; se distribuyen en secciones con funciones claras y se ajusta el esquema al enunciado de la entrega.
```

### Método y reproducibilidad

Un resultado pierde contexto si aparece como una cifra suelta. Para valorar de dónde salió, el lector necesita saber qué operaciones se hicieron y en qué condiciones.[^icmje]

> [!definicion] Descripción reproducible del método
> Descripción que proporciona información suficiente para reconstruir las operaciones que produjeron un resultado: materiales, condiciones, decisiones, datos necesarios y tratamiento aplicado. Esta suficiencia del texto permite examinar cómo y por qué se ejecutó el procedimiento.[^icmje]

«Se midió varias veces» no dice qué se midió, cuántas repeticiones hubo ni cómo se tomó cada medida. En el caso de un péndulo, aclara si cronometraste una oscilación o varias, qué momento marcó el inicio y el final y cómo trataste las repeticiones. Si una decisión puede cambiar el resultado, deja constancia de ella.[^icmje]

Al redactar el método, distingue lo que observaste de lo que supusiste o modelizaste; esa diferencia se desarrolla en [[Física/Preuniversitario/2 Bachillerato/01 Trabajo científico y herramientas matemáticas/Investigación y modelización en Física|la investigación y modelización en Física]].

```anki
deck: Física::Produção de Relatórios::Informes
tags:
  - fisica
  - informe-cientifico
---
> [!note] Pregunta
> ¿Qué hace suficiente la descripción de un método experimental?
===
> [!important] Respuesta
> Que permita reconstruir las operaciones relevantes mediante los materiales, condiciones, decisiones, datos necesarios y tratamiento aplicado, sin tener que adivinar cómo se obtuvo el resultado.
```

> [!advertencia] Resolución del instrumento e incertidumbre de la medida
> La resolución de un cronómetro es sólo uno de los componentes que pueden intervenir en la incertidumbre de un cronometraje manual. La reacción del operador también puede contribuir. Por tanto, declarar la resolución del instrumento no basta para declarar la incertidumbre total de la medida.[^nist]

```anki
deck: Física::Produção de Relatórios::Informes
tags:
  - fisica
  - informe-cientifico
---
> [!note] Pregunta
> ¿Por qué la resolución de un cronómetro no basta para declarar la incertidumbre total de un cronometraje manual?
===
> [!important] Respuesta
> Porque sólo representa un componente; también pueden intervenir otros, como la reacción del operador al iniciar y detener el cronometraje.
```

## Estructura de un informe breve

Un informe experimental suele hacer seis cosas: plantea la pregunta, cuenta cómo se trabajó, presenta los datos, los interpreta, responde al objetivo y resume el resultado. A veces el enunciado junta resultados y discusión en una misma sección. En ese caso, separa con claridad lo que observaste de la explicación que propones.[^sheffield]

### Introducción

Antes de leer el objetivo, el lector necesita saber de qué problema nace. La introducción lo lleva desde el contexto necesario hasta el aspecto concreto que estudias y la pregunta que quieres responder.[^sheffield]

> [!definicion] Introducción
> Sección que sitúa el problema y formula el objetivo del trabajo. Incluye la motivación y los antecedentes necesarios para comprender la pregunta, y puede declarar una hipótesis cuando corresponda.[^estructura][^sheffield]

Si vas a comparar períodos, incluye en la introducción la teoría que ayude a entender esa comparación. Un rodeo teórico que no vuelva a aparecer en el objetivo, el método o la interpretación distrae de la pregunta. En el esquema extenso de la asignatura, la introducción también presenta las contribuciones y adelanta cómo se organiza el documento.[^estructura][^sheffield]

```anki
deck: Física::Produção de Relatórios::Informes
tags:
  - fisica
  - informe-cientifico
---
> [!note] Pregunta
> ¿Qué función cumple la introducción de un informe científico?
===
> [!important] Respuesta
> Sitúa el problema mediante el contexto y los antecedentes pertinentes, y conduce hasta el objetivo concreto; puede explicitar motivación e hipótesis cuando correspondan.
```

```anki
deck: Física::Produção de Relatórios::Informes
tags:
  - fisica
  - informe-cientifico
---
> [!note] Pregunta
> ¿Qué debe presentar la introducción en el esquema de informe extenso de Produção de Relatórios?
===
> [!important] Respuesta
> Motivación, objetivos, contribuciones y estructura del documento.
```

### Método

> [!definicion] Método
> Sección que describe los materiales, condiciones, operaciones y tratamiento de datos utilizados para obtener los resultados.[^icmje]

Puedes ordenar el método por montaje, toma de datos y análisis. Explica aquí la fórmula que usaste para convertir una medida en otra magnitud; deja para resultados los valores obtenidos. Así, quien lee puede seguir el cálculo y luego examinar sus resultados.[^icmje][^sheffield]

```anki
deck: Física::Produção de Relatórios::Informes
tags:
  - fisica
  - informe-cientifico
---
> [!note] Pregunta
> ¿Qué información pertenece a la sección de método de un informe científico?
===
> [!important] Respuesta
> Los materiales, condiciones, operaciones y tratamiento de datos con los que se obtuvieron los resultados, incluidas las fórmulas que explican los cálculos realizados.
```

### Resultados

> [!definicion] Resultados
> Sección que presenta lo observado, medido o calculado mediante el procedimiento declarado, con la información necesaria para interpretar los datos.[^sheffield]

El orden sigue los objetivos: se presenta primero la evidencia necesaria para responder a la pregunta principal. La prosa destaca los hallazgos relevantes; las tablas y figuras permiten inspeccionarlos. Las magnitudes llevan unidades y los símbolos, columnas y barras de incertidumbre se explican. Los registros muy extensos pueden conservarse en anexos.[^icmje][^sheffield]

```anki
deck: Física::Produção de Relatórios::Informes
tags:
  - fisica
  - informe-cientifico
---
> [!note] Pregunta
> ¿Qué presenta la sección de resultados de un informe científico?
===
> [!important] Respuesta
> Lo observado, medido o calculado mediante el método declarado, organizado según los objetivos y acompañado de unidades y explicaciones que permitan leer los datos.
```

### Discusión

En la discusión, vuelve a la pregunta inicial: ¿qué dicen los datos?, ¿qué explicaciones encajan con ellos? y ¿qué límites del procedimiento afectan la respuesta?[^sheffield]

> [!definicion] Discusión
> Sección que interpreta los resultados: examina qué significan, con qué explicaciones son compatibles y qué limitaciones afectan a la respuesta.[^sheffield]

En resultados puedes informar de la diferencia numérica; para atribuirla al rozamiento hace falta razonar en la discusión. Si no mediste ni controlaste ese factor, preséntalo como una posible explicación y deja claro que los datos no bastan para confirmarla.[^sheffield]

```anki
deck: Física::Produção de Relatórios::Informes
tags:
  - fisica
  - informe-cientifico
---
> [!note] Pregunta
> ¿Qué función cumple la discusión de un informe científico?
===
> [!important] Respuesta
> Interpreta el significado de los resultados respecto a la pregunta, examina explicaciones compatibles y considera las limitaciones que afectan a la respuesta.
```

```anki
deck: Física::Produção de Relatórios::Informes
tags:
  - fisica
  - informe-cientifico
---
> [!note] Pregunta
> En un informe científico, ¿qué diferencia la sección de resultados de la discusión?
===
> [!important] Respuesta
> Resultados comunica lo observado o calculado; discusión interpreta su significado, límites y relación con la pregunta.
```

> [!recuerda] Una explicación plausible necesita contraste
> Si los datos admiten varias explicaciones y el trabajo no permite distinguirlas, la discusión debe declarar esa limitación. Expresiones como «podría deberse a» conservan el carácter hipotético, pero requieren explicar por qué la causa propuesta resulta plausible.[^sheffield]

```anki
deck: Física::Produção de Relatórios::Informes
tags:
  - fisica
  - informe-cientifico
---
> [!note] Pregunta
> ¿Cómo debe presentarse una posible causa de una discrepancia cuando el experimento no permite comprobarla?
===
> [!important] Respuesta
> Como una hipótesis plausible, justificada y limitada por la evidencia disponible, sin atribuirle el carácter de causa comprobada.
```

### Conclusiones

> [!definicion] Conclusiones
> Sección que responde a los objetivos mediante los resultados obtenidos y delimita lo establecido por el trabajo.[^estructura][^sheffield]

Los límites de validez de una conclusión dependen de las condiciones de la investigación y de la evidencia obtenida. Comparar unas pocas medidas con una predicción permite valorar esa comparación; no justifica afirmar que «la teoría quedó demostrada». Una conclusión defendible identifica qué se comparó, qué se encontró y hasta dónde llega la evidencia.[^sheffield]

```anki
deck: Física::Produção de Relatórios::Informes
tags:
  - fisica
  - informe-cientifico
---
> [!note] Pregunta
> ¿Qué función cumple la sección de conclusiones de un informe científico?
===
> [!important] Respuesta
> Responde a los objetivos con los resultados obtenidos y delimita qué ha quedado establecido por el trabajo.
```

```anki
deck: Física::Produção de Relatórios::Informes
tags:
  - fisica
  - informe-cientifico
---
> [!note] Pregunta
> ¿Qué limita el alcance de una conclusión científica?
===
> [!important] Respuesta
> La evidencia y las condiciones del trabajo: sólo puede afirmarse lo que los resultados permiten sostener dentro de ese alcance.
```

### Resumen

El resumen aparece al principio, pero recoge el trabajo completo. Un lector debe poder reconocer la aportación sin consultar las demás secciones.[^icmje][^sheffield]

> [!definicion] Resumen
> Exposición breve y autónoma del objetivo, el procedimiento principal, los hallazgos más importantes y la conclusión del trabajo.[^sheffield]

«El informe contiene una introducción y unos resultados» enumera partes sin comunicar ningún hallazgo. Un resumen informativo indica qué se investigó y qué se obtuvo. Cuando hay versiones portuguesa e inglesa, ambas deben conservar las mismas afirmaciones y limitaciones.[^icmje][^estructura]

```anki
deck: Física::Produção de Relatórios::Informes
tags:
  - fisica
  - informe-cientifico
---
> [!note] Pregunta
> ¿Qué debe comunicar el resumen de un informe científico para ser informativo y autónomo?
===
> [!important] Respuesta
> El objetivo, el procedimiento principal, los hallazgos más importantes y la conclusión, de modo que la aportación se reconozca sin leer el informe completo.
```

```anki
deck: Física::Produção de Relatórios::Informes
tags:
  - fisica
  - informe-cientifico
---
> [!note] Pregunta
> ¿Qué debe mantenerse al traducir el resumen de un informe a otro idioma?
===
> [!important] Respuesta
> Las mismas afirmaciones, resultados y limitaciones; las versiones lingüísticas deben comunicar la misma aportación.
```

## Preliminares y cuerpo del trabajo

El esquema docente de informe extenso organiza primero la identificación y consulta del documento y después desarrolla un proyecto. Incluye capítulos de trabajo relacionado, análisis, diseño e implementación. Estos capítulos se adaptan a la naturaleza del trabajo y al enunciado de la entrega.[^estructura]

### Preliminares

> [!definicion] Preliminares
> Elementos situados antes del cuerpo principal que identifican el trabajo, reconocen contribuciones y facilitan su consulta: portada, posibles dedicatoria y agradecimientos, resúmenes e índices.[^estructura]

Se consultan con finalidades distintas: la portada identifica el documento; el resumen permite reconocer su aportación; los índices permiten localizarla. Su presencia concreta depende de los requisitos de la entrega.[^estructura][^sheffield]

```anki
deck: Física::Produção de Relatórios::Informes
tags:
  - fisica
  - informe-cientifico
---
> [!note] Pregunta
> ¿Qué son los preliminares de un informe extenso?
===
> [!important] Respuesta
> Los elementos anteriores al cuerpo principal que identifican el trabajo, reconocen contribuciones o facilitan su consulta, como portada, resúmenes e índices.
```

### Cuerpo del trabajo

> [!definicion] Cuerpo del trabajo
> Desarrollo principal en el que se plantea el problema, se explica cómo se abordó, se presentan los resultados y se construye la respuesta.[^estructura][^sheffield]

El esquema extenso de la asignatura dedica espacio a la introducción, el trabajo relacionado, el análisis, el diseño, la implementación, los resultados y la conclusión. En una práctica breve, en cambio, el método cuenta el procedimiento y resultados y discusión separan lo observado de su interpretación.[^estructura][^sheffield]

```anki
deck: Física::Produção de Relatórios::Informes
tags:
  - fisica
  - informe-cientifico
---
> [!note] Pregunta
> ¿Qué función cumple el cuerpo principal de un informe?
===
> [!important] Respuesta
> Desarrolla el problema, el procedimiento, la evidencia y la respuesta, mediante las secciones adecuadas al trabajo realizado.
```

### Portada

> [!definicion] Portada
> Página inicial que identifica el informe mediante su título, autoría y contexto de entrega.[^estructura][^sheffield]

El título debe distinguir el objeto del trabajo. Los demás datos se ajustan al enunciado: por ejemplo, asignatura, institución y fecha cuando se soliciten.[^sheffield]

```anki
deck: Física::Produção de Relatórios::Informes
tags:
  - fisica
  - informe-cientifico
---
> [!note] Pregunta
> ¿Para qué sirve la portada de un informe?
===
> [!important] Respuesta
> Para identificar el trabajo mediante su título, autoría y contexto de entrega, con los datos exigidos por el enunciado.
```

### Dedicatoria

> [!definicion] Dedicatoria
> Texto personal que dedica el trabajo a una persona o colectivo. El esquema docente la contempla entre los preliminares.[^estructura][^dedicatoria]

Inclúyela solo si encaja con el documento y con lo que pide la entrega; la dedicatoria no forma parte del argumento científico.[^estructura]

```anki
deck: Física::Produção de Relatórios::Informes
tags:
  - fisica
  - informe-cientifico
---
> [!note] Pregunta
> ¿Qué función cumple una dedicatoria en los preliminares de un informe?
===
> [!important] Respuesta
> Dedica personalmente el trabajo a una persona o colectivo; no forma parte del desarrollo del argumento científico.
```

### Agradecimientos

> [!definicion] Agradecimientos
> Texto que reconoce las ayudas y contribuciones recibidas durante la realización del trabajo.[^estructura][^dedicatoria]

Permite identificar, cuando corresponde, apoyos técnicos, materiales o personales. La dedicatoria expresa a quién se dedica el trabajo; los agradecimientos reconocen aportaciones recibidas.[^dedicatoria]

```anki
deck: Física::Produção de Relatórios::Informes
tags:
  - fisica
  - informe-cientifico
---
> [!note] Pregunta
> ¿Qué reconocen los agradecimientos de un informe?
===
> [!important] Respuesta
> Las ayudas y contribuciones recibidas para realizar el trabajo, como apoyos técnicos, materiales o personales.
```

### Resúmenes en la pauta docente

Para el informe extenso, la profesora propone estas extensiones:[^estructura]

| Lengua del trabajo | Resúmenes indicados |
|---|---|
| Portugués | Uno en portugués y otro en inglés, de aproximadamente 300 palabras cada uno. |
| Lengua extranjera | Un resumen portugués adicional de al menos 1200 palabras. |

> [!advertencia] Alcance de la pauta
> Las cifras pertenecen al esquema docente presentado. ==La extensión y los preliminares de una entrega concreta se comprueban en su enunciado==; esta pauta no establece una longitud universal para todo informe científico.[^estructura][^sheffield]

```anki
deck: Física::Produção de Relatórios::Informes
tags:
  - fisica
  - informe-cientifico
---
> [!note] Pregunta
> ¿Qué pauta de extensión de resúmenes presenta la profesora para el informe extenso de Produção de Relatórios?
===
> [!important] Respuesta
> Si el trabajo está en portugués, resúmenes portugués e inglés de unas 300 palabras cada uno; si está en lengua extranjera, un resumen portugués adicional de al menos 1200 palabras. Su aplicación se contrasta con el enunciado de la entrega.
```

### Índice de contenido

> [!definicion] Índice de contenido
> Relación ordenada de los capítulos y secciones del documento con sus localizadores, que permite recorrer su estructura.[^estructura]

La jerarquía del índice debe corresponder a la del cuerpo: un apartado aparece subordinado al capítulo o sección al que pertenece.[^estructura]

```anki
deck: Física::Produção de Relatórios::Informes
tags:
  - fisica
  - informe-cientifico
---
> [!note] Pregunta
> ¿Qué permite consultar el índice de contenido de un informe?
===
> [!important] Respuesta
> La estructura ordenada y jerárquica de capítulos y secciones, junto con los localizadores que permiten encontrarlos.
```

### Índice de figuras

> [!definicion] Índice de figuras
> Relación de las figuras del documento con su identificación y localización.[^estructura]

Así, quien consulta el informe puede ir directamente al montaje, a una gráfica o a otra representación, sin hojear el documento entero.[^estructura]

```anki
deck: Física::Produção de Relatórios::Informes
tags:
  - fisica
  - informe-cientifico
---
> [!note] Pregunta
> ¿Para qué sirve el índice de figuras de un informe?
===
> [!important] Respuesta
> Para identificar y localizar sus figuras, como gráficas, esquemas o representaciones de montajes.
```

### Índice de tablas

> [!definicion] Índice de tablas
> Relación de las tablas del documento con su identificación y localización.[^estructura]

Permite acudir directamente a los conjuntos de datos o comparaciones dispuestos en filas y columnas.[^estructura]

```anki
deck: Física::Produção de Relatórios::Informes
tags:
  - fisica
  - informe-cientifico
---
> [!note] Pregunta
> ¿Para qué sirve el índice de tablas de un informe?
===
> [!important] Respuesta
> Para identificar y localizar las tablas del documento sin tener que recorrer el cuerpo completo.
```

## Desarrollo de un proyecto extenso

En un proyecto, esas etapas pueden ocupar capítulos distintos: primero sitúas los antecedentes, luego delimitas el problema, justificas la solución y explicas cómo la llevaste a cabo.[^estructura]

### Trabajo relacionado

> [!definicion] Trabajo relacionado
> Sección que sitúa el problema respecto a trabajos previos pertinentes y permite reconocer qué aportación se pretende realizar.[^estructura][^cambridge]

Elige las fuentes pensando en la pregunta del proyecto. Comparar sus enfoques y límites ayuda a explicar por qué seguiste una orientación concreta.[^cambridge]

```anki
deck: Física::Produção de Relatórios::Informes
tags:
  - fisica
  - informe-cientifico
---
> [!note] Pregunta
> ¿Qué función cumple el trabajo relacionado en un informe de proyecto?
===
> [!important] Respuesta
> Sitúa el problema respecto a los trabajos previos pertinentes y ayuda a reconocer y justificar la aportación del proyecto.
```

### Análisis

> [!definicion] Análisis
> Etapa que precisa el problema y las necesidades o condiciones que la solución debe atender.[^estructura][^cambridge]

En una herramienta informática de tratamiento de medidas, el análisis puede identificar qué datos se reciben y qué operaciones necesita realizar el usuario. Así se establece qué debe resolverse antes de elegir la organización de la solución.

```anki
deck: Física::Produção de Relatórios::Informes
tags:
  - fisica
  - informe-cientifico
---
> [!note] Pregunta
> ¿Qué se establece en el análisis de un informe de proyecto?
===
> [!important] Respuesta
> El problema y las necesidades o condiciones que la solución debe atender: qué debe resolverse.
```

### Diseño

Con el problema ya delimitado, explica por qué elegiste esa forma de resolverlo.[^estructura]

> [!definicion] Diseño
> Etapa que propone y justifica cómo se organizará la solución para responder al problema analizado.[^estructura][^cambridge]

En una herramienta para procesar medidas, por ejemplo, puedes separar la entrada de datos, el cálculo y la presentación de resultados. Relaciona esa decisión con las necesidades que encontraste al analizar el problema.

```anki
deck: Física::Produção de Relatórios::Informes
tags:
  - fisica
  - informe-cientifico
---
> [!note] Pregunta
> ¿Qué se explica en el diseño de un informe de proyecto?
===
> [!important] Respuesta
> Cómo se organizará la solución y por qué esa organización responde al problema y a las necesidades del análisis.
```

### Implementación

> [!definicion] Implementación
> Etapa que explica cómo se realizó la solución diseñada, con las decisiones necesarias para comprender su funcionamiento.[^estructura][^cambridge]

En el mismo proyecto, corresponde describir la realización de los módulos y su conexión. Los resultados de probar la herramienta se presentan después, de manera que el lector pueda distinguir la construcción de su evaluación.[^estructura][^cambridge]

```anki
deck: Física::Produção de Relatórios::Informes
tags:
  - fisica
  - informe-cientifico
---
> [!note] Pregunta
> ¿Qué comunica la implementación de un informe de proyecto?
===
> [!important] Respuesta
> Cómo se realizó la solución diseñada y qué decisiones permiten comprender su funcionamiento.
```

### Anexos

> [!definicion] Anexo
> Parte complementaria que conserva material útil para comprobar o ampliar el trabajo sin interrumpir el argumento principal.[^sheffield]

Si el registro de datos es muy largo o el desarrollo técnico desviaría del hilo principal, puedes llevarlo a un anexo. En el cuerpo, señala dónde está y cuándo conviene consultarlo. Mantén en el argumento todo lo que el lector necesita para entender la respuesta.[^sheffield]

```anki
deck: Física::Produção de Relatórios::Informes
tags:
  - fisica
  - informe-cientifico
---
> [!note] Pregunta
> ¿Qué material se sitúa en un anexo de un informe científico?
===
> [!important] Respuesta
> Detalle complementario útil para comprobar o ampliar el trabajo, como registros extensos o desarrollos técnicos, al que el cuerpo remite cuando resulta pertinente.
```

### Bibliografía

> [!definicion] Bibliografía
> Relación de referencias que identifica las fuentes utilizadas para fundamentar el trabajo y permite recuperarlas.[^estructura][^sheffield]

La identificación de las fuentes permite contrastar las afirmaciones del informe. El procedimiento de localización y composición se desarrolla en [[Física/Grado/1º/Produção de Relatórios/04 Búsqueda bibliográfica y referencias|búsqueda bibliográfica y referencias]].[^icmje][^sheffield]

```anki
deck: Física::Produção de Relatórios::Informes
tags:
  - fisica
  - informe-cientifico
---
> [!note] Pregunta
> ¿Qué función cumple la bibliografía de un informe científico?
===
> [!important] Respuesta
> Identifica las fuentes utilizadas para fundamentar el trabajo y proporciona la información necesaria para recuperarlas.
```

### Cita bibliográfica

> [!definicion] Cita bibliográfica
> Indicación situada en el cuerpo del trabajo que identifica la fuente de una afirmación, dato o argumento y remite a su referencia bibliográfica.[^icmje][^sheffield]

Pon la cita junto al dato, la idea o el método que tomaste de otra obra. La bibliografía reúne los datos necesarios para localizarla; la cita muestra qué parte de tu informe depende de ella.[^icmje][^sheffield]

```anki
deck: Física::Produção de Relatórios::Informes
tags:
  - fisica
  - informe-cientifico
---
> [!note] Pregunta
> ¿Qué identifica una cita bibliográfica dentro de un informe?
===
> [!important] Respuesta
> La fuente de una afirmación, dato o argumento, mediante una indicación junto a esa información que remite a su referencia bibliográfica.
```

## Representar resultados con intención

La representación se elige por la información que el lector necesita examinar. Un mismo conjunto de medidas puede requerir consultar valores exactos, reconocer una pauta o destacar un hallazgo en la prosa.[^sheffield]

### Tabla de resultados

> [!definicion] Tabla de resultados
> Disposición de datos en filas y columnas que permite recuperar valores y comparar categorías o medidas concretas.[^icmje]

Cada encabezado identifica la magnitud o categoría de la columna; cuando corresponde, declara la unidad. La tabla debe poder interpretarse mediante su título y sus aclaraciones.[^icmje]

```anki
deck: Física::Produção de Relatórios::Informes
tags:
  - fisica
  - informe-cientifico
---
> [!note] Pregunta
> ¿Qué información permite examinar una tabla de resultados?
===
> [!important] Respuesta
> Valores y comparaciones concretas organizados en filas y columnas, identificados mediante encabezados y unidades cuando correspondan.
```

### Figura científica

> [!definicion] Figura científica
> Representación visual de una relación, un montaje o una pauta relevante para el trabajo, identificada y explicada mediante una leyenda.[^icmje]

Una figura puede mostrar una fotografía del montaje, un esquema o una gráfica. Elige la que ayude a responder una pregunta del informe y asegúrate de que sus detalles se lean bien.[^icmje][^sheffield]

```anki
deck: Física::Produção de Relatórios::Informes
tags:
  - fisica
  - informe-cientifico
---
> [!note] Pregunta
> ¿Qué es una figura científica dentro de un informe?
===
> [!important] Respuesta
> Una representación visual de una relación, montaje o pauta relevante, identificada y explicada mediante una leyenda.
```

### Gráfica de datos

> [!definicion] Gráfica de datos
> Figura que representa datos mediante posiciones u otros elementos visuales para permitir examinar relaciones, tendencias o dispersión.[^sheffield]

Los ejes, cuando los hay, identifican las magnitudes y unidades. La prosa precisa qué relación interesa observar para que el lector reconozca por qué se incluyó la gráfica.[^sheffield][^icmje]

```anki
deck: Física::Produção de Relatórios::Informes
tags:
  - fisica
  - informe-cientifico
---
> [!note] Pregunta
> ¿Qué permite examinar una gráfica de datos en un informe?
===
> [!important] Respuesta
> Relaciones, tendencias o dispersión mediante una representación visual de los datos, con magnitudes y unidades identificadas.
```

### Elegir entre tabla, gráfica y texto

| Necesidad del lector | Representación adecuada |
|---|---|
| Recuperar valores concretos o comparar entradas | Tabla. |
| Examinar tendencias, relaciones o dispersión | Gráfica. |
| Reconocer el hallazgo relevante para el objetivo | Texto que explica la lectura de los datos. |

Usa el texto, las tablas y las figuras para tareas distintas. La tabla conserva los valores; en la prosa, destaca el resultado que importa para el objetivo, en vez de volver a copiarla entera.[^sheffield][^icmje]

#### Ejemplo — Cinco medidas de período

**Tarea.** Supón que obtienes cinco períodos ficticios, en segundos: $1{,}41$, $1{,}44$, $1{,}42$, $1{,}40$ y $1{,}43$. Todos corresponden a la misma longitud del péndulo. Decide cómo guardar cada medida y qué comparación comunicarías.

Para recuperar las medidas individuales se elige una tabla:

| Repetición | Período / s |
|---|---:|
| 1 | 1,41 |
| 2 | 1,44 |
| 3 | 1,42 |
| 4 | 1,40 |
| 5 | 1,43 |

En el texto podrías señalar: «Las cinco medidas, tomadas con la misma longitud, quedaron entre $1{,}40$ y $1{,}44\ \mathrm{s}$». Una gráfica con una marca por repetición mostraría cómo se dispersan. Si calculas la media, explica en el método cómo la obtuviste y comunica el valor en resultados.[^sheffield]

Fíjate en que las cinco medidas se tomaron con la misma longitud: la tabla y la gráfica no añaden datos de otras condiciones. Con ellas puedes estudiar cuánto difieren las repeticiones; todavía no puedes decir cómo cambia el período al cambiar la longitud.

```anki
deck: Física::Produção de Relatórios::Informes
tags:
  - fisica
  - informe-cientifico
---
> [!note] Pregunta
> ¿Cómo se elige entre tabla, gráfica y texto al comunicar resultados?
===
> [!important] Respuesta
> Se usa una tabla para consultar valores concretos, una gráfica para examinar pautas o dispersión y texto para explicar el hallazgo relevante para la pregunta.
```

### Leyenda de una figura

> [!definicion] Leyenda de una figura
> Texto asociado a la figura que identifica lo representado y proporciona las aclaraciones necesarias para interpretarla.[^icmje]

Debe explicar símbolos y unidades que no sean evidentes en la representación. Si aparecen barras de incertidumbre, se declara qué representan. La interpretación científica se desarrolla en la prosa que utiliza la figura para responder a la pregunta.[^icmje][^sheffield]

#### Ejemplo — De una leyenda vaga a una leyenda funcional

**Tarea.** Sustituye «Resultados» por una leyenda que permita interpretar una figura con las cinco medidas anteriores.

Una redacción informativa es: «Períodos medidos en cinco repeticiones para una misma longitud del péndulo. Cada punto corresponde a una repetición y el eje vertical expresa el período en segundos».

Se comprueba que la leyenda identifica los datos, la condición común, el significado de los puntos y la unidad. Si la figura incorporase barras de incertidumbre, sería necesario añadir su significado; no se presupone que representan una magnitud determinada.[^icmje]

```anki
deck: Física::Produção de Relatórios::Informes
tags:
  - fisica
  - informe-cientifico
---
> [!note] Pregunta
> ¿Qué debe aclarar la leyenda de una figura científica?
===
> [!important] Respuesta
> Qué se representa y cómo se interpreta: símbolos, unidades y condiciones pertinentes; si hay barras de incertidumbre, qué representan.
```

## Escritura y revisión del argumento

### Párrafo científico y jerarquía

> [!definicion] Párrafo científico
> Unidad de exposición que desarrolla una idea reconocible y la conecta con la evidencia o el razonamiento que la sostiene.[^parrafo]

Si pasas a otra pregunta, a otro paso del método o a una interpretación, quizá convenga abrir un párrafo nuevo. Por ejemplo, cuenta cómo cronometraste en uno y explica una discrepancia en otro: el lector verá enseguida qué función cumple cada parte.[^parrafo][^sheffield]

```anki
deck: Física::Produção de Relatórios::Informes
tags:
  - fisica
  - informe-cientifico
---
> [!note] Pregunta
> ¿Qué organiza un párrafo científico?
===
> [!important] Respuesta
> Una idea reconocible y su relación con la evidencia o el razonamiento que la sostiene; un cambio de función puede requerir otro párrafo.
```

### Listas

> [!definicion] Lista
> Disposición separada de elementos paralelos o de pasos que deben distinguirse para que su relación resulte visible.[^monash]

Los materiales de un montaje pueden enumerarse como elementos paralelos; las fases de un procedimiento se ordenan cuando su secuencia importa. Una explicación causal necesita además prosa que haga explícita la relación entre las afirmaciones.[^monash]

```anki
deck: Física::Produção de Relatórios::Informes
tags:
  - fisica
  - informe-cientifico
---
> [!note] Pregunta
> ¿Cuándo ayuda una lista en la escritura científica?
===
> [!important] Respuesta
> Cuando hace visibles elementos paralelos o pasos que deben distinguirse; se ordena si la secuencia importa.
```

### Encabezados y jerarquía

> [!definicion] Encabezado
> Título que identifica una parte del argumento y permite localizarla; su nivel indica la relación de esa parte con las secciones que la contienen.[^estructura][^monash]

Reserva los capítulos para las partes amplias del trabajo y usa secciones y subsecciones para separar preguntas o procedimientos concretos. Un encabezado como «Montaje» le dice al lector qué encontrará; «Otros aspectos» no le da esa pista.[^monash]

```anki
deck: Física::Produção de Relatórios::Informes
tags:
  - fisica
  - informe-cientifico
---
> [!note] Pregunta
> ¿Qué debe comunicar un encabezado y su nivel dentro de un informe?
===
> [!important] Respuesta
> El contenido que identifica y su posición en la jerarquía: qué sección lo contiene y qué partes dependen de él.
```

### Referentes, símbolos y unidades

La corrección de la lengua exige que pueda identificarse a qué se refiere cada expresión. Si «la medida» puede designar tanto la longitud como el período, se nombra la magnitud. Los símbolos y abreviaturas se presentan antes de utilizarlos, y las unidades acompañan a los valores correspondientes.[^cap1][^icmje]

Una fórmula destacada facilita inspeccionar una relación, pero la prosa debe identificar sus símbolos y explicar por qué interviene en el procedimiento. Esa información permite relacionar la expresión con las operaciones realmente efectuadas.[^icmje]

```anki
deck: Física::Produção de Relatórios::Informes
tags:
  - fisica
  - informe-cientifico
---
> [!note] Pregunta
> ¿Cómo se evita la ambigüedad al nombrar magnitudes y utilizar símbolos en un informe?
===
> [!important] Respuesta
> Se nombra la magnitud cuando el referente pueda confundirse, se definen símbolos y abreviaturas antes de usarlos y se declaran las unidades de los valores.
```

### Revisión funcional

Al revisar, sigue el argumento y luego mira el informe tal como quedó compuesto. Pregúntate si cada conclusión se apoya en datos; después comprueba que las leyendas y las referencias señalen las figuras correctas.[^cap1][^sheffield]

> [!procedimiento] Reconstruir y revisar el argumento
> 1. Comprobar que cada objetivo recibe una respuesta identificable.
> 2. Localizar los resultados que sostienen cada conclusión.
> 3. Comprobar que el método permite reconstruir cómo se obtuvo esa evidencia.
> 4. Revisar que tablas, figuras y texto cumplen funciones complementarias.
> 5. Comprobar en el documento final la correspondencia de títulos, referencias y leyendas, además de unidades y corrección de la lengua.[^cap1][^estructura][^sheffield]

==Si los datos sostienen una afirmación más modesta, reduce el alcance de la conclusión.== Cuando falte un detalle del procedimiento, búscalo en el cuaderno o registro de laboratorio: pulir la frase no permite recuperar una medida que nunca se anotó.[^icmje][^sheffield]

```anki
deck: Física::Produção de Relatórios::Informes
tags:
  - fisica
  - informe-cientifico
---
> [!note] Pregunta
> ¿Cómo se completa un método experimental al que le faltan datos del procedimiento?
===
> [!important] Respuesta
> Se recupera la información del registro experimental. Si no está disponible, se declara la ausencia; no se inventan operaciones, valores ni características del instrumento.
```

```anki
deck: Física::Produção de Relatórios::Informes
tags:
  - fisica
  - informe-cientifico
---
> [!note] Pregunta
> ¿Cómo se revisa la relación entre objetivos, método, resultados y conclusiones de un informe?
===
> [!important] Respuesta
> Se comprueba que cada objetivo recibe respuesta, que los resultados sostienen cada conclusión y que el método permite reconstruir cómo se obtuvo esa evidencia.
```

```anki
deck: Física::Produção de Relatórios::Informes
tags:
  - fisica
  - informe-cientifico
---
> [!note] Pregunta
> ¿Qué correspondencias deben comprobarse en el documento final de un informe científico?
===
> [!important] Respuesta
> Que texto, tablas y figuras se complementen; que sus títulos, referencias y leyendas correspondan; y que unidades, símbolos y lengua permitan interpretar la información sin ambigüedad.
```

## Práctica con soluciones razonadas

### Clasificar, reparar y adaptar

#### Ejercicio 1 — Clasificar afirmaciones

> [!ejemplo] Enunciado
> Clasifica y justifica la ubicación de estas afirmaciones:
>
> a) «Se realizaron cinco medidas con un cronómetro de resolución $0{,}01\ \mathrm{s}$».
>
> b) «Los valores registrados fueron entre $1{,}40$ y $1{,}44\ \mathrm{s}$».
>
> c) «La discrepancia podría deberse al rozamiento».

> [!resolucion]- Resolución
> **a) Método.** Declara una operación, su repetición y una característica del instrumento. La resolución indicada no determina por sí sola toda la incertidumbre del cronometraje manual.
>
> **b) Resultados.** Comunica el intervalo de valores registrados e identifica la unidad.
>
> **c) Discusión.** Propone una interpretación causal. El condicional conserva su carácter hipotético, pero debe justificarse por qué el rozamiento constituye una explicación plausible y qué permitiría distinguirlo de otras causas.

#### Ejercicio 2 — Reparar un método insuficiente

> [!ejemplo] Enunciado
> «Medimos el péndulo y dio bien». Redacta una versión informativa sin inventar valores ni características del instrumento. Identifica la información que falta.

> [!resolucion]- Resolución
> Una formulación provisional que conserva únicamente lo declarado es: «Se midió el péndulo; faltan por identificar la magnitud medida y el procedimiento empleado».
>
> «Medimos el péndulo» no permite saber si se midió su longitud, su período u otra magnitud, ni con qué instrumento o cuántas veces. Para redactar un método suficiente deben recuperarse del registro experimental la magnitud, las condiciones del montaje, los instrumentos, las operaciones, el número de medidas y el tratamiento de datos. Si se trató de un cronometraje, también debe precisarse el intervalo cronometrado.
>
> «Dio bien» tampoco establece un resultado evaluable: falta identificar la comparación realizada y el criterio de compatibilidad. Los datos ausentes no se completan por intuición.

#### Ejercicio 3 — Elegir la estructura por el trabajo

> [!ejemplo] Enunciado
> Un proyecto desarrolla una herramienta informática y la evalúa con datos. Propón un esquema que conserve análisis, diseño e implementación. Después adapta el esquema a una práctica breve de medidas repetidas.

> [!resolucion]- Resolución
> **Proyecto.** Introducción, trabajo relacionado, análisis del problema, diseño de la solución, implementación, resultados y conclusión, con los preliminares, anexos y bibliografía pertinentes. El esquema distingue qué debe resolverse, cómo se organiza la solución, cómo se realizó y qué produjo su evaluación.
>
> **Práctica breve.** Introducción, método, resultados, discusión y conclusiones, con los demás elementos que exija la entrega. Las operaciones de medida se explican en el método; la evidencia y su interpretación reciben funciones diferenciadas.
>
> Ambos esquemas conservan pregunta → procedimiento → evidencia → respuesta. La adaptación responde a las operaciones y decisiones del trabajo.

La organización hace localizable la relación entre procedimiento y evidencia. [[Física/Grado/1º/Produção de Relatórios/02 LaTeX, entorno y fundamentos|LaTeX]] permite representar esa estructura mediante órdenes y automatizar parte de su composición; sigue siendo necesario decidir qué comunica cada sección y cómo sostiene la respuesta al problema.

## 📚 Fuentes

### Material base aportado

[^cap1]: Eugénia Graça — *Produção de Relatórios, capítulo I*, `cap1 - PR - 2026- 2027.pdf`, julio de 2026, pp. físicas 4–5. Organización, lengua y buenas prácticas independientes de la herramienta.
[^estructura]: Eugénia Graça — *Capítulo II, modo texto*, `cap2 - PR -2026-2027.pdf`, pp. físicas 90–92 (diapositivas 88–90); y *Resumo de LaTeX*, `PR - Resumo - 2025 - 2026.pdf`, julio de 2025, pp. físicas 46–47 (impresas 38–39), §1.34. Arquitectura del informe extenso y pauta de resúmenes. Contraste terminológico: `PR - Resumo - INGLES - 2025 - 2026.pdf`, pp. físicas 40–41 (impresas 32–33), §1.30. Materiales locales de la asignatura.

### Ampliación externa

[^sheffield]: University of Sheffield — [How to structure and write lab reports](https://sheffield.ac.uk/study-skills/writing/academic/lab-reports). Funciones de introducción, método, resultados, discusión, conclusiones, resumen, referencias y anexos; organización y comunicación de datos en informes experimentales. Los ejemplos de péndulo y herramienta informática son aplicaciones didácticas.
[^icmje]: ICMJE — [Preparing a Manuscript for Submission](https://www.icmje.org/recommendations/browse/manuscript-preparation/preparing-for-submission.html), apartados 3b–i: resumen, introducción, métodos, resultados, discusión, referencias, tablas y figuras. Principios de descripción suficiente del procedimiento, correspondencia entre afirmaciones y evidencia, y legibilidad de representaciones. Sus requisitos de publicación biomédica no constituyen normas de entrega de FCUL.
[^nist]: J. C. Gust, R. M. Graham y M. A. Lombardi — NIST, [Stopwatch and Timer Calibrations](https://nvlpubs.nist.gov/nistpubs/Legacy/SP/nistspecialpublication960-12e2.pdf), edición de 2009, §5.C, p. impresa 33 (física 47). Se utiliza únicamente la identificación de componentes de incertidumbre del cronometraje, en particular resolución del dispositivo y reacción del operador.
[^cambridge]: University of Cambridge, Computer Laboratory — [The Pink Book: Briefing Document — Projects and Dissertations](https://www.cl.cam.ac.uk/teaching/projects/pinkbook.pdf), octubre de 2019, §§12.5–12.8 y 13.1, pp. 23–25. Contraste de las funciones de trabajo relacionado, análisis de necesidades, diseño, implementación y evaluación en proyectos. Su esquema y sus requisitos de entrega corresponden a Cambridge.
[^parrafo]: University of Sheffield — [How to structure a paragraph](https://sheffield.ac.uk/study-skills/writing/academic/paragraph), apartados «Paragraph structure» y «Unity». Unidad de idea, evidencia y relación con el argumento.
[^monash]: Monash University — [IT: Report](https://www.monash.edu/student-academic-success/excel-at-writing/annotated-assessment-samples/information-technology/it-report), apartado «Body of the report». Uso de párrafos, listas y encabezados informativos, consistentes y jerárquicos en informes.
[^dedicatoria]: University of Michigan-Dearborn, Mardigian Library — [Dedication, Acknowledgements, & Preface](https://guides.umd.umich.edu/Word_for_Theses/Ded_Ack_Pref), en *Formatting Your Thesis or Dissertation with Microsoft Word*. Distinción entre dedicatoria personal y reconocimiento de ayudas recibidas.

## 🧑‍🏫 Prompt para tutor conversacional

Actúa como profesor de Produção de Relatórios para un estudiante de primer curso universitario. Haz una pregunta cada vez y espera su respuesta antes de dar pistas o explicar la solución.

### Conocimientos que debes evaluar

- **Argumento científico.** Ayuda al estudiante a conectar el problema, el procedimiento, los resultados y las conclusiones que la evidencia permite sostener. La estructura cambia según el tipo de trabajo y lo que pide la entrega. Para describir el método, debe incluir materiales, condiciones, operaciones, decisiones y tratamiento suficientes para que otra persona reconstruya el proceso. Recuerda que la resolución de un cronómetro no representa por sí sola toda la incertidumbre de una medida manual.
- **Informe experimental breve.** Comprueba que la introducción sitúe el problema y formule el objetivo; que el método cuente las operaciones; que resultados presente lo observado o calculado; que discusión interprete y examine límites; y que conclusiones respondan hasta donde llega la evidencia. El resumen debe presentar por sí solo el objetivo, el procedimiento, los hallazgos y la conclusión. Si hay versiones en distintos idiomas, deben comunicar las mismas afirmaciones.
- **Informe extenso.** Los preliminares ayudan a identificar y consultar el documento: portada, posible dedicatoria y agradecimientos, resúmenes e índices de contenido, figuras y tablas. El cuerpo desarrolla el argumento. El capítulo de trabajo relacionado sitúa los antecedentes; el análisis concreta el problema; el diseño justifica la solución; la implementación explica cómo se realizó; y los resultados y la conclusión presentan la evidencia y la respuesta. Los anexos guardan detalles complementarios; las citas muestran dónde se usan las fuentes y la bibliografía permite recuperarlas. La pauta docente propone resúmenes de unas 300 palabras en portugués e inglés si el trabajo está en portugués y añade un resumen portugués de al menos 1200 palabras si se redacta en otra lengua. Antes de aplicar esas extensiones, comprueba qué pide la entrega concreta.
- **Representación y escritura.** Usa tablas cuando el lector necesite consultar valores y gráficas para examinar tendencias o dispersión. Una figura puede mostrar datos o el montaje. El texto debe destacar el hallazgo útil para el objetivo; la leyenda explica qué se ve, con sus símbolos, unidades y posibles barras de incertidumbre. Cada párrafo desarrolla una idea. Las listas separan elementos paralelos o pasos, y los encabezados anticipan el contenido y su lugar en la jerarquía. Nombra las magnitudes y los símbolos con claridad.

### Práctica y protocolo

Para practicar, presenta cinco períodos ficticios —1,41; 1,44; 1,42; 1,40 y 1,43 segundos— medidos con una misma longitud. Pregunta qué representación elegiría y por qué esos valores no permiten estudiar cómo cambia el período con la longitud. Después, pídele clasificar frases como método, resultado o interpretación, reparar un método incompleto sin inventar datos, escribir una leyenda y adaptar la estructura de un proyecto a una práctica breve.

Pídele que revise un informe de principio a fin: que relacione cada objetivo con la evidencia, reconstruya el procedimiento y compruebe que el texto cite las figuras y referencias correctas. Separa los problemas de estructura, evidencia, lenguaje y unidades. Corrige con precisión, espera a que lo intente y luego ofrece pistas. Alterna recuperación activa, repetición espaciada, preguntas de profundización y práctica guiada. Continúa con el fuente, la compilación y la estructura de LaTeX.

```dataviewjs
await dv.view("Planes/Estudio/Scripts/study-session", { location: "end" })
```
