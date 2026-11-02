---
title: Búsqueda bibliográfica y referencias
asignatura: Produção de Relatórios
rama:
  - Comunicación científica
  - Documentación académica
tipo:
  - procedimiento
  - teoría
nivel: universitario-introductorio
estado: revisado
capa: curricular
requiere:
  - "[[Física/Grado/1º/Produção de Relatórios/01 Informes y escritura científica|Informes y escritura científica]]"
  - "[[Física/Grado/1º/Produção de Relatórios/02 LaTeX, entorno y fundamentos|LaTeX, entorno y fundamentos]]"
fsrs_goal: Construye una consulta bibliográfica por conceptos, verifica versión y metadatos, y produce citas locales mediante thebibliography o BibTeX, explicando sus archivos y reparando referencias sin resolver.
tags:
  - fisica
  - bibliografia
  - fuentes
  - latex
  - fcul
  - curricular
---

```dataviewjs
await dv.view("Planes/Estudio/Scripts/study-session", { location: "start" })
```

# Búsqueda bibliográfica y referencias

Una bibliografía se construye antes de elegir su formato: comienza con la pregunta que orienta el trabajo y con la selección de documentos pertinentes. La composición en LaTeX resuelve después cómo relacionar las citas con sus entradas. El programa de FCUL distingue expresamente bibliografía y búsqueda bibliográfica; conocer las órdenes no sustituye comprobar qué fuente sostiene cada afirmación.[^programa][^docente]

## Buscar desde una pregunta

### Búsqueda bibliográfica

> [!definicion] Búsqueda bibliográfica
> Procedimiento para localizar documentos pertinentes mediante conceptos, términos de consulta, campos y criterios de selección explícitos.[^busqueda]

«Péndulos» es un tema demasiado amplio para decidir qué artículo sirve a un informe. «Procedimientos para medir el período de un péndulo en laboratorio docente» delimita sistema, magnitud y contexto. Una lista inicial separa los conceptos y reúne sinónimos o equivalentes lingüísticos; después se prueban campos como título, autor o asunto.[^busqueda]

```anki
deck: Física::Produção de Relatórios::Bibliografía
tags:
  - bibliografia
  - fuentes
---
> [!note] Pregunta
> ¿Qué decisiones hacen que una búsqueda bibliográfica responda a una pregunta concreta?
===
> [!important] Respuesta
> Delimitar conceptos, reunir términos equivalentes, elegir campos de consulta y evaluar los documentos mediante criterios explícitos de pertinencia.
```

### Combinación de términos

> [!definicion] Operadores booleanos de búsqueda
> Operaciones que combinan conjuntos de resultados: `AND` exige ambos conceptos; `OR` admite cualquiera; `NOT` excluye resultados que contengan el término indicado.[^busqueda]

```anki
deck: Física::Produção de Relatórios::Bibliografía
tags:
  - bibliografia
  - fuentes
---
> [!note] Pregunta
> ¿Sobre qué actúan los operadores booleanos de una búsqueda bibliográfica?
===
> [!important] Respuesta
> Sobre conjuntos de resultados: permiten pedir coincidencias simultáneas, reunir alternativas o excluir coincidencias.
```

Una consulta ilustrativa es `pendulum AND (period OR oscillation)`. La combinación con `OR` reúne variantes de un concepto; `AND` pide su intersección con el otro. Las comillas buscan una frase y la truncación permite variantes de una raíz cuando el buscador lo admite. Cada plataforma tiene su sintaxis: se comprueba la ayuda antes de trasladar una consulta literalmente.[^busqueda]

> [!advertencia] Exclusión y pérdida de resultados
> `NOT` reduce el conjunto al excluir registros. La página de técnicas de B-on lo describe correctamente como exclusión, aunque contiene después la frase errónea «expande a pesquisa». Una exclusión demasiado amplia puede retirar documentos relevantes que mencionen ambos términos.[^busqueda]

#### AND: coincidencia de conceptos

> [!definicion] AND
> Operador que obtiene la intersección de los resultados: cada registro debe cumplir ambos términos o grupos de consulta.[^busqueda]

`pendulum AND teaching` pide documentos en los que coincidan el péndulo y la enseñanza, dentro de los campos consultados. Añadir una condición con `AND` mantiene o reduce el conjunto de resultados.

```anki
deck: Física::Produção de Relatórios::Bibliografía
tags:
  - bibliografia
  - fuentes
---
> [!note] Pregunta
> ¿Qué condición impone `AND` entre dos conceptos de una búsqueda?
===
> [!important] Respuesta
> Que el resultado cumpla ambos conceptos; obtiene su intersección y no amplía el conjunto.
```

#### OR: alternativas

> [!definicion] OR
> Operador que reúne resultados que cumplen al menos una de las alternativas consultadas.[^busqueda]

Prueba `period OR oscillation` si quieres localizar trabajos que usen cualquiera de esos términos. En `pendulum AND (period OR oscillation)`, los paréntesis agrupan primero las alternativas y luego las combinan con `pendulum`.

```anki
deck: Física::Produção de Relatórios::Bibliografía
tags:
  - bibliografia
  - fuentes
---
> [!note] Pregunta
> ¿Para qué sirven los paréntesis en `pendulum AND (period OR oscillation)`?
===
> [!important] Respuesta
> Para mantener juntas las alternativas unidas por `OR` al combinarlas con el concepto exigido mediante `AND`.
```

```anki
deck: Física::Produção de Relatórios::Bibliografía
tags:
  - bibliografia
  - fuentes
---
> [!note] Pregunta
> ¿Para qué se reúnen términos con `OR` en una consulta bibliográfica?
===
> [!important] Respuesta
> Para recuperar resultados que contengan al menos una alternativa, como sinónimos o variantes lingüísticas de un concepto.
```

#### NOT: exclusión

> [!definicion] NOT
> Operador que retira los resultados que cumplen la condición excluida.[^busqueda]

Si buscas trabajos sobre prácticas docentes, `NOT teaching` podría quitar justo los textos que te interesan. Mira qué resultados desaparecen antes de mantener la exclusión y pregúntate si tiene sentido para tu objetivo.

```anki
deck: Física::Produção de Relatórios::Bibliografía
tags:
  - bibliografia
  - fuentes
---
> [!note] Pregunta
> ¿Qué riesgo tiene usar `NOT` con un término próximo al objetivo de búsqueda?
===
> [!important] Respuesta
> Puede excluir documentos pertinentes que mencionen ese término; reduce resultados y requiere comprobar qué evidencia se pierde.
```

### Campos, frases y truncación

#### Campo de búsqueda

