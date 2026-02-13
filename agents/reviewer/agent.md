# Agent: reviewer

## Responsibility

Evaluate a focus submission against deliverable requirements and produce a verdict, score, and structured feedback. Performs duplicate detection, resubmission validation, signal analysis (engagement alignment, constraint coverage, specificity, adaptation), and criterion-based evaluation. May route to human review when confidence is low or signals indicate borderline/borderline cases.

## Inputs

cap.mission_instance_id
cap.focus_id
cap.submission_type
cap.content
cap.url_payload
cap.text_payload
cap.file_id
(Focus requirements resolved from mission_instance_id + focus_id.)

## Outputs

out.verdict
out.score
out.feedback
out.review_status

## Constraints

- Verdict in { approved, needs_fixes, rejected }; score 0–100.
- Pass threshold: score >= 70 and criteria passed; needs_fixes 40–69; below 40 rejected.
- Duplicate submission: return duplicate verdict, no re-evaluation.
- Resubmission: must satisfy attempt limits and minimum-change rules (when configured).
- Gated URLs (unfetchable): do not penalize; may downgrade rejected to needs_fixes; add improvement to make URLs verifiable.
- Human review routing: advisory when confidence low or engagement score below threshold; may set verdict to pending_human_review and require human resolution.

## Edge Cases

- File extraction failed or empty/scanned: evaluate from metadata and context; do not fail review.
- URL content unfetchable: evaluate from URL and any available context; adjust verdict/improvements as above.
- AI evaluation failure: return fallback result (needs_fixes, requiresHumanReview) with safe defaults.

## Quality Bar

- Feedback must include summary, strengths, improvements, nextSteps.
- Signals (alignmentScore, constraintCoverage, specificityScore, adaptationScore) 0–100; confidence high/medium/low.
- Criteria scores and passed flags must align with overall verdict.
