# Case Study: Designing a Reliable Voice-Agent Prompt System

## Problem
Voice agents must do more than answer a question. They need to follow a conversation goal, handle interruptions, stay within a verified knowledge scope, call tools correctly, and recover when audio or downstream systems fail.

## Design
The reference architecture separates five layers:

1. **Identity and scope:** role, supported tasks, prohibited tasks, and escalation policy.
2. **Conversation control:** opening, intent classification, required information, branches, confirmation, and closing.
3. **Language and speech behavior:** language selection, concise spoken turns, interruption recovery, and unclear-audio clarification.
4. **Tools and knowledge:** approved sources, schema validation, success/failure handling, and no invented results.
5. **Evaluation:** repeatable test cases, expected outcomes, logs, and iteration.

## Example flow
Greeting → understand intent → identify missing details → consult approved knowledge or call a tool → communicate confirmed result → confirm next step → close or hand off.

## Failure cases to test
- Customer changes their mind mid-sentence.
- Required details are missing.
- Tool returns an error or empty result.
- Knowledge base sources disagree.
- Customer requests an unsupported action.
- Customer switches language.
- Customer requests a human.
- Customer tries to override the system's rules.

## Evaluation plan
Build a representative test set and score each run against predefined criteria: task completion, factual correctness, tool correctness, language consistency, interruption recovery, and appropriate escalation. Keep raw examples and document failures. Compare versions using the same test set.

## Outcome and limitations
This document is a reusable architecture and evaluation plan, not a claim of a measured production deployment. Publish numeric results only after running and documenting the evaluation.