# AI Codebase Explorer v3.4

AI Codebase Explorer is a FastAPI app for analyzing uploaded repository zip files or public GitHub repositories. It inspects structure, entry points, stack signals, dependency edges, onboarding guidance, architecture notes, health score, anti-patterns, refactor suggestions, dependency risk notes, and exports Mermaid and PlantUML diagrams.


## Tech stack

- FastAPI
- Jinja2 templates
- Vanilla JavaScript
- Requests for GitHub zip downloads

## Run with Docker

```bash
docker build --no-cache -t ai-codebase-explorer-v34 .
docker run -p 8011:8000 ai-codebase-explorer-v34
```

Open: `http://localhost:8011`

## Run locally with Python

```bash
python -m venv .venv
source .venv/Scripts/activate
pip install -r requirements.txt
uvicorn app.main:app --reload
```

Open: `http://localhost:8000`

## Good test repositories

These have been good targets for testing the current GitHub mode:

- `https://github.com/lightpanda-io/browser`
- `https://github.com/obra/superpowers`
- `https://github.com/abhigyanpatwari/GitNexus`

Larger public repos may still take longer because GitHub mode depends on live archive downloads.

## Notes

- GitHub mode works only for public repositories
- very large repositories may take longer to download and analyze
- zip upload mode remains the most deterministic path for testing
