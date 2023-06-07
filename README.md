# GRUPO 1: 
    Emma Montalbán
    Erika Samara Alvares
    Juan Carlos Menendez Gijón
    Francisco Polonio Monterroso

# TEMÁTICA: Calidad del aire en Madrid año 2022 (por día y hora)

# OBJETIVO:
1. Escenario: Modelo predictivo de los efectos de la calidad del aire en la salud.
* Calidad del aire vs salud, teniendo en cuenta datos metereológicos
* Datos: Aire, metereología

# RECOGIDA DE DATOS: PORTAL DEL AYUNTAMIENTO DE MADRID

1. Datasets calidad del aire
    https://datos.madrid.es/sites/v/index.jsp?vgnextoid=aecb88a7e2b73410VgnVCM2000000c205a0aRCRD&vgnextchannel=374512b9ace9f310VgnVCM100000171f5a0aRCRD

2. Dataset datos metereológicos
    https://datos.madrid.es/sites/v/index.jsp?vgnextoid=fa8357cec5efa610VgnVCM1000001d4a900aRCRD&vgnextchannel=374512b9ace9f310VgnVCM100000171f5a0aRCRD

# INTERPRETACIÓN DATASETS:

1.  Dataset calidad del aire
* Documentación de referencia 
    https://datos.madrid.es/FWProjects/egob/Catalogo/MedioAmbiente/Aire/Ficheros/Interprete_ficheros_%20calidad_%20del_%20aire_global.pdf

    * Interpretación columnas:
        - Provincia: Código de Provincia 
        - Municipio: Código de Municipio
        - Estación: Ubicación de las estaciones de medida
        - Magnitud: Parámetro contaminantebmedido
        - Punto_de_muestreo: Código estación completo (provincia,municipio y estación) más magnitud y técnica de medida
        - año: año
        - mes: mes 
        - día: día   
        - h: indica el valor de la magnitud contaminante correspondiente. 
            “h01” hace referencia a la 1 de la mañana, 
            “h02” a las 2 de la mañana, y así sucesivamente hasta las 24h
        - v01, ..., v024: Validación de la h01, ..., h024.Dónde:
            "V" hace referencia a valor válido
            "N" a valor no válido

    * MAGNITUDES DE MEDIDA DE LOS CONTAMINANTES ATMOSFÉRICOS.
                                        Técnica de medida
        - 01 SO2: Dióxido de Azufre     38 Fluorescencia ultravioleta
        - 08 NO2: Dióxido de Nitrógeno  08 Quimioluminiscencia  
        - 09 PM2.5: Partículas < 2.5 μm 47 Microbalanza
        - 10 PM10: Partículas < 10 μm   47 Microbalanza
        - 14 O3: Ozono                  06 Absorción ultravioleta 

    *  ESTACIONES DE MEDIDA
        01. 28079004: Pza. de España
        02. 28079008: Escuelas Aguirre
        03. 28079011 Av. Ramón y Caja
        04. 28079016 Arturo Soria
        05. 28079017 Villaverde Alto
        06. 28079018 C/ Farolillo
        07. 28079024 Casa de Campo
        08. 28079027 Barajas
        09. 28079035 Pza. del Carmen
        10. 28079036 Moratalaz 
        11. 28079038 Cuatro Caminos  
        12. 28079039 Barrio del Pilar
        13. 28079040 Vallecas
        14. 28079047 Méndez Álvaro 
        15. 28079048 Pº. Castellana 
        16. 28079049 Retiro 
        17. 28079050 Pza. Castilla 
        18. 28079054 Ensanche Vallecas 
        19. 28079055 Urb. Embajada (Barajas) 
        20. 28079056 Plaza Elíptica 
        21. 28079057 Sanchinarro 
        22. 28079058 El Pardo 
        23. 28079059 Parque Juan Carlos I 
        24. 28079060 Tres Olivos 

