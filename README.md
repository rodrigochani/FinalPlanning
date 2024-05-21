# Análisis de índices NDVI y MNDWI

## Descripción del proyecto
Este proyecto se centra en la evaluación de imágenes satelitales utilizando los índices NDVI (Normalized Difference Vegetation Index) y MNDWI (Modified Normalized Difference Water Index). El objetivo principal es identificar y analizar áreas de vegetación y cuerpos de agua, proporcionando visualizaciones claras y estadísticas detalladas.

### Definición de índices
#### NDVI (Índice de Vegetación de Diferencia Normalizada)
El NDVI (Normalized Difference Vegetation Index) es un indicador comúnmente utilizado en teledetección para evaluar si el área observada contiene vegetación viva y medir su condición. Se calcula usando la luz visible (roja) y la luz cercana al infrarrojo (NIR) que la vegetación refleja de manera distinta. La fórmula para el NDVI es:

NDVI = NIR − Red/ NIR + Red

Donde:

NIR es la reflectancia del infrarrojo cercano,
Red es la reflectancia en el espectro visible rojo.
El NDVI varía entre -1 y +1:

Valores cercanos a +1 indican una alta densidad y salud de la vegetación.
Valores cercanos a 0 y negativos indican la presencia de otras superficies como rocas, ríos, o suelos desnudos, y valores bajos pueden también indicar vegetación escasa o poco saludable.

#### MNDWI (Índice de Agua de Diferencia Normalizada Modificado)
El MNDWI (Modified Normalized Difference Water Index) se utiliza principalmente para realzar y monitorear cuerpos de agua, mejorando la identificación y extracción de características acuáticas en imágenes de satélite. Este índice es particularmente útil para reducir la confusión entre cuerpos de agua y áreas sombreadas o vegetación oscura. La fórmula para el MNDWI es:

MNDWI = Green − SWIR/ Green + SWIR

Donde:

Green es la reflectancia en la banda del espectro visible verde,
SWIR (Short-Wave Infrared) es la reflectancia en la banda de infrarrojo de onda corta.
Los valores del MNDWI también oscilan entre -1 y +1, donde:

Valores positivos altos suelen indicar la presencia de agua abierta,
Valores negativos o bajos indican la ausencia de agua, mostrando en cambio terreno o vegetación.

## Estructura del proyecto
scripts/
│
└── final_planning.ipynb # Script principal que contiene todo el flujo de procesamiento y análisis.

data/
│
└── Los-Molinos_2023-08-18_8_all_bands.zip # Archivo ZIP que contiene las bandas espectrales necesarias.

Imagenes_Landsat/
└── Imágenes y gráficos generados a partir del análisis.

## Requisitos
- Python 3.8+
- Librerías necesarias: numpy, matplotlib, rasterio, shapely, geopandas, scipy, skimage, zipfile.
Instala las dependencias necesarias utilizando el siguiente comando:
```
pip install -r requirements.txt
```

## Flujo de Trabajo
1. Pre-procesamiento de Datos
Descompresión y Carga de Imágenes

## Descomprimir el archivo ZIP
```
unzip_files(zip_path, extract_to)
```
## Cargar bandas
```
red_band, profile_red = load_band(red_band_path)
```
## Cálculo de índices

### Calcular índices para imágenes crudas
```
ndvi_raw = calculate_ndvi(nir_band.astype(float), red_band.astype(float))
mndwi_raw = calculate_mndwi(green_band.astype(float), swir_band.astype(float))
```
## Visualización y Análisis de Resultados

###  Visualizar la imagen RGB y las curvas
```
fig, ax = plt.subplots(2, 2, figsize=(14, 12))
ax[0, 0].imshow(rgb_image, extent=extent)
```
## Más Información
Para más detalles sobre el análisis y los resultados, por favor consulta los scripts y archivos de salida en los directorios correspondientes.

## Autor
Rodrigo José Chani

