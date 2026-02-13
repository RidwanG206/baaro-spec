# UI Contract: architect

type: form

## Fields

- id: field.goal
  type: textarea
  required: true
  label: Goal
  help: What you want to achieve or learn

- id: field.background
  type: textarea
  required: false
  label: Background
  help: Optional context (experience, constraints)

- id: field.clarification_answers
  type: text
  required: false
  label: Clarification answers
  help: Shown when architect returns clarification questions; keyed by question

## Bindings

field.goal -> cap.goal
field.background -> cap.background
field.clarification_answers -> cap.clarification_answers
