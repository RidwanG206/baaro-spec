# Examples: architect

## Good Example

- cap.goal: "I want to become a front-end developer and ship a small SaaS in 6 months."
- cap.background: "I have 2 years of JavaScript, no React yet."
- Architect returns out.needs_clarification false, out.challenge with title, deliverables (e.g. "Build a React dashboard"), evaluation criteria, difficultyTier.

## Bad Example

- cap.goal: ""
- Architect cannot produce challenge without goal; should return out.needs_clarification true and out.clarification_questions, or reject input.
