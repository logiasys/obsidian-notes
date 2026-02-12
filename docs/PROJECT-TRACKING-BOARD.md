# Project Tracking Board (Agile Boards)

Sistema de seguimiento operativo por proyecto con tableros ágiles en Obsidian.

> **Plugin objetivo (obligatorio):** `obsidian-agile-task-notes` (repo: `BoxThatBeat/obsidian-agile-task-notes`).  
> Si no está instalado, el agente debe instalarlo antes de crear/operar tableros.

---

## 1) Instalación del plugin

### Método A — Community plugins (preferido)

1. Obsidian → **Settings** → **Community plugins**
2. Desactivar *Restricted mode* (si aplica)
3. **Browse** → buscar `Agile Task Notes` / `obsidian-agile-task-notes`
4. Instalar + **Enable**

### Método B — Instalación desde GitHub (si no aparece en Community)

1. Instalar plugin **BRAT** (Beta Reviewers Auto-update Tester)
2. Obsidian → BRAT → **Add beta plugin**
3. Pegar URL del repositorio:  
   `https://github.com/BoxThatBeat/obsidian-agile-task-notes`
4. Habilitar el plugin instalado

### Validación rápida

- Crear una nota de prueba `scratch-agile-board.md`
- Ejecutar el comando del plugin para crear board/tareas ágiles
- Confirmar que el board renderiza y que los estados se pueden mover

---

## 2) Estructura estándar por proyecto

Cada proyecto activo en `2-Projects/<project>/` debe tener:

- `README.md` → estado global, riesgos y foco
- `tasks.md` → lista textual maestra
- `board.md` → tablero operativo diario
- `roadmap.md` → fases, hitos, dependencias

---

## 3) Opciones de Agile Boards (presets recomendados)

Usar estas opciones según contexto. Todas se crean en `board.md` o en notas dedicadas (`board-*.md`) dentro del proyecto.

### Opción A — Delivery Flow (Kanban continuo)

Columnas:
1. Inbox
2. Backlog
3. Ready
4. In Progress
5. Review
6. Blocked
7. Done

Cuándo usar: mantenimiento continuo sin sprint fijo.

### Opción B — Sprint Board (Scrum semanal/quincenal)

Columnas:
1. Sprint Backlog
2. Doing
3. QA/Review
4. Done
5. Carry-over

Cuándo usar: trabajo por lotes y compromiso temporal.

### Opción C — Prioridad/Criticidad

Swimlanes o etiquetas por severidad:
- `#critical`
- `#high`
- `#medium`
- `#low`

Cuándo usar: entornos con incidencias, bloqueos o deadlines duros.

### Opción D — Tipo de trabajo

Etiquetas:
- `#feature`
- `#bug`
- `#research`
- `#ops`
- `#admin`

Cuándo usar: separar capacidad por tipo de ejecución.

### Opción E — Roadmap Board (hitos)

Columnas:
1. Planned
2. Next
3. Active
4. At Risk
5. Delivered

Cuándo usar: visibilidad ejecutiva de progreso por fase.

> Recomendación práctica: combinar **A + C + D** para operación diaria, y **E** para revisión semanal/mensual.

---

## 4) Flujo Inbox → Board → Roadmap

Cuando se procese `0-Inbox/`:

1. Detectar `project_ref`
2. Convertir la captura a tarea accionable (verbo + resultado)
3. Asignar tipo (`#feature/#bug/#research/#ops`)
4. Asignar prioridad (`#critical/#high/#medium/#low`)
5. Insertar en board:
   - `Inbox` si falta refinamiento
   - `Backlog`/`Ready` si está lista para ejecución
6. Reflejar también en `tasks.md`
7. Si afecta hitos, actualizar `roadmap.md`

---

## 5) Política de revisión y escalado

En cada **weekly review**:

1. Sincronizar `tasks.md`, `board.md`, `roadmap.md`
2. Verificar tarjetas en `Blocked`
3. Verificar tarjetas `#critical`
4. Escalar a `README.md` todo `#critical` bloqueado por 7+ días
5. Re-priorizar backlog de la semana siguiente

---

## 6) Plantillas de este vault

- `[[_templates/project-kanban]]` → base de board operativo
- `[[_templates/project-roadmap]]` → base de roadmap

Si usas una variante (Sprint / Roadmap Board), duplica la plantilla de board y ajusta columnas según la opción elegida.
