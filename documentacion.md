# Primer capítulo {#ch:primer-capitulo}

## Introducción

Este documento es una plantilla para la elaboración de un trabajo fin de
Grado siguiendo los
[requisitos](https://grados.ugr.es/matematicas/pages/infoacademica/tfg/requisitosTFG)
de la comisión de Grado en Matemáticas de la Universidad de Granada que,
a fecha de junio de 2023, son las siguientes:

-   La memoria debe realizarse con un procesador de texto científico,
    preferiblemente (La)TeX.

-   La portada debe contener el logo de la UGR, incluir el título del
    TFG, el nombre del estudiante y especificar el grado, la facultad y
    el curso actual.

-   La contraportada contendrá además el nombre del tutor o tutores.

-   La memoria debe necesariamente incluir:

    -   Declaración explícita firmada en la que se asume la originalidad
        del trabajo, entendida en el sentido de que no ha utilizado
        fuentes sin citarlas debidamente. Esta declaración se puede
        descargar en la web del Grado.

    -   un índice detallado de capítulos y secciones,

    -   un resumen amplio en inglés del trabajo realizado (se recomienda
        entre 800 y 1500 palabras),

    -   una introducción en la que se describan claramente los objetivos
        previstos inicialmente en la propuesta de TFG, indicando si han
        sido o no alcanzados, los antecedentes importantes para el
        desarrollo, los resultados obtenidos, en su caso y las
        principales fuentes consultadas,

    -   una bibliografía final que incluya todas las referencias
        utilizadas.

-   Se recomienda que la extensión de la memoria sea de unas 50 páginas,
    sin incluir posibles apéndices.

Para generar el pdf a partir de la plantilla basta compilar el fichero
`tfg.tex`. Es conveniente leer los comentarios contenidos en dicho
fichero pues ayudarán a entender mejor como funciona la plantilla.

La estructura de la plantilla es la siguiente[^1]:

-   Carpeta **preliminares**: contiene los siguientes archivos

    `dedicatoria.tex`

    :   Para la dedicatoria del trabajo (opcional)

    `agradecimientos.tex`

    :   Para los agradecimientos del trabajo (opcional)

    `introduccion.tex`

    :   Para la introducción (obligatorio)

    `summary.tex`

    :   Para el resumen en inglés (obligatorio)

    `tablacontenidos.tex`

    :   Genera de forma automática la tabla de contenidos, el índice de
        figuras y el índice de tablas. Si bien la tabla de contenidos es
        conveniente incluirla, el índice de figuras y tablas es
        opcional. Por defecto está desactivado. Para mostrar dichos
        índices hay que editar este fichero y quitar el comentario a
        `\listoffigures` o `\listoftables` según queramos uno de los
        índices o los dos. En este archivo también es posible habilitar
        la inclusión de un índice de listados de código (si estos han
        sido incluidos con el paquete `listings`)

    El resto de archivos de dicha carpeta no es necesario editarlos pues
    su contenido se generará automáticamente a partir de los metadatos
    que agreguemos en `tfg.tex`

-   Carpeta **capitulos**: contiene los archivos de los capítulos del
    TFG. Añadir tantos archivos como sean necesarios. Este capítulo es
    `capitulo01.tex`.

-   Carpeta **apendices**: Para los apéndices (opcional)

-   Carpeta **img**: Para incluir los ficheros de imagen que se usarán
    en el documento.

-   Fichero `library.bib`: Para incluir las referencias bibliográficas
    en formato `bibtex`. Es útil la herramienta
    [doi2bib](https://www.doi2bib.org/) para generar de forma automática
    el código bibtex de una referencia a partir de su [doi]{.smallcaps}
    así como la base de datos bibliográfica
    [MathSciNet](https://mathscinet.ams.org). Para que una referencia
    aparezca en el pdf no basta con incluirla en el fichero
    `library.bib`, es necesario además *citarla* en el documento usando
    el comando `\cite`. Si queremos mostrar todos las referencias
    incluidas en el fichero `library.bib` podemos usar `\cite{*}` aunque
    esta opción no es la más adecuada. Se aconseja que los elementos de
    la bibliografía estén citados al menos una vez en el documento (y de
    esa forma aparecerán de forma automática en la lista de
    referencias).

-   Fichero `glosario.tex`: Para incluir un glosario en el trabajo
    (opcional). Si no queremos incluir un glosario deberemos borrar el
    comando `\input{glosario.tex}` del fichero `tfg.tex` y
    posteriormente borrar el fichero `glosario.tex`

-   Fichero `tfg.tex`: El documento maestro del TFG que hay que compilar
    con LaTeX para obtener el pdf. En dicho documento hay que cambiar la
    *información del título del [tfg]{.smallcaps} y el autor así como
    los tutores*.

## Elementos del texto

En esta sección presentaremos diferentes ejemplos de los elementos de
texto básico. Conviene consultar el contenido de
`capitulos/capitulo01.tex` para ver cómo se han incluido.

### Listas

En LaTeX tenemos disponibles los siguientes tipos de listas:

Listas enumeradas:

1.  item 1

2.  item 2

3.  item 3

Listas no enumeradas

-   item 1

-   item 2

-   item 3

Listas descriptivas

termino1

:   descripción 1

termino2

:   descripción 2

### Tablas y figuras

En la [\[tb:ejemplo-tabla\]](#tb:ejemplo-tabla){reference-type="autoref"
reference="tb:ejemplo-tabla"} o la
[\[fig:logo-ugr\]](#fig:logo-ugr){reference-type="autoref"
reference="fig:logo-ugr"} podemos ver...

::: {#tb:ejemplo-tabla}
  ----------------- ---------- ----------
      Agrupados                
   (r)1-2 cabecera   cabecera   cabecera
      elemento       elemento   elemento
      elemento       elemento   elemento
      elemento       elemento   elemento
  ----------------- ---------- ----------

  : Ejemplo de tabla
:::

![Logotipo de la Universidad de Granada](logo-ugr){#fig:logo-ugr
width="50%"}

## Entornos matemáticos {#sec:entornos-matematicos}

La plantilla tiene definidos varios entornos matemáticos cuyo nombre es
el mismo omitiendo los acentos. Así, para incluir una *proposición*
usaríamos:

    \begin{proposicion}
    texto de la proposición
    \end{proposicion} 

Ver el código fuente del archivo `capitulo01.tex` para el resto de
ejemplos.

::: teorema
[]{#thm:teorema label="thm:teorema"} Esto es un ejemplo de teorema.
:::

::: proposicion
Ejemplo de proposición
:::

::: lema
Ejemplo de lema
:::

::: corolario
Ejemplo de corolario
:::

::: definicion
Ejemplo de definición
:::

::: observacion
Ejemplo de observación
:::

Adicionalmente está definido el entorno `teorema*` que permite incluir
un teorema sin numeración:

::: teorema*
Sea $S$ una superficie compacta y $K$ su curvatura de Gauß. Entonces
$$\int_S K = 2\pi\chi(S)$$ donde $\chi(S)$ es la característica de Euler
de $S$.
:::

Las fórmulas matemáticas se escriben entre símbolos de dólar \$ si van
en línea con el texto o bien usando el entorno [^2] `equation` cuando
queremos que se impriman centradas en una línea propia, como el
siguiente ejemplo $$\label{eq:identidad-pitagorica}
  \cos^2 x + \sin^2 x = 1.$$

Gracias al paquete `mathtools`, las ecuaciones escritas dentro del
entorno `equation` llevarán numeración de forma automática si son
referenciadas en cualquier parte del documento (por ejemplo la identidad
Pitagórica [\[eq:identidad-pitagorica\]](#eq:identidad-pitagorica){reference-type="eqref"
reference="eq:identidad-pitagorica"}, ver el código de los dos
anteriores ejemplos y la
[\[sec:referencias\]](#sec:referencias){reference-type="autoref"
reference="sec:referencias"} para más información sobre referencias
cruzadas en el documento).

## Referencias a elementos del texto {#sec:referencias}

Para las referencias a los elementos del texto (secciones, capítulos,
teoremas,...) se procede de la siguiente manera:

-   Se *marca* el elemento (justo antes del mismo si se trata de un
    capítulo o sección o en el interior del *entorno* en otro caso),
    mediante el comando `\label{`*etiqueta*`}`, donde *etiqueta* debe
    ser un identificador único.

-   Para crear una referencia al elemento en cualquier otra parte del
    texto se usa el comando `\ref{`*etiqueta*`}` (únicamente imprime la
    numeración asociada a dicho elemento, por ejemplo
    [1](#ch:primer-capitulo){reference-type="ref"
    reference="ch:primer-capitulo"} o
    [\[thm:teorema\]](#thm:teorema){reference-type="ref"
    reference="thm:teorema"}) o bien `\autoref{`*etiqueta*`}` (imprime
    la numeración del elemento así como un texto previo indicando su
    tipo, por ejemplo
    [\[ch:primer-capitulo\]](#ch:primer-capitulo){reference-type="autoref"
    reference="ch:primer-capitulo"} o
    [\[thm:teorema\]](#thm:teorema){reference-type="autoref"
    reference="thm:teorema"})

## Bibliografía e índice

Esto es un ejemplo de texto en un capítulo. Incluye varias citas tanto a
libros [@Aigner2018], artículos de investigación [@Euler1985], recursos
online [@EulerWiki] (páginas web), tesis [@CitekeyPhdthesis], trabajo
fin de máster [@CitekeyMastersthesis], trabajo fin de
grado [@CiteKeyBachelorsthesis] así como artículos sin publicar
(preprints) [@castroinfantes2022conjugate] (en estos últimos usar el
campo `note` para añadir la información relevante). Ver el fichero
`library.bib` para las distintas plantillas.

[^1]: Los nombres de las carpetas no se han acentuado para evitar
    problemas en sistemas con Windows

[^2]: También es posible delimitar una ecuación mediante los comandos
    $\backslash$`[` y $\backslash$`]` pero éstas nunca llevarán
    numeración aunque añadamos una etiqueta y las referenciemos (ver
    [\[sec:referencias\]](#sec:referencias){reference-type="autoref"
    reference="sec:referencias"}).
