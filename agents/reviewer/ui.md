# UI Contract: reviewer

type: form

## Fields

- id: field.mission_instance_id
  type: text
  required: true
  label: Mission instance ID
  help: Identifies the mission

- id: field.focus_id
  type: text
  required: true
  label: Focus ID
  help: Identifies the deliverable

- id: field.submission_type
  type: enum
  required: true
  label: Submission type
  help: file, url, or text

- id: field.content
  type: text
  required: false
  label: Content
  help: Single URL or legacy content

- id: field.url_payload
  type: url
  required: false
  label: URL(s)
  help: One or more URLs (e.g. repo, demo, docs); max 5 when multi-URL allowed

- id: field.text_payload
  type: textarea
  required: false
  label: Text submission
  help: Plain or markdown; min 50 characters when type is text

- id: field.file_id
  type: file
  required: false
  label: File
  help: Uploaded file reference when type is file

## Bindings

field.mission_instance_id -> cap.mission_instance_id
field.focus_id -> cap.focus_id
field.submission_type -> cap.submission_type
field.content -> cap.content
field.url_payload -> cap.url_payload
field.text_payload -> cap.text_payload
field.file_id -> cap.file_id
