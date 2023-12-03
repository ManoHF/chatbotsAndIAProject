# chatbotsAndIAProject
Proyecto final para la materia de Chatbots e IA - Oto23

Integrantes:
* Manuel Hermida - 189702
* Paulina Garza - 188456
* Montserrat Olivares
* Iván Valadez - 195717
  

## Introducción
https://www.canva.com/design/DAF1zrvUAvY/wBERndJQtFIMPr1F0-Thng/view?utm_content=DAF1zrvUAvY&utm_campaign=share_your_design&utm_medium=link&utm_source=shareyourdesignpanel 

## Generación del Dataset

Como primer paso del proyecto se debe crear un dataset que contenga las emociones relacionadas con cada canción. En las siguientes líneas de incluye cómo descargar los datos resultantes de este proceso que puede tardar horas si uno quiere etiquetar todas las canciones. Así, pueden aprovechar su tiempo de una mejor manera. [Dataset](https://huggingface.co/datasets/manoh2f2/tsterbak-lyrics-dataset-with-emotions)

```py
from datasets import load_dataset

dataset = load_dataset("manoh2f2/tsterbak-lyrics-dataset-with-emotions")
```

Por lo tanto, si usted gusta, ejecute `tag_emotions_to_songs.ipynb` y detenga el etiquetado de canciones cuando usted considere suficiente. Las siguientes celdas se encargarán de eliminar las canciones no etiquetadas. [Notebook](tag_emotions_to_songs.ipynb)

## Soluciones

### Approach 1: Cache

En primer lugar, aplicamos una solución bastante sencilla. Se recibe una prompt del usuario que es etiquetada de las misma forma que las canciones. Posteriormente, se hace un *match* en el dataset para elegir una canción relacionada. [Notebook](solucion_cache.ipynb)

### Approach 2: Entrenamiento de Modelo

En segundo lugar, se busco entrenar algún modelo con el dataset creado. Se usa el mismo dataset, pero se equilibra el número de muestras por clase. Se utiliza el modelo llamado 'DistilBERT' utilizando 6 *epochs* y el optimizador Adam. Posteriormente, se guarda el modelo para su prueba con distintos prompts. Cabe añadir que nos vimos limitados por la memoria disponible en collab, por lo que tuvimos que elegir un modelo que no ocupara toda la memoria pero fuera lo más complejo posible. [Notebook](solucion_modelo.ipynb)
