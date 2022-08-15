# Mapas de uso del suelo de Costa Rica para REDD+
Esta organización contiene un conjunto de repositorios que implementan los flujos de trabajo necesarios para generar mapas de uso de suelo consistentes con la serie histórica de actividad de uso del suelo y cambio de uso del suelo generada entre 1987 y 2013 en Costa Rica.

## Ambiente conda

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
mamba install git cookiecutter gdal python jupyter jupyterlab

# Desactivación del ambiente (al finalizar la sesión de trabajo)
conda deactivate
```

## Cookiecutter
Para estructurar el proyecto, se utiliza el el utilitario de línea de comandos [cookiecutter](https://pypi.org/project/cookiecutter/), el cual crea un proyecto con base en una plantilla. En este caso, se utiliza la plantilla [cookiecutter-data-science](cookiecutter https://github.com/drivendata/cookiecutter-data-science).

```shell
cookiecutter https://github.com/drivendata/cookiecutter-data-science
```
