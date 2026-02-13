# UI Contract: coach

type: form

## Fields

- id: field.message
  type: textarea
  required: true
  label: Message
  help: Your question or request (1–5000 characters)

- id: field.conversation_history
  type: text
  required: false
  label: Conversation history
  help: Client-maintained history of prior messages (bound from state)

## Bindings

field.message -> cap.message
field.conversation_history -> cap.conversation_history
