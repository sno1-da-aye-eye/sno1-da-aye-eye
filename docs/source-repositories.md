# Source Repositories

This document records the existing material that may contribute to the incubation project. These sources are treated as prototypes to inspect and integrate—not as unquestioned production foundations.

## `snowan-da-aye-eye`

This prototype contains the strongest starting point for the backend conversation flow.

Observed responsibilities include:

- Companion-oriented conversation logic.
- Server-side xAI/Grok integration.
- Streaming responses.
- Request cancellation.
- Bounded conversation context.
- Session or device validation.
- Local browser storage and conversation handling.
- Conversation compaction or “seasoning” concepts.

### What it contributes

- A working provider-backed conversation path.
- Early examples of bounded context and local memory.
- Server-side handling of provider credentials.
- A useful reference for the future model gateway and memory boundary.

### What still needs work

- Provider abstraction.
- Clear separation between temporary context and durable memory.
- Portable storage independent of one browser session.
- Tests and operational documentation.
- A controlled evolution/proposal system.

## `ai-avatar-ui`

This prototype contains a frontend/avatar experience built around React, TypeScript, Vite, Tailwind, and Lucide icons.

Observed responsibilities include:

- Avatar presentation states such as idle, listening, thinking, and speaking.
- Chat panel and message display.
- Theme, accent, bubble, and background settings.
- Local camera and call-style interface elements.
- A responder interface that can be connected to a real backend.

### What it contributes

- A reusable interface shell.
- A clear separation point through an `AIResponder`-style interface.
- Visual state handling that can later reflect model activity.

### What still needs work

- Replace the mock responder with a backend adapter.
- Add streaming support.
- Define authentication and permission behavior.
- Avoid placing privileged logic in the browser.
- Connect avatar state to real request lifecycle events.

## Integration direction

The likely first integration is:

```text
Avatar UI
  → responder adapter
  → companion API
  → model gateway
  → selected provider
  → streamed response
  → avatar and chat state
```

The first integration should not merge every feature at once. It should prove one complete request path, then add memory, tools, and controlled evolution separately.

## Missing or uncertain material

A live Grok application may contain additional configuration or interface behavior that is not present in the exported source archives. Such material should be recovered only through an explicit export or inspection process. It should not be assumed to exist in this repository until verified.
