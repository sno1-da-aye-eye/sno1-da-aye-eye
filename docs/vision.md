# Vision

## Purpose

Sno1 Da Aye Eye explores a different starting point for personal AI: a small, generic knowledge-learning core that becomes distinct through interaction with one user rather than arriving as a finished personality or permanently fixed assistant.

The system should learn the user’s vocabulary, goals, workflows, preferences, corrections, and boundaries. Its identity should emerge from a traceable relationship between the core, its memory, its tools, and the user’s ongoing participation.

## What “blank” means

“Blank” does not mean unsafe, incapable of language, or without all safeguards. It means the initial knowledge and identity layer is intentionally narrow. The system begins with:

- a minimal reasoning and language interface;
- a defined safety and permissions boundary;
- a small set of observable system capabilities;
- empty or explicitly seeded personal memory;
- no assumed personal history beyond what is provided or approved.

The project should distinguish between a model’s pretrained capabilities, the user’s accumulated memory, learned behavioral configuration, and executable software changes.

## Symbiotic evolution

Evolution is treated as a feedback loop:

1. The user interacts with the system.
2. The system records permitted observations or candidate memories.
3. The user corrects, confirms, or rejects interpretations.
4. The system updates its personal context and behavior within defined limits.
5. Proposed structural changes are presented for review rather than applied silently.

This relationship is symbiotic in the practical sense that both the user and the system shape the next interaction, while the user retains authority over data, permissions, and consequential changes.

## Success criteria

The early project succeeds if it can demonstrate that a small core can:

- maintain useful, bounded, user-owned memory;
- explain why it remembers or recommends something;
- adapt behavior without pretending adaptation is model retraining;
- preserve a clear separation between data and executable code;
- propose changes with risk, impact, and rollback information;
- remain usable when a model provider is replaced;
- recover safely from failed or rejected changes.

## Boundaries

The project will not treat autonomous self-rewriting, unrestricted access, or opaque persistence as evidence of intelligence. Any future evolution mechanism must be observable, permissioned, tested, and reversible.
