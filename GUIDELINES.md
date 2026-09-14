# Playnite Series Cleaner Guidelines

## Purpose and scope

These rules govern the .NET Playnite extension, metadata matching, cleanup rules and desktop UI. They complement the root `README.md`, `SERVICES.md` and `SECURITY.md`. Established project behavior and design tokens override generic examples.

## Architecture and ownership

- Keep Playnite integration, matching rules and mutation commands separate. Discovery may propose changes; only an explicit reviewed command mutates library metadata.
- Keep public interfaces typed, narrow and validated at trust boundaries.
- One module owns each product invariant, transformation and persistence rule; do not maintain silent parallel implementations.
- Generated files and build artifacts are not hand-edited or committed unless the repository explicitly treats them as source.

## Product and visual system

- Follow Playnite-native density and controls. Match status, confidence and planned edits must be readable without relying only on color.
- Reuse current spacing, radius, type, color and motion tokens. Add a token only when it represents a reusable project decision.
- Use the established icon or authored asset system; do not use emoji or platform-dependent glyphs as product icons.
- Text must wrap, truncate or scale by a documented rule and may not obscure essential controls.
- Support reduced motion, visible focus, semantic labeling and sufficient contrast where the platform allows it.

## Layout and interaction

- Dialogs support DPI scaling, keyboard navigation and long game/series names. Lists retain identity when sorted or filtered.
- Every primary interaction works without hover. Disabled states remain legible and explain prerequisites when needed.
- Reserve space for asynchronous content to prevent layout jumps. Use restrained skeletons/progress only while work is pending.
- Empty and error states expose the next valid action. Irreversible actions state their scope and require confirmation.

## State, data and failure handling

- Scan, preview, apply, partial failure, undo and rescan states are explicit. Bulk operations preserve an audit or reversible backup where the API allows.
- Persist the minimum needed data. Version stored formats and define migration, backup or safe-reset behavior.
- Never turn an unknown or failed state into a plausible zero, success message or silent fallback.
- Logs omit secrets, access tokens, private content and unnecessary personal identifiers.

## Security and dependencies

- Follow `SECURITY.md`. Secrets belong in ignored environment files, platform secret storage or deployment-provider settings, never in distributable clients.
- Apply least privilege to filesystem, network, database, extension, plugin and store permissions.
- Keep lockfiles and toolchain declarations current. Update dependencies in reviewed groups and read migration notes before major upgrades.
- Preserve third-party licenses and provenance for code, fonts, art, audio, datasets and models.

## Performance and resilience

- Index metadata once per run, avoid repeated full-library scans and keep UI work separate from long operations.
- Every cache has an owner, key, lifetime and invalidation rule.
- Network operations use timeouts, cancellation and bounded retries. Degraded/offline behavior is explicit.
- Interface motion must not block input; prefer transform/opacity animation unless product behavior needs another technique.

## Verification and release

- Build the extension, run matching fixtures and test preview/apply on a disposable Playnite library. Edge cases include missing, duplicate and localized metadata.
- Review a small, representative and large/edge-case input or viewport for affected behavior.
- A build alone is not runtime proof; test the packaged/exported artifact when platform boundaries change.
- Package only after manifest/version checks, supported-Playnite verification and confirmation that no cleanup runs automatically on installation.
- Keep future publication checks in release documentation, not in the active defect register until a release decision makes them actionable.

## Documentation maintenance

Update this file when architecture, platform targets, visual tokens, permissions, service boundaries or release commands change. Keep product/setup material in `README.md` and provider/runtime details in `SERVICES.md`.
