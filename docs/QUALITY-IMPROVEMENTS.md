---
type: resource
created: "2026-02-12"
updated: "2026-02-12"
tags: [quality, operations, governance]
---

# Sugerencias de mejora (calidad y administración)

Este documento propone mejoras para escalar el vault con mejor trazabilidad y gobernanza.

## 1) Gobernanza mínima de metadatos

- Definir un checklist para frontmatter obligatorio por tipo de nota.
- Añadir revisión semanal de campos faltantes (`type`, `created`, `status`).
- Estandarizar fechas ISO (`YYYY-MM-DD`) en todo el vault.

## 2) Métricas simples de salud del sistema

Crear un dashboard Dataview para medir:
- Inbox pendiente > 7 días.
- Ideas de proyecto sin revisión (`next_review` vencida).
- Proyectos activos sin actualización semanal.
- Recursos sin `updated` en 90+ días.

## 3) Portfolio de proyectos (priorización)

Sobre `2-Project-Ideas/`, sumar una matriz 2x2:
- impacto (1-5)
- esfuerzo (1-5)

Con eso, calcular score base: `impacto*2 - esfuerzo`.

## 4) Plantilla de decisión transversal

La plantilla `decision` hoy es por proyecto. Conviene añadir:
- opción A/B/C
- criterio de decisión
- fecha de revisión de la decisión

Esto reduce re-trabajo y discusiones repetidas.

## 5) Ritual de cierre mensual

Además del weekly review, definir monthly review para:
- limpiar `2-Project-Ideas/` (descartar/incubar)
- archivar recursos obsoletos
- seleccionar máximo 1–3 apuestas del mes

## 6) Automatización incremental

Extender la automatización actual con una tarea semanal:
- “ideas-review” que liste ideas vencidas (`next_review < today`)
- sugerencia de acción: incubar, promover o descartar
