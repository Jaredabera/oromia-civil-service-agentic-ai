# Oromia Civil Service Agentic AI

**Afaan Oromoo · AI document intelligence · Goal-directed browser agents · Human oversight**

Independent research prototype exploring how agentic AI could reduce the manual workload involved in receiving, interpreting, categorizing, and routing civil-service requests written in Afaan Oromoo.

🌐 **[Project website and interactive demonstration](https://jaredabera.github.io/oromia-civil-service-agentic-ai/)**

> **Demonstration software.** This project is not an official Oromia government service. Its sample documents and citizen records are synthetic. It has not been certified for government production, data protection compliance, or large-scale reliability.

## What the agent does

| Stage | Agent task | Verification |
|---|---|---|
| 1. Ingest | Receive a PDF or scanned document | Validate supported input format |
| 2. Understand | Extract **Maqaa**, **Lakkoofsa Eenyummaa**, and **Dhimma** | Required fields and confidence check |
| 3. Plan | Categorize the request and select a department | Policy and routing validation |
| 4. Observe | Inspect the sandboxed Chromium portal | Visible controls mapped |
| 5. Act | Enter and check the form fields | Read-back comparison |
| 6. Review | Pause for authenticated supervisor authorization | Claim and approval gate |
| 7. Submit | Present approved request to a **mock portal** | Receipt verification |
| 8. Audit | Persist transitions and exception states | Traceable event history |

**Agent loop:** Goal → Observe → Plan → Action → Verify → Continue / Escalate.

## Components

- Python / FastAPI backend and operator workflow
- Isolated Chromium worker for GUI actions
- Local synthetic Afaan Oromoo mock portal
- Optional OpenAI-compatible multimodal inference
- Supervisor approval, correction, and receipt confirmation
- Persistent state and automated testing
- Separate, static GitHub Pages presentation website

## Source distribution

This public website is **not a live admin interface**. The containerized application requires its own authenticated local deployment.

The full V3 source package is being staged for this repository. Until its entire source tree has been committed, do not interpret this repository as a complete installable release.

## Security and evaluation

- Never put citizen identities, production screenshots, credentials, or approval tokens in Git.
- Do not expose your Docker dashboard or mock-portal APIs directly on GitHub Pages.
- Establish a dataset-based accuracy benchmark, failure-injection tests, and audited throughput measurements before claiming superior accuracy or financial savings.
- Keep humans in control of consequential decisions and submissions.

Read [architecture](docs/architecture.md), [agent tasks](docs/agent-tasks.md), [local deployment](docs/deployment.md), and [security](SECURITY.md).

**Research project:** Oromia Civil Service Digital Assistant — Agentic Human Emulator.