> [!definicion] Campo de búsqueda
> Parte del registro en la que se busca un término, como título, autor o asunto.[^busqueda]

Buscar un apellido en autor resuelve una pregunta distinta de buscarlo en cualquier parte del registro. La elección del campo depende de si se quiere localizar una obra conocida o descubrir trabajos sobre un tema.

```anki
deck: Física::Produção de Relatórios::Bibliografía
tags:
  - bibliografia
  - fuentes
---
> [!note] Pregunta
> ¿Qué restringe elegir un campo como título o autor en una búsqueda bibliográfica?
===
> [!important] Respuesta
> La parte del registro en la que debe aparecer el término, según la pregunta que se intenta resolver.
```

#### Búsqueda de frase

> [!definicion] Búsqueda de frase
> Consulta que pide una secuencia de palabras juntas en el orden indicado, habitualmente mediante comillas.[^busqueda]

Al escribir `"simple pendulum"` pides la expresión completa, no dos palabras que aparezcan por separado. Consulta la ayuda de la plataforma para saber cómo trata las comillas, los signos y las variantes.

```anki
deck: Física::Produção de Relatórios::Bibliografía
tags:
  - bibliografia
  - fuentes
---
> [!note] Pregunta
> ¿Qué se pretende al poner una expresión entre comillas en una búsqueda bibliográfica?
===
> [!important] Respuesta
> Recuperar la secuencia como frase, con las palabras juntas y en ese orden, según la sintaxis de la plataforma.
```

#### Truncación

> [!definicion] Truncación
> Consulta que utiliza una raíz y un símbolo admitido por el buscador para recuperar distintas terminaciones.[^busqueda]

Una raíz excesivamente corta recupera familias de palabras ajenas al objetivo. El símbolo y sus límites se comprueban en la plataforma: no se supone que cualquier buscador interprete el mismo carácter de igual manera.

```anki
deck: Física::Produção de Relatórios::Bibliografía
tags:
  - bibliografia
  - fuentes
---
> [!note] Pregunta
> ¿Qué permite la truncación y qué debe comprobarse antes de utilizarla?
===
> [!important] Respuesta
> Recuperar variantes de una raíz; se comprueban el símbolo admitido y la amplitud de la raíz para evitar resultados ajenos al objetivo.
```

#### Ejemplo — Una consulta que puede revisarse

Busca estudios sobre enseñanza experimental del péndulo. Empieza con `pendulum AND teaching` y revisa títulos y resúmenes. Si necesitas acotar el método, añade un término; si encuentras una palabra más adecuada, anótala y prueba otra consulta. Muchos resultados no significan que la búsqueda haya cubierto todas las formas de nombrar el tema.

Para que otra persona pueda repetir la búsqueda, apunta la base, la fecha, la consulta y los filtros que usaste. Si restringes los años, explica por qué: quizá te interese la tecnología actual, un antecedente histórico o las dos cosas. Elige el alcance pensando en la pregunta, no en cuántos documentos te apetece leer.[^busqueda]

```anki
deck: Física::Produção de Relatórios::Bibliografía
tags:
  - bibliografia
  - fuentes
---
> [!note] Pregunta
> ¿Qué se registra para poder reconstruir una búsqueda bibliográfica?
===
> [!important] Respuesta
> El recurso consultado, la fecha, la expresión de búsqueda y los filtros, junto con la razón de las restricciones relevantes.
```

### B-on y recursos de FCUL

> [!definicion] B-on
> Biblioteca do Conhecimento Online: servicio de descubrimiento y acceso a recursos electrónicos que ofrece revistas, libros y bases de datos a la comunidad de instituciones participantes.[^bon]

```anki
deck: Física::Produção de Relatórios::Bibliografía
tags:
  - bibliografia
  - fuentes
---
> [!note] Pregunta
> ¿Qué servicio ofrece B-on a las instituciones participantes?
===
> [!important] Respuesta
> Descubrimiento y acceso institucional a recursos electrónicos, incluidas revistas, libros y bases de datos.
```

La Biblioteca de Ciências ofrece el catálogo de ULisboa, portales de búsqueda, repositorios y bases bibliográficas. El catálogo sirve para identificar una obra; una base recupera registros; un repositorio puede dar acceso al documento depositado. Que encuentres la referencia no significa que tengas disponible el texto completo.[^biblioteca]

Algunos recursos de Ciências solo se abren desde la red institucional. Si estás fuera, la biblioteca indica conectarte por VPN y usar una cuenta Ciências. El acceso también depende de las condiciones del recurso; iniciar sesión en un buscador no siempre sustituye esa conexión.[^biblioteca]

```anki
deck: Física::Produção de Relatórios::Bibliografía
tags:
  - bibliografia
  - fuentes
---
> [!note] Pregunta
> ¿Cómo indica la biblioteca de Ciências que se accede desde fuera a sus recursos restringidos?
===
> [!important] Respuesta
> Mediante VPN y una cuenta Ciências, según las condiciones institucionales del recurso; localizar un registro no garantiza acceso al texto completo.
```

#### Catálogo

> [!definicion] Catálogo bibliográfico
> Sistema de registros que permite identificar y localizar obras dentro de una colección o conjunto de colecciones.[^biblioteca]

El catálogo de ULisboa ayuda a localizar una obra conocida y sus ejemplares o formas de acceso. Su función se distingue del contenido completo de la obra.

```anki
deck: Física::Produção de Relatórios::Bibliografía
tags:
  - bibliografia
  - fuentes
---
> [!note] Pregunta
> ¿Qué permite localizar un catálogo bibliográfico?
===
> [!important] Respuesta
> Obras y sus formas de localización o acceso en una colección, mediante sus registros descriptivos.
```

#### Base bibliográfica

> [!definicion] Base de datos bibliográfica
> Conjunto organizado de registros de documentos que puede consultarse mediante términos, campos y filtros.[^biblioteca]

Una base temática puede encontrar artículos de distintas revistas. Usa el registro para decidir cuáles consultar y abre el documento antes de valorar sus métodos y resultados.

```anki
deck: Física::Produção de Relatórios::Bibliografía
tags:
  - bibliografia
  - fuentes
---
> [!note] Pregunta
> ¿Qué se consulta en una base de datos bibliográfica antes de abrir los documentos?
===
> [!important] Respuesta
> Registros organizados que describen documentos y se recuperan mediante términos, campos y filtros.
```

#### Repositorio

> [!definicion] Repositorio académico
> Servicio que conserva y pone a disposición documentos depositados, con sus metadatos y condiciones de acceso.[^biblioteca]

