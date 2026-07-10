# Comparación de LDA y QDA — Wine Dataset
 
Proyecto para la asignatura **Aprendizaje Automático**, que compara los modelos de **Análisis Discriminante Lineal (LDA)** y **Análisis Discriminante Cuadrático (QDA)** utilizando el conjunto de datos **Wine Dataset**, sin aplicar tratamiento (estandarización/normalización) a las variables, según lo indicado en el enunciado del trabajo.
 
## Autores
- Sara Maya
## Contenido del repositorio
 
```
├── LDA_vs_QDA_Wine_sin_tratamiento.ipynb   # Notebook principal (código comentado)
├── README.md                                # Este archivo
└── data/                                    # (opcional) instrucciones para obtener el dataset
```
 
## Sobre el dataset
 
El proyecto utiliza el **Wine Dataset**, incluido directamente en `scikit-learn`. No es necesario descargar ningún archivo externo: el notebook lo carga automáticamente con:
 
```python
from sklearn.datasets import load_wine
wine = load_wine()
```
 
- **Origen:** UCI Machine Learning Repository (incluido en `scikit-learn`).
- **Observaciones:** 178 muestras de vino.
- **Variables predictoras:** 13 variables numéricas (alcohol, ácido málico, cenizas, magnesio, flavonoides, prolina, etc.).
- **Variable objetivo:** cultivar de origen del vino (3 clases).
## Cómo ejecutar el proyecto
 
### Opción 1 — Google Colab (recomendado)
1. Abrir [Google Colab](https://colab.research.google.com/).
2. Subir el archivo `LDA_vs_QDA_Wine_sin_tratamiento.ipynb` (`Archivo > Subir cuaderno`).
3. Ejecutar todas las celdas en orden (`Entorno de ejecución > Ejecutar todas`).
4. No se requiere instalar librerías adicionales: `scikit-learn`, `pandas`, `matplotlib` y `seaborn` ya están preinstaladas en Colab.
### Opción 2 — Entorno local (Jupyter)
```bash
pip install pandas numpy matplotlib seaborn scikit-learn jupyter
jupyter notebook LDA_vs_QDA_Wine_sin_tratamiento.ipynb
```
 
## Estructura del notebook
 
1. Descripción del conjunto de datos
2. Exploración de los datos
3. Visualización (histogramas, dispersión, correlaciones, boxplots)
4. Preparación de los datos (train/test 70/30, sin estandarización)
5. Implementación de LDA
6. Implementación de QDA
7. Comparación de modelos
8. Fronteras de decisión (2D)
9. Conclusiones
## Principales hallazgos
 
- El dataset Wine no presenta valores faltantes y las clases están razonablemente balanceadas.
- Variables como `flavanoids`, `color_intensity` y `proline` muestran alto poder discriminante entre las tres clases.
- **LDA** obtuvo un desempeño alto (accuracy y F1-score elevados) generando fronteras de decisión lineales, incluso trabajando sobre los datos sin estandarizar.
- **QDA** obtuvo un desempeño igualmente competitivo, con fronteras de decisión cuadráticas más flexibles, aunque más sensible a las diferencias de escala entre variables al no aplicarse tratamiento previo.
- La comparación de métricas (accuracy, precisión, recall, F1-score) y matrices de confusión muestra resultados similares entre ambos modelos, con ligeras diferencias explicadas por los distintos supuestos de covarianza de cada método.
- Se concluye que, aunque ambos modelos funcionan sin estandarización, LDA es preferible por su simplicidad y menor sensibilidad a la escala, mientras que QDA es más adecuado cuando se sospecha de covarianzas distintas entre clases y se cuenta con datos estandarizados.
## Enlace del Colab (permisos de visualización)
 
> Agregar aquí el enlace compartido del notebook en Google Colab con permisos de visualización, una vez subido a Google Drive.
