# Análisis de índices NDVI y MNDWI

## Descripción del proyecto
Este proyecto se centra en la evaluación de imágenes satelitales utilizando los índices NDVI (Normalized Difference Vegetation Index) y MNDWI (Modified Normalized Difference Water Index). El objetivo principal es identificar y analizar áreas de vegetación y cuerpos de agua, proporcionando visualizaciones claras y estadísticas detalladas.

## Estructura del proyecto
scripts/
│
├── main_analysis.py # Script principal que contiene todo el flujo de procesamiento y análisis.
└── utils.py # Contiene funciones auxiliares como unzip_files, load_band, calculate_ndvi, etc.

data/
│
└── Los-Molinos_2023-08-18_8_all_bands.zip # Archivo ZIP que contiene las bandas espectrales necesarias.

outputs/
├── Imágenes y gráficos generados a partir del análisis.

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

