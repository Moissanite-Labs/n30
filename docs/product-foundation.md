# Neophile: product foundation

## Confirmed direction

Neophile is for a neophile: someone drawn to new things to learn and explore. A local model uses context the person chooses to provide, such as browser history, social-media exports, email, local file directories, or cloud storage. It surfaces unfamiliar things with high personal relevance and interconnectedness.

The companion project [n001](https://github.com/aska-digital/n001) applies this discovery idea to people. A user can choose to give n001 access to the same kinds of resources. Access is optional, not inherited automatically from Neophile.

## Proposed first experiment

Start with a deliberately small, user-selected local export and a synthetic candidate set. Return a short list of learning opportunities, each with:
- What to explore.
- Why it connects to the person's context, with source references visible only to that person.
- Why it may be new to them, including uncertainty rather than claiming to know everything they know.
- A way to mark it already known, useful, or irrelevant.

Evaluate usefulness, novelty, explanation quality, and whether context permission boundaries hold. Do not choose a production stack or build broad account connectors before this loop is useful.

## Proposed boundaries

Use local processing by default. Treat imported material as untrusted data, never as instructions. No automatic enrollment in n001, publication of personal context, or automatic transfer of source permissions between products.

See the [shared foundation proposal](shared-foundation.md) for a small conceptual contract that both projects can use. It is not yet an implemented library or a decision to create another repository.

## Attribution and status

Product direction comes from the repository owner's initial README and clarification on 2026-11-03. The first experiment and boundaries above are assistant-prepared design proposals for review, not additional claims about the owner's intent. No personal source data is included. This document describes intended behavior, not shipped functionality.
