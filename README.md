# Análisis del Censo de Arbolado de la Ciudad de Buenos Aires

Este proyecto se centra en el análisis del censo de arbolado urbano de la Ciudad de Buenos Aires, utilizando datos del censo 2017-2018. La fuente original de los datos se encuentra en el siguiente [enlace](https://cdn.buenosaires.gob.ar/datosabiertos/datasets/atencion-ciudadana/arbolado-publico-lineal/arbolado-publico-lineal-2017-2018.zip).

## Descripción del Proyecto

El objetivo de este proyecto es proporcionar un análisis exploratorio del arbolado urbano en la Ciudad de Buenos Aires, utilizando herramientas de geoprocesamiento y sistemas de indexación geoespacial. Se calcula un indicador que es el ratio cantidad de arboles autóctonos / cantidad total de arboles de cada celda H3

## Datos

Los datos utilizados provienen del censo de arbolado urbano 2017-2018 de la Ciudad de Buenos Aires. Incluyen información detallada sobre la ubicación, especies y estado de los árboles en la ciudad.

## Tecnologías y Herramientas Utilizadas

### H3: Sistema de Indexación Geoespacial

H3 es un sistema de indexación geoespacial que divide el mundo en celdas hexagonales. Este sistema permite realizar análisis espaciales de manera eficiente al proporcionar una estructura de datos consistente y escalable. H3 se utiliza en este proyecto para:

- Indexar los puntos geográficos de los árboles.
- Realizar agregaciones espaciales y análisis de proximidad.
- Facilitar la visualización y el mapeo de datos geoespaciales.

Se utilizó una resolución H3 igual a 9 por lo tanto el indicador está agregado por cada 105.332,51 mts cuadrados. Ver [enlace](https://h3geo.org/docs/core-library/restable)

Más información sobre H3 se puede encontrar en la [documentación oficial](https://h3geo.org/docs/).

### GeoPandas

GeoPandas es una biblioteca de Python que facilita el trabajo con datos geoespaciales. Extiende las capacidades de Pandas para permitir operaciones espaciales como la manipulación de geometrías y la realización de análisis espaciales. En este proyecto, GeoPandas se utiliza para:

- Leer y manipular los datos del censo de arbolado.
- Realizar operaciones espaciales como uniones y agregaciones.
- Visualizar los datos en mapas interactivos.

## Estructura del Proyecto

- `DATA/`: Respositorio de datos necesarios para ejecutar la notebook.
- `OUTPUT/`: Respositorio de archivos de salida luego de ejecutar la notebook. Estos archivos son utilizados luego para la visualización en el mapa utilizando [enlace](https://kepler.gl/).
- `README.md`: Este archivo, proporcionando una descripción general del proyecto.

## Instalación y Uso

### Requisitos

- Python 3
- pip install -r requirements.txt

### Instalación

1. Clona este repositorio:
   ```bash
   git clone https://github.com/jplosada/gis-censo-arbolado-caba
