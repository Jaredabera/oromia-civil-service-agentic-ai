# System architecture

```text
Synthetic Afaan Oromoo PDF / image
               |
      Ingestion + validation
               |
     OCR / optional VLM extraction
               |
      Structured fields + confidence
               |
    Department route + policy engine
               |
       Agent objective + plan
               |
    Isolated Chromium / mock portal
               |
       Observe → Act → Verify
               |
     Human review / correction gate
               |
      Signed approval and submit
               |
      Verified receipt + audit
```

## Trust boundaries

**Document intake:** untrusted document content is data, not instructions. Reject or isolate malicious PDFs and prompt-injection attempts.

**VLM:** probabilistic suggestions require schema validation and calibrated confidence. Optional local inference must be enabled and tested separately.

**Policy engine:** only permits actions on the authorized mock portal. It must never allow the agent to override the human approval requirement.

**Worker:** runs in a sandbox with least-privilege access and controlled network routes. Browser session, screenshots and credentials are sensitive.

**Supervisor service:** authenticates operators, assigns exclusive claims, persists corrections, and records approvals.

**Audit and database:** stores process state, receipt references and errors with an agreed retention policy. Minimize personally identifiable information.

## Research limits

A visually verified browser form is not proof that an external portal accepted a transaction. Completion requires the portal-issued receipt to match authorized fields. Concurrency claims require separate worker isolation, durable queue design, and load testing.