2. Dataset datos metereológicos
    Los datos meteorológicos que se proporcionan en estos ficheros son exclusivamente para evaluar la calidad del aire medida por la Red de Calidad del Aire de la Comunidad de Madrid. Los datos meteorológicos oficiales son los proporcionados por la Agencia Estatal de Meteorología (AEMET).

    * Documentación de referencia 
        https://datos.madrid.es/FWProjects/egob/Catalogo/MedioAmbiente/DatosMeteorologicos/Ficheros/Interpretaci%C3%B3n_datos_meteorologicos.pdf

    * Interpretación columnas:
        - Provincia: Código de Provincia 
        - Municipio: Código de Municipio
        - Estación_en_municipio: Ubicación de las estaciones de medida
        - Magnitud: Parámetro metereológico medido
        - Punto_de_muestreo: Código estación completo (provincia,municipio y estación) más magnitud y técnica de medida
        - año: año
        - mes: mes 
        - día: día   
        - h: indica el valor de la magnitud meteorológica correspondiente. 
            “h01” hace referencia a la 1 de la mañana, 
            “h02” a las 2 de la mañana, y así sucesivamente hasta las 24h
        - v01, ..., v024: Validación de la h01, ..., h024.Dónde:
            "V" hace referencia a valor válido
            "N" a valor no válido

    * CÓDIGOS DE MEDIDAS DE LOS DATOS METEREOLOGICOS:
                                    TECNICA UNIDAD DESCRIPCIÓN_UNIDAD
        80: RADIACIÓN ULTRAVIOLETA  89      m/s     metros por segundo
        81: VELOCIDAD DEL VIENTO    89      Grd     grados
        82: DIRECCIÓN DEL VIENTO    89      ºc      grados centígrados  
        83: TEMPERATURA             89      %       porcentaje
        86: HUMEDAD RELATIVA        89      mbar    milibar
        88: RADIACIÓN SOLAR         89      W/m2    vatios por metro cuadrado
        89: PRECIPITACIÓN           89      l/m2    litros por metro cuadrado 

    # Códigos estaciones:
        CODIGO   CODIGO     NOMBRE
        NACIONAL MUNICIPIO  ESTACION
        28005002 5          ALCALÁ DE HENARES
        28006004 6          ALCOBENDAS
        28007004 7          ALCORCÓN
        28009001 9          ALGETE
        28013002 13         ARANJUEZ
        28014002 14         ARGANDA DEL REY
        28016001 16         EL ATAZAR
        28045002 45         COLMENAR VIEJO
        28047002 47         COLLADO VILLALBA
        28049003 49         COSLADA
        28058004 58         FUENLABRADA
        28065014 65         GETAFE
        28067001 67         GUADALIX DE LA SIERRA
        28074007 74         LEGANÉS
        28080003 80         MAJADAHONDA
        28092005 92         MÓSTOLES
        28102001 102        ORUSCO DE TAJUÑA
        28120001 120        PUERTO DE COTOS
        28123002 123        RIVAS-VACIAMADRID
        28133002 133        SAN MARTÍN DE VALDEIGLESIAS
        28148004 148        TORREJÓN DE ARDOZ
        28161001 161        VALDEMORO
        28171001 171        VILLA DEL PRADO
        28180001 180        VILLAREJO DE SALVANÉS

# ANÁLISIS PRELIMINAR
Este análisis preliminar nos permite determinar que varibles incluiremos en en análisis definitivo.

1. CONTAMINANTES PARA EL ESTUDIO:
En Madrid, los más relevantes en cuanto a sus efectos para la salud son:
* Dióxido de nitrógeno (NO2):
    Es un contaminante atmosférico que se produce fundamentalmente en las combustiones de los vehículos de motor.

    Hasta el 80% de las emisiones de este contaminante procede del tráfico rodado, sobre todo de los vehículos diésel. El resto de las emisiones se origina durante la combustión de gas, petróleo y carbón, en centrales térmicas, actividades industriales, calefacciones, incineradoras, etc

    Los principales síntomas asociados a episodios de alta contaminación por dióxido de nitrógeno son:
    - Picor de ojos, nariz y garganta.
    - Irritación de los bronquios con tos, flemas, dificultad para respirar.