La versión depositada debe identificarse: puede no coincidir con la publicación final del editor. Acceso disponible y versión utilizada son comprobaciones separadas.

```anki
deck: Física::Produção de Relatórios::Bibliografía
tags:
  - bibliografia
  - fuentes
---
> [!note] Pregunta
> ¿Qué ofrece un repositorio académico y qué debe comprobarse al utilizar un documento depositado?
===
> [!important] Respuesta
> Conserva documentos y metadatos; se comprueban el acceso y la versión concreta, que puede diferir de la publicada por el editor.
```

### Evaluación del documento recuperado

> [!definicion] Fuente pertinente
> Documento cuyo contenido aporta evidencia, un método o una explicación que responde a una necesidad concreta del argumento.[^programa][^icmje]

Cuando tengas el documento, mira qué estudia, cómo obtiene sus resultados y qué límites reconoce. Una revisión ayuda a orientarse y comparar; si atribuyes una afirmación a un estudio original, consulta ese estudio cuando sea posible. Las referencias de un artículo útil pueden llevarte a antecedentes, pero revisa cada obra antes de incluirla.[^icmje]

```anki
deck: Física::Produção de Relatórios::Bibliografía
tags:
  - bibliografia
  - fuentes
---
> [!note] Pregunta
> ¿Qué hace pertinente a una fuente para un informe?
===
> [!important] Respuesta
> Que su contenido responda a una necesidad concreta del argumento mediante evidencia, un método o una explicación, dentro de sus límites.
```

```anki
deck: Física::Produção de Relatórios::Bibliografía
tags:
  - bibliografia
  - fuentes
---
> [!note] Pregunta
> ¿Qué se comprueba antes de atribuir a un estudio original un resultado conocido mediante una revisión?
===
> [!important] Respuesta
> El pasaje del estudio original, su alcance y sus límites, cuando sea accesible; la revisión no demuestra por sí sola que la atribución sea fiel.
```

## Identificar la obra y atribuir su uso

### Metadatos bibliográficos

> [!definicion] Metadatos bibliográficos
> Datos que identifican y describen una obra: autoría, título, fecha, tipo de documento y publicación; según el caso, editorial, volumen, número, páginas o identificadores.[^docente][^crossref]

Los campos dependen del tipo de obra. Para un artículo anota la revista y las páginas; para un libro, la editorial y la edición; en un manual técnico, puede importar la versión. La exportación automática ahorra tiempo, pero compárala con la obra y con el registro editorial. Un formato ordenado no corrige un autor o un año equivocados.

```anki
deck: Física::Produção de Relatórios::Bibliografía
tags:
  - bibliografia
  - fuentes
---
> [!note] Pregunta
> ¿Qué son los metadatos bibliográficos y cómo se comprueba una exportación automática?
===
> [!important] Respuesta
> Datos que identifican y describen una obra; se comparan con el documento y el registro editorial, según su tipo y versión.
```

### DOI y versión

> [!definicion] DOI
> Identificador persistente de un objeto registrado. Permite localizar su registro y relacionarlo con metadatos; no certifica por sí solo la calidad de la investigación.[^crossref]

Crossref ofrece recuperación de metadatos e identificadores. Al usar un DOI se comprueba que corresponda al título, los autores y la versión citada. Un manuscrito depositado, una publicación anticipada y la versión de revista pueden mostrar fechas o datos de publicación distintos. La entrada debe describir la versión realmente utilizada.[^crossref]

```anki
deck: Física::Produção de Relatórios::Bibliografía
tags:
  - bibliografia
  - fuentes
---
> [!note] Pregunta
> ¿Qué acredita y qué no acredita el DOI de una obra científica?
===
> [!important] Respuesta
> Identifica un objeto registrado y permite localizarlo; no acredita por sí solo la calidad de sus resultados ni que sus metadatos exportados sean correctos.
```

#### Ejemplo — Dos años para una misma búsqueda

Supón que el gestor bibliográfico muestra un año y el PDF otro. No elijas automáticamente el más reciente. Abre el registro del DOI, averigua si aparecen fechas distintas para la publicación en línea y para el volumen, y comprueba qué versión consultaste. Corrige la referencia para que describa esa versión; si la diferencia sigue sin aclararse, déjala identificada antes de usar el dato.

#### Versión del documento

> [!definicion] Versión bibliográfica
> Estado identificable del documento utilizado, como manuscrito depositado, publicación anticipada o versión final de revista. Sus datos de identificación deben corresponder al ejemplar consultado.[^crossref]

```anki
deck: Física::Produção de Relatórios::Bibliografía
tags:
  - bibliografia
  - fuentes
---
> [!note] Pregunta
> ¿Qué identifica la versión bibliográfica de un documento?
===
> [!important] Respuesta
> El estado concreto utilizado —como manuscrito, publicación anticipada o versión final—, al que deben corresponder los metadatos de la referencia.
```

```anki
deck: Física::Produção de Relatórios::Bibliografía
tags:
  - bibliografia
  - fuentes
---
> [!note] Pregunta
> ¿Cómo se resuelve una discrepancia de años entre un documento y un registro bibliográfico?
===
> [!important] Respuesta
> Identificando la versión consultada y los tipos de fecha —como publicación electrónica o de volumen—, y describiendo esa versión sin escoger un año por apariencia.
```

### Cita local y referencia final

> [!definicion] Cita bibliográfica
> Marca colocada junto a una idea, dato o procedimiento que identifica la fuente de la que procede. La entrada final proporciona la información para recuperar esa obra.[^docente]

```anki
deck: Física::Produção de Relatórios::Bibliografía
tags:
  - bibliografia
  - fuentes
---
> [!note] Pregunta
> ¿Qué función cumple una cita bibliográfica próxima a una afirmación?
===
> [!important] Respuesta
> Identifica qué fuente sostiene esa idea, dato o procedimiento y delimita su atribución.
```

#### Referencia bibliográfica

> [!definicion] Referencia bibliográfica
> Descripción de una obra con los datos necesarios para identificarla y recuperarla, conforme al estilo utilizado.[^docente][^icmje]

```anki
deck: Física::Produção de Relatórios::Bibliografía
tags:
  - bibliografia
  - fuentes
---
> [!note] Pregunta
> ¿Qué aporta la referencia bibliográfica final de una obra?
===
> [!important] Respuesta
> Sus datos de identificación y recuperación; se conecta con las citas que atribuyen usos concretos de esa obra.
```

La bibliografía final enumera las obras, pero no indica qué afirmación depende de cada una. Pon la cita junto a la oración, el dato, la imagen o el método que tomaste. Después revisa las dos direcciones: que cada cita tenga su entrada y que la fuente realmente respalde la atribución.[^icmje]

