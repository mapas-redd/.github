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


