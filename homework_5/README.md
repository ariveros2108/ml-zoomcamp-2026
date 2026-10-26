# Homework 5 — Deployment

Trabajado sobre el entorno de referencia del curso en
`cohorts/2026/homework/05-deployment` del repositorio
DataTalksClub/machine-learning-zoomcamp.

## Respuestas

| Pregunta | Respuesta |
|---|---|
| Q1 — versión de uv | 0.13.5 (verificación de entorno) |
| Q2 — scikit-learn del entorno bloqueado | 1.7.2 |
| Q3 — probabilidad vía pickle | 0.533 |
| Q4 — probabilidad vía API | 0.770 |
| Q5 — imagen base del Dockerfile | python:3.11.15-slim-bookworm |
| Q6 — probabilidad desde el contenedor | 0.770 |

## Comandos ejecutados

```
uv sync --locked
uv run python smoke_test.py
uv run python q3.py

uv run uvicorn predict:app --host 0.0.0.0 --port 9696
uv run python q6_test.py

docker build -t zoomcamp-model:2026-hw5 .
docker run --rm -p 9696:9696 zoomcamp-model:2026-hw5
uv run python q6_test.py
```

## Verificación del artefacto

`pipeline.bin` → SHA-256
`1646bbdcd38d4f044da6b630c5b332c93a314245a8c21929011c42de51f629f1`
