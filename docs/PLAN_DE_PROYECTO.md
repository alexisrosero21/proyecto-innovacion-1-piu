# Plan de proyecto

**Curso:** Proyecto 1 de Innovación Tecnológica — Maestría en IA Aplicada, Universidad Icesi  
**Reto elegido:** Uso problemático de internet en niños y adolescentes  
**Equipo:** máximo 4 personas · Líder: William Alexis Rosero Campos  
**Técnicas:** ensambles, SVM, aprendizaje no supervisado, preprocesamiento tabular

Este plan cubre lo que pide el enunciado (exploración, limpieza, comparación de modelos y discusión de alcances) y se organiza en las **tres entregas** del curso. Ajustar fechas al cronograma oficial publicado por el docente.

---

## 1. Objetivo general

Predecir el **nivel de severidad** de uso problemático de internet a partir de medidas de actividad, aptitud física, cuestionarios y variables demográficas del estudio Healthy Brain Network (Child Mind Institute).

## 2. Objetivos específicos

1. Comprender el problema, el diccionario de datos, la variable objetivo y las reglas de la competencia de Kaggle.
2. Explorar, limpiar e imputar datos tabulares con valores faltantes y desbalance.
3. Comparar al menos: una línea base, SVM, y uno o más ensambles; reportar métricas adecuadas a clasificación ordinal o regresión.
4. Usar métodos no supervisados (reducción de dimensión y clustering) para explorar estructura, no como sustituto del modelo supervisado.
5. Discutir sesgos, uso responsable con datos de menores y lo que **no** se puede afirmar clínicamente.
6. (Opcional) Extraer características de acelerómetro si el tiempo y el cómputo lo permiten.

## 3. Preguntas que el proyecto debe responder

- ¿Qué tan bien se predice la severidad con variables físicas y demográficas (sin usar el uso de pantalla como única señal)?
- ¿Qué modelos del primer semestre rinden mejor y por qué?
- ¿El desbalance y los faltantes cambian las conclusiones?
- ¿Qué grupos o sesgos aparecen en clustering / PCA?
- ¿Qué se puede decir a un profesional de salud y qué no?

## 4. Alcance y no-alcance

**Dentro del alcance**

- Datos tabulares de la competencia; preprocesamiento reproducible; comparación justa (misma partición, mismas métricas).
- Interpretación de importancias y errores (por ejemplo clases extremas vs. intermedias).
- Documento ético breve.

**Fuera del alcance (salvo extra documentado)**

- Despliegue clínico o app de diagnóstico.
- Reidentificación de participantes.
- Redes profundas como único modelo (si se usan, serán complemento, no el núcleo del curso).

## 5. Datos

