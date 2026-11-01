# Resolvedor de captchas con DL

Ruta de archivos del proyecto

[dataset original](./dataset/samples/)

[dataset generado](./dataset/generated/)

[archivo para generar dataset](./dataset.ipynb)

[Generación y entrenamiento NN](./main.ipynb)

[Solución con detección de objetos red yolo](./yolo_focus.ipynb)


# Exploración y descubrimientos al tratar este problema

## Enfoque naive y generacion de datos

Tratando este problema me he dado cuenta que la resolución de captchas con un enfoque naive, empleando una CNN hace que la red intente detectar la imagen al completo es un mal enfoque. Ya que el número de combinaciones posibles se dispara, haciendo que el dataset de entrenamiento necesario sea muy alto. El dataset que encontre en kagglehub aunque tenía un problema de captchas que era más fácil de resolver no tenía suficientes datos por lo que opte por generar mis propios datos usando una librería.

Al tratar de resolver el problema de esta manera el mayor accuracy que he obtenido ha sido del 8%.

El objetivo que me marque tras descubrir que este enfoque era muy ineficiente es encontrar algún metodo que me ayudara a separar las letras.

Este enfoque lo tome en el archivo [Entrenamiento_cnn](./main.ipynb). Los datos necesarios para el entrenamiento y validación de esta red se encuentran en [generacion datos](./dataset.ipynb)

## Uso de algoritmos de aprendizaje no supervisado en separacion de letras

En el archivo [computer vision proves](./computer_vision_proves.ipynb) se ven las pruebas realizadas para la separación de las letras principalmente empleando DBSCAN. Empleaba

Deseche esta idea al darme cuenta que DBSCAN no podía lograr hacer esta tarea y no encontrar ningun algoritmo que me permitiese realizar esta tarea con un alto grado de confianza.

## Deteccion de objetos y redes yolo

La manera correcta de resolver la resolución de captchas 1.0 es mediante object detection, donde una red yolo recorre la iamgen en busca de los objetos con los que ha sido entrenada. De esta manera tenemos un enfoque que requiere de menos pasos de entrenamiento y un dataset más pequeño para funcionar.

El accuracy obtenido mediante esta tecnica ha sido del 99,5%.

En un archivo único hice la generacion de datos, el entrenamiento y los test en [entrenamiento y test de yolo](./yolo_focus.ipynb).

Las dependencias necesarias se encuentran en [requirements.txt](./requierements.txt)