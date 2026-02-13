# Data Handling Policy

- PII guidance: User-provided content (cap.goal, cap.background, cap.message, submission content) may contain PII. Implementers should treat captures as sensitive and apply access control and retention consistent with local policy.
- Retention expectations: This spec does not define retention; implementers should define retention for stored captures and outputs (e.g. reviews, nudges) per jurisdiction and product policy.
- Redaction guidance: When logging or exporting workflow data, redact or pseudonymize PII in cap.* and in free-text out.feedback, out.coach_response, out.nudge.