```anki
deck: Física::Produção de Relatórios::Bibliografía
tags:
  - bibliografia
  - fuentes
---
> [!note] Pregunta
> ¿Por qué no basta una bibliografía al final de un informe para atribuir un resultado ajeno?
===
> [!important] Respuesta
> Porque la cita próxima al resultado indica qué fuente concreta lo respalda; la lista final sólo identifica las obras usadas.
```

## Bibliografía manual en LaTeX

### thebibliography y bibitem

> [!definicion] Bibliografía manual
> Lista de entradas redactadas dentro de `thebibliography`, cada una introducida por `\bibitem{clave}` y citada desde la prosa con `\cite{clave}`.[^docente]

```anki
deck: Física::Produção de Relatórios::Bibliografía
tags:
  - bibliografia
  - bibtex
---
> [!note] Pregunta
> ¿Qué caracteriza una bibliografía manual en LaTeX?
===
> [!important] Respuesta
> Sus entradas se redactan en el propio `.tex`, dentro de `thebibliography`, y cada una se introduce con `\bibitem`.
```

La clave es un nombre interno que eliges para reconocer cada entrada. Puedes combinar apellido y año, pero la clave no es el número que saldrá impreso ni tiene por qué ser el DOI.

```latex
\documentclass{article}
\begin{document}
O resumo docente apresenta o manual de Lamport na sua bibliografia
\cite{Lamport1994}.
\begin{thebibliography}{99}
  \bibitem{Lamport1994}
  Leslie Lamport, \emph{LaTeX: A Document Preparation System},
  2nd ed., Addison-Wesley, 1994.
\end{thebibliography}
\end{document}
```

Los datos de esta entrada proceden de la bibliografía del resumen docente. El ejemplo enseña una cita a esa identificación bibliográfica; no atribuye al libro un pasaje que no se haya consultado.[^docente]

#### Entorno thebibliography

> [!definicion] thebibliography
> Entorno que compone la lista bibliográfica a partir de las entradas escritas en su interior.[^docente]

```anki
deck: Física::Produção de Relatórios::Bibliografía
tags:
  - bibliografia
  - bibtex
---
> [!note] Pregunta
> ¿Qué se coloca dentro de `thebibliography` en LaTeX?
===
> [!important] Respuesta
> Las entradas bibliográficas manuales, cada una iniciada con `\bibitem{clave}` y seguida de los datos de la obra.
```

#### Entrada con bibitem

> [!definicion] bibitem
> Orden que inicia una entrada bibliográfica manual y le asigna la clave utilizada para citarla.[^docente]

```anki
deck: Física::Produção de Relatórios::Bibliografía
tags:
  - bibliografia
  - bibtex
---
> [!note] Pregunta
> ¿Qué relación establece `\bibitem{clave}` en una bibliografía manual LaTeX?
===
> [!important] Respuesta
> Inicia una entrada y asocia sus datos con la clave que utilizarán las citas.
```

#### Clave bibliográfica

> [!definicion] Clave bibliográfica
> Identificador interno de una entrada, compartido por la declaración de la obra y las órdenes que la citan. Debe coincidir exactamente en ambos lugares.[^docente]

La clave `Lamport1994` hace reconocible la entrada, pero su texto no determina por sí mismo el año ni el número impreso. Los metadatos siguen siendo los campos de la referencia.

```anki
deck: Física::Produção de Relatórios::Bibliografía
tags:
  - bibliografia
  - bibtex
---
> [!note] Pregunta
> ¿Qué debe coincidir entre una cita y la entrada bibliográfica de LaTeX?
===
> [!important] Respuesta
> La clave interna, carácter por carácter; no tiene que coincidir con un DOI ni con el número impreso de la referencia.
```

#### Cita con cite

`\cite{Lamport1994}` pide al sistema bibliográfico que inserte la cita asociada a esa clave. Tras compilar, mira que la referencia impresa corresponda a la obra esperada. Si escribes la clave como texto normal, LaTeX no la tratará como una cita.[^docente]

```anki
deck: Física::Produção de Relatórios::Bibliografía
tags:
  - bibliografia
  - bibtex
---
> [!note] Pregunta
> ¿Cómo se solicita desde la prosa una entrada bibliográfica en el esquema LaTeX docente?
===
> [!important] Respuesta
> Con `\cite{clave}`, usando la misma clave que identifica la entrada.
```

### Anchura de las etiquetas

> [!definicion] Argumento de thebibliography
> Modelo de etiqueta que permite reservar anchura para las etiquetas de la lista. `{99}` reserva el ancho de una etiqueta de dos cifras; no fija un máximo de 99 referencias.[^manual]

El material lo describe como número máximo de entradas. La interpretación técnica correcta evita una decisión equivocada: la cantidad de obras la determina el contenido de la lista. Para etiquetas de una cifra suele bastar `{9}`; la selección debe acomodar la etiqueta más ancha prevista.

```anki
deck: Física::Produção de Relatórios::Bibliografía
tags:
  - bibliografia
  - bibtex
---
> [!note] Pregunta
> ¿Qué significa el argumento `{99}` de `thebibliography`?
===
> [!important] Respuesta
> Reserva la anchura de una etiqueta de dos cifras; no establece un máximo de 99 obras.
```

## Base bibliográfica y procesamiento con BibTeX

### Archivo bib y tipos de entrada

> [!definicion] Base bibliográfica
> Archivo `.bib` que reúne entradas estructuradas, cada una con un tipo, una clave y campos. Separa los datos de las obras de su presentación en el documento.[^docente]

```anki
deck: Física::Produção de Relatórios::Bibliografía
tags:
  - bibliografia
  - bibtex
---
> [!note] Pregunta
> ¿Qué contiene una base bibliográfica `.bib`?
===
> [!important] Respuesta
> Entradas estructuradas con tipo, clave y campos; conserva los datos de las obras separados del estilo de presentación.
```

| Tipo | Objeto que representa | Campos pertinentes de ejemplo |
|---|---|---|
| `article` | Artículo de revista. | `author`, `title`, `journal`, `year`, `volume`, `pages`. |
| `book` | Libro. | `author` o `editor`, `title`, `publisher`, `year`, `edition`. |
| `inbook` | Parte de un libro. | Datos del libro y localización por `chapter` o `pages`. |
| `manual` | Documentación técnica. | `title`, autoría u organización y datos de versión o fecha disponibles. |

