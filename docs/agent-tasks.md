# Agent tasks and decision model

## Mission
Given a citizen request written in Afaan Oromoo, prepare a validated administrative record and propose routing to the correct department, using a real browser on an authorized test portal. Obtain human approval before submission.

## Eight observable stages

1. **Receive**: accept PDF/image; record task identifier; validate format and size.
2. **Interpret**: read Afaan Oromoo; extract Maqaa (name), Lakkoofsa Eenyummaa (identity number), Dhimma (issue).
3. **Decide route**: classify the topic and propose the receiving department; surface ambiguity.
4. **Inspect UI**: observe portal screenshot, identify controls and label correspondence.
5. **Execute**: fill each intended field; read it back to verify the actual value.
6. **Escalate**: pause if extraction, route, confidence, or browser state is uncertain; allow human corrections.
7. **Authorize and submit**: claim, approve, sign and submit once using a human-controlled gate.
8. **Verify**: fetch the receipt and confirm it matches the approved record; mark completion only then.

## Action cycle

`goal → observe UI → choose allowed action → execute → verify → persist checkpoint`

Example actions: click, type, select, wait, terminate, or request human takeover. Repeating a failed action indefinitely is prohibited; recover from checkpoints or stop safely.

## Afaan Oromoo vocabulary

| Source label | Meaning |
|---|---|
| Maqaa | Name |
| Lakkoofsa Eenyummaa | Identity number |
| Dhimma | Issue / request |
| Galmee | Record / registration |
| Mirkaneessi | Confirm / approve (verify context) |
| Waajjira | Office |
| Tajaajila | Service |

A glossary is only a fallback: administrative terms may vary by portal and context.

## Expected demo events

`RECEIVED → EXTRACTED → ROUTED → BROWSER_READY → FORM_VERIFIED → AWAITING_APPROVAL → APPROVED → SUBMITTING → VERIFIED_COMPLETE`

Exception transitions: `NEEDS_CORRECTION`, `BLOCKED`, `REJECTED`, `FAILED`. A blocked task is not counted as completed.
