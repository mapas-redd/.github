# Programas para la elaboración de mapas de uso y cobertura de la tierra en el contexto de REDD+
Esta organización contiene un conjunto de repositorios de código fuente de programas informáticos (*scripts*) para la elaboración de mapas de uso y cobertura de la tierra, en el contexto del mecanismo de Reducción de Emisiones por Deforestación y Degradación de bosques más conservación y aumento de reservas de carbono forestal (REDD+).

En este documento, se listan los repositorios, se brindan las instrucciones para la instalación de las herramientas informáticas necesarias y se describe el protocolo metodológico para el uso de los programas en el proceso de elaboración de los mapas.

## Repositorios
Los repositorios de código fuente son los siguientes:

- [https://github.com/redd-costarica-scripts/redd-costarica-scripts-qgis](https://github.com/redd-costarica-scripts/redd-costarica-scripts-qgis): programas para ejecutarse en el sistema de información geográfica QGIS.
- [https://github.com/redd-costarica-scripts/redd-costarica-randomforest-r](https://github.com/redd-costarica-scripts/redd-costarica-randomforest-r): programa en el lenguaje R que implementa el algoritmo de clasificación Random Forest.
- [https://github.com/redd-costarica-scripts/redd-costarica-scripts-bat](https://github.com/redd-costarica-scripts/redd-costarica-scripts-bat): programas para archivos `.bat` del sistema operativo Microsoft Windows.

## Herramientas informáticas
Para utilizar los programas, es necesario instalar las siguientes herramientas:

- [QGIS](https://qgis.org): sistema de información geográfica. En este proyecto, se utilizó la **versión 3.22.11 Białowieża LTR**. Siga las instrucciones correspondientes a su sistema operativo en la [página de descargas de QGIS](https://qgis.org/en/site/forusers/download.html). Para el caso de Microsoft Windows, se recomienda el instalador [OSGeo4W](https://qgis.org/en/site/forusers/alldownloads.html#osgeo4w-installer).
- [Orfeo Toolbox (OTB)](http://orfeo-toolbox.org/): biblioteca para procesamiento de imágenes de satélite. En este proyecto, se utilizó la **versión 8.1.0**. Siga las instrucciones correspondientes a su sistema operativo en la [página de descargas de OTB](https://www.orfeo-toolbox.org/download/). En QGIS, debe configurar la [interfaz para OTB](https://www.orfeo-toolbox.org/CookBook/QGISInterface.html).
- [FMask](https://github.com/GERSL/Fmask): software para detección de nubes y sombras en imágenes satelitales. En este proyecto, se utilizó la **versión 4.6**. Siga las instrucciones correspondientes a su sistema operativo.
- [R](https://www.r-project.org/) y [RStudio Desktop](https://www.rstudio.com/products/rstudio/): lenguaje de programación para análisis estadístico y ambiente de desarrollo integrado. En este proyecto, se utilizó la **versión 4.2.1 de R** y la **versión 2022.07.1+554 de RStudio Desktop**. Siga las instrucciones correspondientes a su sistema operativo en la [página de descargas de R](https://cloud.r-project.org/) y en la [página de descargas de RStudio](https://www.rstudio.com/products/rstudio/download/).

Adicionalmente, para usuarios avanzados, se recomienda instalar el sistema para control de versiones [Git](https://git-scm.com/). Siga las instrucciones correspondientes a su sistema operativo en la [página de descargas](https://git-scm.com/downloads).

## Protocolo metodológico
Los programas apoyan el protocolo metodológico del proyecto *Generating a Consistent Historical Time Series of Activity Data from Land Use Change for the Development of Costa Rica’s REDD Plus Reference Level*, desarrollado por Agresta, Digital Image Processing (Dimap), la Universidad de Costa Rica y la Universidad Politécnica de Madrid.

Este protocolo consiste de una serie de pasos, los cuales se enumeran seguidamente:

1. Descarga de imágenes y metadatos.


### 1. Descarga de imágenes y metadatos
Para descargar las imágenes, se recomienda el sitio [EarthExplorer](https://earthexplorer.usgs.gov/) u otro similar. Como resultado de la descarga, debe obtenerse un directorio con los archivos correspondientes a las bandas y a los metadatos de la imagen. Por ejemplo:

```
D:\img\LC09_L1TP_016052_20220123_20220124_02_T1>dir
 Volume in drive D is UserProfile
 Volume Serial Number is DCD0-6D08

 Directory of D:\img\LC09_L1TP_016052_20220123_20220124_02_T1

09/17/2022  03:16 PM    <DIR>          .
09/17/2022  03:16 PM    <DIR>          ..
08/25/2022  06:11 PM           117,265 LC09_L1TP_016052_20220123_20220124_02_T1_ANG.txt
08/25/2022  06:11 PM        92,456,776 LC09_L1TP_016052_20220123_20220124_02_T1_B1.TIF
08/25/2022  06:11 PM        78,117,066 LC09_L1TP_016052_20220123_20220124_02_T1_B10.TIF
08/25/2022  06:11 PM        76,638,423 LC09_L1TP_016052_20220123_20220124_02_T1_B11.TIF
08/25/2022  06:11 PM        93,049,369 LC09_L1TP_016052_20220123_20220124_02_T1_B2.TIF
08/25/2022  06:11 PM        94,258,569 LC09_L1TP_016052_20220123_20220124_02_T1_B3.TIF
08/25/2022  06:11 PM        95,043,094 LC09_L1TP_016052_20220123_20220124_02_T1_B4.TIF
08/25/2022  06:11 PM        96,473,639 LC09_L1TP_016052_20220123_20220124_02_T1_B5.TIF
08/25/2022  06:11 PM        94,374,651 LC09_L1TP_016052_20220123_20220124_02_T1_B6.TIF
08/25/2022  06:11 PM        91,639,190 LC09_L1TP_016052_20220123_20220124_02_T1_B7.TIF
08/25/2022  06:11 PM       371,677,952 LC09_L1TP_016052_20220123_20220124_02_T1_B8.TIF
08/25/2022  06:11 PM        48,009,301 LC09_L1TP_016052_20220123_20220124_02_T1_B9.TIF
08/25/2022  06:11 PM            14,842 LC09_L1TP_016052_20220123_20220124_02_T1_MTL.json
08/25/2022  06:11 PM            12,215 LC09_L1TP_016052_20220123_20220124_02_T1_MTL.txt
08/25/2022  06:11 PM            17,820 LC09_L1TP_016052_20220123_20220124_02_T1_MTL.xml
08/25/2022  06:11 PM         3,225,310 LC09_L1TP_016052_20220123_20220124_02_T1_QA_PIXEL.TIF
08/25/2022  06:11 PM           222,898 LC09_L1TP_016052_20220123_20220124_02_T1_QA_RADSAT.TIF
08/25/2022  06:11 PM         2,227,700 LC09_L1TP_016052_20220123_20220124_02_T1_SAA.TIF
08/25/2022  06:11 PM            49,903 LC09_L1TP_016052_20220123_20220124_02_T1_stac.json
08/25/2022  06:11 PM         1,968,117 LC09_L1TP_016052_20220123_20220124_02_T1_SZA.TIF
08/25/2022  06:11 PM           115,739 LC09_L1TP_016052_20220123_20220124_02_T1_thumb_large.jpeg
08/25/2022  06:11 PM            15,541 LC09_L1TP_016052_20220123_20220124_02_T1_thumb_small.jpeg
08/25/2022  06:11 PM         8,971,879 LC09_L1TP_016052_20220123_20220124_02_T1_VAA.TIF
08/25/2022  06:11 PM         3,433,766 LC09_L1TP_016052_20220123_20220124_02_T1_VZA.TIF
              24 File(s)  1,252,131,025 bytes
```

### 2. Detección de nubes y sombras
Este paso se realiza con el programa FMask. Debe ejecutarse en la línea de comandos del sistema operativo y desde el directorio en el que se encuentran los archivos de la imagen.

Entradas:
- Directorio con archivos de la imagen descargada.

Salidas:
- Archivo raster con pixeles marcados como tierra, agua, nubes o sombras.

```shell
cd LC09_L1TP_016052_20220123_20220124_02_T1
"C:\Program Files\GERS\Fmask_4_6\application\Fmask_4_6.exe"
```

```
09/18/2022  06:41 PM         1,691,740 LC09_L1TP_016052_20220123_20220124_02_T1_Fmask4.tif
```

Los pixeles de este archivo tienen 6 posibles valores:

0 = tierra  
1 = agua  
2 = sombra de nubes  
3 = nieve  
4 = nubes  
255 = sin observación  

![](https://github.com/redd-costarica-scripts/.github/blob/master/profile/img/fmask.png)
Imagen: Nubes y sombras detectadas con FMask.

