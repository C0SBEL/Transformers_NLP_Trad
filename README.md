# Traducción automática español → inglés con Transformers

Comparación de modelos Transformer preentrenados para traducción automática español-inglés: baseline, búsqueda de hiperparámetros, fine-tuning, interpretabilidad con mapas de atención y evaluación con métricas clásicas y con un LLM como juez.

Práctica del Máster en Data Science (La Salle, Universitat Ramon Llull).

## Contenido

Todo el trabajo está en [`Deliverable2.ipynb`](Deliverable2.ipynb):

1. **Exploración de datos**: corpus [FLORES](https://huggingface.co/datasets/facebook/flores) (`spa_Latn` → `eng_Latn`), distribución de longitudes y estadísticas del corpus.
2. **Implementación y entrenamiento**: MarianMT y T5-small, tokenización, inferencia baseline, búsqueda sistemática de hiperparámetros y fine-tuning de ambos modelos.
3. **Interpretabilidad**: visualización de attention maps y análisis de errores y sesgos.
4. **Evaluación avanzada**: BLEU-4 y METEOR, y evaluación cualitativa con un LLM como juez (Claude Haiku).

## Stack

Python · PyTorch · Hugging Face Transformers / Datasets / Evaluate · pandas · Matplotlib · Anthropic API

## Resultados

Baseline sin fine-tuning:

| Modelo    | BLEU-4 | METEOR |
|-----------|--------|--------|
| MarianMT  | 29.39  | 0.661  |
| T5-small  | 2.03   | 0.095  |

Los resultados tras el fine-tuning y la evaluación con LLM como juez se detallan en el notebook.

## Cómo ejecutarlo

1. Instala las dependencias:
   ```bash
   pip install torch transformers datasets evaluate sentencepiece pandas matplotlib anthropic jupyter
   ```
2. (Opcional, solo para la sección de LLM como juez) define tu clave de API de Anthropic como variable de entorno:
   ```bash
   export ANTHROPIC_API_KEY=...      # Linux / macOS
   $env:ANTHROPIC_API_KEY = "..."    # Windows PowerShell
   ```
3. Abre y ejecuta el notebook:
   ```bash
   jupyter notebook Deliverable2.ipynb
   ```

## Licencia

[MIT](LICENSE)
