# Scripts para la elaboración de mapas de uso y cobertura de la tierra de Costa Rica en el contexto de REDD+
Este es un conjunto de repositorios de código fuente de programas informáticos (*scripts*) para apoyar la elaboración de mapas de uso y cobertura de la tierra, en el contexto del mecanismo de Reducción de Emisiones por Deforestación y Degradación de bosques más conservación y aumento de reservas de carbono forestal (REDD+).

En este documento, se listan los repositorios, se brindan las instrucciones para la instalación de las herramientas informáticas necesarias y se describe el protocolo metodológico para el uso de los programas durante el proceso de elaboración de los mapas.

## Contenidos
1. [Repositorios](https://github.com/redd-costarica-scripts#repositorios)  
    1.1. [redd-costarica-scripts-qgis](https://github.com/redd-costarica-scripts#11-redd-costarica-scripts-qgis)  
    1.2. [redd-costarica-randomforest-r](https://github.com/redd-costarica-scripts#12-redd-costarica-randomforest-r)  
    1.3. [redd-costarica-scripts-bat](https://github.com/redd-costarica-scripts#13-redd-costarica-scripts-bat)  
2. [Herramientas informáticas](https://github.com/redd-costarica-scripts#herramientas-inform%C3%A1ticas)  
    2.1. [QGIS](https://github.com/redd-costarica-scripts#21-qgis)  
    2.2. [Orfeo Toolbox](https://github.com/redd-costarica-scripts#22-orfeo-toolbox)  
    2.3. [FMask](https://github.com/redd-costarica-scripts#23-fmask)  
    2.4. [R y RStudio](https://github.com/redd-costarica-scripts#24-r-y-rstudio)  
    2.5. [Git](https://github.com/redd-costarica-scripts#25-git)  
    2.6. [Complemento de QGIS `REDD+ Costa Rica`](https://github.com/redd-costarica-scripts#26-complemento-de-qgis-redd-costa-rica)  
3. [Protocolo metodológico](https://github.com/redd-costarica-scripts#protocolo-metodol%C3%B3gico)  
    3.1. [Descarga de imágenes y metadatos](https://github.com/redd-costarica-scripts#31-descarga-de-im%C3%A1genes-y-metadatos)  
    3.2. [Detección de nubes y sombras](https://github.com/redd-costarica-scripts#32-detecci%C3%B3n-de-nubes-y-sombras)  
    3.3. [Creación de una pila de bandas](https://github.com/redd-costarica-scripts#33-creaci%C3%B3n-de-una-pila-de-bandas)  
    3.4. [Cálculo de la reflectancia](https://github.com/redd-costarica-scripts#34-c%C3%A1lculo-de-la-reflectancia)  
    3.5. [Normalización horaria](https://github.com/redd-costarica-scripts#35-normalizaci%C3%B3n-horaria)  
    3.6. [Normalización radiométrica](https://github.com/redd-costarica-scripts#36-normalizaci%C3%B3n-radiom%C3%A9trica)  
        - 3.6.1. [Recorte de la imagen de referencia con la máscara vectorial del contorno del país](https://github.com/redd-costarica-scripts#361-recorte-de-la-imagen-de-referencia-con-la-m%C3%A1scara-vectorial-del-contorno-del-pa%C3%ADs)  
        - 3.6.2. [Recorte de la imagen con normalización horaria con la máscara vectorial del contorno del país](https://github.com/redd-costarica-scripts#362-recorte-de-la-imagen-con-normalizaci%C3%B3n-horaria-con-la-m%C3%A1scara-vectorial-del-contorno-del-pa%C3%ADs)  
        - 3.6.3. [Ejecución de `imad.py`]()  
        - 3.6.4. [Ejecución de `radcal.py`]()  

## 1. Repositorios
Los repositorios de código fuente son los siguientes:

### 1.1. redd-costarica-scripts-qgis
[redd-costarica-scripts-qgis](https://github.com/redd-costarica-scripts/redd-costarica-scripts-qgis) contiene programas para ejecutarse en el sistema de información geográfica QGIS. Se agrupan en un complemento llamado `REDD+ Costa Rica`.

### 1.2. redd-costarica-randomforest-r
[redd-costarica-randomforest-r](https://github.com/redd-costarica-scripts/redd-costarica-randomforest-r) contiene un programa en el lenguaje R que implementa el algoritmo de clasificación Random Forest.

### 1.3. redd-costarica-scripts-bat
[redd-costarica-scripts-bat](https://github.com/redd-costarica-scripts/redd-costarica-scripts-bat) contiene programas para procesamiento por lotes en archivos `.bat` del sistema operativo Microsoft Windows.

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

## 3. Protocolo metodológico
Los programas apoyan el protocolo metodológico del proyecto *Generating a Consistent Historical Time Series of Activity Data from Land Use Change for the Development of Costa Rica’s REDD Plus Reference Level*, desarrollado por Agresta, Digital Image Processing (Dimap), la Universidad de Costa Rica y la Universidad Politécnica de Madrid.

Este protocolo consiste de una serie de pasos, los cuales se enumeran seguidamente:

1. [Descarga de imágenes y metadatos.](https://github.com/redd-costarica-scripts#31-descarga-de-im%C3%A1genes-y-metadatos)  
2. [Detección de nubes y sombras.](https://github.com/redd-costarica-scripts#32-detecci%C3%B3n-de-nubes-y-sombras)  
3. [Creación de una pila de bandas.](https://github.com/redd-costarica-scripts#33-creaci%C3%B3n-de-una-pila-de-bandas)  
4. [Cálculo de la reflectancia](https://github.com/redd-costarica-scripts#34-c%C3%A1lculo-de-la-reflectancia)  
5. [Normalización horaria](https://github.com/redd-costarica-scripts#35-normalizaci%C3%B3n-horaria)  
6. [Normalización radiométrica](https://github.com/redd-costarica-scripts#36-normalizaci%C3%B3n-radiom%C3%A9trica)  
    6.1. [Recorte de la imagen de referencia con la máscara vectorial del contorno del país](https://github.com/redd-costarica-scripts#361-recorte-de-la-imagen-de-referencia-con-la-m%C3%A1scara-vectorial-del-contorno-del-pa%C3%ADs)  
    6.2. [Recorte de la imagen con normalización horaria con la máscara vectorial del contorno del país](https://github.com/redd-costarica-scripts#362-recorte-de-la-imagen-con-normalizaci%C3%B3n-horaria-con-la-m%C3%A1scara-vectorial-del-contorno-del-pa%C3%ADs)  
    6.3. [Ejecución de `imad.py`]()  
    6.4. [Ejecución de `radcal.py`]()  

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
- Archivo raster con pixeles marcados como tierra, agua, nubes o sombras.

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
- Imagen de referencia.
- Imagen a normalizar.

Las rutas y nombres de estos archivos (así como los del archivo de salida), deben modiricarse en el archivo `imad.py`. Por ejemplo:

```python
# Imagen de referencia
referencia = "D:/redd/referencia/P16_r52_2014057_utm16-RECORTADA.TIF"
# Imagen a normalizar
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
- Archivo de salida de `imad.py`. Por ejemplo:

```
IMAD.TIF
```

No se muestra una imagen de esta salida, por ser un producto intermedio.

