# Architecture

The initial architecture is deliberately modular. Each layer should have a clear responsibility so the system can evolve without becoming one opaque application.

## Proposed system view

```text
User
  ↕
UXI — User eXchange Interface
  ↕
Conversation / orchestration layer
  ├── Model gateway
  ├── Memory service
  ├── Tool boundary
  └── Evolution proposal system
          ↓
   Validation / approval / rollback
```

## 1. UXI — User eXchange Interface

The UXI is the primary exchange surface between the user and the AI. It is broader than an avatar or a conventional user interface.

The UXI must support two directions:

- **User to AI:** conversation, instruction, teaching, correction, configuration, feedback, and task interaction.
- **AI to user:** explanations, visualisations, workflows, forms, dashboards, editors, prompts, status views, and other useful interface elements.

The UXI is therefore an evolving workspace rather than a fixed skin around the model.

### UXI responsibilities

- Display conversation, system state, memory state, and task progress.
- Collect user input, feedback, preferences, and consent.
- Render approved, structured UI components.
- Allow the AI to propose task-specific interface elements.
- Preserve accessibility, usability, and user control.
- Separate temporary generated UI from saved personal UI and system-level changes.

### UXI evolution model

The AI may generate a **UI description** rather than arbitrary executable interface code. A renderer validates that description against an allowed component schema before displaying it.

Possible component types include:

- Text, cards, lists, tables, and timelines.
- Forms, filters, selectors, and checklists.
- Charts, maps, diagrams, and visual memory views.
- Editors, workspaces, and task-specific panels.
- Controls that call explicitly permissioned tools.

The UXI should learn which layouts, interaction patterns, and presentation styles are useful to an individual user. It should not silently acquire unrestricted browser, filesystem, device, or operating-system privileges.

### Three levels of UI change

| Level | Example | Default handling |
|---|---|---|
| Session UI | A temporary comparison table or task panel | Automatic within schema and resource limits |
| Personal UI | A saved workspace or preferred layout | User confirmation |
| System UI | New executable code, permissions, navigation, or runtime behavior | Explicit approval, snapshot, validation, and rollback |

## 2. Conversation and orchestration layer

This layer coordinates a request from the UXI. It decides what context is needed, calls the selected model provider, retrieves relevant memory, and returns a structured response or UI proposal.

It should enforce:

- Request limits.
- Cancellation.
- Context-size bounds.
- Session and identity checks.
- Logging appropriate to the user’s privacy settings.
- Validation of model-produced structured output.

## 3. Model gateway

The model gateway provides a stable internal interface while allowing different providers or local models to be used behind it.

Potential providers include hosted APIs, self-hosted models, or future local learning components. Provider-specific credentials must remain server-side and must not become part of the user-facing identity.

## 4. Memory layer

Memory is separate from model weights. Early memory may include:

- User-approved facts.
- Preferences.
- Conversation summaries.
- Corrections.
- Project notes.
- Explicitly marked temporary context.
- UXI preferences and saved workspace definitions.

Memory should be inspectable, editable, exportable, bounded, and deletable. The system must distinguish remembered information from verified information and model-generated assumptions.

## 5. Tool boundary

Tools such as filesystem access, GitHub operations, search, or device functions must be exposed through explicit, permissioned interfaces. The model should not receive unrestricted access merely because it can generate text.

Every privileged tool should define:

- What it can read.
- What it can change.
- Which user approval is required.
- What audit record is created.
- How an action can be reversed.

## 6. Change proposal and evolution layer

Evolution begins as a proposal process, not silent self-rewriting. A proposal may request a prompt adjustment, memory-schema change, UXI change, new capability, or code modification.

A consequential proposal should move through:

1. Explanation of the reason.
2. Identification of affected components.
3. Risk classification.
4. Snapshot or backup.
5. Validation and tests.
6. Explicit user approval.
7. Application and audit record.
8. Rollback path.

## 7. Runtime layer

The runtime is responsible for starting, stopping, supervising, and recovering services. Runtime changes should be treated as high-impact operations. A future “Agree to Change” flow may coordinate snapshot, shutdown, update, validation, restart, and restore if validation fails.

## Important distinction

A system can learn through memory, feedback, retrieval, controlled configuration, and UXI adaptation without changing its executable code. That distinction is central to keeping the first implementation safe and understandable.
