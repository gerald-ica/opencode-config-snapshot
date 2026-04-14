---
name: tribev2-research
description: Use when the task involves Meta's tribev2 multimodal brain-encoding model, including inference, training setup, experiment wiring, or neuroscience research workflows.
---

# TRIBE v2 Research

Use when the task involves Meta's `tribev2` multimodal brain-encoding model, including inference, training setup, experiment wiring, or adapting its pipelines for neuroscience research.

Repo path: `/Users/wendyly/.local/share/agent-skills/vendor/tribev2`

What to do:
- Treat this as a Python 3.11+ package with heavy ML dependencies.
- Prefer inference-only paths unless the user explicitly asks for training.
- Use `TribeModel.from_pretrained("facebook/tribev2")` for the quickest entry point.
- For text or audio input, rely on `get_events_dataframe(...)` rather than hand-rolling preprocessing first.

Useful commands:
```bash
cd /Users/wendyly/.local/share/agent-skills/vendor/tribev2
uv sync
uv run python -c 'from tribev2 import TribeModel; print(\"ok\")'
```

Minimal example:
```python
from tribev2 import TribeModel

model = TribeModel.from_pretrained("facebook/tribev2", cache_folder="./cache")
df = model.get_events_dataframe(video_path="path/to/video.mp4")
preds, segments = model.predict(events=df)
```

Guardrails:
- Training and plotting extras are materially heavier than base inference.
- Be explicit about CPU/GPU constraints before promising end-to-end training runs.
