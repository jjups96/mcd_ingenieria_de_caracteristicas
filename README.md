# mcd_ingenieria_de_caracteristicas

## Descripción del proyecto
Desde un inicio el profesor Waissman nos habló del proyecto final, un proceso de ingeniería de características que podía ser sencillo pero completo. El tema por elegir era libre, pero de cierta manera debía estar relacionado con la región o el país. Siempre ha sido de mi interés los temas relacionados con la marginación, y durante la clase de matemáticas de la profesora Gutu analizamos el índice de marginación de la CONAPO por lo que decidí hacerlo parte central de mi proyecto de ingeniería; otra de las restricciones de la primera tarea era el que necesitábamos dos fuentes de datos distintas, por ello se decidió relacionar la marginación con el crimen. así nuestra primera pregunta a responder fue **¿Hay alguna relación entre la marginación y el crimen reportado?**

## Obtención de información  
[En esta libreta]( https://github.com/jjups96/mcd_ingenieria_de_caracteristicas/blob/main/Proyecto1/Proyecto1_VersionFinal.ipynb) se esta mucho mejor explicado mi lógica para la obtención de los datos pero te doy un resumen en retrospectiva, la obtención de los datos de marginación son muy fáciles de obtener están disponibles a través del la [página de datos abiertos de México]( http://www.conapo.gob.mx/work/models/CONAPO/Marginacion/Datos_Abiertos/Municipio/IMM_2020.xls) , en cuanto a los datos de relacionados con las llamadas al 911 eso es otro boleto se tuvo que realizar un web scraping a la a una [aplicación de la Secretaria de Seguridad Pública del Estado de Sonora]( http://apps.sspsonora.gob.mx/Incidencia911/Analisis/Index).

## Análisis exploratorio de datos
Durante esta fase nos dimos cuenta de que una limpieza ni armonización era necesario pues las dos fuentes seguían las pautas establecidas por la secretaria de datos el gobierno.
Usando pandas-profiler, que por cierto funciono cuando se instalo y a la siguiente vez que lo use tuve que usar un ambiente solo para él, se realizó un análisis exploratorio de datos rápido y furioso, el cual no dio los resultados esperados, no se encontró una relación entre la marginación y las llamadas al 911.

![Primer eda]( https://github.com/jjups96/mcd_ingenieria_de_caracteristicas/blob/main/imagenes/EDARapidoFurioso.png)

Intrigado por el suceso, recurrí a otra fuente de datos relacionada con el crimen, [las incidencias delictivas]( https://www.gob.mx/sesnsp/acciones-y-programas/datos-abiertos-de-incidencia-delictiva?state=published), con el cual se desarrolló de nuevo análisis exploratorio de datos con pandas-profiler, este confirmo lo encontrado con el primero, no hay una relación entre el la incidencia delictiva (reportada) y la marginación, o por lo menos no una muy fuerte.

![Segundo eda]( https://github.com/jjups96/mcd_ingenieria_de_caracteristicas/blob/main/imagenes/EDARapidoFurioso2.png)
Así se procedió a indagar el comportamiento de la incidencia delictiva y las llamadas al 911, puesto que se observo una fuerte relación, y me pareció interesante el definir su naturaleza

![Relacion]( https://github.com/jjups96/mcd_ingenieria_de_caracteristicas/blob/main/imagenes/EDARapidoFurioso2_911.png)

Se procedió a crear un nuevo archivo de recolección de datos, para fusionar los datos de las llamadas y las incidencias.
## Tablero
Para el tablero, se quería que usuario observara los cambios en el uso de la línea de emergencias y al mismo tiempo como ha cambiado la incidencia delictiva.

[Link al tablero](https://datastudio.google.com/reporting/a45a9873-b805-4a28-982a-d22dfe727214)

