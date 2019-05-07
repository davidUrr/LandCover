# LandCover

Este proyecto busca identificar estructuras en imágenes del satélite Sentinell-2, las cuales han sido liberadas a través del [Programa Copernicus](https://www.copernicus.eu/en) el dataset utilizado es descrito en el [siguiente enlace](https://github.com/phelber/EuroSAT), el cual esta conformado por imágenes multiespectrales de 13 bandas de frecuencia (MS) e imágenes RGB, clasificadas con 10 clases de un total de 27000 imágenes etiquetadas y georeferenciadas de Europa.

Las imágenes corresponde a una de las 10 clases, cada clase contienen entre 2000 y 3000 imágenes, con un tamaño de 64x64
- [0] Annual Crop
- [1] Forest
- [2] Herbaceous Vegetation
- [3] Highway
- [4] Industrial Buildings
- [5] Pasture
- [6] Permanent Crop
- [7] Residencial Buildings
- [8] River
- [9] Sea & Lake


<p align="center">
  <img src="https://github.com/davidUrr/LandCover/blob/master/Imagenes/Clases2.png">
</p>

La distribución de los países se observa en la siguiente figura

<p align="center">
  <img src="https://github.com/davidUrr/LandCover/blob/master/Imagenes/distribucion.png">
</p>

Tomado de [[1]](https://arxiv.org/abs/1709.00029)

Para esto se han planteado un archivo que contiene la [fase de experimentación](https://github.com/davidUrr/LandCover/blob/master/LandCover_Experiment.ipynb) y otro con los [resultados finales](https://github.com/davidUrr/LandCover/blob/master/LandCover.ipynb) donde se ha creado un modelo llamando CoverLandModel, el cual alcanza un porcentaje de predicción cercano al 35%, en la identificación de las 10 clases en las imágenes satelitales. Con la red VGG16 se alcanza el 89%.

El flujo experimental planteado fue el siguiente:
1.  Cargar la base de datos desde respositorio.
2. Separación entre train (70%) y test (30%).
3. Las imágenes se separan en carpetas por clase.
4. Las imagenes pasan por un generador de imágenes
5. Se crea el modelo de la red convolucional
6. Se aplica el modelo sobre train y test
7. Se grafican como evaluaciona la predicción y pérdida
8. Se realiza transfer learning de la primera capa de Alex Net
9. Se transfiere la arquitectura de modelo verificado 
10. Se realiza oclusión con el modelo pre entrenado.

