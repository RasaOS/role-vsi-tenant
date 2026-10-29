# Changelog — role-vsi-tenant

## 0.1.0 — 2026-10-28

First release, as a role module. Role `vsi-tenant` version 1, from vsi-tenant `roles/vsi-tenant.md` at `fd0c872`. `prompt.md` is that file's body byte for byte, and `role.json` is its front matter.

- `rasa.json`: `kind: module`, named `rasa.module.role.vsi-tenant`, with no permissions.
- `.claude-plugin/plugin.json`, so a session or agent can load it (galt ADR 0064).
- `bin/check-role`: the release gate.
