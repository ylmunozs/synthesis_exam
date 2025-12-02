# Detección de Regímenes Agroclimáticos usando Modelos Ocultos de Markov (HMM)

Este repositorio contiene la metodología, código y análisis para la identificación de estados agroclimáticos latentes mediante la fusión de datos satelitales (NDVI) y variables climáticas (precipitación, temperatura, humedad).

Este proyecto forma parte de un examen de síntesis enfocada en la gestión del riesgo agrícola y el diseño de mecanismos de aseguramiento basados en datos.

## 📋 Descripción del Proyecto

El objetivo es superar las limitaciones de los índices climáticos tradicionales (como umbrales fijos de lluvia) mediante el uso de modelos probabilísticos que capturan la "memoria" del sistema y la interacción multivariada.

Se implementan dos fases principales:
1.  **Análisis de Distribuciones:** Caracterización estadística de las variables.
2.  **Modelado HMM:** Implementación de un Modelo Oculto de Markov Gaussiano Multivariado para clasificar el tiempo en estados discretos (ej. "Húmedo/Vigoroso", "Seco/Estrés").

## 📂 Estructura del Repositorio

### Archivos Principales
* **`hmm_model_syntheis_exam.ipynb`**: Notebook principal. Contiene el pipeline completo del HMM: preprocesamiento, selección de estados (BIC), entrenamiento (Baum-Welch) y decodificación (Viterbi).
* **`PDF_NDVI_Climatic_Variables`**: Notebook de análisis exploratorio. Realiza el ajuste de distribuciones de probabilidad (Normal, Gamma, Lognormal) para cada variable y justifica las transformaciones utilizadas.

### Datos
* **`Data_Ndvi.xlsx`**: Dataset fuente que contiene las series temporales diarias de:
    * NDVI (Índice de Vegetación)
    * Precipitación (mm)
    * Temperatura Máxima y Mínima (°C)
    * Humedad Relativa (%)

## 🚀 Instalación y Requisitos

El código está desarrollado en Python 3. Se recomienda crear un entorno virtual e instalar las dependencias:

```bash
pip install pandas numpy matplotlib seaborn scipy scikit-learn hmmlearn openpyxl
