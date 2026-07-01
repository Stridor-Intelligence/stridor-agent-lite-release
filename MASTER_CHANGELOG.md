# Stridor Agent Lite — Master Changelog

> **Canonical workspace template — upstream source for all Stridor Agent installations.**
>
> This document tracks every system version release and the complete evolution history of the template. It exists so users, contributors, and evaluators can see exactly how the system has grown from foundation to current.

---

## This is a log of the updates to Stridor Agent System

This folder is the **canonical workspace starter** for any new Stridor Agent installation. It contains a complete, ready-to-copy AI-team operating system with:

- **6 core agents:** Stridor Agent (Routing & Gate), Harry (Agent Operations), Pam (Project Delivery), Rob (Research), Libby (Knowledge), Vera (Workflow Reliability)
- **38+ shared SOPs** across Agent Operations, Quality Management, Project Delivery, Research, Team Operations, Orchestration, Change Management, and Development
- **Structured handoff protocol** (v3.3) for clean context passing between agents
- **Operating principles** (9 durable process discoveries) guiding how work is structured
- **Verification gates** — mechanical (Stridor Agent) and substantive (Vera's Gate-V)
- **Phase gate discipline** preventing downstream work before upstream approval

Every Stridor Agent workspace starts as a copy of this template. Improvements are applied here **first**, then synced to consumer workspaces.

---

## Stridor Agent System Version History

---

### V3.1 — Packaged App Safety & Usage Meter
*2026-07-01*

The packaged Stridor Agent Lite app receives its first dedicated safety and operating-visibility pass. This release focuses on making destructive reset actions explicit and testable, while giving users a practical daily token meter for free-model usage experiments.

**Key changes:**
- **Danger Zone reset controls added** — Stridor Agent System settings now expose Full Factory Reset, Reset App State, and Reset Workspace actions in a clearly marked destructive-actions area
- **Main-process reset confirmation enforced** — each reset IPC handler now shows a native Cancel/Reset confirmation before sidecar shutdown, window destruction, or filesystem deletion can run
- **Reset scope clarified** — reset copy distinguishes full reset, app-state reset, and workspace-only reset so users know what will be deleted and what will be preserved
- **Daily token usage meter added** — titlebar now shows a live daily token progress indicator with formatted token count
- **UTC daily reset behavior added** — token tracking keys usage by UTC date and resets after UTC midnight, including while the app remains open
- **Daily token ceiling calibrated to field test** — daily meter ceiling updated from 3,000,000 to 36,500,000 tokens after reaching the previous test threshold
- **Dev-channel local validation completed** — app and desktop typechecks passed, desktop build passed, and the dev-channel app bundle was verified during local testing

---

### V3.0 — Changelog & Public Readiness
*2026-06-27*

The template gets its first comprehensive changelog. This version introduces public-facing documentation so users and evaluators can trace the system's evolution without needing access to the full history of every file. The version scheme is introduced as the primary organizing principle.

**Key changes:**
- **MASTER_CHANGELOG.md** created with full version inventory — a single document covering every component's current state and the complete improvement history
- Document structured for public release — public-friendly language, organized by meaningful version releases (V1.0 → V3.0) rather than raw date tables
- Current Version Inventory added as reference appendix so readers can check any component's latest version at a glance
- Architectural Decisions section captured — 8 key design choices that shaped the system

---

### V2.4 — Template Sync & Handoff Final
*2026-06-26*

The final template sync from the live workspace brings the handoff skill to its polished v3.3. All components reach their current state before the changelog release. Knowledge structure is finalized with a complete INDEX.md.

**Key changes:**
- **STRIDOR.md** v6.0 final sync to template — self-report check (Item 6), fix-output mode for fix-only tasks
- **Handoff skill** v3.3 final — documentation polish, XML attribute fixes, focus line moved from XML attribute to content line inside `<handoff>`, good/bad examples updated, hygiene rules completed
- **TEAM_REGISTRY.md** updated — Pronouns column added for all 6 core agents
- **Knowledge/INDEX.md** finalized — comprehensive hub structure guide for the entire Knowledge directory
- **Knowledge/Quality/Lessons Learned Register.md** synced to template (1 anonymized entry)
- **Knowledge/Regression Cases/README.md** synced to template
- **PROJECT.md** sync log updated with full version inventory and drift notes

---

### V2.3 — Self-Reporting Protocol
*2026-06-23*

A system-wide mistake self-reporting discipline is rolled out across all agent identity files. Every specialist must now self-report substantive mistakes using a standard format before completing a task. Fixed-but-unreported mistakes are treated as process gaps.

**Key changes:**
- **Mandatory `I MADE A MISTAKE` format** added to all 6 agent identity files — standard block with IMPACT, FIX DOMAIN, and SEVERITY fields
- **Agent identity versions bumped:** Harry v4.2→v4.3, Vera v4.2→v4.3, Pam v4.0→v4.1, Libby v4.0→v4.1, Rob v4.0→v4.1, Stridor Agent v5.4.1→v6.0
- **SOP-QA-017** v1.0 (Lessons Learned Register Entry Standard) finalized — entry authorship rules, quality criteria, three-strike enforcement, Stridor Agent gate integration
- **Harry IDENTITY.md** updated — SOP-AO-002/003/004 bindings added, memory capture on classification rule, output language audit checks

---

### V2.2 — Reliability & Verification Wave
*2026-06-22*

A major reliability pass. The Output Readiness Gate gains three new sub-checks (self-report, file-change audit, install/deploy verification). The handoff skill undergoes a complete rewrite from v1.0 to v3.3, moving to an XML-tagged format. Vera's authority hardens with enforcement tags and install/deploy hard stops. The Lessons Learned Register is populated with a cross-project failure protocol.

**Key changes:**
- **STRIDOR.md** v5.8→v5.9→v6.0 — Self-report check (Item 6) added to Output Readiness Gate; fix-output mode documented for fix-only tasks; MODIFIED_FILES file-change sub-check (PDCA 1); install/deploy file-completeness sub-check (PDCA 3)
- **Handoff skill** v1.0→v3.3 — Major rewrite from delimiter format to XML-tagged format with identity negation (`You are not Stridor Agent`), outcome statements, good/bad example pairs, specialist anchor, PRIOR SPECIALIST OUTPUT content boundary, compatibility gate compliance note
- **Vera IDENTITY.md** v4.2 — `[ENFORCEMENT: STRICT]` tag convention for install/deploy workflows (PDCA 5); hard stop for install/deploy file completeness
- **SOP-QA-017** v1.0 (Lessons Learned Register Entry Standard) — entry authorship rules, quality criteria, three-strike enforcement for recurrence, Stridor Agent gate integration
- **SOP-TEAM-016** v1.0 (File Modification Memory Writeback) — MODIFIED_FILES format standard for PDCA compliance
- **SOP-DEV-001** (Use Ponytail for All Code Writing) created — code quality discipline for all code-writing agents
- **SOP-ORC-004** (Workflow Manifest Standard) created — tracking multi-step workflow state across sequential task calls
- **Knowledge/Quality/Lessons Learned Register.md** populated — cross-project failure protocol with tag vocabulary, recurrence detection, and scan cadence
- **Knowledge/Regression Cases/README.md** created — behavioral examples preventing known failures from recurring
- **Knowledge/INDEX.md** updated — comprehensive Knowledge hub structure guide
- **AGENTS.md, OPERATING_MODEL.md, README.md, STRIDOR_MEMORY.md** — template sync review and last_updated bumps

---

### V2.1 — Handoff & Process Capture
*2026-06-16–17*

The handoff skill is born to solve the fundamental problem that sub-agents start with zero conversation history. SOP-QA-013 introduces same-turn error capture. A major template sync brings the template up to date with the live workspace, adding missing SOPs across every domain and completing the knowledge structure.

**Key changes:**
- **Handoff skill** v1.0 — delimiter format standardised (`*Stridor handoff for:`) to prevent sub-agent misinterpretation of the `=== STRIDOR HANDOFF:` delimiter
- **Handoff skill** v1.1 — Mandatory CONTEXT BASELINE section with 4 fields (PDCA 2 compliance)
- **Handoff skill** v1.2 — Consolidated CONTEXT BASELINE, removed duplication per Gate-V review
- **SOP-QA-013** v1.0 (Immediate Error Capture and Process Improvement) — same-turn three-item capture for process failures
- **SOP-QA-013** v1.1 — Writeback timing changed from 24-hour window to same-turn capture (owner correction incorporated)
- **Major template sync** — Priority 1-4 deltas synced from live workspace; all missing SOPs added across Team Operations, Quality Management, Project Delivery, Orchestration; Workstreams, Tasks, SOPs/INDEX.md, Guidelines, Reference, and Templates directories created; template improvements upstreamed to live workspace
- **Harry IDENTITY.md** v4.2 — template-synced with AO-SOP bindings (AO-002, AO-003, AO-004)

---

### V2.0 — Template Creation & Governance Framework
*2026-06-12–13*

The **New Base Folder template** is created as permanent infrastructure — never closed, never archived. This is the birth of the canonical workspace starter. Twelve new SOPs establish governance across Agent Operations, Quality Management, Change Management, Project Delivery, and Team Operations. Two critical structural gates are added: the Phase Gate Pre-Check (preventing downstream work before upstream approval) and Gate-V (Post-Change Verification by Vera). Nine operating principles codify the team's process discoveries.

**Key changes:**
- **New Base Folder template created** — canonical workspace starter for all Stridor Agent installations. 6-core agent roster: Stridor Agent (Routing & Gate), Harry (Agent Operations), Pam (Project Delivery), Rob (Research), Libby (Knowledge), Vera (Workflow Reliability)
- **Gate-V (Post-Change Verification Gate)** added to Mandatory Ownership Gate — all SOP, operating doc, routing, and activation changes require Vera's substantive verification before reaching the owner. Vera IDENTITY.md v4.0 gains Section 10 (7-criteria Gate-V checklist)
- **Phase Gate Pre-Check (Step 2.5)** established — no downstream work may proceed before the upstream phase gate has passed and transition has been approved by the gate owner
- **Memory Writeback Gate** added to STRIDOR.md Output Readiness Gate (Item 5) — "I'll remember that" is not a valid memory update; writeback must be verifiable
- **12 new SOPs created:**
  - Agent Operations (4): SOP-AO-001 v4.1 (Activate New AI Agent), AO-002 (Verify Config Sync v1.0), AO-003 (Apply Agent Visibility Standard v1.0), AO-004 (Audit Template Defaults v1.0)
  - Quality Management (5): SOP-QA-011 (Gate-V), QA-012 (SOP Numbering), QA-014 (No Prompt-as-Enforcement), QA-015 (Behavioural vs Performance), QA-016 (SOP Update Sync Verification)
  - Change Management (1): SOP-CM-001 (Versioning, Changelog, and Cross-Reference Discipline)
  - Project Delivery (1): SOP-PM-006 (Prevent Stale Project Records)
  - Team Operations (1): SOP-TEAM-013 (Post-Setup Verification Gate)
- **OPERATING_PRINCIPLES.md** created — 9 durable process discoveries (SOP-P-001 through P-009): process-gap-first, structural enforcement, identity vs performance, default value liability, Gate-V self-check, template sync with Vera review, documentation gaps, memory writeback, no complexity without need
- **NAMING_CONVENTION.md** created — file, directory, agent, and heading naming standards
- **SYSTEM_MEMORY.md** created — operating-system failure modes and lessons for the entire team
- **All 6 agent memory files enriched to v2.0** — Activation Mistakes, role learnings, closure classification, Gate-V procedure, shareable operating lessons. Sanitised of workspace-specific content. Template Policy sections added
- **Agent identity files upgraded** with source-backed evidence tiers via Rob research (PMP, PMBOK, PRINCE2 for Pam; ISO 9001, RACI, Galbraith for Harry; ISO 15489, DITA 2.0 for Libby; IEEE 1012, ISTQB, FMEA for Vera; Minto, MECE, ISO 20252 for Rob)
- **STRIDOR.md** template v5.4→v5.6 — Gate-V dependency noted, expanded routing table
- **SHARED_MEMORY.md** updated — XDG Config Access permission message standard
- **OPERATING_MODEL.md** template sync — Phase Gate Pre-Check compressed to canonical reference, PDCA harvest added to Session Close, pre-task standard updated
- **SOP-QA-005** updated to v2.0 — Apply Rigorous Operating File Standard

---

### V1.0 — Foundation
*Early May 2026 – 2026-06-11*

The initial Stridor Agent operating system is built in the live workspace. Core documents establish the team working agreement, setup flow, communication standards, and routing discipline. The first agent identity files are created for all 6 core specialists. Initial SOPs establish quality management, project delivery, and team operations procedures. The AGENTS.md file introduces the Mandatory Ownership Gate, Debug Mode, and the Async-Language Ban.

**Key changes:**
- **Initial operating system** built in live workspace — core documents established: OPERATING_MODEL.md, FIRST_INTERACTION.md, STRIDOR_MEMORY.md, SHARED_MEMORY.md, COMMUNICATION_STANDARD.md
- **STRIDOR.md** initial version — Stridor Agent identity, routing decision tree, output readiness gate
- **AGENTS.md** and **README.md** created — workspace entry instructions, Mandatory Ownership Gate, routing rules with 6-core specialist roster, Debug Mode Contract, Async-Language Ban, template overview with first-setup instructions
- **First agent identity files** created for Stridor Agent, Harry, Pam, Libby, Vera, and Rob
- **Agent identity upgrades to v4.0** — all 6 agents upgraded to source-backed evidence tier via Rob research (PMP, PMBOK, ISO 9001, ISO 15489, IEEE 1012, Minto Pyramid Principle, etc.)
- **Debug Mode — Version Reporting** sections added to all identity files
- **SOPs created:**
  - Quality Management: SOP-QA-005 v2.0 (Apply Rigorous Operating File Standard), QA-006 (Config Change Verification Gate), QA-007 (Deliverable Placement Gate), QA-008 (Agent Config Prompt Rebuild), QA-009 (Verification Gate Record Standard), QA-010 (Agent Activation Failures Register)
  - Project Delivery: SOP-PM-001 (Plan And Control Approved Projects), SOP-PM-002 (Run Post-Setup Re-Entry Brief)
  - Orchestration: SOP-ORC-001 (Run Routing Pre-Flight Check), SOP-ORC-002 (Write Task Tool Delegation Brief), SOP-ORC-003 (Task Tool Delegation — Serial Model & Permissions)
  - Team Operations: SOP-TEAM-011 (Sync Structural Changes to Template), SOP-TEAM-012 (Session Log SOP with mandatory PDCA Harvest), SOP-TEAM-013 (Post-Setup Verification Gate — read-back confirmation of setup persistence)
- **FIRST_INTERACTION.md** — setup sequence, post-setup verification gate, team introduction routine
- **SOP-PM-002** (Run Post-Setup Re-Entry Brief) — daily context recovery and attention surfacing SOP with owner-priority/inferred-attention separation

---

## Architectural Decisions

The template has accumulated several architectural decisions worth noting. These are the design choices that shape how the system works and why.

| Decision | Rationale | Established |
|---|---|---|
| **6-core agent roster only** | New workspaces start lean. New agents added via Harry's V4 activation when a recurring gap proves the need. | 2026-06-12 |
| **Phase Gate Pre-Check** | No downstream work before upstream phase approval. Structural enforcement, not "remember to." | 2026-06-13 |
| **Memory Writeback Gate** | "I'll remember that" is not a valid memory update. Writeback must be verifiable via MODIFIED_FILES or explicit capture. | 2026-06-13 |
| **Gate-V (Post-Change Verification)** | All SOP, operating doc, routing, and activation changes require Vera's substantive verification before reaching the owner. | 2026-06-12 |
| **Self-report protocol** | Mistakes must be self-reported in standard format before task completion. Fixed-but-unreported is still a process gap. | 2026-06-23 |
| **Handoff skill as context bridge** | Sub-agents start with zero conversation history. The XML-tagged handoff document is the only context-passing mechanism. | 2026-06-16 |
| **Mistake self-reporting (all agents)** | Standard `I MADE A MISTAKE` format with IMPACT, FIX DOMAIN, SEVERITY fields. Required before task completion. | 2026-06-23 |
| **Seven-item Output Readiness Gate** | Mechanical completeness check before specialist output reaches owner: recommendation, questions, attribution, format, memory writeback, self-report, gate compliance. | 2026-06-26 |
| **Template as upstream source** | All improvements applied to template first, then synced to consumer workspaces. Template is permanent infrastructure — never closed or archived. | 2026-06-12 |

---

## Current Version Inventory

Every component in the template with its current version or last-updated date.

### Operating Documents

| Document | Version | Last Updated | Owner |
|---|---|---|---|
| `STRIDOR.md` — Stridor Agent identity & routing gate | v6.0 | 2026-06-26 | Stridor Agent |
| `AGENTS.md` — Mandatory Ownership Gate, routing rules | — | 2026-06-22 | Stridor Agent |
| `OPERATING_MODEL.md` — Team working agreement | — | 2026-06-22 | Stridor Agent (Pam sync) |
| `FIRST_INTERACTION.md` — Setup sequence & team intro | — | 2026-06-06 | Stridor Agent |
| `README.md` — Template overview & setup guide | — | 2026-06-22 | Libby |
| `STRIDOR_MEMORY.md` — Stridor Agent operating memory | — | 2026-06-22 | Stridor Agent |

### System Files

| Document | Last Updated | Owner |
|---|---|---|
| `SETUP_STATE.md` — First-run setup flag | Template stub | Stridor Agent |
| `SHARED_MEMORY.md` — Durable team preferences | 2026-06-13 | Stridor Agent |
| `SYSTEM_MEMORY.md` — Operating-system lessons & failure modes | 2026-06-13 | Stridor Agent |
| `APP_HARNESS.md` — Packaged app double-harness rules | — | Stridor Agent |
| `COMMUNICATION_STANDARD.md` — Attribution & speaker tag rules | 2026-05-26 | Vera |
| `Database/schema.sql` + `seed.sql` | — | Libby |

### Agent Identity Files (Stridor Team/)

| Agent | Identity Version | Memory Version | Evidence Tier | Last Updated |
|---|---|---|---|---|
| **Stridor Agent** (Routing & Gate) | v6.0 | Deprecated → STRIDOR_MEMORY.md | — | 2026-06-23 |
| **Harry** (Agent Operations Lead) | v4.3 | v2.0 | Source-backed | 2026-06-23 |
| **Pam** (Project Delivery Manager) | v4.1 | v2.0 | Source-backed (PMP, PMBOK) | 2026-06-23 |
| **Libby** (Knowledge & Information Manager) | v4.1 | v2.0 | Source-backed (ISO 15489, DITA 2.0) | 2026-06-23 |
| **Vera** (Workflow Reliability Engineer) | v4.3 | v2.0 | Source-backed (IEEE 1012, ISTQB, FMEA) | 2026-06-23 |
| **Rob** (Senior Research Analyst) | v4.1 | v2.0 | Source-backed (Minto, MECE, ISO 20252) | 2026-06-23 |
| **TEAM_REGISTRY.md** | — | — | — | 2026-06-26 |

### Skills

| Skill | Version | Last Updated | Owner |
|---|---|---|---|
| `handoff/SKILL.md` — Structured XML context passing | v3.3 | 2026-06-26 | Stridor Agent |

### Guidelines

| Guideline | Created | Owner |
|---|---|---|
| `OPERATING_PRINCIPLES.md` — 9 process discoveries (SOP-P-001 through P-009) | 2026-06-13 | Libby |
| `NAMING_CONVENTION.md` — File, directory, agent, and heading standards | 2026-06-13 | Libby |

### Shared SOPs — Agent Operations

| SOP ID | Title | Version | Status | Owner |
|---|---|---|---|---|
| SOP-AO-001 | Activate New AI Agent | v4.1 | Active | Harry / Vera / Libby |
| SOP-AO-002 | Verify Config Sync | v1.0 | Active | Harry |
| SOP-AO-003 | Apply Agent Visibility Standard | v1.0 | Active | Harry |
| SOP-AO-004 | Audit Template Defaults | v1.0 | Active | Harry |

### Shared SOPs — Change Management

| SOP ID | Title | Status | Owner |
|---|---|---|---|
| SOP-CM-001 | Versioning, Changelog, and Cross-Reference Discipline | Active | Libby |

### Shared SOPs — Development

| SOP ID | Title | Status | Owner |
|---|---|---|---|
| SOP-DEV-001 | Use Ponytail for All Code Writing | Active | Vera |

### Shared SOPs — Orchestration

| SOP ID | Title | Status | Owner |
|---|---|---|---|
| SOP-ORC-001 | Run Routing Pre-Flight Check | Active | Stridor Agent |
| SOP-ORC-002 | Write Task Tool Delegation Brief | Draft | Stridor Agent |
| SOP-ORC-003 | Task Tool Delegation — Serial Model & Permissions | Active | Stridor Agent |
| SOP-ORC-004 | Workflow Manifest Standard | Active | Stridor Agent |

### Shared SOPs — Project Delivery

| SOP ID | Title | Status | Owner |
|---|---|---|---|
| SOP-PM-001 | Plan And Control Approved Projects | Active | Pam |
| SOP-PM-002 | Run Post-Setup Re-Entry Brief | Active | Pam |
| SOP-PM-006 | Prevent Stale Project Records | Active | Pam |

### Shared SOPs — Quality Management

| SOP ID | Title | Version | Status | Owner |
|---|---|---|---|---|
| SOP-QA-002 | Use Verification Gates for Agent Workflows | — | Active | Vera |
| SOP-QA-003 | Run Shared Agent Execution Lifecycle | — | Active | Vera |
| SOP-QA-004 | Run the PDCA Cycle for SOPs | — | Active | Vera |
| SOP-QA-004 | Run PDCA Reviews For Projects And Agents | — | Active | Vera |
| SOP-QA-005 | Apply Rigorous Operating File Standard | v2.0 | Active | Vera |
| SOP-QA-006 | Apply Config Change Verification Gate | — | Active | Vera |
| SOP-QA-007 | Apply Deliverable Placement Gate | — | Active | Vera |
| SOP-QA-008 | Agent Config Prompt Rebuild (Spec-Driven Workflow) | — | Active | Vera |
| SOP-QA-009 | Verification Gate Record Standard | — | Active | Vera |
| SOP-QA-010 | Agent Activation Process — Failures Register | — | Active | Vera |
| SOP-QA-011 | Apply Post-Change Verification Gate (Gate-V) | — | Active | Vera |
| SOP-QA-012 | SOP Numbering and ID Conflict Resolution | — | Active | Libby |
| SOP-QA-013 | Immediate Error Capture and Process Improvement | v1.1 | Active | Vera |
| SOP-QA-014 | No Prompt-as-Enforcement Policy | — | Active | Vera |
| SOP-QA-015 | Behavioural vs Performance Distinction | — | Active | Vera |
| SOP-QA-016 | SOP Update Sync Verification | — | Active | Vera |
| SOP-QA-017 | Lessons Learned Register Entry Standard | v1.0 | Active | Vera |

### Shared SOPs — Research

| SOP ID | Title | Status | Owner |
|---|---|---|---|
| SOP-RES-001 | Conduct Deep Research | Active | Rob |
| SOP-RES-002 | Run Role Capability Research And Review | Active | Rob |

### Shared SOPs — Team Operations

| SOP ID | Title | Version | Status | Owner |
|---|---|---|---|---|
| SOP-TEAM-004 | Manage Memory System | — | Active | Libby |
| SOP-TEAM-005 | Apply Shared Agent Culture, Communication, And Presentation | — | Active | Vera |
| SOP-TEAM-007 | Configure OpenCode Subagents For Team Members | v3.0 | Active | Harry |
| SOP-TEAM-011 | Sync Structural Changes to New Base Folder Template | — | Active | Libby |
| SOP-TEAM-012 | Session Log SOP | — | Active | Libby |
| SOP-TEAM-013 | Post-Setup Verification Gate | — | Active | Libby |
| SOP-TEAM-016 | File Modification Memory Writeback | v1.0 | Active | Libby |

### Other Knowledge Assets

| Asset | Last Updated | Owner |
|---|---|---|
| `Knowledge/INDEX.md` — Hub structure guide | 2026-06-26 | Libby |
| `Knowledge/Quality/Lessons Learned Register.md` — Cross-project failure protocol | Template | Libby |
| `Knowledge/Regression Cases/README.md` — Behavioral regression standards | 2026-06-26 | Vera / Libby |
| `Knowledge/BEHAVIORAL_CONFIGURATION_REFERENCE.md` | — | Harry |

---

## Template Maintenance

This template is the **upstream source** for all Stridor Agent workspaces. It is maintained as a permanent infrastructure project — never closed, archived, or deleted.

### Sync Discipline

- **SOP changes** in the live workspace → duplicate to template SOP file, update `last_updated`
- **Agent identity upgrades** → copy to `Stridor Team/[Agent]/` after Vera verification
- **Routing rule changes** → update AGENTS.md and STRIDOR.md
- **New agent activation** → add to template only after 2+ successful proving assignments
- **Drift check** → every 3 months, compare template state against live workspace

### Current Known Drift

| Component | Template Version | Live Workspace Version | Status |
|---|---|---|---|
| Agent identities | v4.0–4.3 | v4.1–4.3 | ⚠️ Minor drift — needs sync |
| Routing roster | 6-core agents | 12+ agents (Otto, Dean, Prost, Tyler, Daan, Constantine, Mark added) | Deliberate — template stays lean |

---

## Change Log for This Document

| Date | Change | Owner |
|---|---|---|
| 2026-06-27 | Initial creation — full version inventory and version-organized history compiled from 30+ file surveys across the entire template | Pam |
| 2026-06-27 | Restructured from date-ordered tables to version-organized format (V1.0 → V3.0, latest first) per owner request | Pam |

---

*Maintained by Pam (Project Delivery Manager). This document is public-ready for distribution with Stridor Agent Lite releases.*
