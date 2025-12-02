# Detección de Regímenes Agroclimáticos usando Modelos Ocultos de Markov (HMM)

Este repositorio contiene la metodología, código y análisis para la identificación de estados agroclimáticos latentes mediante la fusión de datos satelitales (NDVI) y variables climáticas (precipitación, temperatura, humedad).

Este proyecto forma parte de una investigación doctoral enfocada en la gestión del riesgo agrícola y el diseño de mecanismos de aseguramiento basados en datos.

## 📋 Descripción del Proyecto

El objetivo es superar las limitaciones de los índices climáticos tradicionales (como umbrales fijos de lluvia) mediante el uso de modelos probabilísticos que capturan la "memoria" del sistema y la interacción multivariada.

Se implementan dos fases principales:
1.  **Análisis de Distribuciones:** Caracterización estadística rigurosa de las variables (ej. modelo Bernoulli-Gamma para precipitación).
2.  **Modelado HMM:** Implementación de un Modelo Oculto de Markov Gaussiano Multivariado para clasificar el tiempo en estados discretos (ej. "Húmedo/Vigoroso", "Seco/Estrés").

## 📂 Estructura del Repositorio

### Archivos Principales
* **`hmm_model_syntheis_exam.ipynb`**: Notebook principal. Contiene el pipeline completo del HMM: preprocesamiento, selección de estados (BIC), entrenamiento (Baum-Welch) y decodificación (Viterbi).
* **`hmm_model_V3.2 - Distribuciones.ipynb`**: Notebook de análisis exploratorio. Realiza el ajuste de distribuciones de probabilidad (Normal, Gamma, Lognormal) para cada variable y justifica las transformaciones utilizadas.

### Datos
* **`exp9b_ndvi_mae_robusto.xlsx`**: Dataset fuente que contiene las series temporales diarias de:
    * NDVI (Índice de Vegetación)
    * Precipitación (mm)
    * Temperatura Máxima y Mínima (°C)
    * Humedad Relativa (%)

## 🚀 Instalación y Requisitos

El código está desarrollado en Python 3. Se recomienda crear un entorno virtual e instalar las dependencias:

```bash
pip install pandas numpy matplotlib seaborn scipy scikit-learn hmmlearn openpyxl
