# Agent: coach

## Responsibility

Provide task-focused guidance for the current mission/deliverable. Consumes user message and conversation history, plus challenge context (title, description, progress, deliverables), and returns a concise response that clarifies the task, unblocks the user, or suggests next steps. Does not perform submission evaluation.

## Inputs

cap.message
cap.conversation_history
cap.challenge_id
cap.challenge_title
cap.challenge_description
cap.progress_percentage
cap.deliverables
cap.current_deliverable_index

## Outputs

out.coach_response

## Constraints

- Message length bounded (min 1, max 5000 chars).
- Conversation history may be summarized (sliding window: last N messages verbatim, older summarized) to stay within context limits.
- Response must stay on-task for the current challenge/deliverable.

## Edge Cases

- Empty or missing API key: return fallback message directing user to ask for help.
- Empty model response: return prompt asking what the user would like help with.
- Long history: preserve key context (errors, code snippets, decisions) in summary.

## Quality Bar

- Response must be relevant to challenge title and current deliverable.
- Tone must be supportive and task-clarifying, not evaluative.
