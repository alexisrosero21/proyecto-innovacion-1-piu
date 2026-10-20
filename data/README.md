# Datos

Los archivos crudos **no se versionan** en GitHub.

1. Crear cuenta en [Kaggle](https://www.kaggle.com/).
2. Aceptar las reglas de [Child Mind Institute — Problematic Internet Use](https://www.kaggle.com/competitions/child-mind-institute-problematic-internet-use).
3. Descargar el dataset de la competencia.
4. Colocar los archivos en:

```text
data/raw/          # original, inmutable
data/processed/    # salidas de limpieza (tampoco se suben si pesan o contienen microdatos)
```

Carpetas `raw/` y `processed/` están en `.gitignore`.