El material presenta esos cuatro tipos y campos como `author`, `title`, `publisher`, `address` y `year`. No todos tienen la misma función en todos los tipos: `address` suele identificar el lugar de publicación, y `publisher` no reemplaza el campo `journal` de un artículo.[^docente]

Un archivo llamado `fuentes.bib` puede contener:

```bibtex
@book{Lamport1994,
  author    = {Lamport, Leslie},
  title     = {{LaTeX}: A Document Preparation System},
  edition   = {2},
  publisher = {Addison-Wesley},
  address   = {Reading, Massachusetts},
  year      = {1994}
}
```

Las llaves adicionales en `{LaTeX}` protegen su grafía frente a estilos que cambian mayúsculas. En entradas con varios autores se separan sus nombres mediante `and`, para que el procesador identifique correctamente cada persona.[^bibexterna]

```anki
deck: Física::Produção de Relatórios::Bibliografía
tags:
  - bibliografia
  - bibtex
---
> [!note] Pregunta
> ¿Para qué se utilizan llaves adicionales alrededor de una grafía como `{LaTeX}` dentro de un título BibTeX?
===
> [!important] Respuesta
> Para proteger su capitalización frente a estilos que cambian las mayúsculas del título.
```

```anki
deck: Física::Produção de Relatórios::Bibliografía
tags:
  - bibliografia
  - bibtex
---
> [!note] Pregunta
> ¿Cómo se separan varios autores en el campo `author` de BibTeX?
===
> [!important] Respuesta
> Mediante `and`, para que el procesador reconozca los nombres como autores distintos.
```

#### Tipo article

> [!definicion] Entrada article
> Tipo bibliográfico para un artículo de revista; identifica, entre otros datos, título, autoría, revista y año.[^docente]

En un artículo, `journal` indica la revista y `volume`, `number` y `pages` sitúan el texto cuando esos datos existen. No pongas ahí la editorial de un libro: no ocupa el lugar de la revista.

```anki
deck: Física::Produção de Relatórios::Bibliografía
tags:
  - bibliografia
  - bibtex
---
> [!note] Pregunta
> ¿Cuándo se elige el tipo `article` en BibTeX y qué campo identifica su revista?
===
> [!important] Respuesta
> Para un artículo de revista; `journal` identifica la revista y los demás campos describen su autoría, título, fecha y ubicación.
```

#### Tipo book

> [!definicion] Entrada book
> Tipo bibliográfico para un libro, con título, autores o personas editoras, editorial y año, además de los datos de edición pertinentes.[^docente][^patashnik]

La entrada de Lamport muestra este tipo. `publisher` identifica la editorial; `edition` diferencia una edición de otra.

```anki
deck: Física::Produção de Relatórios::Bibliografía
tags:
  - bibliografia
  - bibtex
---
> [!note] Pregunta
> ¿Qué objeto describe una entrada `book` de BibTeX?
===
> [!important] Respuesta
> Un libro; sus datos incluyen título, autores o personas editoras, editorial, año y la edición utilizada cuando corresponda.
```

#### Tipo inbook

> [!definicion] Entrada inbook
> Tipo bibliográfico para una parte identificable de un libro mediante un capítulo o intervalo de páginas, junto con los datos del libro.[^docente]

Indica la página o sección concreta que consultaste; una referencia al volumen entero puede no bastar para que el lector encuentre el pasaje.

```anki
deck: Física::Produção de Relatórios::Bibliografía
tags:
  - bibliografia
  - bibtex
---
> [!note] Pregunta
> ¿Qué distingue el uso de `inbook` del uso de `book` en BibTeX?
===
> [!important] Respuesta
> `inbook` identifica una parte mediante capítulo o páginas, además de describir el libro que la contiene.
```

#### Tipo manual

> [!definicion] Entrada manual
> Tipo bibliográfico para documentación técnica, descrita mediante título, autoría u organización y los datos de versión o fecha disponibles.[^docente]

La versión importa cuando una orden o un comportamiento cambian entre ediciones del programa documentado.

```anki
deck: Física::Produção de Relatórios::Bibliografía
tags:
  - bibliografia
  - bibtex
---
> [!note] Pregunta
> ¿Qué objeto describe el tipo `manual` de BibTeX?
===
> [!important] Respuesta
> Documentación técnica, cuya identificación conserva título, autoría u organización y fecha o versión disponibles.
```

### Estilo y selección de citas

#### Sintaxis de las entradas

La forma general es `@tipo{clave, campo = {valor}, ...}`. El signo `@` precede al tipo; la clave identifica el registro. La forma «Tipo@» del material invierte ese orden. Las siguientes entradas son **plantillas esquemáticas**, no referencias a obras reales:[^docente][^patashnik]

```bibtex
@article{clave-articulo,
  author  = {Apellido, Nombre},
  title   = {Título del artículo},
  journal = {Nombre de la revista},
  year    = {AAAA},
  volume  = {V},
  number  = {N},
  pages   = {inicio--fin}
}

@inbook{clave-parte,
  author    = {Apellido, Nombre},
  title     = {Título del libro},
  chapter   = {capítulo},
  publisher = {Nombre de la editorial},
  year      = {AAAA}
}

@manual{clave-manual,
  title        = {Título del manual},
  organization = {Organización responsable},
  edition      = {Edición},
  year         = {AAAA}
}
```

Los valores se sustituyen por metadatos comprobados. Un campo opcional desconocido se omite; no se rellena con un dato inventado para que la entrada parezca completa.

```anki
deck: Física::Produção de Relatórios::Bibliografía
tags:
  - bibliografia
  - bibtex
---
> [!note] Pregunta
> ¿Cuál es la sintaxis general de una entrada BibTeX?
===
> [!important] Respuesta
> `@tipo{clave, campo = {valor}, ...}`: primero el signo `@`, después tipo, clave y campos.
```

#### Campos de publicación

`editor` identifica personas responsables de la edición intelectual; `publisher` identifica la editorial. `edition` describe la edición del libro, como segunda edición. `address` suele indicar el lugar o dirección de la editorial o institución. En artículos, `volume`, `number` y `pages` localizan el texto dentro de la revista.[^patashnik]

```anki
deck: Física::Produção de Relatórios::Bibliografía
tags:
  - bibliografia
  - bibtex
---
> [!note] Pregunta
> ¿Qué diferencia los campos `editor` y `publisher` en BibTeX?
===
> [!important] Respuesta
> `editor` identifica personas editoras; `publisher` identifica la editorial que publica la obra.
```

```anki
deck: Física::Produção de Relatórios::Bibliografía
tags:
  - bibliografia
  - bibtex
---
> [!note] Pregunta
> ¿Qué describe el campo `edition` de un libro en BibTeX?
===
> [!important] Respuesta
> La edición utilizada, como segunda edición; no identifica a las personas editoras.
```

