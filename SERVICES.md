# Playnite Series Cleaner Services

## Scope

Playnite Series Cleaner is a local Playnite extension. Its principal service is the user's Playnite library API. This file records runtime, local, build-time and delivery services so an offline dependency is not mistaken for “no services.”

## Service map

| Service | Boundary | Status | Responsibility |
| --- | --- | --- | --- |
| Playnite extension API | Host runtime | Required | Provides library records, dialogs, commands and extension lifecycle. |
| Matching/cleanup engine | In-process service | Required | Builds deterministic series-cleanup proposals from library metadata. |
| Local backup/audit data | Local storage | Recommended for mutations | Supports preview, traceability and recovery where implemented. |
| External metadata providers | External | Not required by default | Must be explicitly documented, rate-limited and optional if introduced. |

## Data and credential boundaries

Do not collect or store account tokens unless an explicitly approved provider requires them. Any token stays outside logs and source control.

- Keep secrets in ignored local environment files, operating-system/platform secret storage or the selected deployment service.
- Never print tokens, private paths or user content in routine logs.
- Validate data when it crosses a process, browser, plugin, native, filesystem or network boundary.
- Third-party services require a named owner, least-privilege access and a documented removal/fallback path.

## Offline and failure behavior

Scanning, preview and cleanup should work against the local Playnite database without network access.

Every service call or local subsystem operation must expose a bounded failure state. Use timeouts/cancellation for network work, caps for untrusted files or queues, and retries only where the operation is idempotent.

## Operations and release checks

Never mutate on installation or background startup. Measure scan duration, preserve cancellation and verify preview/apply/undo behavior on disposable data.

Before publication, verify only the services used by that target. Future store, hosting, domain or signing checks are release gates, not active risks while no release is planned.

## Change policy

Update this document when a service, provider, permission, credential class, storage location, port, data owner or failure behavior changes. Also update `SECURITY.md` for security implications and `GUIDELINES.md` for architecture or UX rules.
