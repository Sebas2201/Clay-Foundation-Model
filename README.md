# Clay foundation model

## Descripción general

Clay es un modelo fundacional de observación de la Tierra, de código abierto, basado en un Vision Transformer (ViT) entrenado de forma autosupervisada como Masked Autoencoder (MAE). Su versión 1.5 es agnóstica al sensor: recibe imágenes satelitales junto con su ubicación y fecha, y produce embeddings semánticos que sirven para clasificación, regresión, búsqueda por similitud o como backbone de otros modelos geoespaciales.

Este repositorio documenta el uso del modelo Clay v1.5 preentrenado, sin modificaciones, en el proyecto de la asignatura de Inteligencia Artificial de la Universidad Distrital Francisco José de Caldas.

## Ficha del modelo

La ficha (model card) está en este mismo repositorio: [MODEL_CARD.md](./MODEL_CARD.md)

## Autor de la ficha

| Nombre completo | Usuario de GitHub | Correo |
| --- | --- | --- |
| Jose Sebastian Noguera Arias | [Sebas2201](https://github.com/Sebas2201) | jsnogueraa@udistrital.edu.co |

## Referencias

- Repositorio oficial del modelo: https://github.com/Clay-foundation/model
- Pesos y ficha oficial en Hugging Face: https://huggingface.co/made-with-clay/Clay
- Mitchell, M., Wu, S., Zaldivar, A., Barnes, P., Vasserman, L., Hutchinson, B., ... & Gebru, T. (2019). Model cards for model reporting. https://arxiv.org/abs/1810.03993
