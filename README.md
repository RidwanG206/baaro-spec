# LocalFirst Build: Baaro Mission & Review Workflow

## What this is

A portable, MD-only agent workflow specification bundle extracted from the Baaro product. It describes workflow order, agent responsibilities, UI contracts (inputs collected and outputs shown), and loop semantics (iteration caps, retries, schedules, throttles) without backend, infrastructure, or framework details.

## What this is not

- Not an implementation: no code, no database, no auth, no deployment.
- Not a runnable app: the bundle is a specification for import into other systems or for validation and documentation.

## Agents table

| Agent ID   | Responsibility summary |
|-----------|-------------------------|
| architect | Turn user goal (+ optional background and clarification answers) into a personalized challenge or clarification questions. |
| reviewer  | Evaluate focus submissions (file/URL/text) against requirements; produce verdict, score, feedback; handle duplicates and human-review routing. |
| coach     | Provide task-focused guidance for the current mission/deliverable from user message and conversation history. |
| sentinel  | Monitor engagement, detect stalls, apply nudge rate limits, and optionally generate nudges on a schedule. |

## How to import

- Consume `workflow/schema.md` for canonical cap.* and out.* identifiers.
- Consume `workflow/workflow.md` for execution order and completion condition.
- Consume `workflow/loop.md` for loop DSL, blocking budget, and evidence.
- For each agent, use `agents/<agent-id>/agent.md`, `ui.md`, and `examples.md` for behavior and UI contracts.
- Apply `policies/security.md` and `policies/data-handling.md` as operational constraints.

## Assumptions & TODOs

- Sentinel inputs (activity/nudge history) are system-derived; no single user form. Documented as TODO in sentinel agent.
- Completion is defined as all focuses passed; archive or abandon flows are not modeled as alternate completion.
- Loop DSL throttle and schedule values are product-evidenced; implementers may override for different deployment constraints.

## How to run

This bundle is not executed. To validate: ensure all required files exist, all cap.*/out.* references resolve in schema, execution order matches agent folder names, loop DSL phases match execution order, and bindings in UI contracts reference valid cap.*.
# baaro-spec
