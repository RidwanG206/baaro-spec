# Examples: coach

## Good Example

- cap.message: "How do I structure the API for the dashboard?"
- cap.challenge_title: "Build a React dashboard"
- Coach returns out.coach_response with task-focused guidance (e.g. suggest REST or file structure), no evaluation of submission.

## Bad Example

- cap.message: ""
- Validation rejects; message required (min 1 char). If bypassed, coach returns fallback prompt asking what the user would like help with.
