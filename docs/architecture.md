# Architecture

The initial architecture is deliberately modular. Each layer should have a clear responsibility so the system can evolve without becoming one opaque application.

## Proposed layers

```text
User
  ↓
Interface layer
  ↓
Conversation / orchestration layer
  ├── Model gateway
  ├── Memory service
  ├── Tool boundary
  └── Change proposal system
          ↓
   Validation / approval / rollback
```

## 1. Interface layer

The interface may be a web app, avatar UI, desktop shell, mobile UI, or future operating-system surface. It should not own the model, long-term memory, or privileged operations.

Responsibilities:

- Display conversation and system state.
- Collect user input and consent.
- Show proposed changes clearly.
- Present errors and recovery options.

## 2. Conversation and orchestration layer

This layer coordinates a request from the interface. It decides what context is needed, calls the selected model provider, retrieves relevant memory, and returns a structured response.

It should enforce:

- Request limits.
- Cancellation.
- Context-size bounds.
- Session and identity checks.
- Logging appropriate to the user’s privacy settings.

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

Evolution begins as a proposal process, not silent self-rewriting. A proposal may request a prompt adjustment, memory-schema change, UI change, new capability, or code modification.

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

A system can learn through memory, feedback, retrieval, and controlled configuration without changing its executable code. That distinction is central to keeping the first implementation safe and understandable.
