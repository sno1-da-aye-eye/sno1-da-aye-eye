# Sno1 Da Aye Eye — Project State

## Purpose

Sno1 Da Aye Eye explores a small, adaptable learning model that evolves uniquely through interaction with its user. The user and model participate in that evolution symbiotically.

## Current repository state

This repository is currently being prepared as the canonical project workspace. The original Grok-derived build will be imported as an immutable reference before implementation decisions are made.

## Working architectural direction

- Separate the base inference/model layer from user-specific evolving state.
- Treat interaction as the source of candidate learning.
- Make retention explicit, inspectable, correctable, and persistent.
- Prove a minimal end-to-end learning loop before attempting custom model training.

## Immediate milestone

### v0.1 — Persistent learning loop

1. Accept a user interaction.
2. Produce a candidate knowledge item.
3. Allow confirmation, correction, or rejection.
4. Persist accepted knowledge for a specific user.
5. Retrieve the knowledge in a later interaction.
6. Add tests proving that later context changes as a result.

## Open questions

- What exactly is contained in the original Grok-derived export?
- Which runtime, framework, and model interface does it use?
- Which memory, retrieval, or adaptation mechanisms are already implemented?
- Which parts are proprietary or opaque external services?
- Which interface patterns should be retained, especially parallel interaction patterns?

## Status

Concept: established  
Repository implementation: not yet audited  
Reference build: awaiting import  
Persistent learning loop: not yet implemented
