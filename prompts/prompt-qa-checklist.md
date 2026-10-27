# Prompt Engineering QA Checklist

Use this before shipping a prompt or changing a production agent.

## Specification
- [ ] Role, intended users, scope, and success criteria are explicit.
- [ ] Mandatory rules are separated from tone/style guidance.
- [ ] Tool names, schemas, required fields, and failure behavior are documented.
- [ ] The prompt defines what the agent must do when information is missing.

## Conversation behavior
- [ ] One question at a time where appropriate.
- [ ] Interruption and correction behavior is defined.
- [ ] Language detection and language switching are tested.
- [ ] Duplicate questions and repeated confirmations are minimized.
- [ ] Opening, recovery, escalation, and closing paths are defined.

## Reliability and safety
- [ ] No fabricated facts, tool results, availability, or completion claims.
- [ ] Prompt injection and conflicting instructions are tested.
- [ ] Sensitive information collection is minimized.
- [ ] Human handoff and tool failure fallbacks are verified.
- [ ] Consequential actions require the appropriate confirmation.

## Test set
Run each test at least once and record expected versus actual output:
1. Typical request with complete information.
2. Typical request with one required detail missing.
3. Ambiguous or contradictory request.
4. User interruption / correction.
5. Unsupported question.
6. Tool timeout or malformed result.
7. Prompt injection attempt.
8. Language switch mid-conversation.
9. Customer refusal or request for a human.
10. Closing after successful resolution.

## Metrics
Choose metrics that match the use case, such as task completion rate, factual/tool correctness, required-field capture, escalation precision, latency, and language consistency. Define the dataset, sample size, scoring rules, and limitations before publishing any percentage claim.