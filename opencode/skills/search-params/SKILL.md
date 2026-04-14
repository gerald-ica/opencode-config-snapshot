---
name: search-params
description: URL search param and hash state management. Use when adding or modifying URL search params, `useSearchParams`, `setSearchParams`, `useSearchParamState`, or hash-based navigation, especially when back-button behavior matters.
license: MIT
---

# Search Params

Use this skill for:

- `/Users/wendyly/.local/share/agent-skills/external/promptfoo`
- other React apps with URL-driven state

## Decision Rule

Choose history behavior based on whether the change is in-page state or a user-navigable step:

- In-page state:
  - filters
  - sort
  - pagination
  - tabs
  - search queries
  - Use `replace`
- Navigable step:
  - wizard progression
  - multi-step forms
  - Use `push`

If unclear, ask rather than guessing.

## Preferred Patterns

### Single param

Use a validated helper like `useSearchParamState` when available.

### Multiple params

Use `setSearchParams(..., { replace: true })` for in-page state changes.

### Hash navigation

- Use push for actual step progression.
- Use replace for non-navigational in-page state.

### URL normalization after save

When updating the URL after a create/save side effect, use `replace`.

## Anti-Patterns

- Pushing every filter or tab change into browser history
- Managing a single param manually without validation when a helper hook exists
- Using empty strings instead of `null` when clearing params in typed helpers

## Review Focus

- back/forward button behavior
- param validation
- consistent replace vs push semantics
- avoiding history clutter for in-page state
