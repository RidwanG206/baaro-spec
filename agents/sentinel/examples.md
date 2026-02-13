# Examples: sentinel

## Good Example

- User inactive 8 days; no nudge in last 48h. Sentinel sets out.stall_urgency high, out.should_nudge true, out.nudge with subject and body; rate limit allows one high nudge per 48h.

## Bad Example

- User inactive 8 days but already received high nudge 24h ago. out.should_nudge false; out.nudge not sent (throttle 1/48h for high).
