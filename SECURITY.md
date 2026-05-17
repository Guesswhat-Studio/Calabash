# Security Policy

Calabash stores reader data locally and has no hosted reader database. Security reports are still important, especially around local data handling, import/export behavior, desktop file access, release artifacts, and the GitHub Pages demo.

## Supported Versions

The latest public beta release is supported for security review. Older `0.x` beta versions may receive guidance to upgrade before a fix is investigated.

## Reporting a Vulnerability

Please do not open a public issue with vulnerability details, proof-of-concept payloads, private reading notes, or unreleased security findings.

Use GitHub private vulnerability reporting if it is available on this repository. If that entry point is not visible, open a minimal public issue titled `[Security contact]` without technical details so a maintainer can arrange a private channel.

Useful reports include:

- Affected Calabash version and platform.
- Whether the issue affects the web demo, desktop app, local development build, or release artifact.
- Minimal reproduction steps that avoid private data and copyrighted story text.
- Expected impact and whether the issue requires local access, a crafted import file, or user interaction.

Non-security bugs, support questions, and product ideas should use the normal issue forms or Discussions.