```anki
deck: Física::Produção de Relatórios::Bibliografía
tags:
  - bibliografia
  - bibtex
---
> [!note] Pregunta
> ¿Qué información suele aportar el campo `address` en una entrada BibTeX?
===
> [!important] Respuesta
> El lugar o dirección de la editorial o de la institución correspondiente, según el tipo de obra.
```

```anki
deck: Física::Produção de Relatórios::Bibliografía
tags:
  - bibliografia
  - bibtex
---
> [!note] Pregunta
> ¿Qué localizan `volume`, `number` y `pages` en una entrada de artículo BibTeX?
===
> [!important] Respuesta
> El volumen, número y páginas del artículo dentro de la revista, cuando esos datos existen.
```

#### Procesamiento con BibTeX

> [!definicion] BibTeX
> Programa que lee información bibliográfica solicitada por el documento, extrae las entradas de las bases indicadas y genera una bibliografía según un estilo.[^docente]

En el documento principal se escribe:

```latex
\documentclass{article}
\begin{document}
O resumo docente identifica o manual de Lamport \cite{Lamport1994}.
\bibliographystyle{plain}
\bibliography{fuentes}
\end{document}
```

`\bibliographystyle{plain}` selecciona el estilo y `\bibliography{fuentes}` identifica la base sin su extensión. Por defecto se extraen las entradas citadas; tener cien obras en la base no obliga a imprimirlas todas. El nombre de la clave debe coincidir exactamente con el de la entrada.[^docente]

La grafía `\bibliographynome` que aparece en el resumen no corresponde a la orden de selección de base del flujo mostrado; la forma utilizada es `\bibliography{fuentes}`.[^docente][^bibexterna]

```anki
deck: Física::Produção de Relatórios::Bibliografía
tags:
  - bibliografia
  - bibtex
---
> [!note] Pregunta
> ¿Qué tarea realiza BibTeX dentro de la preparación de una bibliografía?
===
> [!important] Respuesta
> Lee las peticiones del documento, extrae las entradas solicitadas de las bases indicadas y genera su presentación según un estilo.
```

#### Estilo bibliográfico

> [!definicion] Estilo bibliográfico
> Conjunto de reglas que determina la presentación de las referencias. En el flujo BibTeX docente se selecciona mediante `\bibliographystyle` y se implementa en un archivo `.bst`.[^docente]

La base conserva los datos; el estilo decide su orden y forma de presentación. Cambiar `plain` por otro estilo disponible no modifica por sí mismo los metadatos de la obra.

```anki
deck: Física::Produção de Relatórios::Bibliografía
tags:
  - bibliografia
  - bibtex
---
> [!note] Pregunta
> ¿Qué selecciona `\bibliographystyle{plain}` en el flujo BibTeX?
===
> [!important] Respuesta
> Las reglas de presentación de la bibliografía, implementadas por el estilo `.bst`; no selecciona la base de datos.
```

```anki
deck: Física::Produção de Relatórios::Bibliografía
tags:
  - bibliografia
  - bibtex
---
> [!note] Pregunta
> ¿Cómo se identifica la base `fuentes.bib` en el flujo BibTeX clásico de LaTeX?
===
> [!important] Respuesta
> Con `\bibliography{fuentes}`, sin la extensión `.bib`; se extraen ordinariamente las entradas citadas mediante sus claves.
```

### Archivos y secuencia de compilación

> [!definicion] Bibliografía generada
> Archivo `.bbl` construido por BibTeX a partir de las citas registradas en `.aux`, los datos `.bib` y el estilo `.bst`, e incorporado después por LaTeX.[^docente]

El recorrido habitual es **LaTeX → BibTeX → LaTeX → LaTeX**. La primera pasada registra las citas; BibTeX prepara la bibliografía, y las dos últimas pasadas incorporan las entradas y estabilizan las referencias. Si algo falla, revisa el registro: ahí pueden aparecer claves inexistentes o campos problemáticos.[^docente][^bibexterna]

```anki
deck: Física::Produção de Relatórios::Bibliografía
tags:
  - bibliografia
  - bibtex
---
> [!note] Pregunta
> ¿Qué es el archivo `.bbl` del flujo BibTeX?
===
> [!important] Respuesta
> La bibliografía generada a partir de las peticiones `.aux`, los datos `.bib` y el estilo `.bst`, que LaTeX incorpora al documento.
```

```anki
deck: Física::Produção de Relatórios::Bibliografía
tags:
  - bibliografia
  - bibtex
---
> [!note] Pregunta
> ¿Qué secuencia actualiza una bibliografía del flujo BibTeX y por qué incluye varias pasadas?
===
> [!important] Respuesta
> LaTeX → BibTeX → LaTeX → LaTeX: registra las peticiones, genera las entradas, las incorpora y estabiliza sus referencias.
```

```anki
deck: Física::Produção de Relatórios::Bibliografía
tags:
  - bibliografia
  - bibtex
---
> [!note] Pregunta
> ¿Qué cambia entre `thebibliography` y BibTeX al preparar la bibliografía de un documento LaTeX?
===
> [!important] Respuesta
> `thebibliography` contiene entradas `\bibitem` escritas en el `.tex`; BibTeX extrae de una base `.bib` las entradas citadas y exige una pasada propia entre compilaciones de LaTeX.
```

### Bibliografía en el índice

> [!definicion] Entrada bibliográfica del índice
> Registro que permite localizar la sección de bibliografía desde el índice de contenido, independiente de las citas que remiten a obras.[^docente]

El material propone `\usepackage[nottoc,numbib,notlot,notlof]{tocbibind}`. `numbib` solicita una bibliografía numerada; `nottoc`, `notlot` y `notlof` evitan incorporar el propio índice de contenido y las listas de tablas y figuras. Una alternativa manual en `article` es colocar `\addcontentsline{toc}{section}{Bibliografia}` junto al comienzo de la bibliografía. Se elige una vía para evitar entradas duplicadas, se recompila y se comprueba título y página.[^docente]

```anki
deck: Física::Produção de Relatórios::Bibliografía
tags:
  - bibliografia
  - bibtex
---
> [!note] Pregunta
> ¿Qué permite localizar la entrada de bibliografía en el índice de contenido LaTeX?
===
> [!important] Respuesta
> La sección bibliográfica del documento; es distinta de las citas que conducen a obras concretas.
```

