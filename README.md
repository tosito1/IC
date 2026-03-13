# Inteligencia Computacional
## Deep Learning y Optimización Evolutiva en Problemas Complejos

Este repositorio recopila proyectos desarrollados en la asignatura **Inteligencia Computacional**, enfocados en el diseño e implementación de modelos avanzados de aprendizaje automático y algoritmos metaheurísticos para resolver problemas complejos de visión por computador y optimización combinatoria.

Los proyectos exploran tanto la implementación desde cero de algoritmos fundamentales como el uso de librerías modernas del ecosistema de Machine Learning, permitiendo comprender en profundidad cómo funcionan internamente estas técnicas y cómo se aplican en problemas reales.

---

## 🛠️ Tecnologías Utilizadas

* `Python`
* `NumPy`
* `TensorFlow` / `Keras`
* `joblib`
* Deep Learning
* Algoritmos Genéticos
* Optimización Combinatoria
* Computer Vision
* Machine Learning

---

## 💻 Proyectos

### 1. Reconocimiento Óptico de Caracteres con Deep Learning (OCR)

#### Overview
Este proyecto aborda el problema clásico de Reconocimiento Óptico de Caracteres (OCR) utilizando el dataset MNIST, compuesto por imágenes de dígitos escritos a mano del 0 al 9.

El objetivo fue diseñar y comparar distintas arquitecturas de redes neuronales, comenzando por implementaciones manuales desde cero y evolucionando hacia modelos avanzados de Deep Learning con redes convolucionales. 

El proyecto demuestra cómo el incremento en la complejidad arquitectónica mejora significativamente la capacidad de reconocimiento de patrones visuales.

#### Arquitecturas Implementadas

**1. Red neuronal desde cero**
Implementación completa del entrenamiento de una red neuronal utilizando únicamente cálculo matricial con NumPy.
* Forward propagation
* Backpropagation
* Cálculo de gradientes
* Actualización de pesos

*Técnicas avanzadas de inicialización aplicadas:* He Initialization y Xavier / Glorot Initialization. Estas técnicas permiten mantener la estabilidad de las activaciones y evitar problemas de gradientes explosivos o desvanecidos.

**2. Perceptrón Multicapa (MLP)**
Red neuronal profunda con múltiples capas ocultas que mejora significativamente la capacidad de representación frente a redes simples.
* Hasta 4 capas ocultas.
* Funciones de activación modernas: `ReLU`, `Leaky ReLU`.
* Entrenamiento optimizado mediante TensorFlow/Keras.

**3. Redes Neuronales Convolucionales (CNN)**
La arquitectura final implementa CNNs, especialmente diseñadas para problemas de visión por computador. Estas redes aprenden automáticamente características visuales como bordes, formas y texturas.
* Capas de convolución para extracción de patrones espaciales.
* Max Pooling para reducción de dimensionalidad.
* Global Average Pooling.
* Capas densas finales para clasificación.

#### Regularización y Optimización
Para mejorar la estabilidad del entrenamiento y evitar *overfitting*, se aplicaron múltiples técnicas avanzadas:
* Batch Normalization
* Dropout (30–50%)
* Regularización L2
* Optimizador AdamW

También se utilizaron callbacks (`Early Stopping`, `ReduceLROnPlateau`) para mejorar el proceso de entrenamiento.

#### Data Augmentation
Para mejorar la capacidad de generalización del modelo se aplicaron técnicas de aumento de datos, incluyendo **rotaciones**, **desplazamientos** y **zoom**. Esto permite aumentar artificialmente el tamaño del conjunto de entrenamiento y mejorar la robustez del modelo.

#### Resultados
Comparación de precisión entre las arquitecturas evaluadas:

| Modelo | Precisión |
| :--- | :--- |
| Red neuronal manual | 91.22% |
| MLP | 98.08% |
| **CNN optimizada** | **99.72%** |

> La CNN final clasificó correctamente más del 99.7% de las imágenes, alcanzando un rendimiento cercano al estado del arte para MNIST.

#### Aplicaciones Reales
Los sistemas OCR son fundamentales en múltiples aplicaciones industriales:
* Digitalización automática de documentos.
* Reconocimiento de matrículas de vehículos.
* Procesamiento de cheques bancarios.
* Automatización documental.

---

### 2. Optimización Combinatoria con Algoritmos Genéticos (QAP)

#### Overview
Este proyecto aborda el Problema de Asignación Cuadrática (QAP), uno de los problemas más complejos de optimización combinatoria clasificado como NP-difícil.

El objetivo consiste en asignar 256 instalaciones a 256 ubicaciones minimizando el coste total derivado de la matriz de flujos entre instalaciones y la matriz de distancias entre ubicaciones. Se trabajó con la instancia estándar `tai256c`, ampliamente utilizada en benchmarks de optimización.

#### Algoritmo Genético Implementado
Se desarrolló un algoritmo genético completo desde cero, adaptado a problemas de permutación.

* **Selección:** Selección por torneo, Elitismo (preservación del 10% mejor) y Niching para mantener diversidad genética.
* **Operadores de Cruce:** Order Crossover (OX) y Cycle Crossover (CX). Garantizan que las soluciones generadas no contengan duplicados.
* **Mutación:** Swap mutation, Scramble mutation y un sistema de mutación adaptativa que incrementa dinámicamente la probabilidad de mutación cuando se detecta estancamiento.

#### Estrategias Evolutivas
Se compararon dos enfoques evolutivos inspirados en teorías biológicas:
* **Baldwiniano:** El aprendizaje local mejora el *fitness*, pero no modifica el genotipo.
* **Lamarckiano:** Las mejoras se incorporan al genotipo y se transmiten a la descendencia. *(Este enfoque demostró una convergencia significativamente más rápida).*

#### Búsqueda Local y Metaheurísticas
Para mejorar la explotación del espacio de soluciones se integraron técnicas avanzadas como **2-opt**, **3-opt** y **Simulated Annealing**. Estas permiten escapar de óptimos locales y mejorar las soluciones generadas.

#### Optimización del Rendimiento
Se implementaron mejoras para acelerar el proceso de búsqueda:
* Paralelización con `joblib`.
* Evaluación simultánea de individuos.
* Inyección de diversidad en poblaciones estancadas.

#### Resultados
Comparación de rendimiento entre las variantes del algoritmo:

| Algoritmo | Coste Final |
| :--- | :--- |
| Algoritmo genético básico | ~4.9e7 |
| Variante evolutiva avanzada | ~4.6e7 |
| **Variante Lamarckiana v3** | **~4.5e7** |

> La variante Lamarckiana combinada con búsqueda local y Simulated Annealing obtuvo el mejor rendimiento.

#### Aplicaciones Reales
El QAP aparece en múltiples problemas del mundo real:
* Diseño de plantas industriales.
* Distribución de circuitos integrados.
* Optimización logística.
* Planificación de infraestructuras.

---

## 🧠 Principales Aprendizajes

A lo largo de estos proyectos se desarrollaron competencias clave en Inteligencia Computacional:
* Implementación matemática de redes neuronales desde cero.
* Diseño de arquitecturas avanzadas de Deep Learning.
* Aplicación de técnicas modernas de regularización y optimización.
* Desarrollo de algoritmos genéticos avanzados.
* Integración de metaheurísticas híbridas.
* Optimización de rendimiento mediante paralelización.

---

## 👨‍💻 Autor

**Antonio José Muriel Gálvez** *Ingeniero Informático*
