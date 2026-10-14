# Ficha del modelo: Clay foundation model

Ficha elaborada para la asignatura de Inteligencia Artificial, siguiendo la propuesta de Mitchell et al. (2019) y la plantilla de model cards de Hugging Face.

## Detalles del modelo

- **Nombre:** Clay foundation model
- **Versión:** v1.5
- **Desarrollado por:** Clay Foundation
- **Tipo de modelo:** Vision Transformer adaptado a observación de la Tierra, entrenado de forma autosupervisada como Masked Autoencoder (MAE)
- **Entradas:** imágenes de satélite de distintos sensores (la versión 1.5 es agnóstica al sensor), junto con metadatos de ubicación y fecha
- **Salidas:** embeddings semánticos de cada imagen o parche
- **Licencia:** Apache 2.0
- **Código:** https://github.com/Clay-foundation/model
- **Pesos y ficha oficial:** https://huggingface.co/made-with-clay/Clay
- **Documentación y especificación:** https://clay-foundation.github.io/model/

## Usos

### Uso directo

Generar embeddings para cualquier lugar y fecha, y compararlos entre sí, por ejemplo para encontrar zonas con características parecidas.

### Uso como backbone o con ajuste fino

Servir de base para modelos de clasificación, regresión o tareas generativas sobre imágenes satelitales, con ajuste fino o con sondeo lineal (linear probing) sobre los embeddings.

### Uso en este proyecto

El proyecto trabaja con el modelo preentrenado v1.5 tal como lo publica Clay Foundation, sin modificaciones, ajuste fino ni entrenamiento adicional.

### Usos fuera de alcance

Decisiones críticas sobre personas o propiedades sin validación local, vigilancia, y cualquier uso que trate los embeddings como una medición directa de variables físicas sin calibrarlos contra datos de referencia.

## Sesgos, riesgos y limitaciones

- El rendimiento depende de qué tan representadas estén las regiones, coberturas y condiciones atmosféricas en los datos de preentrenamiento.
- Los embeddings no se interpretan de forma directa. Cualquier conclusión sobre el terreno exige validación con datos de referencia.
- Con imágenes de resolución media, los objetos pequeños, como construcciones individuales o parcelas estrechas, quedan fuera de lo que el modelo puede distinguir.

## Cómo empezar

```python
from claymodel.module import ClayMAEModule

model = ClayMAEModule.load_from_checkpoint("clay-v1.5.ckpt")
```

El checkpoint oficial se descarga desde https://huggingface.co/made-with-clay/Clay. El preprocesamiento de los datos sigue el flujo del repositorio oficial.

## Detalles de entrenamiento

Clay Foundation preentrenó el modelo con imágenes de observación de la Tierra de varios sensores, mediante reconstrucción de parches enmascarados (MAE). Las cifras de datos, sensores e hiperparámetros están en la especificación oficial: https://clay-foundation.github.io/model/release-notes/specification.html

Este proyecto no realiza entrenamiento propio.

## Evaluación

Este proyecto no incluye una evaluación propia. Las métricas del modelo base están en la documentación oficial de Clay.

## Impacto ambiental

El preentrenamiento lo realizó Clay Foundation con GPU a gran escala. Este proyecto no entrena el modelo, solo lo usa, así que no suma costo de entrenamiento.

## Citación

Clay Foundation. *Clay Foundation Model*. Hugging Face, doi:10.57967/hf/1537. https://huggingface.co/made-with-clay/Clay

Mitchell, M., Wu, S., Zaldivar, A., Barnes, P., Vasserman, L., Hutchinson, B., ... & Gebru, T. (2019). Model cards for model reporting. *Proceedings of the Conference on Fairness, Accountability, and Transparency*, 220-229. https://arxiv.org/abs/1810.03993

## Autor de la ficha

| Nombre completo | Usuario de GitHub | Correo |
| --- | --- | --- |
| Jose Sebastian Noguera Arias | [Sebas2201](https://github.com/Sebas2201) | jsnogueraa@udistrital.edu.co |
