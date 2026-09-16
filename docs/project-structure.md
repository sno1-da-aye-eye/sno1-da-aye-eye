# Sno1 Da Aye Eye — Project Structure

## Purpose

This document defines the initial separation between the Sno1 Da Aye Eye core application and the UXI layer.

## Architectural model

Sno1 Da Aye Eye is the core application: the protected foundation responsible for model interaction, memory, orchestration, tools, permissions, identity, and controlled evolution.

UXI (User eXchange Interface) is the adaptable layer above the core. It is the shared environment through which the user and AI communicate, collaborate, and shape how the system is presented and used.

```text
Sno1 Da Aye Eye
├── core/       Protected application foundation
├── uxi/        Adaptable user–AI exchange layer
├── packages/   Shared contracts and reusable components
├── services/   Optional service boundaries
├── docs/       Architecture and project documentation
└── experiments/ Early, isolated research
```

## Adaptation and agreement

UXI adaptation is governed by three levels:

1. **Automatic adaptation** — low-risk, reversible presentation changes.
2. **Proposed adaptation** — changes that the AI suggests and the user accepts or rejects.
3. **Explicitly authorised change** — changes affecting permissions, executable behaviour, memory rules, core constraints, or system boundaries.

The UXI may evolve within its permitted schema and capabilities. Changes to those capabilities require explicit authorisation, validation, versioning, and rollback support.

## Initial implementation principle

We will begin with documentation and directory boundaries before introducing application code. Empty conceptual areas will be represented by small README files until implementation is justified.
