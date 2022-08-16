# Mapas de uso del suelo de Costa Rica para REDD+
Esta organización contiene un conjunto de repositorios que implementan los flujos de trabajo necesarios para generar mapas de uso de suelo consistentes con la serie histórica de actividad de uso del suelo y cambio de uso del suelo generada entre 1987 y 2013 en Costa Rica.

## Ambiente conda
Los módulos necesarios se instalan mediante un ambiente [Conda](https://docs.conda.io/).


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
mamba install make git cookiecutter gdal python jupyter jupyterlab

# Desactivación del ambiente (al finalizar la sesión de trabajo)
conda deactivate
```

## Mapas de uso del suelo (uso-suelo)
Para dar una estructura inicial al proyecto, se utiliza el el utilitario de línea de comandos [cookiecutter](https://pypi.org/project/cookiecutter/), el cual crea un proyecto con base en una plantilla. En este caso, se utiliza la plantilla [cookiecutter-data-science](cookiecutter https://github.com/drivendata/cookiecutter-data-science).

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

En la organización, debe crearse el repositorio `uso-suelo` y sincronizarlo con el directorio recién creado a través de los comandos:

```shell
```
