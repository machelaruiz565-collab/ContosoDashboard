<!--
Sync Impact Report
- Version change: 0.0.0 -> 1.0.0
- Modified principles: Initial constitution established for the repository
- Added sections: Training and Security Constraints; Development Workflow
- Removed sections: none
- Follow-up TODOs: none
-->

# ContosoDashboard Constitution

## Core Principles

### I. Security-by-Default
The application MUST treat security as a first-class requirement, not an afterthought. Every change that affects authentication, authorization, routing, file handling, or data exposure MUST preserve the least-privilege model, guard against IDOR patterns, and document any intentional exceptions. This protects the training environment from accidental unsafe patterns while modeling production-grade practices.

### II. Offline-First Training Architecture
The codebase MUST remain runnable without external cloud dependencies so learners can work in local and disconnected environments. Infrastructure boundaries MUST be abstracted behind interfaces or service seams, and local implementations must remain easy to replace with Azure or enterprise equivalents later. This preserves training portability while demonstrating a realistic migration path.

### III. Test-First and Validation
All behavior changes MUST be validated before merge through the smallest meaningful automated checks available, and any fix to a defect MUST include a regression test when practical. Changes that affect authentication, permissions, task behavior, or project access MUST be explicitly verified for correctness. This keeps the repository trustworthy as a learning platform and prevents regressions.

### IV. Separation of Concerns
Business logic, persistence, authentication, and UI concerns MUST be kept in clearly separated layers. Services MUST own business rules, data access MUST be isolated in the data layer, and page components MUST delegate to services rather than embedding logic directly. This reduces coupling and makes the training examples easier to understand and extend.

### V. Simplicity and Learnability
Features MUST favor clear names, direct implementation, and explainable flow over clever abstractions or hidden side effects. Code and documentation MUST remain understandable to beginners, with complexity justified by a clear requirement. This supports the project’s purpose as a teaching artifact and reduces maintenance overhead.

## Training and Security Constraints

The repository MUST remain a training-only application. It MUST not be treated as production-ready software, and any security controls in the codebase MUST be labeled as mock training implementations unless they are explicitly hardened for a production environment. The application MUST continue to demonstrate safe defaults such as authorization checks, user isolation, and defensive coding patterns without introducing unsupported external dependencies.

The project MUST not require cloud services for basic learning scenarios. Local database and file operations MUST remain available by default, and production replacements MUST be introduced only through explicit abstraction layers that do not require rewriting business logic.

## Development Workflow

All changes MUST be reviewed against this constitution before merge. Contributors MUST keep the codebase aligned with the repository’s training goals, ensure security-sensitive changes are documented, and validate the relevant application behavior with the least expensive reliable check. Pull requests MUST explain the intent of the change, identify affected behaviors, and note any security or architectural implications.

The default workflow for repository maintenance is:
- keep the application simple and understandable
- prefer explicit, testable code over hidden behavior
- verify the changed path with build or test evidence
- document assumptions, limitations, and training intent when relevant

## Governance

This Constitution governs the ContosoDashboard repository and supersedes informal practices when a conflict arises. Amendment proposals MUST be documented, reviewed for impact on security, architecture, and training clarity, and approved before becoming effective. Changes that alter the project’s security posture, architectural boundaries, or operating assumptions MUST include a clear migration note or compatibility explanation.

The project follows semantic versioning for constitutional changes:
- MAJOR: backwards-incompatible governance changes or principle removals
- MINOR: added or materially expanded guidance
- PATCH: clarifications, wording fixes, and non-semantic refinements

Compliance reviews MUST confirm that changes remain aligned with the project’s training purpose, security expectations, and separation-of-concerns model. If a change cannot satisfy the rules in this document, it MUST be rejected or revised before merge.

**Version**: 1.0.0 | **Ratified**: 2026-10-15 | **Last Amended**: 2026-10-15
