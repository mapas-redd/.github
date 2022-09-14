# Mapas de Costa Rica para REDD+
Esta organización contiene un conjunto de repositorios que implementan flujos de trabajo para generar mapas de Costa Rica para Reducción de Emisiones por Deforestación y Degradación más conservación y aumento de reservas de carbono forestal (REDD+).

La programación se realiza con el lenguaje [Python](https://www.python.org/) y varios de sus módulos, los cuales se instalan y mantienen con el administrador de paquetes y ambientes [Conda](https://docs.conda.io/).

## Ambiente conda para Python
Los siguientes comandos crean un ambiente Conda llamado `mapas-redd`, con los módulos requeridos por los programas.

```shell
# Actualización de Conda
conda update conda

# Borrado del ambiente (si es que existe)
# conda remove -n mapas-redd --all

# Creación del ambiente
conda create -n mapas-redd

# Activación del ambiente
conda activate mapas-redd

# Configuración del ambiente
conda config --env --add channels conda-forge
conda config --env --set channel_priority strict

# Instalación de mamba
conda install -c conda-forge mamba

# Instalación de módulos
mamba install make git python cookiecutter jupyter jupyterlab matplotlib gdal rasterio

# Desactivación del ambiente (al finalizar la sesión de trabajo)
conda deactivate
```

## Ambiente conda para Random Forest (R)

```shell
# Actualización de Conda
conda update conda

# Borrado del ambiente (si es que existe)
# conda remove -n random-forest --all

# Creación del ambiente
conda create -n random-forest

# Activación del ambiente
conda activate random-forest

# Configuración del ambiente
conda config --env --add channels conda-forge
conda config --env --set channel_priority strict

# Instalación de mamba
conda install -c conda-forge mamba

# Instalación de módulos
mamba install r-base r-essentials r-rgeos r-maptools r-sp r-randomforest r-rgdal r-raster r-rsaga

# Desactivación del ambiente (al finalizar la sesión de trabajo)
conda deactivate
```

## Mapas de uso del suelo (repositorio `uso-suelo`)
Para configurar la estructura del directorio del proyecto, se emplea el utilitario de línea de comandos [cookiecutter](https://pypi.org/project/cookiecutter/), el cual crea la estructura con base en la plantilla [cookiecutter-data-science](cookiecutter https://github.com/drivendata/cookiecutter-data-science).

```shell
# Creación del directorio del proyecto con la estructura de cookiecutter

cookiecutter https://github.com/drivendata/cookiecutter-data-science
# project_name [project_name]: uso-suelo
# repo_name [uso-suelo]: 
# author_name [Your name (or your organization/company/team)]: Manuel Vargas
# description [A short description of the project.]: Mapas de uso del suelo
# Select open_source_license:
# 1 - MIT
# 2 - BSD-3-Clause
# 3 - No license file
# Choose from 1, 2, 3 [1]: 
# s3_bucket [[OPTIONAL] your-bucket-for-syncing-data (do not include 's3://')]: 
# aws_profile [default]: 
# Select python_interpreter:
# 1 - python3
# 2 - python
# Choose from 1, 2 [1]: 
```

Seguidamente, dentro de esta organización GitHub, debe crearse el repositorio `uso-suelo` (público y sin ningún contenido) y sincronizarlo con el directorio recién creado, a través de los comandos:

```shell
# Sincronización de los repositorios local y remoto

cd uso-suelo
git init
git add .
git commit -m "Commit inicial"
git branch -M main
git remote add origin git@github.com:mapas-redd/uso-suelo.git
git push -u origin main
```
