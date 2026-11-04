# Engineering Approach

## LLMs are not the source of truth for critical business logic

A recurring pattern in my projects:

```
Incoming file or message
        ↓
Extraction / intent analysis (LLM + tools)
        ↓
Schema validation and source reconciliation
        ↓
Deterministic business rules and permission checks
        ↓
Human review / approval when required
        ↓
Document, CRM update or authorized outbound action
        ↓
Logs, regression tests and release verification
```

These stages represent a design pattern across projects, **not** a promise that every project implements every stage.

### Evidence from source review

- **LexIA**: a rules layer separate from extraction and final DOCX mapping, with Jest tests.
- **ClaraIA**: tool orchestration and server-side rules for unsubscribe, distress and human handoff; simulation mode.
- **Mandat2a**: data validity checks and strict rendering tests for representative ownership configurations.
- **PV Syndic**: independent mathematical voting and majority logic without LLM dependency.
- **LexAuto**: automated validation of document templates and generation output.

### Production engineering

The repositories inspected use TypeScript, build scripts, test frameworks and Git-based delivery workflows. A passing build or deployed URL should **not** be treated as proof of security, performance or reliability without operational evidence. For each engagement I aim to establish a clear acceptance checklist, testable business invariants and a documented handover.

### AI-assisted development

I use coding agents to speed implementation while retaining responsibility for specification, review and product acceptance. The important distinction is between *AI-generated code* and *verified, fit-for-purpose software*.