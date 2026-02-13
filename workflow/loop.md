# Loop

## Loop DSL

```
architect:4[mode=block]
→ reviewer:3[mode=async]
→ coach:*[mode=block]
→ sentinel:*[mode=async,schedule=15m,throttle=3/72h]
```

## Blocking Budget

blocking.max_cycles: UNBOUNDED

(Coach has max=* so at least one blocking phase is non-finite.)

## Evidence

- architect max=4: src/agents/architect/index.ts MAX_CLARIFICATION_ROUNDS = 3; one initial run + up to 3 clarification rounds = 4. mode=block: synchronous API call.
- reviewer max=3: CONFIG.queue.maxAttempts = 3 (src/config/agents.ts), convex/jobs.ts DEFAULT_MAX_ATTEMPTS for job retries. mode=async: review-focus-submission enqueued, worker processes (src/app/api/submissions/submit/route.ts, runFocusSubmissionReview.ts). Per-focus attempt cap and minimumChangePercentage: convex/schema.ts submissionAttemptRules (maxAttempts default 5, minimumChangePercentage 10), convex/focusSubmissions.ts checkResubmissionEligibility.
- coach max=*: No cap on number of coach turns in code; mode=block: synchronous streamed response (src/app/api/agents/coach/route.ts).
- sentinel max=*, schedule=15m, throttle=3/72h: CONFIG.sentinel.cronIntervalMinutes = 15 (src/config/agents.ts). CONFIG.nudge.maxPerWindow = 3, maxPerWindowHours = 72 (src/config/agents.ts). mode=async: send-nudge job type, batch monitoring (src/agents/sentinel/README.md).
