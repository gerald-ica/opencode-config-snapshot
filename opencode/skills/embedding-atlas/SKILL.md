---
name: embedding-atlas
description: Use when the task involves visualizing, exploring, or integrating high-dimensional embeddings with Apple's embedding-atlas tools and workflows.
---

# Embedding Atlas

Use when the task involves visualizing, exploring, or integrating high-dimensional embeddings with Apple's `embedding-atlas`.

Repo path: `/Users/wendyly/.local/share/agent-skills/vendor/embedding-atlas`

What to do:
- Use the Python package when the user wants a CLI or notebook workflow.
- Use the npm workspace when the user wants web integration, React/Svelte components, or viewer development.
- Prefer parquet-backed datasets for large interactive visualization runs.
- For repo work, start from the root workspace scripts in `package.json`.

Useful commands:
```bash
cd /Users/wendyly/.local/share/agent-skills/vendor/embedding-atlas
npm install
npm run build
npm run test
```

Python usage:
```bash
pip install embedding-atlas
embedding-atlas path/to/dataset.parquet
```

Notebook usage:
```python
from embedding_atlas.widget import EmbeddingAtlasWidget
EmbeddingAtlasWidget(df)
```