```anki
deck: Física::Produção de Relatórios::Bibliografía
tags:
  - bibliografia
  - bibtex
---
> [!note] Pregunta
> ¿Qué solicitan las opciones `numbib`, `nottoc`, `notlot` y `notlof` de `tocbibind`?
===
> [!important] Respuesta
> Numerar la bibliografía y excluir de la incorporación automática el propio índice de contenido y las listas de tablas y figuras.
```

```anki
deck: Física::Produção de Relatórios::Bibliografía
tags:
  - bibliografia
  - bibtex
---
> [!note] Pregunta
> ¿Cómo se añade manualmente la bibliografía de un `article` al índice de contenido?
===
> [!important] Respuesta
> Con `\addcontentsline{toc}{section}{Bibliografia}` junto al inicio de la sección; se evita duplicar la misma entrada mediante otra vía.
```

## Ampliación: biblatex y Biber

### biblatex

> [!definicion] biblatex
> Paquete que gobierna citas y bibliografía mediante su propio sistema de estilos y órdenes, a partir de una base bibliográfica.[^bibexterna]

```latex
% Preámbulo
\usepackage[backend=biber,style=authoryear]{biblatex}
\addbibresource{fuentes.bib}
% Cuerpo
Uma referência documentada \autocite{Lamport1994}.
\printbibliography
```

Se declara la base con su extensión, a diferencia de `\bibliography{fuentes}`. No se mezclan estas órdenes con el esquema de estilo `.bst` de BibTeX. La alternativa permite reconocer flujos presentes en herramientas y plantillas; el desarrollo docente base utiliza `thebibliography` y BibTeX.[^bibexterna]

```anki
deck: Física::Produção de Relatórios::Bibliografía
tags:
  - bibliografia
  - bibtex
---
> [!note] Pregunta
> ¿Qué hace `\autocite{clave}` en el ejemplo de `biblatex`?
===
> [!important] Respuesta
> Solicita una cita de la entrada identificada por esa clave, cuya presentación depende del estilo configurado.
```

```anki
deck: Física::Produção de Relatórios::Bibliografía
tags:
  - bibliografia
  - bibtex
---
> [!note] Pregunta
> ¿Qué función cumple `biblatex` en la gestión de citas y bibliografía?
===
> [!important] Respuesta
> Gobierna citas y bibliografía con su propio sistema de estilos y órdenes, declarando la base con `\addbibresource` e imprimiéndola con `\printbibliography`.
```

```anki
deck: Física::Produção de Relatórios::Bibliografía
tags:
  - bibliografia
  - bibtex
---
> [!note] Pregunta
> ¿Se incluye la extensión al declarar `fuentes.bib` con `biblatex`?
===
> [!important] Respuesta
> Sí: `\addbibresource{fuentes.bib}`, a diferencia de `\bibliography{fuentes}` del flujo BibTeX clásico.
```

### Biber

> [!definicion] Biber
> Procesador habitual de los datos bibliográficos de `biblatex`, seleccionado mediante la opción `backend=biber`.[^bibexterna]

Con Biber, el ciclo es LaTeX → Biber → LaTeX; si el registro pide otra pasada, vuelve a ejecutar LaTeX. Que dos sistemas usen archivos `.bib` no significa que sean intercambiables: ejecuta el procesador que corresponda a la configuración del documento.[^bibexterna]

```anki
deck: Física::Produção de Relatórios::Bibliografía
tags:
  - bibliografia
  - bibtex
---
> [!note] Pregunta
> ¿Qué secuencia corresponde a `biblatex` cuando se declara `backend=biber`?
===
> [!important] Respuesta
> LaTeX → Biber → LaTeX, con otra pasada si se solicita; la opción selecciona Biber como procesador de los datos.
```

```anki
deck: Física::Produção de Relatórios::Bibliografía
tags:
  - bibliografia
  - bibtex
---
> [!note] Pregunta
> ¿Qué función cumple Biber cuando `biblatex` utiliza `backend=biber`?
===
> [!important] Respuesta
> Procesa los datos bibliográficos de ese flujo; se ejecuta entre pasadas de LaTeX y no sustituye sin más a BibTeX en un documento de otro esquema.
```

### Diagnóstico de referencias sin resolver

Si una cita no aparece, revisa primero que la clave exista, que LaTeX pueda encontrar el archivo y que hayas ejecutado el procesador adecuado. Cambiar órdenes al azar puede ocultar el origen del problema.

> [!procedimiento] Reparar una cita
> 1. Comparar la clave de la cita con la entrada real.
> 2. Comprobar nombre y ubicación de la base.
> 3. Identificar el flujo: manual, BibTeX o biblatex/Biber.
> 4. Ejecutar sus pasos y leer los registros.
> 5. Revisar la cita impresa y los metadatos de su entrada.[^docente][^bibexterna]

```anki
deck: Física::Produção de Relatórios::Bibliografía
tags:
  - bibliografia
  - bibtex
---
> [!note] Pregunta
> ¿Qué dependencias se revisan al diagnosticar una cita LaTeX sin resolver?
===
> [!important] Respuesta
> La clave, el archivo bibliográfico y su ubicación, el flujo configurado, la ejecución de sus pasos y los registros antes de verificar la salida.
```

## Práctica con soluciones razonadas

#### Ejercicio 1 — Una bibliografía sin atribución local

> [!ejemplo] Enunciado
> Una afirmación empírica aparece junto a una lista final de cinco obras, sin cita en el párrafo. ¿Qué operaciones faltan?

> [!resolucion]- Resolución
> Se localiza la obra que contiene el resultado y se comprueba el pasaje. Después se inserta la cita próxima y se revisa su correspondencia con los metadatos finales. Los límites de validez de la atribución dependen de la versión consultada y del alcance real de la evidencia; no se atribuye a un estudio lo que sólo se leyó en una descripción ajena.

#### Ejercicio 2 — Elegir y reparar el flujo

> [!ejemplo] Enunciado
> Un documento usa `\bibitem`; otro `\bibliography{fuentes}`. El segundo cambió `fuentes.bib`, pero la salida conserva el título antiguo. Justifica la diferencia y la reparación.

> [!resolucion]- Resolución
> El primero redacta la lista en el propio `.tex`; el segundo necesita BibTeX. Se comprueba que se editó la base correcta y se ejecuta LaTeX → BibTeX → LaTeX → LaTeX. El error frecuente es recompilar sólo LaTeX: puede seguir incorporándose un `.bbl` antiguo. Biber no sustituye a BibTeX en ese flujo.

#### Ejercicio 3 — Revisar una búsqueda y sus metadatos

