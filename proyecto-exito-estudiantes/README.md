# ð Factores del Ãxito Profesional en Estudiantes Universitarios

> EspecializaciÃ³n en Ciencia de Datos e IA â UTEC  
> Asignatura: Fundamentos de ProgramaciÃ³n para la Ciencia de Datos e IA  
> **Autores:** TomÃ¡s Clavijo Â· MarÃ­a Martinote Â· Yuri Martin Biardo

---

## ð DescripciÃ³n

AnÃ¡lisis exploratorio y estadÃ­stico de los factores que influyen en el Ã©xito profesional de estudiantes universitarios, a partir de un dataset sintÃ©tico de 5.000 registros basado en tendencias reales. El proyecto abarca desde la limpieza de datos hasta la aplicaciÃ³n de pruebas estadÃ­sticas formales para validar hipÃ³tesis sobre las variables que predicen mejores salarios y oportunidades laborales.

---

## ð¯ Objetivo

Identificar quÃ© variables acadÃ©micas, personales y de actividad extracurricular se asocian significativamente con indicadores de Ã©xito profesional (salario inicial, nÃºmero de ofertas laborales), y validar esas asociaciones mediante pruebas estadÃ­sticas formales.

---

## ð Estructura del repositorio

```
proyecto-exito-estudiantes/
â
âââ EntregaExitoEstudiantes.ipynb    # Notebook completo (149 celdas)
âââ README.md
```

---

## ð Dataset

- **TamaÃ±o**: 5.000 registros Ã 18 variables
- **Tipo**: Dataset sintÃ©tico basado en tendencias reales
- **Variables incluidas**:
  - Datos personales: edad (18â30), gÃ©nero
  - DesempeÃ±o acadÃ©mico: GPA secundaria y universitario, puntaje SAT, ranking universitario, campo de estudio
  - Actividades: internados, proyectos, certificaciones, habilidades blandas, networking
  - Resultados profesionales: salario inicial, ofertas laborales recibidas

---

## ð ï¸ TecnologÃ­as y metodologÃ­as

| Componente | Detalle |
|---|---|
| Lenguaje | Python |
| LibrerÃ­as | pandas, numpy, matplotlib, seaborn, plotly, scipy |
| Entorno | Google Colab |

**MetodologÃ­a por etapas:**

- **Etapa I â ContextualizaciÃ³n**: definiciÃ³n del problema y exploraciÃ³n inicial del dataset
- **Etapa II â Limpieza y preprocesamiento**: verificaciÃ³n de nulos, duplicados, tipos de datos y outliers
- **Etapa III â VisualizaciÃ³n y anÃ¡lisis**: scatterplots, heatmaps, distribuciones, anÃ¡lisis multivariado
- **Etapa IV â Resultados y discusiÃ³n**: sÃ­ntesis de hallazgos y reflexiÃ³n crÃ­tica

**Pruebas estadÃ­sticas aplicadas:**
- Test de Kolmogorov-Smirnov (normalidad de variables continuas)
- Test de Chi-cuadrado (asociaciÃ³n entre variables categÃ³ricas)
- AnÃ¡lisis de varianza y covarianza

---

## ð Resultados principales

- El GPA universitario muestra asociaciÃ³n positiva con el salario inicial, pero con alta dispersiÃ³n â el efecto existe pero es dÃ©bil
- El networking aparece como variable diferenciadora mÃ¡s asociada al nÃºmero de ofertas laborales que el GPA
- Diferencias estadÃ­sticamente significativas en distribuciÃ³n salarial por gÃ©nero (Chi-cuadrado)
- Todas las variables continuas evaluadas rechazan la hipÃ³tesis de normalidad (KS test)
- El Ã©xito profesional responde a una combinaciÃ³n de factores, sin un Ãºnico predictor dominante

---

## ð ConclusiÃ³n analÃ­tica

El anÃ¡lisis evidencia que el Ã©xito profesional no responde a una Ãºnica fÃ³rmula. Los indicadores acadÃ©micos clÃ¡sicos (GPA, SAT) muestran asociaciones dÃ©biles o no lineales con los resultados laborales, mientras que factores como el networking y las actividades extracurriculares resultan variables diferenciadoras mÃ¡s relevantes.
