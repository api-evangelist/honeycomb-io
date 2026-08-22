# Honeycomb (honeycomb-io)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/honeycomb-io/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/honeycomb-io/refs/heads/main/apis.yml)

## Scope

- **Access:** 3rd-Party

## Tags

- Observability
- Tracing
- Distributed Tracing
- Telemetry
- OpenTelemetry
- Events
- Logs
- Metrics
- SLO
- AIOps
- AI Observability

## APIs

### Honeycomb Events API

Send arbitrary JSON events into Honeycomb datasets via single-event POST, high-throughput batch POST, and Kinesis-style ingest. Events are the lowest-level ingest primitive; OpenTelemetry traces, metrics, and logs all land here. Each event becomes a row in a columnar dataset that you can query, trigger on, or derive SLOs from.

- **Human URL:** [https://docs.honeycomb.io/api/tag/Events](https://docs.honeycomb.io/api/tag/Events)
- **Base URL:** `https://api.honeycomb.io`

#### Tags

- Observability
- Events
- Telemetry
- Ingest

#### Properties

- [Documentation](https://docs.honeycomb.io/api/tag/Events)
- [OpenAPI](openapi/honeycomb-events-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/honeycomb-events-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/honeycomb-events-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Honeycomb Datasets API

Manage datasets — the columnar tables that hold ingested events for a service — and dataset definitions that map well-known OpenTelemetry fields (service.name, trace.parent_id, span.kind, etc.) to the columns Honeycomb uses for trace assembly, BubbleUp, and Service Map rendering.

- **Human URL:** [https://docs.honeycomb.io/api/tag/Datasets](https://docs.honeycomb.io/api/tag/Datasets)
- **Base URL:** `https://api.honeycomb.io`

#### Tags

- Observability
- Datasets
- Configuration

#### Properties

- [Documentation](https://docs.honeycomb.io/api/tag/Datasets)
- [Documentation](https://docs.honeycomb.io/api/tag/Dataset-Definitions)
- [OpenAPI](openapi/honeycomb-datasets-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/honeycomb-datasets-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/honeycomb-datasets-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Honeycomb Columns API

Inspect and manage columns inside a dataset, including custom hidden columns and calculated (derived) columns. Calculated fields use Honeycomb's expression language to compute new dimensions from existing event attributes — used heavily for normalizing high-cardinality data and building reusable business-level metrics.

- **Human URL:** [https://docs.honeycomb.io/api/tag/Columns](https://docs.honeycomb.io/api/tag/Columns)
- **Base URL:** `https://api.honeycomb.io`

#### Tags

- Observability
- Columns
- Schema
- Derived Columns

#### Properties

- [Documentation](https://docs.honeycomb.io/api/tag/Columns)
- [Documentation](https://docs.honeycomb.io/api/tag/Calculated-Fields)
- [OpenAPI](openapi/honeycomb-columns-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/honeycomb-columns-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/honeycomb-columns-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Honeycomb Queries API

Construct, save, and execute queries against the Honeycomb columnar store. Define breakdowns, calculations, filters, orders, and havings; persist a query as a reusable specification; trigger async execution via Query Data and poll for results. Query Annotations let you decorate saved queries with human-readable context. The Query Data API is the foundation for AI-assisted observability and Honeycomb MCP.

- **Human URL:** [https://docs.honeycomb.io/api/tag/Queries](https://docs.honeycomb.io/api/tag/Queries)
- **Base URL:** `https://api.honeycomb.io`

#### Tags

- Observability
- Queries
- Query Data
- Analytics

#### Properties

- [Documentation](https://docs.honeycomb.io/api/tag/Queries)
- [Documentation](https://docs.honeycomb.io/api/tag/Query-Data)
- [Documentation](https://docs.honeycomb.io/api/tag/Query-Annotations)
- [OpenAPI](openapi/honeycomb-queries-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/honeycomb-queries-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/honeycomb-queries-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Honeycomb Boards API

Manage Boards — Honeycomb's dashboard primitive — and the multi-dataset Views composed on top of them. Boards pin queries, SLO panels, and text panels into a single shareable surface for incident response, weekly reviews, and team-owned operational dashboards.

- **Human URL:** [https://docs.honeycomb.io/api/tag/Boards](https://docs.honeycomb.io/api/tag/Boards)
- **Base URL:** `https://api.honeycomb.io`

#### Tags

- Observability
- Boards
- Dashboards
- Views

#### Properties

- [Documentation](https://docs.honeycomb.io/api/tag/Boards)
- [OpenAPI](openapi/honeycomb-boards-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/honeycomb-boards-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/honeycomb-boards-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Honeycomb Triggers API

Define thresholded alerts on top of saved queries — Triggers — and route their firings to Recipients (PagerDuty, Slack, MS Teams, webhooks, email, OpsGenie). Trigger frequency, thresholds, and evaluation schedule are fully configurable per dataset.

- **Human URL:** [https://docs.honeycomb.io/api/tag/Triggers](https://docs.honeycomb.io/api/tag/Triggers)
- **Base URL:** `https://api.honeycomb.io`

#### Tags

- Observability
- Triggers
- Alerting
- Recipients

#### Properties

- [Documentation](https://docs.honeycomb.io/api/tag/Triggers)
- [Documentation](https://docs.honeycomb.io/api/tag/Recipients)
- [OpenAPI](openapi/honeycomb-triggers-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/honeycomb-triggers-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/honeycomb-triggers-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Honeycomb SLOs API

Define Service Level Objectives backed by a derived-column SLI, attach Burn Alerts that fire when error-budget burn rate crosses a configured threshold, and pull historical SLO compliance through the Reporting endpoint. SLO Reporting is an Enterprise-tier surface used to feed reliability dashboards and quarterly review packs.

- **Human URL:** [https://docs.honeycomb.io/api/tag/SLOs](https://docs.honeycomb.io/api/tag/SLOs)
- **Base URL:** `https://api.honeycomb.io`

#### Tags

- Observability
- SLO
- Burn Alerts
- Reliability
- Reporting

#### Properties

- [Documentation](https://docs.honeycomb.io/api/tag/SLOs)
- [Documentation](https://docs.honeycomb.io/api/tag/Burn-Alerts)
- [Documentation](https://docs.honeycomb.io/api/tag/Reporting)
- [OpenAPI](openapi/honeycomb-slos-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/honeycomb-slos-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/honeycomb-slos-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Honeycomb Markers API

Annotate the Honeycomb timeline with Markers representing deploys, feature flag changes, incidents, or arbitrary externally meaningful events. Marker Settings define per-type appearance (colour, label) so deploy-vs-incident annotations render distinctly on every graph.

- **Human URL:** [https://docs.honeycomb.io/api/tag/Markers](https://docs.honeycomb.io/api/tag/Markers)
- **Base URL:** `https://api.honeycomb.io`

#### Tags

- Observability
- Markers
- Deployments
- Annotations

#### Properties

- [Documentation](https://docs.honeycomb.io/api/tag/Markers)
- [Documentation](https://docs.honeycomb.io/api/tag/Marker-Settings)
- [OpenAPI](openapi/honeycomb-markers-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/honeycomb-markers-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/honeycomb-markers-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Honeycomb Service Maps API

Submit asynchronous Service Map dependency requests and retrieve the materialized service-to-service call graph derived from trace data. Service Map is an Enterprise feature used to visualise blast radius and onboard new engineers to a complex microservice estate.

- **Human URL:** [https://docs.honeycomb.io/api/tag/Service-Maps](https://docs.honeycomb.io/api/tag/Service-Maps)
- **Base URL:** `https://api.honeycomb.io`

#### Tags

- Observability
- Service Map
- Dependencies
- Tracing

#### Properties

- [Documentation](https://docs.honeycomb.io/api/tag/Service-Maps)
- [OpenAPI](openapi/honeycomb-service-maps-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/honeycomb-service-maps-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/honeycomb-service-maps-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Honeycomb Auth API

Validate an API key, discover its scopes, and identify which Team and Environment it belongs to. Available on both the v1 (configuration key) and v2 (management key) surfaces, so tools can probe whichever credential they were handed.

- **Human URL:** [https://docs.honeycomb.io/api/tag/Auth](https://docs.honeycomb.io/api/tag/Auth)
- **Base URL:** `https://api.honeycomb.io`

#### Tags

- Observability
- Authentication
- API Keys

#### Properties

- [Documentation](https://docs.honeycomb.io/api/tag/Auth)
- [OpenAPI](openapi/honeycomb-auth-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/honeycomb-auth-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/honeycomb-auth-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Honeycomb Key Management API

Create, list, rotate, and revoke Honeycomb API keys (ingest, configuration, and management scopes) at the team level. Uses the v2 JSON:API surface (application/vnd.api+json) under /2/teams/{teamSlug}/api-keys. Requires a Management Key.

- **Human URL:** [https://docs.honeycomb.io/api/tag/Key-Management](https://docs.honeycomb.io/api/tag/Key-Management)
- **Base URL:** `https://api.honeycomb.io`

#### Tags

- Observability
- API Keys
- Administration
- Security

#### Properties

- [Documentation](https://docs.honeycomb.io/api/tag/Key-Management)
- [OpenAPI](openapi/honeycomb-key-management-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/honeycomb-key-management-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/honeycomb-key-management-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Honeycomb Environments API

Create and manage Environments — the isolation primitive in Honeycomb Classic-replacement teams. Each Environment has its own datasets, ingest keys, boards, triggers, and SLOs. Lives on the v2 JSON:API surface under /2/teams/{teamSlug}/environments. Requires a Management Key.

- **Human URL:** [https://docs.honeycomb.io/api/tag/Environments](https://docs.honeycomb.io/api/tag/Environments)
- **Base URL:** `https://api.honeycomb.io`

#### Tags

- Observability
- Environments
- Administration

#### Properties

- [Documentation](https://docs.honeycomb.io/api/tag/Environments)
- [OpenAPI](openapi/honeycomb-environments-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/honeycomb-environments-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/honeycomb-environments-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [Documentation](https://docs.honeycomb.io/api/)
- [Portal](https://docs.honeycomb.io/)
- [OpenAPI](https://docs.honeycomb.io/api/openapi-public.yaml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Authentication](https://docs.honeycomb.io/get-started/best-practices/api-keys/)
- [Status Page](https://status.honeycomb.io/)
- [Blog](https://www.honeycomb.io/blog)
- [Changelog](https://www.honeycomb.io/changelog)
- [Pricing](https://www.honeycomb.io/pricing)
- [Support](https://docs.honeycomb.io/troubleshoot/community/)
- [Support](https://support.honeycomb.io/)
- [LinkedIn](https://www.linkedin.com/company/honeycomb-io/)
- [Twitter](https://twitter.com/honeycombio)
- [Source Code](https://github.com/honeycombio)
- [Website](https://www.honeycomb.io/)
- [Documentation](https://www.honeycomb.io/product/honeycomb-intelligence)
- [Documentation](https://www.honeycomb.io/product/telemetry-pipeline)
- [Standards](https://opentelemetry.io/)
- [Plans](plans/honeycomb-io-plans-pricing.yml)
- [Rate Limits](rate-limits/honeycomb-io-rate-limits.yml)
- [Fin Ops](finops/honeycomb-io-finops.yml)
- [Open Source](https://github.com/honeycombio/refinery)
- [SDK](https://github.com/honeycombio/honeycomb-opentelemetry-web)
- [SDK](https://github.com/honeycombio/honeycomb-opentelemetry-go)
- [SDK](https://github.com/honeycombio/honeycomb-opentelemetry-java)
- [SDK](https://github.com/honeycombio/honeycomb-opentelemetry-dotnet)
- [SDK](https://github.com/honeycombio/libhoney-py)
- [SDK](https://github.com/honeycombio/libhoney-go)
- [SDK](https://github.com/honeycombio/libhoney-js)
- [SDK](https://github.com/honeycombio/libhoney-dotnet)
- [Tools](https://github.com/honeycombio/terraform-provider-honeycombio)
- [Tools](https://github.com/honeycombio/honeycomb-kubernetes-agent)
- [Tools](https://github.com/honeycombio/helm-charts)
- [Tools](https://github.com/honeycombio/honeytail)
- [Tools](https://github.com/honeycombio/buildevents)
- [Tools](https://github.com/honeycombio/gha-buildevents)
- [Tools](https://github.com/honeycombio/honeycomb-lambda-extension)
- [Tools](https://github.com/honeycombio/honeyaws)
- [Integrations](https://github.com/honeycombio/agentless-integrations-for-aws)
- [M C P](https://github.com/honeycombio/honeycomb-mcp)
