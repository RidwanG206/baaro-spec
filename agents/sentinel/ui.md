# UI Contract: sentinel

type: text

No user-facing form. Sentinel is triggered by a scheduled job; inputs (activity, nudge history) are derived from system state. Outputs (nudge, stall_urgency, should_nudge) drive notifications or in-app surfaces.
