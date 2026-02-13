# Agent: architect

## Responsibility

Analyze user learning goals and produce a personalized calibration challenge (mission template) or request clarification. Transforms goal and optional background into structured challenge with deliverables and evaluation criteria. May request clarification up to a bounded number of rounds; after that may generate challenge with stated assumptions.

## Inputs

cap.goal
cap.background
cap.clarification_answers

## Outputs

out.challenge
out.clarification_questions
out.analysis
out.needs_clarification

## Constraints

- Goal text length bounded (min 1, max 10000 chars).
- Clarification rounds capped (max 3); after cap, challenge may be generated with assumptions.
- Output challenge must include title, description, deliverables (name, format, description, requirements), evaluation criteria (name, weight, description, passingThreshold), difficultyTier, optional estimatedHours.

## Edge Cases

- Empty or very short goal: treat as needs_clarification or use defaults.
- After max clarification rounds without full clarity: generate challenge with explicit assumptions list.
- Background optional; when absent, analysis uses only goal.

## Quality Bar

- Challenge deliverables must align with analyzed skill gaps and target identity.
- Clarification questions must target unclear areas (e.g. target_role, timeline, current_skills).
- Assumptions (when forced) must be enumerated and non-opaque.
