# Prediccion de Supervivencia en el Titanic.
Proyecto de Machine Learning que predice si un pasajero sobrevivió al hundimiento del Titanic, basándose en variables como clase social, sexo, edad y composición
familiar.

# Objetivo
Construir y evaluar modelos de clasificación capaces de la supervivencia de un pasajero a partir de datos históricos, aplicando un flujo complejo de ciencia de datos:
limpieza, análisis  exploratorio ,entrenamiento y evaluación.

# Dataset
- **Fuente**: [Titanic - Machine Learning from Disaster (Kaggle)](https://www.kaggle.com/c/titanic)
- **Archivo**: `train.csv`
- **Filas**: ~891 pasajeros
- **Variables utilizadas**: `Pclass`, `Sex`, `Age`, `SibSp`, `Parch`, `Fare`, `FamilySize` (creada)

# Proceso
### 1. Limpieza de datos
- Imputación de valores nulos en `Age` (mediana) y `Embarked` (moda)
- Codificación de `Sex` a variable numérica (`male`=0, `female`=1)
- Creación de la variable `FamilySize` (`SibSp` + `Parch` + 1)

### 2. Análisis Exploratorio (EDA)
Principales hallazgos:
- **Sexo**: las mujeres tuvieron una tasa de supervivencia de ~74%, frente a ~19% en hombres — la variable más determinante del dataset.
- **Clase social**: los pasajeros de 1ª clase sobrevivieron en mayor proporción que los de 2ª y 3ª clase.
- **Edad**: los niños tuvieron mayor probabilidad de supervivencia frente a otros grupos de edad.

### 3. Modelos entrenados
Se entrenaron y compararon dos algoritmos de clasificación con `scikit-learn`:

| Modelo | Accuracy |
|---|---|
| Regresión Logística | 81.0% |
| Random Forest | 80.4% |

*(Split de datos: 80% entrenamiento / 20% prueba, `random_state=42`)*

# Conclusion Final
El modelo de Regresión Logística obtuvo un rendimiento ligeramente superior al Random Forest, sugiriendo que las relaciones entre las variables 
y la supervivencia son mayormente lineales. Ambos modelos superan ampliamente el baseline de referencia (~62% de accuracy si se predijera siempre 
"no supervivencia").


