---
title: Introducción a ImagePlot y la visualización de metadatos de colecciones de imágenes
authors:
  - Joshua Ortiz Baco
reviewers:
  - 
layout: lesson
difficulty: 2
---
 ## Introducción a ImagePlot y la visualización de metadatos de colecciones de imágenes

### Qué aprenderás en este tutorial

En esta lección se ofrece una introducción a ImagePlot, una herramienta para generar visualizaciones basadas en los datos de colecciones de imágenes o videos. Aprenderás cómo utilizar la herramienta para:

* Extraer metadatos relacionados con las medidas de imágenes
* Entender características básicas de imágenes
* Crear representaciones gráficas de colecciones visuales

Como paso final, utilizarás las medidas generadas a través de ImagePlot para complementar los metadatos de una colección de afiches. Con estos realizarás una representación gráfica para aprender cómo este tipo de visualizaciones pueden ser útiles al explorar colecciones.


### Información de trasfondo
#### ¿Qué es ImagePlot?
Esta herramienta fue creada por el equipo de [Software Studies Initiative](http://lab.softwarestudies.com/search/label/espa%C3%B1ol) para realizar visualizaciones que puedan abarcar la totalidad de una colección de imágenes y opera dentro de otro programa de libre acceso llamado [ImageJ](https://imagej.nih.gov/ij/?). Los creadores de ImagePlot utilizan el término "vista a distancia", *distant viewing* en inglés, para describir este tipo de visualización y análisis porque el punto de partida o enfoque principal es lo que se puede percibir de la totalidad de los elementos de la colección, en vez de uno o dos elementos a la vez.

#### Visualización de metadatos

En este sentido, el uso de ImagePlot generalmente cae bajo la analítica cultural ya que es capaz de procesar metadatos de colecciones de miles de millones de objetos. Las visualizaciones a esta escala pueden utilizarse para varios propósitos como, por ejemplo: demostrar cambios a través del tiempo, encontrar imágenes con características atípicas, detectar grupos de imágenes similares o descubrir patrones en colecciones, entre otros. ImagePlot, al igual que programas similares, utiliza metadatos de los objetos expresados numéricamente para generar estas representaciones gráficas.

No obstante, no necesitamos una colección inmensa para sacarle provecho a la visualización de datos y a ImagePlot. En esta lección utilizaremos esta herramienta con el objetivo de familiarizarnos con algunos aspectos de una colección y el tipo de preguntas que se pueden hacer, tanto de esta colección en particular, como de materiales visuales en general.

#### La colección y los metadatos

Para esta lección utilizaremos una serie de imágenes provenientes de una colección de afiches del [Museo de la Palabra y la Imágen](http://museo.com.sv/es/) en San Salvador, El Salvador. Los 394 afiches representados en los metadatos fueron creados durante los 12 años de la Guerra Civil de El Salvador, por más de 171 organizaciones de por lo menos 21 países. Los metadatos fueron preparados por personal de MUPI junto con el equipo de [Iniciativas Digitales de América Latina](http://ladi.lib.utexas.edu/)[1] y la hoja de metadatos que utilizarás en esta lección es una versión modificada de la original.

## Imageplot
ImagePlot se puede descargar desde el sitio web de [Software Studies Initiative](http://lab.softwarestudies.com/p/imageplot.html#download). Existen dos opciones, "ImagePlot_v1.1.zip" y "ImagePlot_v1.1-program-only.zip", pero utilizaremos la primera ya que tiene todo lo necesario para este tutorial e información relacionada a la metodología de la herramienta. Luego puedes explorar los conjuntos de datos y artículos de teoría y metodología adicionales. Verás que además contiene archivos extras (`theory` y `sample_files`) los cuales son útiles si deseas utilizar los tutoriales en el sitio web de ImagePlot, para conocer más sobre *distant viewing* o para aprender del proceso de creación de la herramienta.

El archivo zip descomprimido tendrá el nombre de `imageplot-master`. Puedes poner la carpeta en cualquier parte, pero las instrucciones del tutorial parten de que estará ubicada en el escritorio de tu computadora. También descarga las [imágenes de la colección](link) a esta misma carpeta y crea una nueva carpeta, `imagenes_miniatura`, para las imágenes procesadas que ImagePlot crea al hacer la visualización.

#### Macros y medidas
Dentro de `imageplot-master` está la carpeta `ImageJ` y dentro de la misma está el programa en `ij.jar`. En el menú del programa navega a `Plugins -> Macros -> Run`. Abrirá una caja para seleccionar la carpeta de `imageplot-master/extras` en la cual están los tres macros o macroinstrucciones para hacer medidas en ImagePlot. Este tipo de recurso funciona como un conjunto de instrucciones para que los programas puedan realizar operaciones automáticas, repetitivas y secuenciales. Esto nos ahorra tener que manualmente seleccionar una operación, como medir el tamaño, para cada uno de los ítems que estemos analizando.    

[carpeta_directorios](/path/to/img.jpg)

De los macros disponibles, selecciona `imageMeasure.txt`. Se abrirá una caja nueva para seleccionar la carpeta de tus imágenes y luego otra para seleccionar la carpeta en la que se guardará el archivo con las medidas. Puedes guardar este último archivo en la carpeta de `imageplot-master` seleccionando tu escritorio en el menú despegable.

Los resultados proveen los valores de luminosidad (brightness), saturación (saturation) y tono (hue) de las imágenes al igual que la desviación típica de las medidas. La luminosidad corresponde a los valores promedios de la imagen en una escala de grises, la saturación es la intensidad de los colores y el tono es la diferencia en valores de RGB de los pixeles. Para más información sobre estos elementos consulta información sobre la [teoría del color](https://edu.gcfglobal.org/es/conceptos-basicos-de-diseno-grafico/teoria-del-color/1/).

#### Problemas con datos a gran escala

Este proceso puede tomar mucho tiempo dependiendo del tamaño de la colección y de la resolución de las imágenes. También, cabe la posibilidad de que si utilizas muchas imágenes o imágenes de alta resolución el programa agote el almacenamiento de memoria RAM que tiene disponible. Cuando ésto sucede aparece este error:
```"java.lang.OutOfMemoryError: Java heap space".

```
[memory_and_thread](/path/to/img.jpg)
Para arreglar esto selecciona `Edit -> Options -> Memory and Thread` y cambia el número predeterminado, 658 MB o 0.6 GB, que aparece en `Maximum Memory`. Tendrás que reiniciar el programa para que el cambio haga efecto y recuerda no exceder los límites de memoria RAM de tu computadora.

## Metadatos y visualizaciones

Al hacer clic derecho en la pantalla de `Results` aparece un menú para guardar el archivo dentro de una carpeta. No es necesario guardar estos resultados en tu computadora porque el programa ya ha grabado las medidas en el paso anterior dentro del archivo `measurements.txt`. Si abres este archivo verás que es un documento con la extensión `.txt` pero los campos están divididos por cuatro espacios consecutivos o *tabs*. Este tipo de estructura se llama *tab separated values* y es el único formato que ImagePlot puede leer como datos al generar las visualizaciones.

[hoja_de_datos](/path/to/img.jpg)

Es importante verificar que el programa que utilices para abrir el archivo `measurements.txt` importe correctamente las columnas y los diacríticos o eñes en los nombres de los archivos bajo la columna `filename`. Para que ImagePlot pueda identificar las medidas que corresponden a cada imagen, la información de esta columna debe ser idéntica al nombre del archivo de la imagen, incluyendo la extensión.

Toma un segundo para abrir la hoja y ver los campos que se han generado. Con esta información ya es posible visualizar la colección en base a las medidas generadas. Esta visualización, sin embargo, solamente sería una representación gráfica de la luminosidad, saturación o tono y las posibles preguntas estarían limitadas a estas tres medidas. Para complementar estos datos miremos los valores que ya generamos junto con los metadatos recopilados por el personal de MUPI. Descarga [`mupi_afiches_datos`](link) a la carpeta `imageplot-master` .

Vuelve a tomar unos minutos para familiarizarte con los campos de esta hoja. ImagePlot solamente procesa las primeras 16 columnas y por esto están en este orden. La colección todavía está siendo procesada y por lo tanto hay algunos campos que no se han rellenado y otros que no contienen datos porque se desconocen debido a la naturaleza de la colección. Es importante reconocer cuales son las limitaciones de los metadatos porque estas pueden afectar cómo escoges abordar la colección y las precauciones que debes tomar al planificar su visualización.

### Visualizar la colección y ajustes opcionales
De aquí en adelante se escogen cuales características queremos visualizar y los aspectos de esta que se pueden modificar. En la próxima caja podrás seleccionar los campos representados en las coordenadas, es decir, las medidas que determinan la posición en el gráfico de cada imagen. Estos valores provienen de nuestra hoja de metadatos. Además, abajo encontrarás los ajustes mínimos y explicaciones sobre sus efectos. Los valores son el resultado de experimentar con estos ajustes para esta colección y muy probablemente tengan que ser modificados al trabajar con otros materiales.

Nuevamente selecciona `Plugins -> Macros -> Run`, la carpeta de `imageplot-master` y ahora el macro necesario para hacer las visualizaciones, `ImagePlot.txt`. En la caja que aparece, deja las opciones de `Data` e `Images` en `Open...` para que la herramienta pida esa información en el próximo paso. En la primera ocasión que proceses las imágenes marca la opción de `Save thumbnail images`. Esto es porque ImagePlot genera las imágenes en miniatura como parte de procesar la colección y guardarlas hace que realizar las visualizaciones posteriores sea mucho más rápido. Finalmente, deshaz la selección de `Polar` para que la visualización no sea circular - esto ayudará luego para la interpretación - y marca `Options` para que en el próximo paso puedas hacer ajustes a la visualización final.

[algunas_de_las_cajas_opciones_marcadas](/path/to/img.jpg)

Al oprimir `ok` aparecerá una caja para seleccionar la hoja de `mupi_afiches_datos`. Luego aparecerá otra caja para seleccionar las imágenes de la colección que descargamos anteriormente.

#### Seleccionar los ejes
La opción de `Image filename` debe reflejar `id(Column)` en la que están los nombres de los archivos de las imágenes. Para el eje horizontal, `X axis`, selecciona la columna `country-id(Column 7)` que corresponde a un número único por cada país representado en la colección. Para la vertical, `Y axis`, `hue_stdev(Column6)`, que corresponde a la diferencia de la media de tonalidad. Esto mide, por ejemplo, cuan diferente es el rojo del rosado, o el azul del azul celeste. La visualización de estos datos está diseñada para dar una idea de cuán similar o distinta es la tonalidad entre los afiches agrupados por países.
[cajas_opciones_marcadas1](/path/to/img.jpg)
#### Modificar lienzo, etiquetas, imágenes y ejes
El `Canvas` es el lienzo en el que aparecerá el gráfico. Cambia el campo de `Border size` a 800 pixeles para que haya suficiente espacio entre el borde del lienzo y el gráfico. En la caja `Elements` están las etiquetas que acompañarán a cada imagen. Utiliza `cname1 (Column8)` la cual corresponde a la organización que creó el afiche y mantén el tamaño de la letra en `32pt`. En `Images` debes aumentar el tamaño de las imágenes en miniatura para que todavía sean distinguibles, `Thumbnail width`, a 400 pixeles.
[cajas_opciones_2](/path/to/img.jpg)
En `Axes` cambia a 100 px los siguientes: `Axis line width`, `Font size`, y `Tick size` (grosor de la línea del eje, tamaño de letra y tamaño de marcador). Ahora escoge `Mark by distance between labels` o a la cantidad de espacio entre cada valor y entonces pon las etiquetas de los ejes, `Axis labels`(etiquetas de los ejes) para tener `for X: 1` y `for Y: 10`. La diferencia entre estos valores corresponde a que hay un total de 22 identificadores únicos, 0-21, por país para el eje x, pero las variaciones de tonalidad en el eje y van desde .03 a 123.30. Si se utiliza un valor demasiado alto o bajo en `distance between labels` se corre el riesgo de que las imágenes sean indistinguibles o que la separación dificulte ver la relación entre ellas. Esto también se aplica al próximo paso en el que seleccionarás los rangos de los ejes en la caja de `Range`: `X start value: 0 units`, `X end value: 25 units`, `Y start value: -10 units` y `Y end value: 125 units`. Verifica que hayas marcado las casillas "X range specified?" y “Y range specified?” porque si no el programa ignorará los valores (especificas rangos para los ejes X y Y).
[cajas_opciones_3](/path/to/img.jpg)
#### Analizar la visualización de la colección

El canvas abrirá y comenzarán a aparecer las imágenes poco a poco. Nuevamente, el proceso puede tardar más o menos tiempo dependiendo de la cantidad de imágenes con las que estés trabajando. Guarda la visualización para poder explorar en más detalles yendo a `File -> Save As` y escogiendo el formato de preferencia. Por alguna razón, ImagePlot tiene problemas para guardar en otros formatos que no sean TIF.

Ahora podemos observar la visualización en cualquier programa que pueda abrir este formato. Hay dos aspectos interesantes en esta primera visualización que son evidentes a primera vista. Primero, tenemos bastantes imágenes en la categoría de El Salvador que sería la séptima columna y la siguiente en cantidad es la última. Esta última está compuesta de imágenes que tienen cero en la columna `country-id(Column 7)`. Es decir, no tienen información geográfica que permita asignarle un país. Segundo, el límite superior del valor del eje parece tener imágenes en las que predomina el rojo y tenemos cinco columnas más altas que el resto.
[visualizacion](/path/to/img.jpg)

De esta representación visual podemos formular una pregunta inicial, siempre consciente de la naturaleza de la colección y sus metadatos, sobre una posible similitud estética entre los países que se ven representados en los valores más altos de tonalidad. ¿En qué nos puede ayudar esta pregunta en la exploración de la colección? Si recuerdas la columna que aparece última del gráfico notarás que aparecen dos imágenes que por su posición tienen similitudes de tonalidad con las otras cuatro. Al hacer esta comparación podemos mirar también el lenguaje que se utiliza en el afiche, francés, y buscar si un país francófono está representado en alguna de las otras cuatro columnas. En efecto, tenemos a Francia en la columna 10 y Suiza en la columna 19. Para confirmar la procedencia de los afiches no-identificados todavía tendríamos que encontrar más información, pero la visualización a distancia con ImagePlot ya nos provee una pista por donde comenzar.

***
[1]: La digitalización de esta colección fue hecha en parte gracias a una beca de la Fundación Andrew W. Mellon.
