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

Para esto se han planteado un archivo que contiene la [fase de experimentación]() y otro con los [resultados finales]() donde se ha creado un modelo llamando CoverLandModel, el cual alcanza un XX.X% de precisión, en la identificación de las 10 clases en las imágenes satelitales.

Los elementos utilizado son:
- Convolutional Neural Network
- Transfer Learning


El resumen del modelo se presenta a continuación
_________________________________________________________________
Layer (type)                 Output Shape              Param #   
=================================================================
input_1 (InputLayer)         (None, 64, 64, 3)         0         
_________________________________________________________________
conv2d (Conv2D)              (None, 64, 64, 96)        1248      
_________________________________________________________________
max_pooling2d (MaxPooling2D) (None, 32, 32, 96)        0         
_________________________________________________________________
conv2d_1 (Conv2D)            (None, 22, 22, 96)        1115232   
_________________________________________________________________
dropout (Dropout)            (None, 22, 22, 96)        0         
_________________________________________________________________
flatten (Flatten)            (None, 46464)             0         
_________________________________________________________________
dense (Dense)                (None, 128)               5947520   
_________________________________________________________________
dropout_1 (Dropout)          (None, 128)               0         
_________________________________________________________________
dense_1 (Dense)              (None, 64)                8256      
_________________________________________________________________
dense_2 (Dense)              (None, 128)               8320      
_________________________________________________________________
dropout_2 (Dropout)          (None, 128)               0         
_________________________________________________________________
output_1 (Dense)             (None, 10)                1290      
=================================================================
Total params: 7,081,866
Trainable params: 7,081,866
Non-trainable params: 0
_________________________________________________________________
