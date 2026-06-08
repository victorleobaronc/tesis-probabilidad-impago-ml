# Estimación de la Probabilidad de Impago en Carteras de Crédito Empresarial
### Comparación de Modelos Estadísticos y de Machine Learning bajo el Estándar IFRS 9

**Universidad de La Salle — Maestría en Analítica e Inteligencia de Negocios**  
**Autores:** Victor Leonardo Barón Castrillo · Oscar Fernando Bolaños Caicedo · Sindy Carolina Roldán Guerra  
**Tutor:** Leandro Vivas Fuentes  
**Año:** 2025

---

## Descripción

Este repositorio contiene el notebook de Google Colab desarrollado como parte del proyecto investigativo de grado. El objetivo del estudio es identificar qué modelo estadístico o de aprendizaje automático predice con mayor precisión la probabilidad de incumplimiento crediticio en una cartera empresarial colombiana, bajo el estándar contable IFRS 9.

El proceso analítico completo sigue la metodología **CRISP-DM** (Cross-Industry Standard Process for Data Mining) y está estructurado en **22 scripts** que cubren desde la exploración inicial de los datos hasta la validación cruzada del modelo ganador.

---

## Resultados principales

| Modelo | AUC-ROC | Recall | Precision | F1-Score |
|---|---|---|---|---|
| **XGBoost** 🥇 | 0.9949 | 0.9649 | 0.9016 | 0.9322 |
| Random Forest | 0.9973 | 0.9649 | 0.8871 | 0.9244 |
| Árbol de Decisión | 0.9851 | 0.9298 | 0.8548 | 0.8908 |
| SVM | 0.9689 | 0.8596 | 0.7903 | 0.8235 |
| Regresión Logística | 0.9582 | 0.9298 | 0.6883 | 0.7910 |

**XGBoost** fue seleccionado como modelo ganador por su equilibrio entre Recall (96.49%) y Precision (90.16%), detectando 55 de 57 casos reales de Default en el conjunto de prueba. La validación cruzada K-Fold (k=5) confirmó la robustez del modelo con una variación de apenas ±0.006.

---

## Estructura del notebook

El notebook está organizado en las 6 fases de CRISP-DM:

| Fase | Scripts | Descripción |
|---|---|---|
| 1. Comprensión del negocio | — | Definición del problema, variable objetivo IFRS 9 Stage 3 |
| 2. Comprensión de los datos | Scripts 01–03 | Tablas de frecuencia, estadísticos descriptivos, boxplots |
| 3. Preparación de los datos | Scripts 04–12 | Limpieza, imputación, outliers, escalado, PCA, SMOTE |
| 4. Modelado | Scripts 13–19 | K-Means, 5 modelos de clasificación, comparación final |
| 5. Evaluación | Scripts 19–21 | Validación cruzada K-Fold, análisis SHAP, perfil de clústeres |
| 6. Despliegue | Script 22 | Documentación de resultados y recomendaciones |

---

## Dataset

- **Registros:** 1.632 operaciones de crédito empresarial directo
- **Variables originales:** 131
- **Variables finales (modelo):** 16
- **Variable objetivo:** Incumplimiento bajo IFRS 9 Stage 3 (≥ 90 días de mora)
- **Tasa de incumplimiento:** 17.46% (286 defaults / 1.346 al día)
- **Corte temporal:** Abril de 2025

> ⚠️ El dataset no se incluye en este repositorio por razones de confidencialidad institucional.

---

## Tecnologías utilizadas

- Python 3
- Google Colab
- Pandas · NumPy · Scikit-learn · XGBoost · SHAP · Matplotlib · Seaborn · Imbalanced-learn (SMOTE)

---

## Cómo visualizar el notebook

El notebook incluye todos los outputs ya ejecutados (gráficas, tablas y métricas). Para visualizarlo sin necesidad de ejecutarlo:

1. Abre el archivo `.ipynb` directamente en GitHub — GitHub renderiza los notebooks automáticamente
2. O usa [nbviewer](https://nbviewer.org/) pegando la URL del archivo

---

## Referencia

> Barón Castrillo, V. L., Bolaños Caicedo, O. F., & Roldán Guerra, S. C. (2025). *Estimación de la probabilidad de impago en carteras de crédito empresarial: comparación de modelos estadísticos y de machine learning bajo el estándar IFRS 9* [Tesis de maestría]. Universidad de La Salle.
