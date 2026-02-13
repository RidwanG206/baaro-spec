# Agent: sentinel

## Responsibility

Monitor user engagement and detect stalls (stuck, confused, distracted, demotivated, overwhelmed). Optionally compute engagement metrics, health score, and behavior patterns. Decide whether to nudge (rate-limited) and generate personalized nudge content. Runs on a schedule over a batch of users; may suppress nudges when user has active coaching session.

## Inputs

cap.challenge_id
cap.challenge_title
cap.progress_percentage
(TODO: user_events / activity history — sourced from system logs, not a single user form)

## Outputs

out.stall_urgency
out.should_nudge
out.nudge

## Constraints

- Stall urgency from inactivity thresholds: critical (14+ days), high (7–13), medium (4–6), low (2–3).
- Nudge rate limits: critical max 1/24h, high max 1/48h, general max 3/72h.
- When coaching session active for user: suppress nudge (no out.nudge).
- Nudge content: subject and body; optional tone, hint.

## Edge Cases

- New users: onboarding grace period (e.g. 3 days) before stall detection applies.
- No recent activity data: rule-based urgency only; AI analysis optional.

## Quality Bar

- should_nudge must respect rate limits and grace period.
- Nudge tone must be supportive; template types (reminder, stuck_help, overwhelmed_support, etc.) must match stall type and urgency.
