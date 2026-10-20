# Uso responsable, sesgos y alcances

Documento vivo. Se profundiza en las entregas 1 y 3.

## Por qué importa

Los datos corresponden a **niños y adolescentes** del Healthy Brain Network, publicados **sin identificar** a los participantes. Un modelo que estima severidad de uso de internet puede usarse mal (estigma, vigilancia familiar, decisiones escolares) aunque el score de Kaggle sea alto.

## Principios del equipo

1. No subir datos crudos ni capturas con información potencialmente sensible al repositorio público.
2. No presentar el modelo como diagnóstico de adicción ni como herramienta clínica.
3. Reportar desempeño por subgrupos cuando sea posible (edad, sexo) para no ocultar sesgos.
4. Distinguir correlación (actividad física vs. uso de internet) de causalidad.
5. Reconocer que las etiquetas clínicas de la competencia tienen limitaciones (ver lecciones del Child Mind Institute).

## Lo que sí podemos concluir

- Si un conjunto de variables fáciles de medir se asocia, en esta muestra, con niveles de severidad etiquetados.
- Qué algoritmos del primer semestre son más estables ante faltantes y desbalance **en este dataset**.

## Lo que no podemos concluir

- Que el modelo generaliza a Colombia u otros sistemas de salud sin nueva validación.
- Que una puntuación alta implica trastorno o justifica intervención automática.
- Que mejorar actividad física **causa** menor uso problemático, salvo diseño causal que este proyecto no tiene.

## Referencias de contexto

- [Anuncio de la competencia](https://childmind.org/blog/child-mind-institute-and-kaggle-launch-competition-to-predict-teen-internet-addiction/)
- [Lecciones de la competencia](https://childmind.org/blog/screen-time-struggles/)
