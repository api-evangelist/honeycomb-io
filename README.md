# Honeycomb (honeycomb-io)

Honeycomb is an event-based observability platform purpose-built for high-cardinality telemetry. Engineers send events, traces, logs, and metrics — usually via OpenTelemetry — into Honeycomb's columnar store, then query, alert, and reliability-budget against that data through Boards, Triggers, SLOs, and the AI-assisted Canvas / Honeycomb MCP surfaces. The Honeycomb API is a clean OpenAPI 3.1 contract split between a v1 surface (event ingest plus most configuration: datasets, columns, queries, boards, triggers, SLOs, markers, recipients) and a v2 JSON:API surface (team-level resources: API keys and environments).

**URL:** [Visit APIs.json](https://raw.githubusercontent.com/api-evangelist/honeycomb-io/refs/heads/main/apis.yml)

**Run:** [Capabilities Using Naftiko](https://github.com/naftiko/fleet?utm_source=api-evangelist&utm_medium=readme&utm_campaign=company-api-evangelist&utm_content=repo)

## Tags

 - Observability, Tracing, Distributed Tracing, Telemetry, OpenTelemetry, Events, Logs, Metrics, SLO, AIOps, AI Observability

## Timestamps

- **Created:** 2026-05-25
- **Modified:** 2026-05-25

## Plans

| Plan | Price | Events / month | Metric data points / month | Triggers | SLOs | Notes |
|---|---|---|---|---|---|---|
| Free | $0 | 20M | 100M | 2 | 0 | Distributed tracing, BubbleUp, OTel, Canvas Copilot, Honeycomb MCP |
| Pro | from $130 | 1.5B | 7.5B | 100 | 2 | SSO, Honeycomb Support |
| Enterprise | Custom | 10B/year base | volume discounts | 300+ | 100+ | Service Map, Query Data API, PrivateLink, SLO Reporting, Private Cloud |
| Telemetry Pipeline | $0.10/GB | n/a | n/a | n/a | n/a | Collect, filter, sample, route telemetry |

## APIs

### Honeycomb Events API
Send arbitrary JSON events into Honeycomb datasets via single-event POST, high-throughput batch POST, and Kinesis-style ingest. Events are the lowest-level ingest primitive — OpenTelemetry traces, metrics, and logs all land here.

**Human URL:** [https://docs.honeycomb.io/api/tag/Events](https://docs.honeycomb.io/api/tag/Events)

- [Documentation](https://docs.honeycomb.io/api/tag/Events)
- [OpenAPI](openapi/honeycomb-events-api-openapi.yml)
- [Naftiko Capability — Events](capabilities/events-events.yaml)
- [Naftiko Capability — Kinesis Events](capabilities/events-kinesis.yaml)

### Honeycomb Datasets API
Manage datasets (the columnar tables that hold events for a service) and dataset definitions that map OpenTelemetry fields to the columns Honeycomb uses for trace assembly, BubbleUp, and Service Map.

**Human URL:** [https://docs.honeycomb.io/api/tag/Datasets](https://docs.honeycomb.io/api/tag/Datasets)

- [Documentation — Datasets](https://docs.honeycomb.io/api/tag/Datasets)
- [Documentation — Dataset Definitions](https://docs.honeycomb.io/api/tag/Dataset-Definitions)
- [OpenAPI](openapi/honeycomb-datasets-api-openapi.yml)
- [JSON Schema — Dataset](json-schema/honeycomb-dataset-schema.json)
- [Naftiko Capability — Datasets](capabilities/datasets-datasets.yaml)
- [Naftiko Capability — Dataset Definitions](capabilities/datasets-definitions.yaml)

### Honeycomb Columns API
Inspect and manage columns inside a dataset, including hidden columns and calculated (derived) columns. Calculated fields use Honeycomb's expression language to compute new dimensions on the fly.

**Human URL:** [https://docs.honeycomb.io/api/tag/Columns](https://docs.honeycomb.io/api/tag/Columns)

- [Documentation — Columns](https://docs.honeycomb.io/api/tag/Columns)
- [Documentation — Calculated Fields](https://docs.honeycomb.io/api/tag/Calculated-Fields)
- [OpenAPI](openapi/honeycomb-columns-api-openapi.yml)
- [JSON Schema — Column](json-schema/honeycomb-column-schema.json)
- [Naftiko Capability — Columns](capabilities/columns-columns.yaml)
- [Naftiko Capability — Calculated Fields](capabilities/columns-calculated-fields.yaml)

### Honeycomb Queries API
Construct, save, and execute queries against the columnar store. Define breakdowns, calculations, filters, orders, and havings; persist a query as a reusable spec; trigger async execution via Query Data and poll for results.

**Human URL:** [https://docs.honeycomb.io/api/tag/Queries](https://docs.honeycomb.io/api/tag/Queries)

- [Documentation — Queries](https://docs.honeycomb.io/api/tag/Queries)
- [Documentation — Query Data](https://docs.honeycomb.io/api/tag/Query-Data)
- [Documentation — Query Annotations](https://docs.honeycomb.io/api/tag/Query-Annotations)
- [OpenAPI](openapi/honeycomb-queries-api-openapi.yml)
- [JSON Schema — Query](json-schema/honeycomb-query-schema.json)
- [Naftiko Capability — Queries](capabilities/queries-queries.yaml)
- [Naftiko Capability — Query Data](capabilities/queries-query-data.yaml)
- [Naftiko Capability — Query Annotations](capabilities/queries-annotations.yaml)

### Honeycomb Boards API
Manage Boards — Honeycomb's dashboard primitive — and the multi-dataset Views composed on top of them.

**Human URL:** [https://docs.honeycomb.io/api/tag/Boards](https://docs.honeycomb.io/api/tag/Boards)

- [Documentation](https://docs.honeycomb.io/api/tag/Boards)
- [OpenAPI](openapi/honeycomb-boards-api-openapi.yml)
- [JSON Schema — Board](json-schema/honeycomb-board-schema.json)
- [Naftiko Capability — Boards](capabilities/boards-boards.yaml)
- [Naftiko Capability — Views](capabilities/boards-views.yaml)

### Honeycomb Triggers API
Define thresholded alerts on top of saved queries and route firings to Recipients (PagerDuty, Slack, MS Teams, webhook, email, OpsGenie).

**Human URL:** [https://docs.honeycomb.io/api/tag/Triggers](https://docs.honeycomb.io/api/tag/Triggers)

- [Documentation — Triggers](https://docs.honeycomb.io/api/tag/Triggers)
- [Documentation — Recipients](https://docs.honeycomb.io/api/tag/Recipients)
- [OpenAPI](openapi/honeycomb-triggers-api-openapi.yml)
- [JSON Schema — Recipient](json-schema/honeycomb-recipient-schema.json)
- [Naftiko Capability — Triggers](capabilities/triggers-triggers.yaml)
- [Naftiko Capability — Recipients](capabilities/triggers-recipients.yaml)

### Honeycomb SLOs API
Define SLOs backed by a derived-column SLI, attach Burn Alerts that fire when error-budget burn rate crosses thresholds, and pull historical SLO compliance via Reporting (Enterprise).

**Human URL:** [https://docs.honeycomb.io/api/tag/SLOs](https://docs.honeycomb.io/api/tag/SLOs)

- [Documentation — SLOs](https://docs.honeycomb.io/api/tag/SLOs)
- [Documentation — Burn Alerts](https://docs.honeycomb.io/api/tag/Burn-Alerts)
- [Documentation — Reporting](https://docs.honeycomb.io/api/tag/Reporting)
- [OpenAPI](openapi/honeycomb-slos-api-openapi.yml)
- [JSON Schema — SLO](json-schema/honeycomb-slo-schema.json)
- [Naftiko Capability — SLOs](capabilities/slos-slos.yaml)
- [Naftiko Capability — Burn Alerts](capabilities/slos-burn-alerts.yaml)
- [Naftiko Capability — Reporting](capabilities/slos-reporting.yaml)

### Honeycomb Markers API
Annotate the timeline with Markers representing deploys, flag flips, incidents, or externally meaningful events. Marker Settings define per-type rendering.

**Human URL:** [https://docs.honeycomb.io/api/tag/Markers](https://docs.honeycomb.io/api/tag/Markers)

- [Documentation — Markers](https://docs.honeycomb.io/api/tag/Markers)
- [Documentation — Marker Settings](https://docs.honeycomb.io/api/tag/Marker-Settings)
- [OpenAPI](openapi/honeycomb-markers-api-openapi.yml)
- [JSON Schema — Marker](json-schema/honeycomb-marker-schema.json)
- [Naftiko Capability — Markers](capabilities/markers-markers.yaml)
- [Naftiko Capability — Marker Settings](capabilities/markers-settings.yaml)

### Honeycomb Service Maps API
Submit asynchronous Service Map dependency requests and retrieve the materialized service-to-service call graph. Enterprise feature.

**Human URL:** [https://docs.honeycomb.io/api/tag/Service-Maps](https://docs.honeycomb.io/api/tag/Service-Maps)

- [Documentation](https://docs.honeycomb.io/api/tag/Service-Maps)
- [OpenAPI](openapi/honeycomb-service-maps-api-openapi.yml)
- [Naftiko Capability — Service Maps](capabilities/service-maps-dependencies.yaml)

### Honeycomb Auth API
Validate an API key, discover its scopes, and identify which Team and Environment it belongs to. Available on both v1 (configuration key) and v2 (management key).

**Human URL:** [https://docs.honeycomb.io/api/tag/Auth](https://docs.honeycomb.io/api/tag/Auth)

- [Documentation](https://docs.honeycomb.io/api/tag/Auth)
- [OpenAPI](openapi/honeycomb-auth-api-openapi.yml)
- [Naftiko Capability — Auth](capabilities/auth-auth.yaml)

### Honeycomb Key Management API
Create, list, rotate, and revoke API keys at the team level. v2 JSON:API surface under `/2/teams/{teamSlug}/api-keys`. Requires a Management Key.

**Human URL:** [https://docs.honeycomb.io/api/tag/Key-Management](https://docs.honeycomb.io/api/tag/Key-Management)

- [Documentation](https://docs.honeycomb.io/api/tag/Key-Management)
- [OpenAPI](openapi/honeycomb-key-management-api-openapi.yml)
- [Naftiko Capability — API Keys](capabilities/key-management-api-keys.yaml)

### Honeycomb Environments API
Create and manage Environments — the isolation primitive in Honeycomb teams. Each Environment has its own datasets, ingest keys, boards, triggers, and SLOs. v2 JSON:API surface under `/2/teams/{teamSlug}/environments`. Requires a Management Key.

**Human URL:** [https://docs.honeycomb.io/api/tag/Environments](https://docs.honeycomb.io/api/tag/Environments)

- [Documentation](https://docs.honeycomb.io/api/tag/Environments)
- [OpenAPI](openapi/honeycomb-environments-api-openapi.yml)
- [Naftiko Capability — Environments](capabilities/environments-environments.yaml)

## SDKs and Tooling

Honeycomb publishes OpenTelemetry-aligned SDKs plus their pre-OTel `libhoney` clients, a Terraform provider, a Kubernetes agent, the open-source Refinery trace-aware sampling proxy, and a Honeycomb MCP server.

- [Refinery — trace-aware tail-based sampling](https://github.com/honeycombio/refinery)
- [Honeycomb OpenTelemetry Web SDK](https://github.com/honeycombio/honeycomb-opentelemetry-web)
- [Honeycomb OpenTelemetry Go SDK](https://github.com/honeycombio/honeycomb-opentelemetry-go)
- [Honeycomb OpenTelemetry Java SDK](https://github.com/honeycombio/honeycomb-opentelemetry-java)
- [Honeycomb OpenTelemetry .NET SDK](https://github.com/honeycombio/honeycomb-opentelemetry-dotnet)
- [libhoney-py](https://github.com/honeycombio/libhoney-py)
- [libhoney-go](https://github.com/honeycombio/libhoney-go)
- [libhoney-js](https://github.com/honeycombio/libhoney-js)
- [libhoney-dotnet](https://github.com/honeycombio/libhoney-dotnet)
- [Terraform Provider for Honeycomb](https://github.com/honeycombio/terraform-provider-honeycombio)
- [Honeycomb Kubernetes Agent](https://github.com/honeycombio/honeycomb-kubernetes-agent)
- [Honeycomb Helm Charts](https://github.com/honeycombio/helm-charts)
- [honeytail — log shipper](https://github.com/honeycombio/honeytail)
- [buildevents — CI tracing](https://github.com/honeycombio/buildevents)
- [gha-buildevents — GitHub Actions tracing](https://github.com/honeycombio/gha-buildevents)
- [Honeycomb Lambda Extension](https://github.com/honeycombio/honeycomb-lambda-extension)
- [honeyaws — AWS observability](https://github.com/honeycombio/honeyaws)
- [Agentless Integrations for AWS](https://github.com/honeycombio/agentless-integrations-for-aws)
- [Honeycomb MCP](https://github.com/honeycombio/honeycomb-mcp)

## Resources

- [Honeycomb API Reference](https://docs.honeycomb.io/api/)
- [Honeycomb OpenAPI Spec](https://docs.honeycomb.io/api/openapi-public.yaml)
- [API Keys best practices](https://docs.honeycomb.io/get-started/best-practices/api-keys/)
- [Honeycomb Status](https://status.honeycomb.io/)
- [Honeycomb Blog](https://www.honeycomb.io/blog)
- [Honeycomb Changelog](https://www.honeycomb.io/changelog)
- [Honeycomb Pricing](https://www.honeycomb.io/pricing)
- [Pollinators Slack](https://docs.honeycomb.io/troubleshoot/community/)
- [Honeycomb on GitHub](https://github.com/honeycombio)
- [Plans](plans/honeycomb-io-plans-pricing.yml)
- [Rate Limits](rate-limits/honeycomb-io-rate-limits.yml)
- [FinOps](finops/honeycomb-io-finops.yml)
- [JSON-LD context](json-ld/honeycomb-io-context.jsonld)
- [Vocabulary](vocabulary/honeycomb-io-vocabulary.yml)
- [Spectral rules](rules/honeycomb-rules.yml)
