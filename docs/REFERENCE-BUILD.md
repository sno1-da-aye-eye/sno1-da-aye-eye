# Grok-Derived Reference Build

## Purpose

This directory and its associated branch are reserved for the clean export of the Grok-derived build that preceded the current Sno1 Da Aye Eye project.

## Handling rules

- Preserve the imported reference unchanged wherever possible.
- Do not mix reference code with the evolving Sno1 implementation.
- Record the source, export date, commit, and any modifications separately.
- Remove secrets, API keys, tokens, credentials, and private user data before import.
- Treat undocumented behaviour as unverified until inspected.

## Planned import location

```text
reference/grok-build/
```

## Audit checklist

- [ ] Import clean export
- [ ] Record source and provenance
- [ ] Inventory files and dependencies
- [ ] Identify runtime and entry points
- [ ] Identify model/API integrations
- [ ] Identify memory and persistence mechanisms
- [ ] Identify learning or adaptation mechanisms
- [ ] Document interface and interaction flow
- [ ] Mark proprietary or opaque dependencies
- [ ] Produce feature comparison against Sno1 Da Aye Eye

## Comparison outputs

- `docs/architecture-diff.md`
- `docs/feature-matrix.md`
- `docs/decisions.md`
