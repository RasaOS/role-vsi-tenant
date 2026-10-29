# role-vsi-tenant

**Version:** 0.1.1 · `rasa.module.role.vsi-tenant` · public

The **VSI Tenant** role (`vsi-tenant`) as a RasaOS role module. The standing authority on how VSI builds things. Ask it what the standard is, where it is written, and whether a plan meets it.

| File | What it is |
|---|---|
| `role.json` | The role's fields (id, name, summary, version, consumers, knowledge, takes, kinds, grants). galt publishes them to `/tenant_config/roles/vsi-tenant`. |
| `prompt.md` | The role's prompt, byte for byte the body of `roles/vsi-tenant.md` in vsi-tenant. |
| `.claude-plugin/plugin.json` | The plugin manifest, which makes the repo loadable into a session with `--plugin-dir`. |
| `rasa.json` | The Element manifest: `kind: module`, with the role's id and version under `rasa`. |
| `bin/check-role` | The release gate. |

Role version **1**, from `roles/vsi-tenant.md` at vsi-tenant `fd0c872`.

## Loading it

- **As an agent's brain:** `galt agent new <name> --brain RasaOS/role-vsi-tenant@v0.1.1`. galt reads `role.json` and `prompt.md`. There is no role assignment this way, so no grants.
- **As the source of the published role:** the tenant's `roles/vsi-tenant.md` becomes the one line `element: RasaOS/role-vsi-tenant@v0.1.1`. After a person runs Publish roles, every agent with role `vsi-tenant` loads this Element. galt's scheduler supports this; it advertises `role_elements` (galt ADR 0064).
- **Public:** any computer can fetch it. No vault token is needed.

## Changing the role

Until the tenant's `roles/vsi-tenant.md` points here, that file is what Publish roles reads, and this repo is a snapshot of it. Change both together; see `CLAUDE.md`.
