# Calidad del Aire en Madrid (2001-2018)
  Diferentes niveles de contaminación en Madrid de 2001 a 2018
  Objetivo: Analizar las mediciones históricas de la calidad del aire en Madrid y examinar factores que influyen en la contaminación atmosférica, como el tráfico vehicular, la actividad industrial y las condiciones meteorológicas. Desarrollar un modelo predictivo para estimar la calidad del aire en el futuro.

# Acerca del conjunto de datos
  Contexto

En los últimos años, los altos niveles de contaminación durante ciertos periodos secos en Madrid ha obligado a las autoridades a tomar medidas contra el uso de automóviles en el centro de la ciudad, y ha sido utilizado como razón para proponer modificaciones drásticas en el urbanismo de la ciudad. Gracias a la web de Datos Abiertos del Ayuntamiento de Madrid, los datos de calidad del aire que se han subido están públicamente disponibles. Hay varios archivos disponibles, que incluyen datos históricos diarios y horarios de los niveles registrados desde 2001 hasta 2018 y la lista de estaciones que se utilizan para el análisis de contaminación y otras partículas en la ciudad.

Sin embargo, al explorar estos datos desde un punto de vista de análisis de datos y series temporales, encontramos que el formato era algo confuso y poco común, y algunas decisiones de diseño en el conjunto de datos estaban lejos de ser óptimas: Los datos por hora se dividieron en archivos mensuales que contenían formatos ligeramente diferentes a lo largo de los años, que eran igualmente poco comunes: las filas son ciertas medidas en ciertos días, cada una de las cuales contiene 24 columnas (una por hora del día) que incluye un carácter de control. Este carácter de control es V si la medida es válida, y mayoritariamente (pero no exclusivamente) N si no lo es.

Estos handicaps a la hora de explorar los datos históricos pueden arruinar el propósito de los Datos Abiertos: ser auditados públicamente, y ser libremente explorados y utilizados para la experimentación. Por esa razón, en Decide lanzamos nuestra propia versión de los datos, que ha sido diseñada para facilitar su uso utilizando estándares comunes y formatos de rendimiento. Esto permite enviar un conjunto de datos más rápido, más pequeño y más conveniente e intuitivamente estructurado.

# Contenido

Todos los datos se extraen de los archivos originales y se procesan para dar como resultado un formato más conveniente para los propósitos típicos de Kaggle.
Mientras que los datos originales incluyen horas como columnas diferentes y medidas como filas diferentes, esta versión está estructurada al revés: cada fila tiene una marca de tiempo y las columnas son las diferentes medidas realizadas en ese momento en ciertas estaciones. Esto permite una preparación más rápida para las tareas de análisis y predicción de series temporales.

Este conjunto de datos define las estaciones como el nivel jerárquico más alto: el historial de cada estación individual se puede extraer individualmente del archivo para su estudio posterior. Dentro del DataFrame de cada estación, todas las medidas de partículas que dicha estación ha registrado en el periodo 2001/01 - 2018/04 (si está activo todo este tiempo). No todas las estaciones tienen el mismo equipo, por lo que cada estación puede medir solo un cierto subconjunto de partículas. La lista completa de posibles medidas y sus explicaciones (siguiendo el documento explicativo original) son:

  * SO_2: nivel de dióxido de azufre medido en μg/m³. Los altos niveles de dióxido de azufre     pueden producir irritación en la piel y las membranas, y empeorar el asma o enfermedades del corazón en grupos sensibles.
  * CO: nivel de monóxido de carbono medido en mg/m³. El envenenamiento por monóxido de carbono implica dolores de cabeza, mareos y confusión en exposiciones cortas y puede provocar pérdida del conocimiento, arritmias, convulsiones o incluso la muerte a largo plazo.
  * NO: nivel de óxido nítrico medido en μg/m³. Se trata de un gas altamente corrosivo generado, entre otros, por los vehículos de motor y los procesos de quema de combustibles.
  * NO_2: nivel de dióxido de nitrógeno medido en μg/m³. La exposición a largo plazo es una causa de enfermedades pulmonares crónicas y es dañina para la vegetación.
  * PM25: partículas menores a 2.5 μm nivel medido en μg/m³. El tamaño de estas partículas les permite penetrar en las regiones de intercambio de gases de los pulmones (alvéolos) e incluso entrar en las arterias. Se ha demostrado que la exposición a largo plazo está relacionada con el bajo peso al nacer y la presión arterial alta en los recién nacidos.
  * PM10: partículas menores de 10 μm. Aunque no pueden penetrar el alvéolo, aún pueden penetrar a través de los pulmones y afectar otros órganos. La exposición a largo plazo puede provocar cáncer de pulmón y complicaciones cardiovasculares.
  * NOx: nivel de óxidos de nitrógeno medido en μg/m³. Afectan el sistema respiratorio humano empeorando el asma u otras enfermedades, y son responsables del color marrón amarillento del smog fotoquímico.
  * O_3: nivel de ozono medido en μg/m³. Altos niveles pueden producir asma, bronquitis u otras enfermedades pulmonares crónicas en grupos sensibles o trabajadores al aire libre.
  * TOL: nivel de tolueno (metilbenceno) medido en μg/m³. La exposición a largo plazo a esta sustancia (presente también en el humo del tabaco) puede provocar complicaciones renales o daño cerebral permanente.
  * BEN: nivel de benceno medido en μg/m³. El benceno irrita los ojos y la piel, y las exposiciones prolongadas pueden provocar varios tipos de cáncer, leucemia y anemia. El benceno es considerado un cancerígeno del grupo 1 para los humanos por la IARC.
  * EBE: nivel de etilbenceno medido en μg/m³. La exposición a largo plazo puede causar problemas auditivos o renales y la IARC ha concluido que la exposición a largo plazo puede producir cáncer.
  * MXY: nivel de m-xileno medido en μg/m³. Los xilenos pueden afectar no solo el aire, sino también el agua y el suelo, y puede resultar en una exposición prolongada a altos niveles de xilenos.

# madrid.h5(75.88 MB)
  Acerca de este archivo

Este archivo contiene toda la información disponible en el conjunto de datos en formato de archivo HDF5. Esto significa que el archivo está comprimido y accesible en diferentes segmentos. Por conveniencia, los datos se han separado en estaciones: esto se debe a que HDF5 es más rápido para acceder a filas contiguas y este diseño permite descartar todas las medidas que no se están utilizando en una estación.

Se puede acceder a los datos de cada estación individual para el historial completo de la misma utilizando la identificación de la estación. En el interior, cada marco de datos contiene una entrada por hora, que incluye los niveles de todas las medidas que la estación puede realizar (si están disponibles). La lista completa de claves se puede ver en el documento original explicativo de los datos (página 3) o explorando la lista de claves de este archivo. Si lo necesita, consulte el núcleo introductorio de HDF5 para obtener algunos fragmentos útiles.

Cada marco de datos individual contiene una fila por entrada, marcada por una marca de tiempo. Las columnas incluyen los niveles de cada posible medición en dicha estación (consulte la descripción del conjunto de datos para obtener más información sobre las mediciones). Este archivo también contiene master, el marco de datos que incluye toda la información disponible sobre las estaciones actuales. La misma información también se puede encontrar en el archivo estaciones.csv.