* Partículas en suspensión: 
    Constituyen un contaminante atmosférico procedente    tanto de fuentes naturales (tormentas de arena, erupciones volcánicas, incendios forestales, etc.) como de la actividad humana (tráfico, especialmente vehículos diésel, incineradoras, calefacciones de carbón, minería, procesos industriales, etc.).
    - PM2,5 (tamaño inferior a 2,5 micras): 
        Proceden fundamentalmente de la actividad humana, pueden penetrar hasta las partes más profundas del pulmón y pasar a la sangre, y por ello resultan especialmente nocivas.
    - PM10 ():tamaño inferior a 10 micras
        Al ser más grandes quedan en buena parte retenidas en las porciones superiores del aparato respiratorio, como las fosas nasales o los grandes bronquios. Resultan menos perjudiciales para la salud que las PM2,5, pero no son inocuas y se ha observado un aumento de la demanda de atención urgente por crisis asmáticas cuando aumenta su concentración en el aire.

    En nuestra Comunidad, una causa muy frecuente de aumento de partículas es la llegada de polvo del desierto del Sáhara empujado por vientos del sur.

    Este polvo, que puede permanecer en el aire durante horas y presentarse como una neblina de color marrón, puede llevar en su composición materia mineral (arcillas, cuarzos, carbonatos, etc.) y también biológico, como fragmentos vegetales, polen, virus, bacterias, etc.


* Ozono troposférico(O3):
    Es un gas incoloro que puede resultar beneficioso o nocivo para la salud, dependiendo de si se encuentra en las capas más altas de la atmósfera o a nivel del suelo. Por ello se habla de:

    - Ozono bueno (ozono estratosférico): 
        Se localiza en la estratosfera, a una distancia de la superficie terrestre de entre 12 a 50 km, formando una capa que nos protege de los dañinos rayos ultravioleta del sol. Este es el ozono al que se hace referencia cuando se habla del “agujero de la capa de ozono”.
    - Ozono malo (ozono troposférico): 
        Se localiza en la troposfera, es decir, la parte de la atmósfera donde se desarrolla la vida humana. Este ozono se forma como resultado de reacciones químicas, en presencia de la luz solar, a partir de los contaminantes emitidos por automóviles, centrales térmicas, refinerías, procesos industriales diversos etc. Cuanto mayor sea la luz solar y la temperatura, mayor será la cantidad de ozono que se forme; por ello, las mayores concentraciones de este gas se dan en verano.


    Los posibles síntomas asociados a episodios de contaminación por ozono, entre otros, son:

    - Irritación ocular y de las vías respiratorias con tos, molestias de garganta, dolor torácico al respirar profundamente.
    - Mayor dificultad para respirar con normalidad, sobre todo al hacer ejercicio.
    - Mayor susceptibilidad a las infecciones respiratorias.
    - Ataques de asma y agravamiento de ésta y otras enfermedades  respiratorias, como el enfisema o la bronquitis crónica.
    
2. OBTENCION DEL ICA (INDICE DE CALIDAD DEL AIRE)
    El Índice de Calidad del Aire (ICA) establecido por la Red de Vigilancia y Control de la Contaminación Atmosférica de la Comunidad de Madrid (REVA). 
    El ICA de Madrid se basa en la concentración de cuatro contaminantes principales: 

    * dióxido de azufre (SO2)
    * dióxido de nitrógeno (NO2)
    * partículas en suspensión (PM10) 
    * ozono (O3).

    El cálculo del ICA de Madrid se realiza asignando un valor numérico a cada uno de los contaminantes y luego promediando estos valores ponderados. La fórmula utilizada para calcular el ICA es la siguiente:

    - ICA = (ICA_SO2 + ICA_NO2 + ICA_PM10 + ICA_O3) / 4

    Donde ICA_SO2, ICA_NO2, ICA_PM10 y ICA_O3 son los valores individuales del índice de calidad del aire para cada contaminante, que se calculan de la siguiente manera:

    - ICA_SO2 = (Concentración_SO2 / Valor_Límite_SO2) * 100
    - ICA_NO2 = (Concentración_NO2 / Valor_Límite_NO2) * 100
    - ICA_PM10 = (Concentración_PM10 / Valor_Límite_PM10) * 100
    - ICA_O3 = (Concentración_O3 / Valor_Límite_O3) * 100

    En cada fórmula, se divide la concentración del contaminante por el valor límite establecido para ese contaminante y se multiplica por 100 para obtener un porcentaje. Luego, se promedian los valores de ICA de los cuatro contaminantes para obtener el índice de calidad del aire general.


    * Supongamos que tenemos los siguientes datos ficticios para las concentraciones  de los contaminantes en Madrid:

        Dióxido de Azufre (SO2): Concentración = 15 μg/m³, Valor Límite = 50 μg/m³
        Dióxido de Nitrógeno (NO2): Concentración = 40 μg/m³, Valor Límite = 40 μg/m³
        Partículas en Suspensión (PM10): Concentración = 25 μg/m³, Valor Límite = 50 μg/m³
        Ozono (O3): Concentración = 60 μg/m³, Valor Límite = 120 μg/m³
