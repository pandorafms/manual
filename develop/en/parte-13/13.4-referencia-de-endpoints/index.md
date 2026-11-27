# API v2 endpoint reference

!!! info "Generated, English only"
    This reference is generated from the API specification and is always in English,
    whatever the language of the documentation.

*Generated automatically from the API v2 OpenAPI specification (branch `develop`, commit `080555b819`). Do not edit by hand; run `make api-ref`.*

All endpoints require a bearer token unless the operation says otherwise. Each operation lists its parameters, the fields of the request and response bodies and the error status codes it can return.

Every console publishes the exact specification of its own version at `<console>/api/v2/swagger.json` (no authentication) and an interactive Swagger UI at `<console>/api/documentation/`. Use them when your version differs from this reference.

## Domains

| Domain | Contents | Operations |
|---|---|---|
| [Agents](agents.md) | Agents and the data attached to them: custom fields, extended data, collections and secondary groups. | 36 |
| [Modules](modules.md) | Agent modules, their data, states and tags, plus module groups, types, components and data translations. | 56 |
| [Alerts](alerts.md) | Alert templates, actions, commands, calendars and special days, module alerts and the alert queues. | 53 |
| [Events](events.md) | Events, comments, filters, tags and lifetime, and event alerts with their rules and actions. | 52 |
| [Policies](policies.md) | Policies and everything they apply: agents, groups, modules, plugins, alerts, collections and the policy queue. | 94 |
| [Collections](collections.md) | File collections and the agents they are assigned to. | 19 |
| [Users and access](users-and-access.md) | Authentication and tokens, users, profiles, groups and tags, and the audit log. | 50 |
| [Dashboards and notifications](dashboards-and-notifications.md) | Dashboards, widgets and graphs, plus notifications and emails. | 44 |
| [Reports](reports.md) | Report designs, pages, widgets, templates and data sources. | 54 |
| [Services and scheduled downtimes](services-and-downtimes.md) | Services with their elements, and scheduled downtimes for agents and modules. | 29 |
| [Bulk operations and data](bulk-operations-and-data.md) | Bulk drafts and queue, logs, servers and system information. | 22 |
| [Security](security.md) | SIEM rules, events and logs, security vulnerabilities and Windows patches. | 28 |
| [Pandora AI and ITSM](ai-and-itsm.md) | Pandora AI audit, notifications and scheduled tasks, and the Pandora ITSM integration. | 19 |
| [Network Configuration Manager](ncm.md) | Network configuration management (NCM). | 61 |
| [RMM](rmm.md) | Remote monitoring and management (RMM). | 90 |
