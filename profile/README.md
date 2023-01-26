# Scripts para la elaboración de mapas de uso y cobertura de la tierra de Costa Rica en el contexto de REDD+
Este es un conjunto de repositorios de código fuente de programas informáticos (*scripts*) para apoyar la elaboración de mapas de uso y cobertura de la tierra, en el contexto del mecanismo de [Reducción de Emisiones por Deforestación y Degradación de bosques más conservación y aumento de reservas de carbono forestal (REDD+)](https://es.wikipedia.org/wiki/Reducci%C3%B3n_de_las_emisiones_de_la_deforestaci%C3%B3n).

En este documento, se listan los repositorios, se brindan las instrucciones para la instalación de las herramientas informáticas necesarias y se describe el protocolo metodológico para el uso de los programas durante el proceso de elaboración de los mapas.

## Contenidos
1. [Repositorios](https://github.com/redd-costarica-scripts#1-repositorios)  
    1.1. [redd-costarica-scripts-qgis](https://github.com/redd-costarica-scripts#11-redd-costarica-scripts-qgis)  
    1.2. [redd-costarica-scripts-bat](https://github.com/redd-costarica-scripts#12-redd-costarica-scripts-bat)  
    1.3. [redd-costarica-randomforest-r](https://github.com/redd-costarica-scripts#13-redd-costarica-randomforest-r)      
2. [Herramientas informáticas](https://github.com/redd-costarica-scripts#2-herramientas-inform%C3%A1ticas)  
    2.1. [QGIS](https://github.com/redd-costarica-scripts#21-qgis)  
    2.2. [Orfeo Toolbox](https://github.com/redd-costarica-scripts#22-orfeo-toolbox)  
    2.3. [FMask](https://github.com/redd-costarica-scripts#23-fmask)  
    2.4. [R y RStudio](https://github.com/redd-costarica-scripts#24-r-y-rstudio)  
    2.5. [Git](https://github.com/redd-costarica-scripts#25-git)  
    2.6. [Complemento de QGIS `REDD+ Costa Rica`](https://github.com/redd-costarica-scripts#26-complemento-de-qgis-redd-costa-rica)  
    2.7. [Programas para procesamiento por lotes](https://github.com/redd-costarica-scripts#27-programas-para-procesamiento-por-lotes)  
    2.8. [Programas del algoritmo de clasificación Random Forest](https://github.com/redd-costarica-scripts#28-programas-del-algoritmo-de-clasificaci%C3%B3n-random-forest)  
3. [Protocolo metodológico](https://github.com/redd-costarica-scripts#3-protocolo-metodol%C3%B3gico)  
    3.1. [Descarga de imágenes y metadatos](https://github.com/redd-costarica-scripts#31-descarga-de-im%C3%A1genes-y-metadatos)  
    3.2. [Detección de nubes y sombras](https://github.com/redd-costarica-scripts#32-detecci%C3%B3n-de-nubes-y-sombras)  
    3.3. [Creación de una pila de bandas](https://github.com/redd-costarica-scripts#33-creaci%C3%B3n-de-una-pila-de-bandas)  
    3.4. [Cálculo de la reflectancia](https://github.com/redd-costarica-scripts#34-c%C3%A1lculo-de-la-reflectancia)  
    3.5. [Normalización horaria](https://github.com/redd-costarica-scripts#35-normalizaci%C3%B3n-horaria)  
    3.6. [Normalización radiométrica](https://github.com/redd-costarica-scripts#36-normalizaci%C3%B3n-radiom%C3%A9trica)  
        - 3.6.1. [Recorte de la imagen de referencia con la máscara vectorial del contorno del país](https://github.com/redd-costarica-scripts#361-recorte-de-la-imagen-de-referencia-con-la-m%C3%A1scara-vectorial-del-contorno-del-pa%C3%ADs)  
        - 3.6.2. [Recorte de la imagen con normalización horaria con la máscara vectorial del contorno del país](https://github.com/redd-costarica-scripts#362-recorte-de-la-imagen-con-normalizaci%C3%B3n-horaria-con-la-m%C3%A1scara-vectorial-del-contorno-del-pa%C3%ADs)  
        - 3.6.3. [Ejecución de `imad.py`](https://github.com/redd-costarica-scripts#363-ejecuci%C3%B3n-de-imadpy)  
        - 3.6.4. [Ejecución de `radcal.py`](https://github.com/redd-costarica-scripts#364-ejecuci%C3%B3n-de-radcalpy)  
    3.7. [Cálculo de índices de vegetación y textura](https://github.com/redd-costarica-scripts#37-c%C3%A1lculo-de-%C3%ADndices-de-vegetaci%C3%B3n-y-textura)  
    3.8. [Creación de máscaras de nubes y sombras](https://github.com/redd-costarica-scripts#38-creaci%C3%B3n-de-m%C3%A1scaras-de-nubes-y-sombras)  
    3.9. [Recorte de las máscaras de nubes y sombras con la máscara raster del contorno del país](https://github.com/redd-costarica-scripts#39-recorte-de-las-m%C3%A1scaras-de-nubes-y-sombras-con-la-m%C3%A1scara-raster-del-contorno-del-pa%C3%ADs)  
    3.10. [Eliminación de nubes y sombras](https://github.com/redd-costarica-scripts#310-eliminaci%C3%B3n-de-nubes-y-sombras)  
    3.11. [Combinación de bandas](https://github.com/redd-costarica-scripts#311-combinaci%C3%B3n-de-bandas)  
    3.12. [Generación de regiones de interés](https://github.com/redd-costarica-scripts#312-generaci%C3%B3n-de-regiones-de-inter%C3%A9s)  
    3.13. [Clasificación de las imágenes](https://github.com/redd-costarica-scripts#313-clasificaci%C3%B3n-de-las-im%C3%A1genes)  
    3.14. [Generación de mosaicos](https://github.com/redd-costarica-scripts#314-generaci%C3%B3n-de-mosaicos)  

## 1. Repositorios
Los repositorios de código fuente son los siguientes:

### 1.1. redd-costarica-scripts-qgis
[redd-costarica-scripts-qgis](https://github.com/redd-costarica-scripts/redd-costarica-scripts-qgis) contiene programas para ejecutarse en el sistema de información geográfica QGIS. Se agrupan en un complemento llamado `REDD+ Costa Rica`.

### 1.2. redd-costarica-scripts-bat
[redd-costarica-scripts-bat](https://github.com/redd-costarica-scripts/redd-costarica-scripts-bat) contiene programas para procesamiento por lotes en archivos `.bat` del sistema operativo Microsoft Windows.

### 1.3. redd-costarica-randomforest-r
[redd-costarica-randomforest-r](https://github.com/redd-costarica-scripts/redd-costarica-randomforest-r) contiene programas que implementan en el lenguaje R el algoritmo de clasificación Random Forest.

## 2. Herramientas informáticas
Para utilizar los programas contenidos en los repositorios, es necesario instalar diferentes herramientas que incluyen sistemas de información geográfica (SIG), bibliotecas y aplicaciones para teledetección, lenguajes de programación y sistemas de control de versiones. También un complemento de QGIS llamado `REDD+ Costa Rica`, el cual fue desarrollado como parte de esta iniciativa.

### 2.1. QGIS
[QGIS](https://qgis.org) es un SIG de escritorio. En este proyecto, se utilizó la **versión 3.22.11 Białowieża LTR**. Para su instalación, siga las instrucciones correspondientes a su sistema operativo en la [página de descargas de QGIS](https://qgis.org/en/site/forusers/download.html). Para el caso de Microsoft Windows, se recomienda el instalador [OSGeo4W](https://qgis.org/en/site/forusers/alldownloads.html#osgeo4w-installer).

### 2.2. Orfeo Toolbox
[Orfeo Toolbox (OTB)](http://orfeo-toolbox.org/) es una biblioteca para procesamiento de imágenes de satélite. En este proyecto, se utilizó la **versión 8.1.0**. Para instalarla, siga las instrucciones correspondientes a su sistema operativo en la [página de descargas de OTB](https://www.orfeo-toolbox.org/download/). En QGIS, debe configurar la [interfaz para OTB](https://www.orfeo-toolbox.org/CookBook/QGISInterface.html).

### 2.3. FMask
[FMask](https://github.com/GERSL/Fmask) es un programa para detección de nubes y sombras en imágenes satelitales. En este proyecto, se utilizó la **versión 4.6**. Para instalarla, siga las instrucciones correspondientes a su sistema operativo.

### 2.4. R y RStudio
[R](https://www.r-project.org/) es un lenguaje de programación para análisis estadístico y [RStudio Desktop](https://www.rstudio.com/products/rstudio/) es un ambiente de desarrollo integrado para R. En este proyecto, se utilizó la **versión 4.2.1 de R** y la **versión 2022.07.1+554 de RStudio Desktop**. Para instalarlos, siga las instrucciones correspondientes a su sistema operativo en la [página de descargas de R](https://cloud.r-project.org/) y en la [página de descargas de RStudio](https://www.rstudio.com/products/rstudio/download/).

### 2.5. Git
[Git](https://git-scm.com/) es un sistema de control de versiones distribuido. Para su instalación, siga las instrucciones correspondientes a su sistema operativo en la [página de descargas](https://git-scm.com/downloads). La instalación de Git es necesaria solamente para usuarios avanzados que deseen manejar el código fuente de los programas como, por ejemplo, los del complemento `REDD+ Costa Rica`.

### 2.6. Complemento de QGIS `REDD+ Costa Rica`
[`REDD+ Costa Rica`](https://github.com/redd-costarica-scripts/redd-costarica-scripts-qgis) es un complemento (*plugin*) de QGIS desarrollado con el marco de trabajo `Processing`. Puede descargarse como un [archivo ZIP](https://github.com/redd-costarica-scripts/redd-costarica-scripts-qgis/archive/refs/heads/main.zip) e instalarse en QGIS con la opción de menú `Plugins - Manage and Install Plugins... - Install from ZIP`.

![](https://github.com/redd-costarica-scripts/.github/blob/master/profile/img/plugin-install-zip.png)  
**Figura 1**. Instalación del complemento `REDD+ Costa Rica` a partir de un archivo ZIP.

Después de presionar el botón `Install Plugin`, el complemento se instalará y estará disponible en la barra de herramientas de `Processing`.

![](https://github.com/redd-costarica-scripts/.github/blob/master/profile/img/processing-toolbox-redd.png)  
**Figura 2**. Complemento `REDD+ Costa Rica` en la barra de herramientas de `Processing`.

Si se desea editar u observar el código fuente, el repositorio del complemento puede clonarse con el comando:

```shell
git clone https://github.com/redd-costarica-scripts/redd-costarica-scripts-qgis.git
```

Para que el directorio resultante (`redd-costarica-scripts-qgis`) funcione también en producción, debe colocarse en el directorio de complementos de QGIS (ej. `D:\Users\mfvargas\AppData\Roaming\QGIS\QGIS3\profiles\default\python\plugins`).

### 2.7. Programas para procesamiento por lotes
Pueden descargarse como un [archivo ZIP](https://github.com/redd-costarica-scripts/redd-costarica-scripts-bat/archive/refs/heads/main.zip). Si se desea editar u observar el código fuente, el repositorio puede clonarse con el comando:

```shell
git clone https://github.com/redd-costarica-scripts/redd-costarica-scripts-bat.git
```

### 2.8. Programas del algoritmo de clasificación Random Forest
Pueden descargarse como un [archivo ZIP](https://github.com/redd-costarica-randomforest-r/redd-costarica-scripts-bat/archive/refs/heads/main.zip). Si se desea editar u observar el código fuente, el repositorio puede clonarse con el comando:

```shell
git clone https://github.com/redd-costarica-scripts/redd-costarica-randomforest-r.git
```

## 3. Protocolo metodológico
Los programas apoyan el protocolo metodológico del proyecto *Generating a Consistent Historical Time Series of Activity Data from Land Use Change for the Development of Costa Rica’s REDD Plus Reference Level*, desarrollado por Agresta, Digital Image Processing (Dimap), la Universidad de Costa Rica y la Universidad Politécnica de Madrid.

El protocolo consiste de los siguientes pasos:

1. [Descarga de imágenes y metadatos.](https://github.com/redd-costarica-scripts#31-descarga-de-im%C3%A1genes-y-metadatos)  
2. [Detección de nubes y sombras.](https://github.com/redd-costarica-scripts#32-detecci%C3%B3n-de-nubes-y-sombras)  
3. [Creación de una pila de bandas.](https://github.com/redd-costarica-scripts#33-creaci%C3%B3n-de-una-pila-de-bandas)  
4. [Cálculo de la reflectancia](https://github.com/redd-costarica-scripts#34-c%C3%A1lculo-de-la-reflectancia)  
5. [Normalización horaria](https://github.com/redd-costarica-scripts#35-normalizaci%C3%B3n-horaria)  
6. [Normalización radiométrica](https://github.com/redd-costarica-scripts#36-normalizaci%C3%B3n-radiom%C3%A9trica)  
    6.1. [Recorte de la imagen de referencia con la máscara vectorial del contorno del país](https://github.com/redd-costarica-scripts#361-recorte-de-la-imagen-de-referencia-con-la-m%C3%A1scara-vectorial-del-contorno-del-pa%C3%ADs)  
    6.2. [Recorte de la imagen con normalización horaria con la máscara vectorial del contorno del país](https://github.com/redd-costarica-scripts#362-recorte-de-la-imagen-con-normalizaci%C3%B3n-horaria-con-la-m%C3%A1scara-vectorial-del-contorno-del-pa%C3%ADs)  
    6.3. [Ejecución de `imad.py`](https://github.com/redd-costarica-scripts#363-ejecuci%C3%B3n-de-imadpy)  
    6.4. [Ejecución de `radcal.py`](https://github.com/redd-costarica-scripts#364-ejecuci%C3%B3n-de-radcalpy)  
7. [Cálculo de índices de vegetación y textura](https://github.com/redd-costarica-scripts#37-c%C3%A1lculo-de-%C3%ADndices-de-vegetaci%C3%B3n-y-textura)  
8. [Creación de máscaras de nubes y sombras](https://github.com/redd-costarica-scripts#38-creaci%C3%B3n-de-m%C3%A1scaras-de-nubes-y-sombras)  
9. [Recorte de las máscaras de nubes y sombras con la máscara raster del contorno del país](https://github.com/redd-costarica-scripts#39-recorte-de-las-m%C3%A1scaras-de-nubes-y-sombras-con-la-m%C3%A1scara-raster-del-contorno-del-pa%C3%ADs)  
10. [Eliminación de nubes y sombras](https://github.com/redd-costarica-scripts#310-eliminaci%C3%B3n-de-nubes-y-sombras)  
11. [Combinación de bandas](https://github.com/redd-costarica-scripts#311-combinaci%C3%B3n-de-bandas)  
12. [Generación de regiones de interés](https://github.com/redd-costarica-scripts#312-generaci%C3%B3n-de-regiones-de-inter%C3%A9s)  
13. [Clasificación de las imágenes](https://github.com/redd-costarica-scripts#313-clasificaci%C3%B3n-de-las-im%C3%A1genes)  
14. [Generación de mosaicos](https://github.com/redd-costarica-scripts#314-generaci%C3%B3n-de-mosaicos)  

En las secciones siguientes, se detalla la ejecución de cada uno de estos pasos.

### 3.1. Descarga de imágenes y metadatos
Para descargar las imágenes, se recomienda acceder el sitio [EarthExplorer](https://earthexplorer.usgs.gov/) u otro similar. Como resultado de la descarga de cada imagen, debe obtenerse un directorio con los archivos correspondientes a las bandas y a los metadatos de esta. Por ejemplo:

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

### 3.2. Detección de nubes y sombras
Este paso se realiza con el programa FMask. Debe ejecutarse en la línea de comandos del sistema operativo y en el directorio en el que se encuentran los archivos de la imagen.

**Entradas**:
- Directorio con archivos de la imagen descargada. Por ejemplo:

```
D:\img\LC09_L1TP_016052_20220123_20220124_02_T1
```

**Procesamiento**:
- Cambio al directorio en el que se encuentran los archivos de la imagen y ejecución de FMask:

```shell
cd D:\img\LC09_L1TP_016052_20220123_20220124_02_T1
"C:\Program Files\GERS\Fmask_4_6\application\Fmask_4_6.exe"
```

**Salidas**:
- Imagen con pixeles marcados como tierra, agua, nubes o sombras.

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
**Figura 3**. Imagen con nubes (en blanco) y sombras (en negro) detectadas con FMask.

### 3.3. Creación de una pila de bandas
La "pila" (*stack*) de bandas, se utiliza para reunir varias bandas en un solo archivo. Se crea con el programa [gdal_merge.py](https://gdal.org/programs/gdal_merge.html) de GDAL. Está disponible en la opción de menú `Raster - Miscellaneous - Merge` de QGIS. Debe activarse la opción para almacenar cada archivo de entrada en una banda separada del archivo resultante con la pila.

**Entradas**:
- Archivos con bandas 2-7. Por ejemplo:

```
LC09_L1TP_016052_20220123_20220124_02_T1_B2.TIF
LC09_L1TP_016052_20220123_20220124_02_T1_B3.TIF
LC09_L1TP_016052_20220123_20220124_02_T1_B4.TIF
LC09_L1TP_016052_20220123_20220124_02_T1_B5.TIF
LC09_L1TP_016052_20220123_20220124_02_T1_B6.TIF
LC09_L1TP_016052_20220123_20220124_02_T1_B7.TIF
```

**Procesamiento**:
- Ejecución de `gdal_merge.py`, desde la línea de comandos del sistema operativo, o de `Raster - Miscellaneous - Merge` en QGIS.

![](https://github.com/redd-costarica-scripts/.github/blob/master/profile/img/merge.png)  
**Figura 4**. Opción de menú `Raster - Miscellaneous - Merge` de QGIS.


**Salidas**:
- Archivo con pila de bandas.

![](https://github.com/redd-costarica-scripts/.github/blob/master/profile/img/pila.png)  
**Figura 5**. Pila de bandas en falso color (4-3-2).

### 3.4. Cálculo de la reflectancia
En este paso, se convierten los valores digitales de las seis bandas con las que se está trabajando a valores de reflectancia. Se realiza con el algoritmo `Reflectancia` del complemento `REDD+ Costa Rica`.

**Entradas**:
- Archivo con pila de bandas (2 - 7). Por ejemplo, `LC09_L1TP_016052_20220123_20220124_02_T1-PILA.TIF`.
- `a`: se obtiene del campo `REFLECTANCE_MULT_BAND_X` del archivo de metadatos de la imagen.
- `b`: se obtiene del campo `REFLECTANCE _ADD_BAND_X` del archivo de metadatos de la imagen.
- `Cénit`: se obtiene al restar 90 - valor del campo `SUN_ELEVATION` del archivo de metadatos de la imagen.

**Procesamiento**:
- Ejecución del algoritmo `Reflectancia` del complemento `REDD+ Costa Rica` de QGIS.

![](https://github.com/redd-costarica-scripts/.github/blob/master/profile/img/ejecutar-reflectancia.png)  
**Figura 6**. Algoritmo `Reflectancia` del complemento `REDD+ Costa Rica`.

**Salidas**:
- Archivo con pila de bandas con valores de reflectancia.

![](https://github.com/redd-costarica-scripts/.github/blob/master/profile/img/reflectancia.png)   
**Figura 7**. Pila de bandas con valores de reflectancia en falso color (4-3-2).

### 3.5. Normalización horaria
Cuando se realizan análisis temporales con imágenes captadas en diferentes fechas y horas, es necesario normalizarlas para que sean comparables entre sí. Para normalizar una imagen, se corrige el valor de cada pixel con un factor que considera la variación del flujo solar incidente en la imagen respecto a otra imagen de referencia. 

Esta tarea se realiza con el algoritmo `Normalización horaria` del complemento `REDD+ Costa Rica`.

**Entradas**:
- Archivo con pila de bandas con valores de reflectancia (2 - 7). Por ejemplo, `LC09_L1TP_016052_20220123_20220124_02_T1-REFLECTANCIA.TIF`.
- `Cénit`: se obtiene al restar 90 - valor del campo `SUN_ELEVATION` del archivo de metadatos de la imagen.
- `Cénit de la imagen de referencia`: se utiliza por defecto un valor igual a 36.9.

**Procesamiento**:
- Ejecución del algoritmo `Normalización horaria` del complemento `REDD+ Costa Rica` de QGIS.

![](https://github.com/redd-costarica-scripts/.github/blob/master/profile/img/ejecutar-normalizacion-horaria.png)  
**Figura 8**. Algoritmo `Normalización horaria` del complemento `REDD+ Costa Rica`.

**Salidas**:
- Archivo con pila de bandas con normalización horaria.

![](https://github.com/redd-costarica-scripts/.github/blob/master/profile/img/horaria.png)   
**Figura 9**. Pila de bandas con normalización horaria en falso color (4-3-2).

### 3.6. Normalización radiométrica
La normalización radiométrica se realiza para corregir diferencias entre imágenes, causadas por variaciones en las condiciones atmosféricas y de iluminación. La implementación usada aquí está basada en el algoritmo IR-MAD (Iteratively Reweighted Multivariante ALteration Detection), propuesto por Canty & Nielsen. Este método se basa en la localización de pixeles invariantes entre la imagen que se desea corregir y una imagen de referencia.

Este paso se ejecuta con los programas `imad.py` y `radcal.py`, los cuales se distribuyen junto con el complemento `REDD+ Costa Rica`. Antes de ejecutar estos programas, tanto la imagen de referencia como la imagen que desea normalizarse, deben recortarse con la máscara vectorial del contorno del país, en formato vectorial. Para el caso de Costa Rica, el contorno del país se divide de acuerdo con los *paths* ("pasadas") correspondientes a los recorridos de Landsat: P14 (este), P15 (centro) y P16 (oeste), por lo que cada imagen se recorta con respecto al contorno de su *path*.

#### 3.6.1. Recorte de la imagen de referencia con la máscara vectorial del contorno del país
Se realiza con la herramienta `Clip raster by Mask Layer (gdalwarp)` del marco de trabajo `Processing` de QGIS.

**Entradas**:
- Imagen de referencia para la "pasada" correspondiente (P14, P15, P16).
- Máscara vectorial para la "pasada" correspondiente (P14, P15, P16).

**Procesamiento**:
- Ejecución de la herramienta `Clip raster by Mask Layer (gdalwarp)` del marco de trabajo `Processing` de QGIS.

![](https://github.com/redd-costarica-scripts/.github/blob/master/profile/img/recortar-referencia-p16-01.png)  
**Figura 10**. Herramienta `Clip raster by Mask Layer (gdalwarp)` de `Processing` de QGIS.

**Salidas**:
- Imagen de referencia recortada.

![](https://github.com/redd-costarica-scripts/.github/blob/master/profile/img/referencia-p16-recortada.png)   
**Figura 11**. Imagen de referencia recortada en falso color (4-3-2).

#### 3.6.2. Recorte de la imagen con normalización horaria con la máscara vectorial del contorno del país
Se realiza con la herramienta `Clip raster by Mask Layer (gdalwarp)` del marco de trabajo `Processing` de QGIS.

**Entradas**:
- Imagen con normalización horaria.
- Máscara vectorial para la "pasada" correspondiente (P14, P15, P16).

**Procesamiento**:
- Ejecución de la herramienta `Clip raster by Mask Layer (gdalwarp)` del marco de trabajo `Processing` de QGIS.

![](https://github.com/redd-costarica-scripts/.github/blob/master/profile/img/recortar-horaria-01.png)  
**Figura 12**. Herramienta `Clip raster by Mask Layer (gdalwarp)` de `Processing` de QGIS.

**Salidas**:
- Imagen con normalización horaria recortada.

![](https://github.com/redd-costarica-scripts/.github/blob/master/profile/img/horaria-recortada.png)   
**Figura 13**. Imagen con normalización horaria recortada en falso color (4-3-2).

#### 3.6.3. Ejecución de `imad.py`
Se ejecuta desde la consola de Python en QGIS o (en Microsoft Windows) desde la 
línea de comandos de `OSGeo4W Shell` (esta opción permite visualizar mejor el progreso del script y los mensajes de error). **En ambos casos, deben modificarse las rutas de los archivos de entrada y salida ubicados al inicio del script**. Si se ejecuta desde QGIS, debe abrirse el script en el editor de la consola de Python y presionar el botón `Run Script`.

**Entradas**:
- Imagen de referencia recortada.
- Imagen a normalizar recortada.

Las rutas y nombres de estos archivos (así como los del archivo de salida), deben modiricarse en el archivo `imad.py`. Por ejemplo:

```python
# Imagen de referencia recortada
referencia = "D:/redd/referencia/P16_r52_2014057_utm16-RECORTADA.TIF"
# Imagen a normalizar recortada
imagen_a_normalizar = "D:/redd/img/LC09_L1TP_016052_20220123_20220124_02_T1-SALIDA/LC09_L1TP_016052_20220123_20220124_02_T1-HORARIA_RECORTADA.tif"
# Archivo de salida
outfile = "D:/redd/img/LC09_L1TP_016052_20220123_20220124_02_T1-SALIDA/IMAD.tif"
```

**Procesamiento**:
- Ejecución de `imad.py`.

Si se ejecuta desde `OSGeo4W Shell`:
```shell
cd redd-costarica-scripts-qgis
python imad.py
```

**Salidas:**
- Imagen de salida de `imad.py`. Por ejemplo:

```
IMAD.TIF
```

No se muestra una imagen de esta salida, por ser un producto intermedio.

#### 3.6.4. Ejecución de `radcal.py`
Se ejecuta desde la consola de Python en QGIS o (en Microsoft Windows) desde la 
línea de comandos de `OSGeo4W Shell` (esta opción permite visualizar mejor el progreso del script y los mensajes de error). **En ambos casos, deben modificarse las rutas de los archivos de entrada y salida ubicados al inicio del script**. Si se ejecuta desde QGIS, debe abrirse el script en el editor de la consola de Python y presionar el botón `Run Script`.

**Entradas**:
- Imagen de referencia recortada.
- Imagen a normalizar recortada.
- Imagen con normalización horaria.
- Imagen de salida de `imad.py`.

Las rutas y nombres de estos archivos (así como los de los archivos de salida), deben modiricarse en el archivo `radcal.py`. Por ejemplo:

```python
# Imagen de referencia recortada
referencia = "D:/redd/referencia/P16_r52_2014057_utm16-RECORTADA.TIF"
# Imagen a normalizar recortada
imagen_a_normalizar = imagen_a_normalizar = "D:/redd/img/LC09_L1TP_016052_20220123_20220124_02_T1-SALIDA/LC09_L1TP_016052_20220123_20220124_02_T1-HORARIA_RECORTADA.tif"
# Imagen con normalización horaria
fsfile = "D:/redd/img/LC09_L1TP_016052_20220123_20220124_02_T1-SALIDA/LC09_L1TP_016052_20220123_20220124_02_T1-HORARIA.tif"
# Imagen de salida de imad.py
iMad = "D:/redd/img/LC09_L1TP_016052_20220123_20220124_02_T1-SALIDA/IMAD.tif"
ncpThresh = 0.95
format_1GTiff_2PCIDSK_3HFA_4_ENVI = 1
# Imagen de salida de radcal.py
outfile = "D:/redd/img/LC09_L1TP_016052_20220123_20220124_02_T1-SALIDA/RADCAL.tif"
# Imagen con normalización radiométrica
fsoutfile = "D:/redd/img/LC09_L1TP_016052_20220123_20220124_02_T1-SALIDA/RADIOMETRICA.tif"
```

**Procesamiento**:
- Ejecución de `radcal.py`.

Si se ejecuta desde `OSGeo4W Shell`:
```shell
cd redd-costarica-scripts-qgis
python imad.py
```

**Salidas:**
- Imagen de salida de `radcal.py`. Por ejemplo:

```
RADCAL.TIF
```

- Imagen con normalización radiométrica. Por ejemplo:

```
RADIOMETRICA.tif
```

![](https://github.com/redd-costarica-scripts/.github/blob/master/profile/img/radiometrica.png)   
**Figura 14**. Imagen con normalización radiométrica en falso color (4-3-2).

### 3.7. Cálculo de índices de vegetación y textura
En este paso, se calculan dos tipos de índices:

- Índice de vegetación de diferencia normalizada (NDVI): mide el estado de salud de la vegetación, con base en la medición de la radiación que las plantas emiten o reflejan.
- Índices de textura de Haralick: se calculan los índices: “Mean”, “Sum Entropy”, “Diference of Entropies”, “Diference of Variances”, “IC1”, e “IC2”.

El cálculo de los índices se realiza con el algoritmo `Índices de vegetación y textura` del complemento `REDD+ Costa Rica`.

**Entradas**:
- Imagen con normalización radiométrica.

```
RADIOMETRICA.tif
```

**Procesamiento**:
- Ejecución del algoritmo `Índices de vegetación y textura` del complemento `REDD+ Costa Rica` de QGIS.

![](https://github.com/redd-costarica-scripts/.github/blob/master/profile/img/calcular-indices-vegetacion-textura.png)  
**Figura 15**. Algoritmo `Índices de vegetación y textura` del complemento `REDD+ Costa Rica`.

**Salidas**:
- Índice de vegetación NDVI.

![](https://github.com/redd-costarica-scripts/.github/blob/master/profile/img/ndvi.png)   
**Figura 16**. Índice de vegetación NDVI.

- Índices de textura de Haralick.

![](https://github.com/redd-costarica-scripts/.github/blob/master/profile/img/haralick.png)   
**Figura 17**. Índices de textura de Haralick.

### 3.8. Creación de máscaras de nubes y sombras
En este paso, la imagen generada con FMask en el paso 2 (detección de nubes y sombras), se utiliza para generar una imagen con una máscara de nubes y otra con una máscara de sombras.

Esta tarea se realiza con la herramienta `r.reclass` del marco de trabajo `Processing` de QGIS.

**Entradas**:
- Imagen con nubes y sombras generada en el paso 2.
- Archivos con reglas.

**Procesamiento**:
- Ejecución de la herramienta `Clip raster by Mask Layer (gdalwarp)` del marco de trabajo `Processing` de QGIS. Debe ejecutarse dos veces: una para generar la máscara de nubes y otra para generar la máscara de sombras.

![](https://github.com/redd-costarica-scripts/.github/blob/master/profile/img/reclass.png)  
**Figura 18**. Herramienta `r.reclass` del marco de trabajo `Processing` de QGIS.

**Salidas**:
- Máscara de nubes (nubes = 1, otros = 0).

![](https://github.com/redd-costarica-scripts/.github/blob/master/profile/img/mascara-nubes.png)   
**Figura 19**. Máscara de nubes.

- Máscara de sombras (sombras = 1, otros = 0).

![](https://github.com/redd-costarica-scripts/.github/blob/master/profile/img/mascara-sombras.png)   
**Figura 20**. Máscara de sombras.

### 3.9. Recorte de las máscaras de nubes y sombras con la máscara raster del contorno del país
Esta operación se realiza para reducir el área de trabajo y mejorar la clasificación posterior de las imágenes. Al igual que en el caso de las máscaras vectoriales, el contorno del país se divide de acuerdo con los paths ("pasadas") correspondientes a los recorridos de Landsat: P14 (este), P15 (centro) y P16 (oeste), por lo que cada imagen se recorta con respecto a la máscara de su *path*.

Este paso se realiza con la herramienta `r.mapcalc.simple` del marco de trabajo `Processing` de QGIS.

**Entradas**:
- (A) Máscara de nubes, creada en el paso 8 (nubes = 1, otros = 0).
- (A) Máscara de sombras, creada en el paso 8 (sombras = 1, otros = 0).
- (B) Máscara raster para la "pasada" correspondiente (P14, P15, P16) (fuera del país = 1, dentro del país = 0).
- Fórmula para recortar las máscaras: `if(A+B == 2, 1, A+B)`.

**Procesamiento**:
- Ejecución de la herramienta `r.mapcalc.simple` del marco de trabajo `Processing` de QGIS. Debe ejecutarse dos veces: una para recortar la máscara de nubes y otra para recortar la máscara de sombras.

![](https://github.com/redd-costarica-scripts/.github/blob/master/profile/img/rmapcalcsimple.png)  
**Figura 21**. Herramienta `r.mapcalc.simple` de `Processing` de QGIS.

**Salidas**:
- Máscara de nubes recortada (nubes o fuera del país = 1, otros = 0).

![](https://github.com/redd-costarica-scripts/.github/blob/master/profile/img/mascara-nubes-recortada.png)   
**Figura 22**. Máscara de nubes recortada.

- Máscara de sombras recortada (sombras o fuera del país = 1, otros = 0).

![](https://github.com/redd-costarica-scripts/.github/blob/master/profile/img/mascara-sombras-recortada.png)   
**Figura 23**. Máscara de nubes recortada.

### 3.10. Eliminación de nubes y sombras
Este paso elimina de una imagen los pixeles con nubes o sombras, asigándoles un valor de -9999 (sin datos), para que no sean tomados en cuenta cuando se clasifique la imagen. 

Este paso se realiza con el programa `nubessombras.py`, el cual se ejecuta desde la consola de Python en QGIS o (en Microsoft Windows) desde la línea de comandos de `OSGeo4W Shell` (esta opción permite visualizar mejor el progreso del script y los mensajes de error). **En ambos casos, deben modificarse las rutas de los archivos de entrada y salida ubicados al inicio del script**. Si se ejecuta desde QGIS, debe abrirse el script en el editor de la consola de Python y presionar el botón `Run Script`.

**Entradas**:
- Archivo con máscara de nubes recortada.
- Archivo con máscara de sombras recortada.
- Archivo con índices de textura de Haralick.

Las rutas y nombres de estos archivos (así como los de los archivos de salida), deben modiricarse en el archivo `nubessombras.py`. Por ejemplo:

```python
# Máscara de nubes
nubes = "D:/redd/img/LC09_L1TP_016052_20220123_20220124_02_T1-SALIDA/LC09_L1TP_016052_20220123_20220124_02_T1_Fmask4-NUBES-RECORTADA.tif"
# Máscara de sombras
sombras = "D:/redd/img/LC09_L1TP_016052_20220123_20220124_02_T1-SALIDA/LC09_L1TP_016052_20220123_20220124_02_T1_Fmask4-SOMBRAS-RECORTADA.tif"
# Índices de textura de Haralick
haralick = "D:/redd/img/LC09_L1TP_016052_20220123_20220124_02_T1-SALIDA/LC09_L1TP_016052_20220123_20220124_02_T1-HARALICK.tif"
# Resultado intermedio
ns0 = "D:/redd/img/LC09_L1TP_016052_20220123_20220124_02_T1-SALIDA/NS0.tif"
# Resultado intermedio
nsnd = "D:/redd/img/LC09_L1TP_016052_20220123_20220124_02_T1-SALIDA/NSND.tif"
# Imagen sin nubes ni sombras
sinnubessombras = "D:/redd/img/LC09_L1TP_016052_20220123_20220124_02_T1-SALIDA/LC09_L1TP_016052_20220123_20220124_02_T1-SINNUBESSOMBRAS.tif"
```

**Procesamiento**:
- Ejecución de `nubessombras.py`.

Si se ejecuta desde `OSGeo4W Shell`:
```shell
cd redd-costarica-scripts-qgis
python nubessombras.py
```
**Salidas:**
- Imagen sin nubes y sombras

### 3.11. Combinación de bandas
En este paso, se combinan las salidas de los pasos anteriores, para construir un archivo con todas las bandas raster necesarias para ejecutar la clasificación de una imagen, en el paso 13.

Se realiza con el programa `combinacion.bat`, contenido en el repositorio `redd-costarica-scripts-bat`. Este es un programa de procesamiento por lotes (*batch*), que puede procesar múltiples imágenes.

**Entradas**:
Para cada combinación, se requiere:
- Imagen con normalización radiométrica.
- Imagen con índice de vegetación NDVI.
- Imagen con índices de textura.
- Modelo digital de elevaciones.

Las rutas y nombres de estos archivos (así como los de los archivos de salida), deben modiricarse en el archivo `combinacion.bat`. Por ejemplo:

```shell
echo %DATE%
echo %TIME%

call gdal_merge.bat -o C:\combinacion\LC08_P15_R54_c20b_2021_197.tif -separate -ot Float32 D:\redd\combinacion\radiometrica\LC08_P15_R54_NR_2021_197.tif D:\redd\combinacion\ndvi\LC08_P14_R54_NDVI_2021_197.tif D:\redd\combinacion\sinnubessombras\lc08_p14_r54_2021_197_sin_nubes_sombras.tif D:\redd\combinacion\dem\p15_derivadas_DEM.tif
```

En el mismo archivo `.bat`, pueden incluirse varios comandos como el anterior, para así generar varias combinaciones con un solo archivo.

**Procesamiento**:
- Ejecución de `combinacion.bat`.

Si se ejecuta desde `OSGeo4W Shell`:
```shell
cd redd-costarica-scripts-bat
combinacion.bat
```

**Salidas**:
- Archivos con combinaciones de bandas.

### 3.12. Generación de regiones de interés
Este paso se realiza sin apoyo de los programas descritos en este documento. Se utilizan otras aplicaciones, como sistemas de información geográfica (ej. QGIS). Como salida, se obtiene un archivo tipo shapefile `.shp` con las regiones de interés, las cuales se utilizarán como entrada en la clasificación de las imágenes.

### 3.13. Clasificación de las imágenes
La clasificación se realiza mediante el algoritmo "Random Forest", el cual se implementa con el programa `Script_RandonmForest_clasificacion.R`, contenido en el repositorio `redd-costarica-randomforest-r`.

El programa `Script_RandonmForest_clasificacion.R` puede ejecutarse desde un ambiente de desarrollo integrado, como RStudio, o desde la línea de comandos del sistema operativo, a través del utlitario `Rscript.exe`, el cual se instala junto con el sistema base de R. Opcionalmente, puede utilizarse el programa de procesamiento por lotes `clasificacion.bat`, contenido en el mismo repositorio, para clasificar múltiples imágenes con un solo llamado al programa.

**Entradas:**
- Imagen a clasificar, con la combinación de 20 bandas generada en el paso 11.
- Archivo de tipo shapefile `.shp` (y archivos asociados) con las regiones de interés generadas en el paso 12.
- Cantidad de puntos a muestrear.

Las rutas y nombres de estos archivos (así como los de los archivos de salida), deben modificarse en el archivo `clasificacion.bat`. Por ejemplo:

```shell
call "C:/Program Files/R/R-4.2.1/bin/x64/Rscript.exe" D:/redd/clasificacion/randomforest.R C:/combinacion/LC08_P15_R54_c20b_2021_197.tif D:/redd/clasificacion/roi/p15_ROI.shp 10000 clases D:/redd/clasificacion/clasificacion-resultado/LC08_P15_R54_c20b_2021_197-clas.tif D:/redd/clasificacion/clasificacion-resultado/LC08_P15_R54_c20b_2021_197-clas.shp
```

**Procesamiento**:
- Ejecución de `clasificacion.bat`.

Ejecución desde la línea de comandos del sistema operativo:
```shell
cd redd-costarica-randomforest-r
clasificacion.bat
```

**Salidas**:
- Archivo raster de resultados. Tiene tres bandas:
    1. Una primera banda con la clasificación asignada a cada pixel pixel.
    2. Una segunda banda con el porcentaje de árboles de decisión que predicen la clase asignada en la primera banda. Esta banda proporciona una estimación de la calidad de la clasificación para cada uno de los pixeles de la imagen. Esta información se usa en el siguiente paso para priorizar los pixeles en la generación del mosaico.
    3. Una tercera banda con la clasificación de los pixeles que han recibido un porcentaje de "votos" superior al 60%.
- Archivo de tipo shapefile `.shp` (y archivos asociados) con regiones clasificadas.

### 3.14. Generación de mosaicos
En este paso, se fusionan todas las clasificaciones, de manera que cada pixel tenga asignada una sola clase (bosque, cultivo, área urbana, etc.). Se selecciona la clase que más "votos" suma en la banda 2 del archivo raster de resultados obtenido en el paso 13.

La fusión se realiza con el programa `fusion.py`, el cual puede llamarse desde el programa de procesamiento por lotes `fusion.bat`, para así fusionar múltiples imágenes. Ambos programas están contenidos en el repositorio `redd-costarica-scripts-bat`.

**Entradas**:
- Directorio (carpeta) con los archivos de resultados (i.e. imágenes clasificadas) que se desea fusionar.

La ruta del directorio de entrada (y el de salida también), debe modificarse en el archivo `fusion.bat`. Por ejemplo:

```shell
call python D:/redd/fusion/fusion.py D:/redd/fusion/raster_files_folder/ D:/redd/fusion/results_folder/
```

**Procesamiento**:
- Ejecución de `fusion.bat`.

Ejecución desde la línea de comandos del sistema operativo:
```shell
cd redd-costarica-scripts-bat
fusion.bat
```

**Salidas**:
- Directorio (carpeta) del mosaico resultante.