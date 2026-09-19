# Production Engineering Case Studies

These case studies are deliberately sanitized. The underlying production repositories, customer data, credentials, commercial rules, and operational datasets remain private.

## 1. Production ERP & Analytics Platform

**Context:** Internal business software for a wholesale/distribution operation with data coming from legacy ERP/SQL systems and operational services.

**Stack:** React 19, TypeScript, Vite, ASP.NET Core/.NET 10, Dapper, Npgsql, PostgreSQL/Supabase, SQL Server integration, GitHub Actions, Heroku.

### What I worked on

- Built and maintained business modules covering sales, purchases, inventory, collections, customers, suppliers, cash flow, profitability, reporting, and administration.
- Integrated legacy ERP/SQL data into a modern API and web application without pretending the upstream data was clean or internally consistent.
- Implemented authentication/RBAC, module permissions, export/reporting flows, localization, caching, persistence, and drill-down analytics.
- Worked on reconciliation problems where the same business fact could appear differently across ERP exports, invoice-level detail, snapshots, and operational tables.
- Added automated build/test validation and release checks so changes are reviewed against production behavior rather than accepted because generated code “looks right.”

### Engineering themes

- Legacy-system integration
- Data reconciliation and provenance
- PostgreSQL/Supabase design
- ASP.NET Core APIs
- Complex React/TypeScript state
- Production debugging and release hardening

---

## 2. Logistics, Routing & GPS/Delivery Systems

**Context:** Delivery planning and execution workflows connected to ERP invoices, customer locations, route optimization, dispatcher decisions, and vehicle/GPS evidence.

**Technologies:** .NET, React/TypeScript, PostgreSQL, Google Maps APIs, routing/optimization engines, GPS/telematics data, mobile delivery workflows.

### What I worked on

- Route-planning workflows that combine customer/location data, shipment constraints, vehicle capacity, territory rules, and routing engines.
- Dispatcher editing flows where human decisions must survive optimization rather than being silently rearranged.
- Driver/delivery workflows with explicit state transitions, retries, idempotency, and evidence-aware completion.
- GPS/telematics analysis for stop reconstruction, service-time estimation, route-vs-execution comparison, and delivery evidence.
- Geocoding and location-quality pipelines where weak, stale, or conflicting coordinates must be treated differently from verified evidence.
- Experiments and forensic analyses to understand why apparently valid optimization output can still fail operational business rules.

### Engineering themes

- Vehicle routing and route editing
- GPS/telematics analytics
- Geospatial data quality
- Human-in-the-loop optimization
- Idempotent mobile/backend workflows
- Operational evidence and auditability

---

## 3. AI-Assisted Production Engineering

I use AI coding systems as engineering accelerators, not as substitutes for verification.

### Typical workflow

1. Turn the business problem into explicit invariants and acceptance criteria.
2. Inspect the real repository, schema, logs, and existing behavior before changing code.
3. Use coding agents for implementation, investigation, test generation, and alternative designs.
4. Independently review diffs and use a second model/agent when adversarial review is useful.
5. Run focused and regression tests, inspect edge cases, and verify migrations/contracts.
6. Treat deploy success and business correctness as separate claims.
7. Keep evidence/receipts for changes that affect production behavior.

### Where this is useful

- Inheriting AI-generated or “vibe-coded” applications that now need production discipline.
- Debugging large unfamiliar codebases.
- Refactoring React/Supabase/.NET applications without breaking hidden business rules.
- Turning prototypes into maintainable products.
- Performing architecture, data-integrity, security-minded, and production-readiness audits.

---

## Public technical work

Some representative public repositories:

- [CV_Segmentation](https://github.com/musabaku/CV_Segmentation) — computer-vision / medical-imaging work.
- [Hyper-Thyroid-ML](https://github.com/musabaku/Hyper-Thyroid-ML) — machine-learning experimentation.
- [NomuBackend](https://github.com/musabaku/NomuBackend) — C# backend work.
- [MealDiary](https://github.com/musabaku/MealDiary) — full-stack application work.

For production ERP/logistics work, the source and operational data are private; the case studies above describe the engineering scope without exposing proprietary material.
