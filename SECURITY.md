# Security policy

This codebase is a research and demonstration prototype, **not a certified government platform**.

## Do not commit

- Real citizen PDFs, IDs, scans, addresses, or grievance text.
- `.env`, tokens, JWT signing keys, operator passwords or approval keys.
- Runtime database files, screenshots, event histories, audit exports or portal sessions.

## System boundaries

The static GitHub Pages website is informational and must never host the operational API, stream a real desktop, or include real identities. Keep worker networks isolated, use short-lived signed approvals, restrict operator access, and independently validate all portal actions. A model-generated confidence score must not be treated as calibrated evidence.

## Vulnerability reporting

Please avoid filing public issues with exploit details, production URLs, passwords, or identifying data. Contact the repository maintainer privately using GitHub's private vulnerability reporting feature if enabled.

## Deployment gates

Before any government pilot: threat modeling, explicit authorization, privacy review, bilingual accuracy evaluation, access-control tests, logging and retention standards, recovery and concurrency tests, and portal owner approval.
