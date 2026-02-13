# Baaro Mission & Review Workflow

## Description

User defines a learning goal; architect produces a calibration challenge or asks for clarification. User creates a mission from a template (or architect output) and works through focuses. For each focus, user submits content (file, URL, or text); reviewer evaluates and returns verdict and feedback. Coach can be invoked anytime for task guidance. Sentinel runs on a schedule, detects stalls, and may send rate-limited nudges. Mission is complete when all focuses have passed review.

## Execution Order

1. architect
2. reviewer
3. coach
4. sentinel

## Completion

Completion holds when out.mission_completed is true: all focuses in the mission have at least one submission with out.review_status corresponding to passed (out.verdict approved). Alternatively the user may archive the mission without completing all focuses; then completion is not asserted.
