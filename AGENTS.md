# OpenAPI Repository Agent Contract

This repository owns shared OpenAPI contracts and interface definitions.

## Environment branch model

Promotion order is: `development` -> `testing` -> `staging` -> `production`.
`main` is the protected source-of-truth branch. Changes move between environment branches by reviewed pull request; do not force-push, rewrite history, or bypass required checks.

## Contract rules

- Treat published schemas as versioned compatibility contracts.
- Keep operation IDs, paths, methods, request/response schemas, auth requirements, error semantics, and headers explicit.
- Run schema validation and compatibility checks before promotion.
- Do not silently introduce breaking API changes.
- Do not commit secrets, tokens, credentials, or production-only values.
- Cross-repository consumers must pin or otherwise identify the exact contract revision they certify against.
