# Resolvedor de captchas con DL

Ruta de archivos del proyecto

[dataset original](./dataset/samples/)

[dataset generado](./dataset/generated/)

[archivo para generar dataset](./dataset.ipynb)

[Generación y entrenamiento NN](./main.ipynb)


## Aspectos a mejorar

- ~~No cargar todo en la vram directamente, si no pinnear memoria para que la carga sea dinamica.~~
- Aumento del dataset de entrenamiento.
- Reducción del overfitting.
- poner un .gitignore y eliminar las imagenes, si quieres el dataset se genera. No hace falta subirlo a github si la generación es rápida.