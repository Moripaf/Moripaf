## Hi there 👋

<!--
**Moripaf/Moripaf** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.
-->
# Moripaf — Personal / Project README

[![Build Status](https://img.shields.io/badge/build-pending-lightgrey.svg)](https://github.com/)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](./LICENSE)
[![Languages](https://img.shields.io/github/languages/top/your-gh-username/your-repo.svg)](https://github.com/)

---

## Table of contents

* [Overview](#overview)
* [Highlights & Goals](#highlights--goals)
* [Key Projects](#key-projects)
* [Tech Stack](#tech-stack)
* [Usage / Getting started](#usage--getting-started)
* [Development workflow](#development-workflow)
* [Coding standards & conventions](#coding-standards--conventions)
* [Architecture & patterns](#architecture--patterns)
* [Examples & snippets](#examples--snippets)
* [Roadmap & future work](#roadmap--future-work)
* [Contributing](#contributing)
* [License](#license)
* [Contact](#contact)

---

## Overview

This repository contains a curated collection of projects, templates, and notes for **Moripaf**, a software engineer focused on practical, high-performance engineering. The material here emphasizes clarity, maintainability, and pragmatic engineering trade-offs.

Use this README as the canonical index for what I work on and how to get productive with my code quickly.

---

## Highlights & Goals

* Produce cross-platform, local-first applications (desktop / native) with plugin-capable architectures.
* Ship secure, auditable server components (ASP.NET / T-SQL / EF Core) with sound governance and validation rules.
* Maintain high performance as the top non-functional requirement while keeping integrations straightforward.
* Provide clean, well-documented templates for migrating legacy logic (rule engines, stored procedures) into safer, testable forms.

---

## Key Projects (short descriptions)

* **Multichain Wallet (open-source side project)** — cross-platform, plugin-based desktop wallet (C# core, native UI). Goal: local-first, multi-chain support without web-hosted secrets.

* **Legacy Migration Tools** — utilities and scripts to automate migration of old rule definitions (T-SQL + stored-procedure driven systems) into a centralized, testable ruleset.

* **Blazor Porting Kit** — patterns and helpers for porting JS apps (annotated JSDoc classes) to Blazor components (C# rewrite strategy included).

* **Large jQuery App Refactor Plan** — a documented pathway to modularize an 8k+ line jQuery codebase into ES modules, complete with risk assessment and incremental rollout.

* **ASP.NET Minimal API Template** — secure starter that includes JWT auth, user registration with validation (national code / age / phone), and event-application patterns.

* **T-SQL Governance Examples** — stored procedure patterns and Service Broker workflows used for production data validation and time-series updates.

---

## Tech Stack

Primary languages and frameworks used across projects:

* C# / .NET (ASP.NET Minimal APIs, Blazor)
* SQL Server / T-SQL (Service Broker, stored procedures)
* JavaScript (legacy jQuery, ES6+ modularization)
* SQLite (lightweight local storage for prototypes)
* Linux (Fedora) and Windows dual-boot development environments

Tooling & conventions:

* Git (feature branches, PRs)
* CI: GitHub Actions (recommended)
* Testing: xUnit / NUnit for .NET, Jest for JS where applicable
* Containerization: Docker for reproducible test environments

---

## Usage / Getting started

**Clone the repository**

```bash
git clone https://github.com/<your-gh-username>/<your-repo>.git
cd <your-repo>
```

**Run a .NET project**

```bash
dotnet restore
dotnet build
dotnet run --project src/YourProject
```

**Run a local JS prototype**

```bash
npm install
npm run dev
```

**Database**

* For SQL Server demos: use Docker to run a local SQL Server instance.
* For simple demos: local SQLite files are included in the `data/` folder.

---

## Development workflow

A concise, practical workflow that I follow and recommend for collaborators:

1. Create a feature branch: `git checkout -b feat/short-description`
2. Make focused commits; prefer small, logical commits.
3. Push and open a Pull Request with a clear description and test plan.
4. CI runs unit tests + linters. Fix issues, then squash/merge using a descriptive merge commit.

**Commit message guidance** (short form):

```
<type>(<scope>): <short summary>

Optional body describing the change in more detail.

Refs: #issue-number
```

Types: `feat`, `fix`, `chore`, `docs`, `refactor`, `perf`, `test`.

---

## Coding standards & conventions

* Prefer readability and explicitness over clever one-liners.
* Keep public API surfaces minimal, document invariants and assumptions.
* Use dependency injection for most runtime dependencies in .NET projects.
* For SQL: keep stored-procedure side effects explicit, use transactions for multi-table updates, and document message shapes for Service Broker queues.
* Add unit tests and a small set of deterministic integration tests for any migration tooling.

---

## Architecture & patterns

* **Clean Architecture / Hexagonal principles** for server-side code: keep domain logic independent from persistence and transport layers.
* **Plugin architecture** for the wallet and similar projects: define a minimal plugin contract and load implementations dynamically.
* **Rule-migration pattern**: map legacy parameterized rule rows into normalized expressions, then generate automated tests that validate migrated rules against sample data.

(See `docs/architecture.md` for diagrams and a deeper explanation.)

---

## Examples & snippets

**Example: Simple rule-expression migration (pseudo-T-SQL / C#)**

```sql
-- Legacy: rules stored with parameters and separate expressions
-- New approach: store a single normalized expression or precompiled predicate
```

```csharp
// Example C# predicate compilation (sketch)
var compiled = CSharpScript.Create<bool>(expression, globalsType: typeof(RecordGlobals)).CreateDelegate();
var result = await compiled.Invoke(new RecordGlobals { Age = 34, Salary = 1200 });
```

---

## Roadmap & future work

* Harden the multichain wallet architecture; add example plugin templates for at least 2 chains.
* Produce an automated rule migration utility with a verification harness and CI checks.
* Publish a set of Blazor porting recipes (JS→C#) and a sample conversion of a small client app.
* Record and publish a condensed version of the one-hour lecture on databases aimed at data-analyst students.

---

## Contributing

Contributions are welcome. If you want to contribute:

1. Open an issue describing the change or bug.
2. Discuss design in the issue if the change is non-trivial.
3. Submit a PR against `main` or another agreed integration branch.

Please follow the commit conventions and include tests for new behavior.

---

## License

This repository is offered under the **MIT License**. See `LICENSE` for details.

---

## Contact

* GitHub: `https://github.com/<your-gh-username>`
* Email: `<your-email@example.com>` (replace with preferred contact)

---

## Acknowledgements

Thanks to the open-source community and the various OSS projects and patterns that informed these templates and guides.

---

*Generated by an assistant using your public project goals and engineering preferences. Replace placeholders (`<...>`) with your real repository values.*
