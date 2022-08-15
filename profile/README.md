# Mapas de uso del suelo de Costa Rica para REDD+
Esta organización contiene un conjunto de repositorios que implementan los flujos de trabajo necesarios para generar mapas de uso de suelo consistentes con la serie histórica de actividad de uso del suelo y cambio de uso del suelo generada entre 1987 y 2013 en Costa Rica.

### Ambiente conda

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
mamba install git gdal python jupyter jupyterlab plotly plotly_express geopandas rasterio folium

# Desactivación del ambiente
conda deactivate
```
