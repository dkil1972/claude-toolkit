# Default Spec Conventions

Use these conventions when the target project has no existing spec files.

## Directory Structure

```
docs/specs/<feature-slug>/
├── OVERVIEW.md
├── <PREFIX>-<NNNN>-<slug>.md
├── <PREFIX>-<NNNN>-<slug>.md
└── ...
```

- `<feature-slug>` — kebab-case feature name (e.g. `cv-braindump-integration`)
- `<PREFIX>` — project abbreviation, uppercase (e.g. `JST`, `APP`). Ask the user what prefix to use.
- `<NNNN>` — zero-padded sequential number, continuing from the highest existing spec number or starting at `0001`
- `<slug>` — kebab-case summary of the spec (e.g. `add-file-attachment`)

## OVERVIEW.md Template

```markdown
# <Feature Name> - Overview

## Problem Statement

<What is the current situation and why does it need to change? Be concrete — describe observed behaviour, not abstract goals.>

## Goals

1. <Goal one>
2. <Goal two>
3. ...

## Architecture / Approach

<How the feature works. Include user flow, system interactions, and key design decisions with rationale. Use diagrams where they add clarity.>

## Scope

| Spec | Title |
|------|-------|
| `<PREFIX>-<NNNN>-<slug>.md` | <Short title> |
| ... | ... |

## Builds On

- <Existing work this depends on>

## Constraints

- <Technical constraints, things that must not change, invariants>
```

## Individual Spec Template

```markdown
# <PREFIX>-<NNNN>: <Title>

Status: Pending

## Description

<What this spec delivers and why. 2-3 sentences.>

## Problem

<What's wrong or missing today. Skip this section if the spec is purely additive.>

## Changes Required

### 1. <First change area>

<Description of what needs to change, with enough detail for an implementer.>

### 2. <Second change area>

<...>

## Acceptance Criteria

- [ ] <Specific, testable criterion>
- [ ] <...>

## Dependencies

- <Spec ID> (<brief description of the dependency>)

## Complexity

<Low / Medium / High> — <Brief justification, 1 sentence.>
```

## Guidelines

- **Status values**: `Pending`, `In Progress`, `Implemented`
- **Complexity values**: `Low` (single file or straightforward change), `Medium` (multiple files, async flows, or non-trivial logic), `High` (architectural change, cross-cutting concerns, or significant risk)
- **One spec per PR**: Each spec should represent a unit of work that can be implemented and reviewed as a single pull request
- **Acceptance criteria**: Should be checkboxes, specific enough that someone can unambiguously determine pass/fail
- **Skip empty sections**: If a spec has no dependencies or no problem section, omit them rather than leaving empty headings
