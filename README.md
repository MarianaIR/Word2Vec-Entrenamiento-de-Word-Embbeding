# 📖 Word2Vec: Entrenamiento de Word Embedding Propio

[![Python](https://img.shields.io/badge/Python-3670A0?style=flat&logo=python&logoColor=ffdd54)](https://www.python.org/)
[![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat&logo=pandas&logoColor=white)](https://pandas.pydata.org/)
[![spaCy](https://img.shields.io/badge/spaCy-09A3D5?style=flat&logo=spacy&logoColor=white)](https://spacy.io/)
[![Gensim](https://img.shields.io/badge/Gensim-5A7079?style=flat&logo=python&logoColor=white)](https://radimrehurek.com/gensim/models/word2vec.html)

Este proyecto se centra en el desarrollo de representaciones de **Word Embedding** propias mediante el entrenamiento del modelo **Word2Vec** sobre un *dataset* específico de noticias. El objetivo final es utilizar estas representaciones vectoriales para construir un modelo de clasificación que pueda ser desplegado en una API.

---

## 🎯 Objetivos Principales

El flujo de trabajo cubre el proceso completo desde la obtención de datos hasta la puesta en producción del modelo:

1.  **Obtención de Noticias:** Preparar el *dataset* para el modelado.
2.  **Vectorización de Titulares:** Crear las representaciones de Word Embedding a partir de los titulares.
3.  **Clasificación:** Entrenar un modelo para clasificar las noticias por categoría.
4.  **Producción:** Colocar el modelo en producción dentro de una API.

---

## 🧠 Fases y Metodología

### 1. Preparación de Datos
* **Datasets:** Se importan los archivos `noticias_entrenamiento.csv` (91844 registros) y `noticias_prueba.csv` (22961 registros).
* **Variables:** La variable independiente es el **`titulo`** y la variable dependiente (Target) es la **`categoria`**.

### 2. Entrenamiento de Word2Vec
* El núcleo del proyecto es la implementación de **Word2Vec** para modelar representaciones vectoriales del vocabulario de noticias.
* Se utiliza la librería **Gensim** para la implementación del modelo.
* El desarrollo incluye la **exploración de spaCy** para el pre-procesamiento del texto.
* El entrenamiento se centra en generar un vocabulario y modelos de *embedding* altamente específicos para el contenido de las noticias.

### 3. Resultados y Despliegue
* **Modelos Resultantes:** El proceso genera y entrena clasificadores para las arquitecturas **CBOW** (Continuos Bag-of-Words) y **Skip-gram** (ej. `RL_cbow` y `RL_sg`).
* **Serialización:** Los modelos entrenados se guardan usando la librería **`pickle`** (`lr_cbow.pkl` y `lr_sg.pkl`) para ser utilizados posteriormente en una API o aplicación web.

---

## 📚 Librerías y Recursos Clave

| Librería/Recurso | Uso principal |
| :--- | :--- |
| **Pandas** | Importación y manipulación de los datasets de entrenamiento y prueba (`.csv`). |
| **Gensim** | Implementación y modelado de las arquitecturas **Word2Vec**. |
| **spaCy** | Herramienta de NLP explorada para la construcción del vocabulario y procesamiento. |
| **`logging`** | Configuración básica de mensajes durante el proceso de construcción del vocabulario. |
| **`pickle`** | Herramienta para serializar y guardar los modelos entrenados (e.g., `lr_cbow.pkl`) para despliegue. |

---

## 📝 Conclusión

Crear un modelo propio de Word Embedding a partir del contenido del proyecto (noticias) es más específico y produce mejores resultados para las necesidades del proyecto que usar un modelo pre-entrenado general. Los modelos finales están listos para ser utilizados por una API para la clasificación en tiempo real.
