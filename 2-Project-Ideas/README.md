---
type: resource
created: "2026-02-12"
updated: "2026-02-12"
tags: [ideas, portfolio, projects]
---

# Project Ideas Pipeline

Espacio para seguimiento de **ideas de proyectos** antes de crear un proyecto en `2-Projects/`.

## Estados sugeridos

- `seed` → idea recién capturada
- `exploring` → validando problema/valor
- `incubating` → pausada con fecha de revisión
- `ready` → lista para promover a proyecto
- `discarded` → no se ejecutará (quedarse con aprendizaje)

## Criterios de promoción a proyecto

Promover a `2-Projects/` cuando se cumplan al menos 3:
- problema claramente definido
- entregable explícito
- siguiente acción concreta
- owner definido
- viabilidad inicial validada

## Tablero de seguimiento (Dataview)

```dataview
TABLE status AS "Estado", score AS "Score", owner AS "Owner", next_review AS "Próxima revisión"
FROM "2-Project-Ideas"
WHERE type = "project-idea"
SORT score DESC, next_review ASC
```

## Flujo recomendado

1. Capturar idea en Inbox con `action_type: project-seed`.
2. Inbox processing crea/mueve una nota aquí usando plantilla `project-idea`.
3. Revisar semanalmente y actualizar `score`, `status`, `next_review`.
4. Cuando pase a `ready`, crear carpeta en `2-Projects/` y enlazar origen.
