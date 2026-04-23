# Virtual environments

A **virtual environment** keeps a project's Python packages separate
from the rest of your system. Create one per project:

```bash
python3 -m venv .venv
source .venv/bin/activate
```

When the environment is active, `pip install` puts packages inside it,
not globally.