| Ítem | Detalle |
|------|---------|
| Origen | Healthy Brain Network — Child Mind Institute, publicación en Kaggle |
| Tipo | Tabular (+ acelerómetro opcional) |
| Retos | Faltantes, desbalance de severidad, posible ruido de etiquetas clínicas |
| Licencia / uso | Aceptar reglas de Kaggle; no subir datos crudos al repo |
| Enlaces | [Competencia](https://www.kaggle.com/competitions/child-mind-institute-problematic-internet-use) · [Anuncio](https://childmind.org/blog/child-mind-institute-and-kaggle-launch-competition-to-predict-teen-internet-addiction/) · [Lecciones](https://childmind.org/blog/screen-time-struggles/) |

**Decisión de modelado:** tratar la severidad como **clasificación ordinal** (métrica principal tipo quadratic weighted kappa u otra alineada a la competencia) y, en paralelo, una **regresión** sobre el puntaje si existe. Reportar ambas si aplica.

## 6. Metodología (técnicas del semestre)

1. **EDA:** distribución de la etiqueta, correlaciones, faltantes por instrumento, fugas potenciales.
2. **Limpieza:** tipos, outliers plausibles, imputación (mediana/moda o modelos simples), encoding, escalado para SVM.
3. **Desbalance:** `class_weight`, oversampling solo en train, o umbrales; nunca filtrar el test.
4. **Línea base:** Dummy / regresión logística multinomial o regresión lineal.
5. **SVM:** kernel lineal y RBF; búsqueda de `C` y `gamma` con validación cruzada.
6. **Ensamble:** Random Forest y Gradient Boosting (o HistGradientBoosting, útil con faltantes); opcional voting.
7. **No supervisado:** PCA/t-SNE para visualización; k-means o GMM; comparar clusters vs. etiqueta (ARI, homogeneidad) **sin usar la etiqueta para ajustar el cluster**.
8. **Evaluación:** partición estratificada train/val/test o CV; matriz de confusión; análisis por subgrupo (edad, sexo) si las variables lo permiten.
9. **Opcional:** estadísticos de acelerómetro (media, varianza, magnitud) como features extra.

## 7. Tres entregas (mapa de trabajo)

Las fechas las fija el curso; aquí va el **contenido mínimo** para cumplir con el enunciado.

### Entrega 1 — Comprensión del problema y de los datos

**Incluye la Actividad 1 actual.**

- [x] Repositorio en GitHub (plantilla del curso adaptada)
- [x] Integrantes, problema, descripción de contexto en el README
- [ ] Cuenta Kaggle, aceptar competencia, descarga de datos en `data/raw/` (local)
- [ ] Diccionario de variables (qué es cada columna, tipo, % faltantes)
- [ ] Notebook de EDA: etiqueta, desbalance, faltantes, primeras visualizaciones
- [ ] Formulación formal: X, y, tipo de tarea, métrica principal y métricas secundarias
- [ ] Nota ética inicial (`docs/etica_y_alcances.md`)
- [ ] Informe corto en `reports/entrega_1.md`

**Criterio de listo:** un extraño entiende el problema, los datos y los riesgos sin leer Kaggle entero.

### Entrega 2 — Modelado y comparación

- [ ] Pipeline de preprocesamiento versionado en `src/`
- [ ] Línea base + SVM + al menos un ensamble, misma validación
- [ ] Experimento no supervisado documentado (qué se aprendió)
- [ ] Tabla comparativa de métricas y tiempos aproximados
- [ ] Diagnóstico de errores (qué niveles se confunden)
- [ ] Informe en `reports/entrega_2.md` y notebooks en `notebooks/`

**Criterio de listo:** comparación reproducible, no un solo modelo que funcionó.

### Entrega 3 — Síntesis, limitaciones y cierre

- [ ] Modelo final justificado (no necesariamente el de mayor score si es inestable o opaco)
- [ ] Importancia de variables / interpretación acotada
- [ ] Discusión: limitaciones de la etiqueta clínica, sesgos, generalización, menores de edad
- [ ] Qué **no** se debe hacer con el modelo (lista explícita)
- [ ] Conclusiones y trabajo futuro (acelerómetro, otros instrumentos)
- [ ] Presentación / informe final en `reports/entrega_3.md`
- [ ] README actualizado (estado Completado, enlaces a notebooks)

**Criterio de listo:** el docente puede reproducir la idea central y evaluar el juicio crítico, no solo el accuracy.

## 8. Cronograma sugerido (adaptar a las fechas del aula)

Asumiendo un semestre típico; **reemplazar con las fechas reales**.

| Semana | Actividad | Entrega asociada |
|--------|-----------|------------------|
| 1 | Repo, README, elección del reto, acceso a Kaggle | Actividad 1 / Entrega 1 |
| 2 | Diccionario de datos y EDA completo | Entrega 1 |
| 3 | Estrategia de faltantes y desbalance; split definitivo | Entrega 1–2 |
| 4 | Línea base y primer SVM | Entrega 2 |
| 5 | Ensambles y ajuste de hiperparámetros | Entrega 2 |
| 6 | No supervisado + análisis de errores | Entrega 2 |
| 7 | (Opcional) features de acelerómetro | Entrega 2–3 |
| 8 | Modelo final, interpretación, ética | Entrega 3 |
| 9 | Informe, presentación, limpieza del repo | Entrega 3 |

## 9. Organización del equipo (hasta 4 personas)

Roles rotativos o fijos; un nombre por rol cuando el equipo esté completo:

| Rol | Responsabilidad |
|-----|-----------------|
| Líder / integración | README, plan, calidad del repo, narrativa |
| Datos | Descarga, diccionario, EDA, pipelines |
| Modelos | SVM, ensambles, CV, métricas |
| Crítica y ética | No supervisado, sesgos, limitaciones, presentación |

Todo el código va por pull request o commits claros en `main`.

## 10. Riesgos y mitigación

| Riesgo | Mitigación |
|--------|------------|
| Poca señal en variables físicas (la competencia mostró techos bajos) | Reportar el techo honestamente; comparar contra baseline; no inflar conclusiones |
| Desbalance extremo | Métricas no ingenuas; no optimizar solo accuracy |
| Faltantes sistemáticos (no al azar) | Indicadores de missingness; discutir MAR/MNAR |
| Fuga de información | Separar test antes de cualquier imputación global |
| Cómputo del acelerómetro | Dejarlo opcional; tabular primero |
| Ética / menores | No datos en GitHub; no ejemplos identificables; lenguaje de riesgo / screening de investigación |

## 11. Criterios de éxito del proyecto de curso

1. Repositorio navegable y README al día.
2. Al menos tres familias de modelos comparadas con el mismo protocolo.
3. Uso explícito de no supervisado con interpretación.
4. Discusión ética y de alcances, no un párrafo genérico.
5. Resultados reproducibles en CPU de laptop en tiempo razonable.

## 12. Alternativas no elegidas (por si el docente pregunta)

- **Hojas de café (BRACOL + RoCoLe):** clasificación de imágenes; exigiría extraer color/textura o embeddings y discutir generalización arábica vs. robusta. Queda como plan B si el equipo prefiere visión.
- **BirdCLEF+ 2025:** audio de biodiversidad en el Magdalena Medio; subconjunto de 10–20 especies y MFCC. Queda como plan B si el interés es bioacústica.

La elección del reto 1 prioriza **datos tabulares reales**, técnicas del primer semestre sin depender de GPU, y una discusión ética exigida por el enunciado.
