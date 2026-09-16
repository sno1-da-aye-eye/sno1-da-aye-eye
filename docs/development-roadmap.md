# Development Roadmap

The roadmap is staged so each step produces something understandable and testable before the next layer is added.

## Phase 0 — Incubation foundation

**Status: underway**

- Establish the `incubation` branch.
- Document the vision and boundaries.
- Describe the proposed architecture.
- Record the existing source repositories.
- Keep the repository documentation-first.

## Phase 1 — Repository and engineering baseline

- Choose the initial monorepo or workspace structure.
- Add formatting, linting, type checking, and test conventions.
- Add `.env.example` without real credentials.
- Add contribution and decision-record templates.
- Define supported runtime versions.
- Establish a simple changelog.

## Phase 2 — Minimal conversation core

- Define a provider-neutral model interface.
- Implement one provider adapter.
- Create a minimal conversation API.
- Support cancellation, bounded context, and useful error states.
- Add basic request and integration tests.

**Success condition:** a user can send a message and receive a response through a documented, replaceable interface.

## Phase 3 — Memory boundary

- Define short-term context versus durable memory.
- Add user-approved memory entries.
- Add inspect, edit, export, and delete operations.
- Track source, confidence, timestamps, and user approval where appropriate.
- Prevent uncontrolled growth through limits and retention rules.

**Success condition:** the system can remember something intentionally, explain where it came from, and remove it when requested.

## Phase 4 — Avatar and interface integration

- Connect the avatar UI to the conversation core.
- Add streaming response display.
- Map request lifecycle to avatar states.
- Keep provider credentials and privileged operations server-side.
- Add accessibility and responsive behavior.

**Success condition:** the interface feels alive without hiding the underlying system state.

## Phase 5 — Tools and permissions

- Define explicit tool contracts.
- Add read-only tools first.
- Introduce write operations only with clear scope and approval.
- Record tool calls and outcomes.
- Add dry-run behavior where possible.

**Success condition:** tools are useful, bounded, and understandable rather than unrestricted.

## Phase 6 — Controlled evolution

- Define change proposals.
- Show reasons, affected files, risks, and expected effects.
- Add snapshots and validation.
- Require explicit approval for consequential changes.
- Add rollback and recovery procedures.
- Begin with UI, prompt, and configuration proposals before runtime changes.

**Success condition:** the system can suggest an improvement without silently applying it.

## Phase 7 — Local and operating-environment experiments

Only after the previous phases are stable should the project explore:

- Local model execution.
- Small learning components.
- Sandboxed code execution.
- Mist OS foundations.
- Raindrop OS and Rainforest Desktop surfaces.
- Raincloud services and collaboration infrastructure.

These experiments should remain separable from the core until their security, maintenance, and resource requirements are understood.

## Working rule

At every phase, prefer a small vertical slice over a large unfinished framework. Record what was learned, what failed, and what changed in the project notes.
