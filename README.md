# LandCover

Este proyecto busca identificar estructuras en imágenes del satélite Sentinell-2, las cuales han sido liberadas a través del [Programa Copernicus](https://www.copernicus.eu/en) el dataset utilizado es descrito en el [siguiente enlace](https://github.com/phelber/EuroSAT), el cual esta conformado por imágenes multiespectrales de 13 bandas de frecuencia (MS) e imágenes RGB, clasificadas con 10 clases de un total de 27000 imágenes etiquetadas y georeferenciadas de Europa.

Las imágenes tiene una Las clases contienen entre 2000 y 3000 imágenes, con un tamaño de 64x64
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

Para esto se han planteado un archivo que contiene la [fase de experimentación]() y otro con los [resultados finales]() donde se ha creado un modelo llamando CoverLandModel, el cual alcanza un XX.X% de precisión, en la identificación de las 10 clases en las imágenes satelitales.

Los elementos utilizado son:
- Convolutional Neural Network
- Transfer Learning
