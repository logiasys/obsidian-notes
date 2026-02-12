# Process Inbox

Triage items in `0-Inbox/`.

## Before processing

1. Load glossary: `4-Resources/system/action-glossary.md`
2. For each note, read `action_type` from frontmatter
3. If missing/invalid, set route to `normal`

## For Each Item

1. **Resolve route by action_type**:

   | action_type | Primary Route |
   |---|---|
   | `normal` | Standard triage (task, idea, reference, concept, unclear) |
   | `task` | Convert to actionable task in project `tasks.md` (or keep in inbox if missing context) |
   | `project-seed` | Create/update note in `2-Project-Ideas/` using `project-idea` template |
   | `resource` | Move to `4-Resources/` as resource note with tags |
   | `decision` | Route to project/area `decisions.md` |
   | `incubate` | Add to `2-Project-Ideas/` with paused follow-up (`next_review`) |

2. **If route is `normal`, analyze content type**:

   | Type | Indicators | Action |
   |------|------------|--------|
   | Task | Action words, deadlines | → Project's `tasks.md` |
   | Idea | "What if", concepts | → Daily note Ideas with `#idea` |
   | Reference | Links, facts, quotes | → `4-Resources/` as note |
   | Project concept | Multi-step, has deliverable | → `2-Project-Ideas/` |
   | Unclear | Can't categorize | → Add `#needs-review`, move to `4-Resources/` |

3. **Route the item:**
   - Move or copy content to appropriate location
   - Add proper links and tags
   - Delete the original inbox item

4. **Update daily note:**
   - Add new notes to "🔗 Links Created" section

## After Processing All Items

Report what was processed:
```
Processed X items from inbox:
- [item name] → [destination] (route: [action_type])
- [item name] → [destination] (route: [action_type])
```

**Goal: Inbox zero.**
