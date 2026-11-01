# Deployment guide

## Prerequisites

- Windows 11 + WSL2 + Docker Desktop Linux Engine, or Linux host with Docker Compose.
- A supported Python installation for bootstrap.
- Sufficient disk space and RAM for headless Chromium.
- For optional VLM inference: a separately deployed vision-capable local OpenAI-compatible endpoint.

## Local source checkout (once published)

```powershell
git clone https://github.com/Jaredabera/oromia-civil-service-agentic-ai.git
cd oromia-civil-service-agentic-ai
```

**Note:** the executable V3 code tree is being staged separately. The public website by itself is not the Docker system.

When the full source tree is present:

```powershell
python scripts/bootstrap.py
docker compose config --quiet
docker compose up --build -d
docker compose ps
docker compose logs --tail=60
```

The intended local dashboard address is `http://localhost:8080`, assuming the Compose API publishes that port and all services start.

## Troubleshooting

- `docker info` must return a working **Server** section. Docker CLI alone is not enough.
- If Python cannot be located, use the explicit Python executable installation path or fix PATH.
- If Compose reports missing `JWT_SECRET`, `APPROVAL_KEY`, `WORKER_TOKEN` or passwords, initialize the environment and verify `.env` exists. Do not commit this file.
- If a task fails, inspect the worker logs and observe the last verified stage. Do not change a failed task to Completed without a receipt.
- Earlier V3 builds could time out trying to `fill()` a hidden approval token input; use the corrected worker implementation.

## Safety

Use synthetic test documents and the mock portal only. Do not connect this prototype to a government production portal without explicit authorization and assessment.
