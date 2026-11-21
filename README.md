# 🎬 Sistemas recomendadores de películas

Checkpoint 6 · Inteligencia Artificial. Todo el trabajo está en **[`sistemas_recomendadores.ipynb`](sistemas_recomendadores.ipynb)**, ya ejecutado con sus resultados.

| # | Recomendador | Técnica |
|---|---|---|
| 1 | Simple (clon del Top 250 de IMDB) | Calificación ponderada `WR = v/(v+m)·R + m/(v+m)·C` |
| 2 | Basado en contenido: sinopsis | TF-IDF + similitud coseno |
| 3 | Basado en contenido: metadatos | Director, top 3 actores, géneros, keywords + CountVectorizer |
| 4 | Mejoras | Director con peso x3 y filtro híbrido de popularidad |

**Mejora técnica:** la lección calcula una matriz de similitud de 45,466 × 45,466 (unos 16 GB de RAM), que truena en la mayoría de las laptops. Aquí se calcula solo la fila de la película consultada: el resultado es idéntico y usa menos de 1 MB.

**Sobre `credits.csv`:** el notebook está ejecutado sin ese archivo, así que la sección 4 no tiene actores ni director. En su lugar usa la saga (`belongs_to_collection`) y las productoras, que vienen en `movies_metadata.csv`. Si colocas `credits.csv` en `data/` y lo vuelves a ejecutar, corre exactamente el recomendador de la lección, con director y elenco.

## Cómo ejecutarlo

1. Descarga *The Movies Dataset* ([Kaggle](https://www.kaggle.com/datasets/rounakbanik/the-movies-dataset)) y copia `movies_metadata.csv`, `credits.csv` y `keywords.csv` en la carpeta `data/`. No vienen en el repo porque `credits.csv` pesa unos 190 MB.
2. Instala las dependencias y abre el notebook:

```bash
python3 -m venv venv
source venv/bin/activate        # Windows: venv\Scripts\activate
pip install -r requirements.txt
jupyter notebook sistemas_recomendadores.ipynb
```
