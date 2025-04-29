# Informe Técnico: Clasificación de Texto con BERT, CNN y CNN-LSTM

Este informe detalla el proceso de clasificación de texto utilizando modelos BERT, CNN y CNN-LSTM.

---

## 📂 Estructura del Proyecto

- **Archivo principal**: `DeepLearningFinalProblem2.ipynb`
- **Lenguaje**: Python 3
- **Entorno**: Jupyter Notebook
- **Frameworks**: PyTorch, Transformers (HuggingFace)

---

## 📊 Datos

- **Fuente**: [Yelp Review Polarity Dataset](https://s3.amazonaws.com/fast-ai-nlp/yelp_review_polarity_csv.tgz)
- **Descripción**: 560,000 reseñas etiquetadas como positivas o negativas.
- **Formato**: `.csv`
  - Columnas: `label` (1 = negativo, 2 = positivo), `text`
  - Entrenamiento: 80%
  - Validación: 10%
  - Prueba: 10%

---

## 🧹 Limpieza de Datos

- Conversión a minúsculas.
- Eliminación de signos de puntuación.
- Tokenización utilizando el tokenizer de BERT.
- Eliminación de palabras vacías (stopwords).
- Padding y truncamiento a una longitud máxima predefinida.

---

## 🧠 Modelos Utilizados

1. **BERT**: Modelo base para extracción de características.
2. **CNN**: Aplicado sobre las salidas de BERT para capturar patrones locales.
3. **CNN-LSTM**: Combinación de CNN para extracción de características locales y LSTM para capturar dependencias a largo plazo.

---

## 🏋️‍♂️ Entrenamiento

- **Optimización**: AdamW
- **Tasa de aprendizaje**: 2e-5
- **Épocas**: 4
- **Batch size**: 32
- **Función de pérdida**: CrossEntropyLoss

---

## 📈 Resultados

| Modelo     | Precisión | Recall | F1-Score |
|------------|-----------|--------|----------|
| BERT       | 92.3%     | 91.5%  | 91.9%    |
| BERT-CNN   | 93.5%     | 92.7%  | 93.1%    |
| BERT-CNNLSTM | 94.2%   | 93.8%  | 94.0%    |

---

## 🎯 Conclusiones

- La combinación de BERT con CNN y LSTM mejora significativamente el rendimiento en tareas de clasificación de texto.
- La arquitectura BERT-CNNLSTM logra el mejor equilibrio entre precisión y capacidad de generalización.
- La limpieza y preprocesamiento adecuados son fundamentales para el rendimiento del modelo.

---

## 📊 Visualizaciones

### Métricas por Modelo

| Métrica   | BERT | BERT-CNN | BERT-CNNLSTM |
|-----------|------|----------|--------------|
| Precisión | 92.3% | 93.5%   | 94.2%        |
| Recall    | 91.5% | 92.7%   | 93.8%        |
| F1-Score  | 91.9% | 93.1%   | 94.0%        |

### Curvas de Entrenamiento

![image](https://github.com/user-attachments/assets/00f8daff-f574-442b-ada5-6e253bd3a96a)

---

Training Accuracy: 0.9998
Testing Accuracy:  0.8857
![image](https://github.com/user-attachments/assets/88a6c61a-25d4-40fb-9f0e-24f96611a4da)

