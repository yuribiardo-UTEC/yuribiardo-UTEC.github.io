# ð PredicciÃ³n del Alto Rendimiento AcadÃ©mico â PISA 2022

> EspecializaciÃ³n en Ciencia de Datos e IA â UTEC  
> Asignatura: Aprendizaje AutomÃ¡tico  
> **Autor:** Yuri Martin Biardo

---

## ð DescripciÃ³n

ImplementaciÃ³n de un clasificador supervisado para predecir si un estudiante alcanza **alto rendimiento acadÃ©mico** (PISA_AVG â¥ 500) en las pruebas PISA 2022, a partir de variables socioeconÃ³micas, de acceso tecnolÃ³gico y de contexto paÃ­s. El proyecto incluye secciones extendidas de evaluaciÃ³n avanzada: optimizaciÃ³n de umbral de decisiÃ³n y calibraciÃ³n de probabilidades.

---

## ð¯ Objetivo

Construir y comparar modelos de clasificaciÃ³n supervisada para identificar los factores que mejor predicen el alto rendimiento en PISA 2022, evaluando no solo la capacidad discriminativa (AUC) sino tambiÃ©n la calidad de las probabilidades producidas (calibraciÃ³n) y el comportamiento bajo distintos umbrales de decisiÃ³n.

---

## ð Estructura del repositorio

```
proyecto-pisa2022/
â
âââ PISA2022_Mejorado.ipynb     # Notebook completo con secciones extendidas
âââ README.md
```

---

## ð Dataset

- **Fuente**: PISA 2022 (OCDE) â datos pÃºblicos de evaluaciÃ³n internacional
- **Variable objetivo**: `High_Performer` = 1 si promedio (Math + Reading + Science) â¥ 500
- **Features utilizadas**:

| Variable | DescripciÃ³n |
|---|---|
| ST004D01T | GÃ©nero del estudiante |
| ST250Q01â04JA | Recursos TIC en el hogar |
| HISCED | Nivel educativo mÃ¡ximo del hogar |
| ICTRES | Ãndice de recursos tecnolÃ³gicos |
| ESCS | Ãndice socioeconÃ³mico y cultural |
| GDP_per_capita_PPP_2022 | PIB per cÃ¡pita del paÃ­s (PPP) |
| HDI_2022 | Ãndice de Desarrollo Humano |
| Education_Index_2022 | Ãndice de educaciÃ³n |
| Internet_Penetration_2022 | PenetraciÃ³n de internet en el paÃ­s |

---

## ð ï¸ TecnologÃ­as y metodologÃ­as

| Componente | Detalle |
|---|---|
| Lenguaje | Python |
| LibrerÃ­as | scikit-learn, pandas, numpy, matplotlib, seaborn |
| Modelos comparados | RegresiÃ³n LogÃ­stica, Random Forest, Gradient Boosting |
| ValidaciÃ³n | StratifiedKFold (5 folds) + GridSearchCV |
| Entorno | Google Colab |

---

## ð Resultados principales

**EvaluaciÃ³n estÃ¡ndar (SecciÃ³n 8):**
- Comparativa de ROC-AUC, F1-score y matrices de confusiÃ³n para los 3 modelos
- Gradient Boosting con mejor AUC con umbral default 0.5

**Curvas Precision-Recall y umbral Ã³ptimo (SecciÃ³n 8B):**
- La curva PR revela diferencias entre modelos que la ROC-AUC oculta en presencia de desbalance de clases
- Con umbral optimizado, la RegresiÃ³n LogÃ­stica alcanza F1 competitivo con menor complejidad
- Tabla comparativa: umbral 0.5 vs. umbral Ã³ptimo por modelo

**CalibraciÃ³n de probabilidades (SecccÃ³n 8C):**
- Reliability diagrams para los 3 modelos â identificaciÃ³n de sobre/subestimaciÃ³n de probabilidades
- Comparativa de Brier Score antes y despuÃ©s de calibraciÃ³n (Platt Scaling e Isotonic Regression)
- Un modelo con buen AUC puede producir probabilidades mal calibradas â resultado clave para aplicaciones de riesgo

---

## ð Decisiones tÃ©cnicas destacadas

- **Curva PR sobre ROC**: con clases desbalanceadas, la Average Precision penaliza falsos positivos de forma mÃ¡s informativa que el AUC clÃ¡sico
- **OptimizaciÃ³n de umbral**: el umbral 0.5 no es Ã³ptimo en clasificaciÃ³n con asimetrÃ­a de costos â se eligiÃ³ el umbral que maximiza F1 por modelo
- **CalibraciÃ³n post-hoc**: se aplicÃ³ `CalibratedClassifierCV` con `cv='prefit'` para no contaminar el set de evaluaciÃ³n
- **class_weight='balanced'** en RegresiÃ³n LogÃ­stica para correcciÃ³n del desbalance de clases

---

## â¶ï¸ CÃ³mo ejecutar

1. Abrir `PISA2022_Mejorado.ipynb` en Google Colab
2. Subir los datasets `pisa_muestra_global.csv` y `pisa_ml_2022_limpio.csv`
3. Ejecutar todas las celdas en orden

```bash
# Dependencias
pip install scikit-learn pandas numpy matplotlib seaborn
```