3. VALORES LIMITE CONTAMINANTES
Compuesto   Valor límite /      Concentración       Nº máximo de superaciones
            objetivo / 
            Umbral de Alerta

* PM10: 	Media anual. 	     40 μg/m3 	 
            Media diaria. 	     50 μg/m3 	         35 días/año
* SO2   	Media diaria. 	     125 μg/m3 	         3 días/año
            Media horaria. 	     350 μg/m3 	         24 horas/año
            Umbral de alerta     500 μg/m3
            (3 horas consecutivas en área representativa de 100 km o zona o aglomeración entera). 	 	 
* NO2   	Media anual. 	     40 μg/m3 	 
            Media horaria. 	     200 μg/m3 	        18 horas/año
            Umbral de alerta     400 μg/m3
            (3 horas consecutivas en área representativa de 100 km o zona o aglomeración entera). 	 	 
* O3   	    Máxima diaria de     120 μg/m3 	        25 días /  año,
            las medias móviles octohorarias.  	promediados en un período de 3 años
            Umbral de información:
            Media horaria. 	      180 μg/m3 	 
            Umbral de alerta. 
            Media horaria. 	      240 μg/m3 	 
 	 

Calculamos el índice de calidad del aire para cada contaminante utilizando las fórmulas proporcionadas anteriormente:

ICA_SO2 = (15 / 50) * 100 = 30
ICA_NO2 = (40 / 40) * 100 = 100
ICA_PM10 = (25 / 50) * 100 = 50
ICA_O3 = (60 / 120) * 100 = 50

Luego, promediamos los valores de ICA de los cuatro contaminantes para obtener el índice de calidad del aire general:

ICA = (30 + 100 + 50 + 50) / 4 = 57.5

En este ejemplo ficticio, el índice de calidad del aire en Madrid sería de aproximadamente 57.5.


- CODIGO DE EJEMPLO PARA CALCULAR ICA.
    # Crear función calcular_ICA
        def calcular_ICA(concentraciones, valores_limites):
            num_contaminantes = len(concentraciones)
            ica_total = 0
            
            for i in range(num_contaminantes):
                ica_contaminante = (concentraciones[i] / valores_limites[i]) * 100
                ica_total += ica_contaminante
            
            ica_promedio = ica_total / num_contaminantes
            return ica_promedio

        # Datos de concentraciones de contaminantes ficticios en Madrid
        concentraciones = [15, 40, 25, 60]  # SO2, NO2, PM10, O3
        valores_limites = [50, 40, 50, 120]  # SO2, NO2, PM10, O3

        # Calcular el índice de calidad del aire
        ica = calcular_ICA(concentraciones, valores_limites)
        print("El índice de calidad del aire en Madrid es:", ica)

# ESTRUCTURA DEL PROYECTO:
1.  DATA 
    Carpeta con los csv reccopilados del portal de datos abiertos del Ayuntamiento de Madrid.
    * aire:
    Carpeta con los csv originales referentes a la calidad del aire en en año 2022/meses recogidos por la estaciones:
        - estaciones.cvs
    * metereología:
    Carpeta con los csv originales referentes a la metereología en en año 2022/meses recogidos por la estaciones:
        - Estaciones_control_datos_metereológicos.csv
    * Datos ya procesados con las columnas que nos interesan
        - aire_2022.csv
        - metee_2022.csv
2. NOTEBOOKS





   