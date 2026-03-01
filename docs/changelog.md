---
id: changelog
title: Changelog
sidebar_label: Changelog
---

<!-- markdownlint-disable MD025 -->

All notable changes to MosBot OS documentation are recorded here.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).

For application-level changes, see the changelogs in the respective repositories:

- [mosbot-api CHANGELOG](https://github.com/bymosbot/mosbot-api/blob/main/CHANGELOG.md)
- [mosbot-dashboard CHANGELOG](https://github.com/bymosbot/mosbot-dashboard/blob/main/CHANGELOG.md)

---

## [Unreleased]

_No unreleased changes._

---

## [0.1.0] — 2026-03-01

Initial documentation site release. Covers MosBot OS as of:

- **mosbot-api** [`0.1.2`](https://github.com/bymosbot/mosbot-api/releases/tag/v0.1.2)
- **mosbot-dashboard** [`0.1.3`](https://github.com/bymosbot/mosbot-dashboard/releases/tag/v0.1.3)

### Added

- Getting Started: overview, prerequisites, quickstart, configuration, first login
- OpenClaw Integration: setup, workspace service, gateway, local development, Kubernetes
- Skills: overview, shared vs agent-specific, structure, examples
- Configuration Reference: annotated `openclaw.json` sample with field-level explanations
- Features: task management, agent monitor, org chart, workspaces, standups
- Deployment: Docker, Kubernetes, production hardening
- Security: authentication, roles & permissions, secrets management
- Troubleshooting: common issues, FAQ

### Notes

- Workspace paths reflect API `0.1.2`: `/shared/docs` → `/docs`, `/shared/projects` → `/projects`
- Dashboard `0.1.3` adds frontmatter parsing in the file preview component
