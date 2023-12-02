# chatbotsAndIAProject
Proyecto final para la materia de Chatbots e IA - Oto23

Integrantes:
* Manuel Hermida - 189702
* Paulina Garza - 188456
* Montserrat Olivares
* Iván Valadez

## Generación del Dataset

Como primer paso del proyecto se debe crear un dataset que contenga las emociones relacionadas con cada canción. En el repo se incluye el excel resultante de este proceso que puede tardar horas si uno quiere etiquetar todas las canciones. Así, pueden aprovechar su tiempo de una mejor manera.

Por lo tanto, si usted gusta, ejecute `tag_emotions_to_songs.ipynb` y detenga el etiquetado de canciones cuando usted considere suficiente. Las siguientes celdas se encargarán de eliminar las canciones no etiquetadas. [Notebook](tag_emotions_to_songs.ipynb)

## Soluciones

### Approach 1: Cache

En primer lugar, aplicamos una solución bastante sencilla. Se recibe una prompt del usuario que es etiquetada de las misma forma que las canciones. Posteriormente, se hace un *match* en el dataset para elegir una canción relacionada. [Notebook](solucion_cache.ipynb)

### Approach 2: Entrenamiento de Modelo

En segundo lugar, se busco entrenar algún modelo con el dataset creado.
