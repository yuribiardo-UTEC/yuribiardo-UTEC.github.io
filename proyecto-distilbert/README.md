# ð¬ ClasificaciÃ³n de Quejas Financieras con DistilBERT

> EspecializaciÃ³n en Ciencia de Datos e IA â UTEC  
> Asignatura: Procesamiento de Lenguaje Natural  
> **Autores:** Aranda Â· Yuri Martin Biardo Â· Sambucetti

---

## ð DescripciÃ³n

Desarrollo de un clasificador automÃ¡tico de quejas financieras basado en **DistilBERT**, modelo de lenguaje preentrenado de la familia BERT. El sistema categoriza texto libre de consumidores en productos financieros especÃ­ficos, con aplicaciÃ³n directa en sistemas de atenciÃ³n al cliente y cumplimiento regulatorio. El proyecto incluye notebook de entrenamiento, versiÃ³n HTML autocontenida e informe tÃ©cnico escrito.

---

## ð¯ Objetivo

Construir un clasificador multiclase eficiente para quejas financieras utilizando transfer learning, evaluando su desempeÃ±o con mÃ©tricas apropiadas para datasets con desbalance de clases y documentando las decisiones de diseÃ±o del pipeline completo.

---

## ð Estructura del repositorio

```
proyecto-clasificador-quejas/
â
âââ ProyectoFinal_Clasificacion_Quejas.ipynb   # Notebook de entrenamiento y evaluaciÃ³n
âââ ProyectoFinal_Clasificacion_Quejas.html    # VersiÃ³n HTML autocontenida (sin dependencias)
âââ Final_Project_Written_Report.pdf           # Informe tÃ©cnico escrito
âââ ProyectoFinal_PPT.pdf                      # PresentaciÃ³n del proyecto
âââ requirements.txt                           # Dependencias del entorno
âââ README.md
```

---

## ð Dataset

- **Fuente**: Kaggle â Consumer Financial Protection Bureau (CFPB), dataset pÃºblico de quejas financieras reales
- **Tarea**: ClasificaciÃ³n multiclase de texto en lenguaje natural
- **CategorÃ­as**: Tarjetas de crÃ©dito, hipotecas, prÃ©stamos estudiantiles, cuentas corrientes, cobros de deuda, entre otras
- **Preprocesamiento**: TokenizaciÃ³n con tokenizador DistilBERT, truncado a 512 tokens
- **Acceso**: Se requiere cuenta de Kaggle (ver instrucciones de ejecuciÃ³n)

---

## ð ï¸ TecnologÃ­as y metodologÃ­as

| Componente | Detalle |
|---|---|
| Modelo base | DistilBERT (distilbert-base-uncased) |
| TÃ©cnica | Transfer learning + fine-tuning supervisado |
| Framework | Hugging Face Transformers + PyTorch |
| MÃ©tricas | F1-score macro, accuracy, matriz de confusiÃ³n |
| Manejo de desbalance | Class weights en funciÃ³n de pÃ©rdida |
| Hardware | GPU T4 (Google Colab) |
| Entorno | Google Colab |

---

## ð Resultados principales

- ClasificaciÃ³n multiclase con F1-score macro superior a baseline de bag-of-words
- AnÃ¡lisis de errores con identificaciÃ³n de las categorÃ­as con mayor confusiÃ³n entre sÃ­
- EvaluaciÃ³n del impacto del desbalance de clases con y sin class weights
- Pipeline completo de inferencia con persistencia del modelo entrenado (checkpoint)
- Comparativa de resultados con y sin early stopping (hasta 10 epochs)

**Tiempos de entrenamiento (referencia en Colab T4):**
- Primera corrida completa (instalaciÃ³n + descarga + entrenamiento): 20â40 min
- Entrenamiento modelo base (3 epochs): ~30â40 min

---

## ð Decisiones tÃ©cnicas destacadas

- **DistilBERT sobre BERT completo**: 40% menos de parÃ¡metros conservando ~97% del desempeÃ±o â viable en Colab gratuito
- **Class weights**: correcciÃ³n del sesgo hacia clases mayoritarias en datasets desbalanceados
- **F1-score macro**: evaluaciÃ³n equitativa entre categorÃ­as independientemente de su frecuencia de apariciÃ³n
- **Early stopping**: control del sobreajuste con hasta 10 epochs de entrenamiento

---

## â¶ï¸ CÃ³mo ejecutar

1. Abrir `ProyectoFinal_Clasificacion_Quejas.ipynb` en Google Colab
2. Activar GPU: `Entorno de ejecuciÃ³n > Cambiar tipo > GPU T4`
3. Obtener credenciales Kaggle: `kaggle.com > perfil > Settings > API > Create New Token`
4. Ejecutar todas las celdas en orden â cuando se solicite, subir el archivo `kaggle.json`

```
# El notebook instala automÃ¡ticamente todas las dependencias en la primera celda
# No es necesario instalar nada de forma manual
```

**Dependencias principales:** transformers Â· datasets Â· accelerate Â· scikit-learn Â· torch Â· pandas Â· numpy Â· matplotlib Â· seaborn
