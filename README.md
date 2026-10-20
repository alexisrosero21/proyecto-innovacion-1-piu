![Proyecto I de innovación Tecnológica en Inteligencia Artificial](https://github.com/MIA-PID/projectTemplate/assets/16925921/2ff335c7-65a6-4b2b-9eae-3612b8d64e93)

# Predicción de severidad de uso problemático de internet en niños y adolescentes

Este proyecto forma parte del curso **Proyecto 1 de Innovación Tecnológica** de la Maestría en Inteligencia Artificial Aplicada, Universidad Icesi (Cali, Colombia).

Repositorio basado en la [plantilla oficial del curso](https://github.com/MIA-PID/projectTemplate).

**Estado del proyecto:** Activo — Actividad 1 (configuración del repositorio y selección del problema)

## Integrantes

**Líder del equipo:** [William Alexis Rosero Campos](https://github.com/alexisrosero21)

**Docente / tutor:** *por completar*

#### Otros integrantes (máximo 4 personas en total)

| Nombre | GitHub | Correo |
|--------|--------|--------|
| William Alexis Rosero Campos | [@alexisrosero21](https://github.com/alexisrosero21) | *warosero@icesi.edu.co* |


> Actualizar esta tabla cuando se confirmen los demás integrantes. Si el equipo es de menos de 4 personas, eliminar las filas vacías.

## Contacto

Pueden escribir al líder del equipo o al docente del curso para dudas o contribuciones.

## Problema a abordar

**Reto 1 — Uso problemático de internet en niños y adolescentes.**

El uso problemático de internet se asocia con problemas de salud mental como ansiedad y depresión. Detectarlo a tiempo permite activar intervenciones antes de que el hábito se consolide. El objetivo es **predecir el nivel de severidad** de uso problemático de internet a partir de medidas de actividad, aptitud física, cuestionarios y variables demográficas, fáciles de recolectar y de uso extendido.

## Introducción y objetivo

El propósito del proyecto es construir y comparar modelos de aprendizaje supervisado (clasificación ordinal y/o regresión) que estimen la severidad de uso problemático de internet en menores, usando datos reales y desidentificados del estudio *Healthy Brain Network* del Child Mind Institute, publicados en Kaggle.

Además del desempeño predictivo, el equipo debe discutir **qué se puede y qué no se puede concluir**: los datos corresponden a menores de edad, hay desbalance entre niveles de severidad, valores faltantes y limitaciones de las definiciones clínicas actuales evidenciadas por la competencia. El impacto potencial es social (detección temprana), no diagnóstico clínico automatizado.

### Fuentes de datos y referencias

- Competencia y datos: [Child Mind Institute — Problematic Internet Use (Kaggle)](https://www.kaggle.com/competitions/child-mind-institute-problematic-internet-use)
- Anuncio: [Child Mind Institute y Kaggle](https://childmind.org/blog/child-mind-institute-and-kaggle-launch-competition-to-predict-teen-internet-addiction/)
- Lecciones de la competencia: [Screen time struggles](https://childmind.org/blog/screen-time-struggles/)

### Métodos previstos (técnicas del primer semestre)

- Análisis exploratorio, imputación y tratamiento de desbalance
- Máquinas de soporte vectorial (SVM)
- Modelos de ensamble (bosques aleatorios, gradient boosting, voting/stacking)
- Aprendizaje no supervisado (PCA, clustering) para explorar estructura y posibles sesgos
- Validación cruzada estratificada y métricas adecuadas a clasificación ordinal / regresión
- (Opcional) características de series de tiempo del acelerómetro

### Tecnologías

- Python 3.11+
- pandas, numpy, scikit-learn, matplotlib, seaborn
- Jupyter notebooks
- Git / GitHub
- Datos descargados desde Kaggle (no se versionan archivos crudos pesados)

## Descripción del proyecto (contexto)

1. **Tipo de problema:** aprendizaje supervisado sobre datos principalmente tabulares, con valores faltantes y desbalance entre niveles de severidad. Variable objetivo: severidad de uso problemático de internet (ordinal o continua, según el esquema de etiquetas de la competencia).
2. **Preguntas de investigación:** ¿qué tanto se puede estimar la severidad a partir de actividad física, aptitud y demográficos? ¿qué variables importan? ¿un modelo no supervisado recupera grupos coherentes con la severidad? ¿qué sesgos aparecen por edad, sexo o datos faltantes?
3. **Límite ético:** el modelo es un apoyo de investigación y de discusión metodológica; **no** sustituye evaluación clínica ni se usará para perfilar a menores en producción.
4. **Plan detallado, cronograma y tres entregas:** ver [`docs/PLAN_DE_PROYECTO.md`](docs/PLAN_DE_PROYECTO.md).

## Estructura del repositorio

```text
.
├── README.md                 # Integrantes, problema y contexto (Actividad 1)
├── docs/
│   ├── PLAN_DE_PROYECTO.md    # Plan completo alineado a las tres entregas
│   └── etica_y_alcances.md    # Notas sobre uso responsable y sesgos
├── notebooks/               # Exploración y experimentos
├── src/                     # Código reutilizable (limpieza, modelos, métricas)
├── data/                    # Solo README: los datos se descargan (no se suben)
├── reports/                 # Informes de cada entrega
├── requirements.txt
└── .gitignore
```

## Cómo empezar

1. Clonar este repositorio: `git clone https://github.com/alexisrosero21/proyecto-innovacion-1-piu.git`
2. Crear un entorno virtual e instalar dependencias: `pip install -r requirements.txt`
3. Descargar los datos de Kaggle (requiere cuenta y aceptar las reglas de la competencia) y colocarlos en `data/raw/` siguiendo `data/README.md`.
4. Los notebooks de exploración irán en `notebooks/`.

## Entregables del curso (resumen)

| Entrega | Enfoque |
|---------|---------|
| **1** | Repositorio, problema, EDA, diccionario de datos, planteamiento ético |
| **2** | Preprocesamiento, líneas base, SVM y ensambles, no supervisado exploratorio |
| **3** | Modelo final, comparación, limitaciones, conclusiones y presentación |

Detalle en [`docs/PLAN_DE_PROYECTO.md`](docs/PLAN_DE_PROYECTO.md).

## Notebooks y entregas destacadas

* Pendiente — Entrega 1: análisis exploratorio
* Pendiente — Entrega 2: comparación de modelos
* Pendiente — Entrega 3: informe final
