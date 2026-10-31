# Resolvedor de captchas con DL

Ruta de archivos del proyecto

[dataset original](./dataset/samples/)

[dataset generado](./dataset/generated/)

[archivo para generar dataset](./dataset.ipynb)

[Generación y entrenamiento NN](./main.ipynb)

[Solución con detección de objetos red yolo](./yolo_focus.ipynb)


# Exploración y descubrimientos al tratar este problema

Tratando este problema me he dado cuenta que tratar la resolución de captchas con un enfoque naive, haciendo que una CNN intente detectar la imagen al completo es un mal enfoque. Ya que el número de combinaciones posibles se dispara, haciendo que el dataset de entrenamiento necesario sea muy alto.

Al tratar de resolver el problema de esta manera el mayor accuracy que he obtenido ha sido del 8%.

La manera correcta de resolver la resolución de captchas 1.0 es mediante object detection, donde una red yolo recorre la iamgen en busca de los objetos con los que ha sido entrenada. De esta manera tenemos un enfoque que requiere de menos pasos de entrenamiento y un dataset más pequeño para funcionar.

El accuracy obtenido mediante esta tecnica ha sido del 99,5%.