> [!ejemplo] Enunciado
> Una búsqueda excluye con `NOT teaching` los registros sobre enseñanza, aunque el objetivo es un laboratorio docente. Además, el DOI exportado lleva a otro título. Propón dos correcciones justificadas.

> [!resolucion]- Resolución
> Se retira la exclusión y se combinan los conceptos que sí responden al objetivo, por ejemplo `pendulum AND teaching`, revisando sus resultados. El DOI se contrasta con el documento y la ficha editorial; si no corresponde a la obra, se corrige o se elimina hasta identificar el correcto. Un resultado recuperado y una referencia con apariencia correcta requieren comprobaciones diferentes.

La misma relación entre afirmación y fuente debe conservarse al seleccionar evidencias para [[Física/Grado/1º/Produção de Relatórios/05 Presentaciones científicas|una presentación científica]]. Reducir el texto visible no elimina la necesidad de atribuir datos, imágenes y procedimientos.

## 📚 Fuentes

### Material base aportado

[^docente]: Eugénia Graça — *Resumo de LaTeX*, julio de 2025, archivo `PR - Resumo - 2025 - 2026.pdf`, pp. físicas 49–52 (impresas 41–44), y bibliografía, p. física 79; *Capítulo II — Modo Texto*, julio de 2026, archivo `cap2 - PR -2026-2027.pdf`, pp. físicas 95–101, diapositivas 93–99 de 99. El capítulo tiene 101 páginas físicas por dos repeticiones. Bibliografía manual, BibTeX, tipos, campos, archivos e índice. Archivo `PR - Resumo - INGLES - 2025 - 2026.pdf`, pp. físicas 43–46, como contraste.
[^programa]: FCUL — [Programa de Produção de Relatórios, 2026/2027](https://fenix.ciencias.ulisboa.pt/courses/pr-847504421686893/programa), unidades 7–8. El capítulo I, p. física 3, incluye B-on en el segundo test.

### Ampliación externa

[^busqueda]: B-on — [Técnicas de pesquisa](https://www.b-on.pt/boas-praticas/tecnicas-de-pesquisa/). Términos, campos, operadores, frases y truncación; se corrige localmente su frase contradictoria sobre `NOT`.
[^bon]: B-on — [Recursos para estudantes](https://www.b-on.pt/a-b-on-para/estudantes/). Recursos electrónicos y acceso institucional; FCCN — [B-on: novo serviço de pesquisa e acesso ao conhecimento científico](https://www.fccn.pt/atualidade/b-on-novo-servico-pesquisa-acesso-conhecimento-cientifico/), 4 de febrero de 2026. Función del servicio de descubrimiento vigente.
[^biblioteca]: Biblioteca de Ciências — [Recursos bibliográficos](https://ciencias.ulisboa.pt/biblioteca/recursos-bibliograficos). Catálogo, bases, repositorios y requisito de red interna o VPN con cuenta Ciências.
[^crossref]: Crossref — [Metadata Retrieval](https://www.crossref.org/services/metadata-retrieval/). Función de metadatos e identificadores y su recuperación.
[^icmje]: ICMJE — [Preparing a Manuscript for Submission](https://www.icmje.org/recommendations/browse/manuscript-preparation/preparing-for-submission.html), apartado de referencias. Fidelidad y comprobación de atribuciones; no se adoptan sus requisitos editoriales biomédicos como normas de FCUL.
[^bibexterna]: LearnLaTeX — [Citations and references](https://www.learnlatex.org/en/lesson-12). Contraste de bases, separación de autores, estilos y alternativa biblatex/Biber.
[^manual]: LaTeX2e reference manual — [thebibliography](https://latexref.xyz/thebibliography.html). Anchura del argumento de etiquetas; corrección de la explicación del material base.
[^patashnik]: Oren Patashnik — [BibTeXing](https://ctan.math.illinois.edu/biblio/bibtex/base/btxdoc.pdf), 8 de febrero de 1988, §§3.1–3.2. Tipos clásicos y significado de campos, con distinción entre `editor`, `edition` y `publisher`.

## 🧑‍🏫 Prompt para tutor conversacional

Actúa como tutor de Produção de Relatórios para un estudiante de primer curso. Haz una pregunta cada vez y espera su respuesta antes de explicar la solución. Ajusta la dificultad con pistas, recuperación activa y repetición espaciada.

Guía la búsqueda desde la pregunta del estudiante. Ayúdale a elegir conceptos, términos y campos, a formular la consulta y a revisar los resultados. Comprueba que distingue AND, que combina conceptos; OR, que reúne alternativas; y NOT, que excluye términos. Las frases entre comillas y la truncación dependen de cada buscador.

Explica que B-on ayuda a descubrir recursos, mientras que algunos textos de Ciências requieren conexión a la red interna o una VPN y una cuenta institucional. Cuando el estudiante elija una fuente, revisa con él autoría, título, año, tipo de obra y versión. Un DOI ayuda a identificar un objeto, pero no demuestra que sus resultados sean de calidad.

Pídele que ponga la cita junto a la afirmación que atribuye y que compruebe que la referencia final permite identificar la obra.

En la bibliografía manual de LaTeX, muestra cómo `\cite` y `\bibitem` comparten una clave. Aclara que `\begin{thebibliography}{99}` reserva el espacio para las etiquetas; el 99 no fija un máximo de referencias.

Para BibTeX, recorre los archivos y pasos: lee `aux`, `bib` y `bst`, genera `bbl` y sigue el ciclo LaTeX → BibTeX → LaTeX → LaTeX. Repasa los tipos `article`, `book`, `inbook` y `manual`, eligiendo sus campos según la obra. `\bibliography` recibe la base sin la extensión `bib`; `\bibliographystyle` elige el estilo.

Muestra cómo `tocbibind` puede incluir y numerar la bibliografía en el índice. También puedes hacerlo con `\addcontentsline`, pero no uses ambas vías a la vez porque podrías crear una entrada duplicada.

Como ampliación, presenta `biblatex` con `\addbibresource` —que recibe el nombre con extensión—, `\autocite` y `\printbibliography`, y explica que ese flujo se procesa con Biber.

Usa la referencia al manual de Lamport que identifica el resumen docente para practicar claves y pasos de compilación. No atribuyas al libro contenidos que no hayas consultado. Propón también un registro con un año o DOI discrepante y un archivo `bbl` antiguo; pide distinguir si el problema está en la búsqueda, los metadatos, la atribución o la compilación.

Termina conectando el trabajo bibliográfico con la atribución en las presentaciones y con la ética académica.

```dataviewjs
await dv.view("Planes/Estudio/Scripts/study-session", { location: "end" })
```
