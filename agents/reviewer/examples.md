# Examples: reviewer

## Good Example

- cap.submission_type: url, cap.content or cap.url_payload with valid repo URL; focus requires "Live GitHub repo with README."
- Reviewer returns out.verdict approved or needs_fixes, out.score 0–100, out.feedback with summary, strengths, improvements, nextSteps; out.review_status passed or failed.

## Bad Example

- cap.content identical to previous submission (duplicate).
- Reviewer returns out.verdict duplicate, out.score 0, out.feedback asking for meaningful changes before resubmit.
