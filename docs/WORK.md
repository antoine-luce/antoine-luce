# Selected Work — Antoine Luce

Private client repositories are intentionally **not made public**. This is a technical overview of the work categories and engineering decisions, not a claim that every module has been independently audited or is deployed at scale. No client data or secrets are disclosed.

## LexIA · Legal workflow automation

**Problem:** Reading heterogeneous legal documents and transferring reliable information into structured case documents is slow and error-prone.

**System:** A Next.js / TypeScript workflow with PDF extraction through an LLM, document-specific prompts, a separate deterministic rules engine, and DOCX output. The observed repository includes Jest tests covering the rules layer and document rendering.

**Engineering decisions:**
- Extract source fields first; compute and resolve inconsistencies in typed business rules, not in the LLM.
- Prefer an explicit review step before final document generation.
- Exercise rules and DOCX rendering in regression tests.

**Stack observed:** Next.js, TypeScript, Anthropic SDK, docxtemplater, Jest.

## ClaraIA · Multi-business conversational agent

**Problem:** Route customer messages across several activities while keeping context, respecting consent, and knowing when to hand over to a human.

**System:** A structured message pipeline with CRM records, conversation history, tools, connectors, voice support, safeguards, and response delivery. There are separate controls for unsubscribe requests, distress signals and human handoff. A simulation mode is defined to prevent real outbound sending in non-live conditions.

**Engineering decisions:**
- Keep consent and safety decisions in server-side code rather than delegating them to the language model.
- Make critical dependencies injectable for testing and simulation.
- Separate conversation state, tool execution, and message delivery.

**Stack observed:** Next.js, TypeScript, Anthropic SDK, PostgreSQL-compatible storage, Zod, Vitest.

## Mandat2a · Property document generation

**Problem:** Transform notarial records and property information into structured real-estate administration mandates without transcription errors.

**System:** PDF analysis, structured data review, rule validation and Word document generation. Observed automated tests include individual/couple/corporate ownership examples and strict document rendering.

**Engineering decisions:**
- Validate entities, parties and lots before producing final documents.
- Separate extraction, review and generation stages.
- Test representative and edge-case document structures.

**Stack observed:** Next.js, TypeScript, Anthropic SDK, JSZip, Node.js tests.

## ComptIA 2A · Accounting process automation

**Problem:** Reduce repeated accounting and back-office work while respecting financial rules and controlled user permissions.

**System:** Rules-based accounting workflows with Supabase integration, role-related access, exports (including structured SEPA and CSV), document templates and optional AI-supported invoice extraction. The repository README documents a Vitest suite and data seed setup.

**Engineering decisions:**
- Use deterministic computations for critical amounts and exports.
- Validate structured model outputs before they affect records.
- Separate demonstration fixtures from production data.

**Stack observed:** Next.js, TypeScript, Supabase, Zod, docxtemplater, Vitest.

## SCI Patrimoine · Property management

**Problem:** Centralize property, tenancy, rent and document records for a real-estate holding company.

**System:** A typed domain model with leases, occupancy status, rent, revision indices and a document-classification workflow. The inspected repository README describes some demo data and planned database connections, so it should be presented as a staged implementation, not an independently confirmed production rollout.

**Stack observed:** Next.js, TypeScript, Supabase, Anthropic SDK, Vitest.

## Additional products

- **PV Syndic:** typed, deterministic vote-majority engine, dynamic attendance/tantième calculations and document workflows.
- **LexAuto:** legal template validator, quality gates and proof-report generator.
- **2A Audit:** business-process audit and director dashboard, using Next.js and database integration.
- **The One:** multi-tenant product architecture with Prisma schema, subscription and user models, and test commands.

## What can be shared with recruiters?

- **Public:** this architecture overview, technology stack and a guided explanation of design decisions.
- **With authorization:** sanitized screenshots, demos and anonymized test examples.
- **Private by default:** client repositories, actual documents, configuration, customer data and commercial agreements.

For a walkthrough, [contact me on LinkedIn](https://www.linkedin.com/in/antoine-luce-01a2ba17b).