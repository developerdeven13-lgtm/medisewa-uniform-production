<!-- BEGIN:nextjs-agent-rules -->
# This is NOT the Next.js you know

This version has breaking changes — APIs, conventions, and file structure may all differ from your training data. Read the relevant guide in `node_modules/next/dist/docs/` before writing any code. Heed deprecation notices.
<!-- END:nextjs-agent-rules -->

## Read Before Anything Else

Read in this exact order before any implementation:

1. context/01-project-overview.md
2. context/02-business-workflow.md
3. context/03-architecture.md
4. context/04-build-plan.md
5. context/05-progress-tracker.md
6. context/06-decision-log.md

Then read:

standards/code-standards.md
standards/api-standards.md
standards/database-standards.md
standards/ui-rules.md
standards/ui-tokens.md
standards/naming-conventions.md

Relevant domain files:

customer-management.md
order-management.md
production-management.md
tailoring-shop-management.md
inventory-management.md
acknowledge-management.md
issue-management.md
quality-control.md
delivery-management.md
user-role-management.md
reporting.md

## Rules That Never Change

- Never use hardcoded hex values or raw Tailwind color classes
- Update `progress-tracker.md` and `ui-registry.md` after every feature
- Before any third party library — load its installed skill first,
  then read `context/library-docs.md` for project-specific rules
- If the same problem persists after one corrective prompt —
  stop immediately and run /recover

  ## Available Skills

- `/architect` — before any complex feature. Think before building.
- `/imprint` — after any new UI component. Capture patterns.
- `/review` — before demo or when something feels off.
- `/recover` — when something breaks after one failed correction.
- `/remember save` — when a feature spans multiple sessions.
- `/remember restore` — when returning after a multi-session feature.