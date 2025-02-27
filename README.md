# DEMO: Análisis del Censo de Arbolado de la Ciudad de Buenos Aires

Análisis del censo de arbolado urbano de la Ciudad de Buenos Aires, utilizando datos del censo 2017-2018. La fuente original de los datos se encuentra en el siguiente [enlace](https://cdn.buenosaires.gob.ar/datosabiertos/datasets/atencion-ciudadana/arbolado-publico-lineal/arbolado-publico-lineal-2017-2018.zip).

## Descripción

El objetivo de este trabajo es mostrar a través de un ejemplo como realizar análisis exploratorio con datos geo referenciados, utilizando herramientas de geoprocesamiento y sistemas de indexación geoespacial y su potencial uso en aplicaciones de políticas públicas.

Se realiza una demo usando como indicador el ratio `cantidad de arboles autóctonos / cantidad total de arboles` encontrados dentro de cada hexágono H3 (Aprox. 105 mil metros cuadrados).

Al final se podrán observar en el mapa las zonas con mayor y menor proporción de especies autóctonas. 

## Datos

Los datos utilizados provienen del censo de arbolado urbano 2017-2018 de la Ciudad de Buenos Aires. Incluyen información detallada sobre la ubicación, especies y estado de los árboles en la ciudad.

## Tecnologías y Herramientas Utilizadas

### H3: Sistema de Indexación Geoespacial

H3 es un sistema de indexación geoespacial que divide el mundo en celdas hexagonales. Este sistema permite realizar análisis espaciales de manera eficiente al proporcionar una estructura de datos consistente y escalable. H3 se utiliza en este proyecto para:

- Indexar los puntos geográficos de los árboles.
- Realizar agregaciones espaciales y análisis de proximidad.
- Facilitar la visualización y el mapeo de datos geoespaciales.

Se utilizó una resolución 9 para el cálculo de los índices H3 por lo tanto el indicador está agregado por cada 105.332,51 mts cuadrados. Ver [enlace](https://h3geo.org/docs/core-library/restable)

Más información sobre H3 se puede encontrar en la [documentación oficial](https://h3geo.org/docs/).

### GeoPandas

GeoPandas es una biblioteca de Python que facilita el trabajo con datos geoespaciales. Extiende las capacidades de Pandas para permitir operaciones espaciales como la manipulación de geometrías y la realización de análisis espaciales. En este proyecto, GeoPandas se utiliza para:

- Leer y manipular los datos del censo de arbolado.
- Realizar operaciones espaciales como uniones y agregaciones.
- Visualizar los datos en mapas interactivos.

### Kepler.gl

Cómo herramienta de visualización de mapas con estructuras de índices H3. [Kepler.gl](https://kepler.gl/)

## Estructura del Proyecto

- `DATA/`: Respositorio de datos necesarios para ejecutar la notebook.
- `OUTPUT/`: Respositorio de archivos de datos de salida. Estos archivos son utilizados luego para la visualización en un mapa utilizando [Kepler.gl](https://kepler.gl/). El mapa es interactivo y se puede ver localmente abriendo el archivo `kepler.gl.html` con un browser. Versión del mapa on-line en [huggingface](https://huggingface.co/spaces/jplosada/gis-censo-arbolada-caba)
- `exploracion.ipynb`: Esta notebook contiene el código necesario para descargar los datos del censo de arbolado, realizar el preprocesamiento de los datos incluyendo el cálculo del índice H3 y generar los archivos de salida para visualización la distribucíon del indicador en un mapa.

## Instalación y Uso

### Requisitos

- Python 3
- pip install -r requirements.txt

### Instalación

1. Clona este repositorio:
   ```bash
   git clone https://github.com/jplosada/gis-censo-arbolado-caba
