---
type: resource
created: "2026-02-12"
updated: "2026-02-12"
tags: [workflow, inbox, glossary, operations]
---

# Glosario de Acciones para Inbox

Define los tipos de procesamiento disponibles para notas en `0-Inbox/`.
Cada nota puede declarar `action_type` en frontmatter.

## Reglas generales

1. Si `action_type` está vacío o no coincide con una acción registrada, usar `normal`.
2. Al procesar, registrar en la nota diaria qué ruta se aplicó.
3. Evitar acciones ambiguas: una nota debe tener una intención principal.
4. Si `action_type = board-update`, se debe identificar `project_ref` y actualizar el Kanban del proyecto.

## Acciones disponibles

| action_type | Cuándo usar | Destino principal | Proceso |
|---|---|---|---|
| `normal` | Captura general sin instrucción especial | Según triage estándar | Clasificar como tarea, idea, referencia o proyecto. |
| `task` | Acción ejecutable concreta | `tasks.md` del proyecto o `0-Inbox/` si falta contexto | Convertir a checkbox con fecha/owner si existe. |
| `project-seed` | Idea de nuevo proyecto todavía sin ejecutar | `2-Project-Ideas/` usando plantilla `project-idea` | Crear/actualizar ficha de idea y asignar `next_review`. |
| `resource` | Material de consulta | `4-Resources/` | Convertir en nota de recurso con tags y enlaces. |
| `decision` | Requiere elección explícita | `decisions.md` de proyecto o área | Registrar opciones, decisión y criterio. |
| `incubate` | Interesante, sin prioridad actual | `2-Project-Ideas/` con estado `incubating` | Guardar con próxima revisión (7-30 días). |
| `board-update` | Actividad de proyecto que debe impactar tablero | `board.md` + `tasks.md` del proyecto | Refinar, priorizar y mover a `Inbox` o `Backlog` del Kanban por proyecto. |

## Ejemplo de frontmatter para inbox

```yaml
---
type: inbox
created: "2026-02-12 09:15"
action_type: "project-seed"
status: "captured"
---
```

## Vista sugerida (Dataview)

```dataview
TABLE action_type AS "Acción", status AS "Estado", created AS "Creado"
FROM "0-Inbox"
WHERE type = "inbox"
SORT created DESC
```
