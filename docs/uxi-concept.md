# UXI Concept

## Definition

**UXI** means **User eXchange Interface**.

It is the shared exchange environment through which a user and an AI communicate, work, teach one another, and shape the tools used during their interaction.

The UXI includes conventional interface elements, but is not limited to a chat window, avatar, or fixed application layout.

## Two-way evolution

The UXI evolves in both directions:

### User shapes the UXI

The user can:

- State preferences.
- Request different ways of seeing information.
- Save useful layouts.
- Reject confusing or unnecessary components.
- Teach the system how tasks are performed.
- Define boundaries around automation and permissions.

### AI proposes UXI improvements

The AI can:

- Notice that a task needs a different presentation.
- Generate a structured component proposal.
- Assemble existing components into a temporary workspace.
- Suggest a reusable personal interface.
- Explain why a new view may help.
- Learn from the user’s acceptance, rejection, and corrections.

## Example

A user asks for help researching family history. Instead of returning only prose, the AI may propose:

- A chronological timeline.
- A family-tree canvas.
- A source-evidence panel.
- A place-and-date filter.
- A notes editor.

The first version can generate these as temporary session UI. If the user finds the arrangement useful, it may propose saving the workspace as a personal template.

## Safety and implementation boundary

The AI should produce declarative UI descriptions using a known schema. The renderer decides which components, properties, events, and data bindings are permitted.

A UI description should not automatically be allowed to:

- Execute arbitrary JavaScript.
- Access secrets.
- Read private files without permission.
- Change operating-system settings.
- Install software.
- Modify its own security boundary.

A component that needs a privileged action should call a defined tool contract and pass through the relevant approval process.

## UXI maturity levels

1. **Static UXI:** human-designed chat and avatar shell.
2. **Composable UXI:** AI can select and arrange approved components.
3. **Personalised UXI:** user-approved layouts and workflows persist.
4. **Proposed UXI evolution:** AI can suggest new component types or renderer capabilities.
5. **Controlled system evolution:** reviewed code changes can expand the UXI after snapshot, validation, approval, and rollback preparation.

The project should progress through these levels gradually rather than beginning with arbitrary generated code.
