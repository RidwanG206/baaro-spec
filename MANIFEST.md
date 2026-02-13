# Manifest

## Spec Identity

name: Baaro Mission & Review Workflow
bundle_version: 1

## File Index

README.md
MANIFEST.md
workflow/schema.md
workflow/workflow.md
workflow/loop.md
agents/architect/agent.md
agents/architect/ui.md
agents/architect/examples.md
agents/reviewer/agent.md
agents/reviewer/ui.md
agents/reviewer/examples.md
agents/coach/agent.md
agents/coach/ui.md
agents/coach/examples.md
agents/sentinel/agent.md
agents/sentinel/ui.md
agents/sentinel/examples.md
policies/security.md
policies/data-handling.md

## Source Provenance

- localfirst-build/README.md — NEW
- localfirst-build/MANIFEST.md — NEW
- localfirst-build/workflow/schema.md — derived from convex/schema.ts, src/agents/*, src/lib/validations/submissions.ts
- localfirst-build/workflow/workflow.md — derived from src/app/api/agents/*, src/services/review/runFocusSubmissionReview.ts, mission/focus flow
- localfirst-build/workflow/loop.md — derived from src/config/agents.ts, convex/jobs.ts, convex/focusSubmissions.ts, src/agents/architect/index.ts, src/agents/sentinel/README.md
- localfirst-build/agents/architect/agent.md — derived from src/agents/architect/index.ts, src/agents/shared/validation.ts
- localfirst-build/agents/architect/ui.md — derived from src/components/dashboard/missions/create-mission-modal.tsx
- localfirst-build/agents/architect/examples.md — NEW (behavior from agent.md)
- localfirst-build/agents/reviewer/agent.md — derived from src/agents/reviewer/index.ts, src/services/review/runFocusSubmissionReview.ts
- localfirst-build/agents/reviewer/ui.md — derived from src/components/dashboard/focus/focus-right-panel.tsx, src/lib/validations/submissions.ts
- localfirst-build/agents/reviewer/examples.md — NEW (behavior from agent.md)
- localfirst-build/agents/coach/agent.md — derived from src/agents/coach/index.ts, src/app/api/agents/coach/route.ts
- localfirst-build/agents/coach/ui.md — derived from src/components/dashboard/ai/ai-chat-panel.tsx, CoachAPIRequestSchema
- localfirst-build/agents/coach/examples.md — NEW (behavior from agent.md)
- localfirst-build/agents/sentinel/agent.md — derived from src/agents/sentinel/README.md, src/config/agents.ts
- localfirst-build/agents/sentinel/ui.md — NEW (no user form; type text)
- localfirst-build/agents/sentinel/examples.md — NEW (behavior from agent.md)
- localfirst-build/policies/security.md — NEW (spec-mandated)
- localfirst-build/policies/data-handling.md — NEW (spec-mandated)

## Validator Checklist

- [x] All required files exist under localfirst-build/
- [x] Only .md files; no hidden/dotfiles
- [x] Required headings present in schema, workflow, loop, each agent (agent.md, ui.md, examples.md), policies, README, MANIFEST
- [x] All cap.* referenced in agents and UI bindings exist in schema.md
- [x] All out.* referenced in agents and workflow completion exist in schema.md
- [x] No unused schema identifiers (all listed cap/out are referenced)
- [x] Form bindings valid (field.* -> cap.*)
- [x] Execution order (architect, reviewer, coach, sentinel) matches agent folder names
- [x] Completion references valid out.* (out.mission_completed, out.review_status / out.verdict)
- [x] No invented behaviors without evidence; TODOs marked where evidence missing (sentinel inputs)
- [x] workflow/loop.md exists
- [x] Loop DSL phase list matches Execution Order (same agent-ids, same order, exactly once each)
- [x] Blocking Budget: UNBOUNDED due to coach max=*
- [x] Loop Evidence section references file/section or TODO per phase
