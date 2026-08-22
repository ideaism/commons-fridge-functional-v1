# Commons Fridge Functional Prototype v1.2 · Chinese build

Public static deployment of the Commons Fridge functional demonstrator.

## Evidence boundary

This is a researcher-tested technical demonstrator using fictional local-browser data. It has not been usability-tested with participants and does not establish adoption or food-waste reduction.

## Routes

- Add: `#add`
- Manage: `#manage`

Both are URL hash fragments resolved in the browser. The server returns the same document for all three addresses, so a `200` response does not by itself prove that each NFC tag lands on the intended screen — that has to be confirmed on a real phone.

## Data

Demo state is stored only in the current browser under the scoped `localStorage` key `commons-fridge-functional-v1`. The page has no account, cloud database, camera, upload, analytics or external runtime dependency.

Ownership is persisted as stable keys (`personal` / `shared` / `ask`) rather than display text, so records saved by earlier versions migrate automatically and switching interface language does not invalidate them.

## Source snapshot

- Version: Functional Prototype v1.2, Chinese build
- Source SHA-256: `425dcda056fb3fce5c16a84f7d7f21943634d3f5d33f06c9f4e0edcc6219da3e`
- Published: 2026-08-22
- Supersedes: v1.0 (`619332ed…`, published 2026-08-21)

## Version history

| Version | Published | Notes |
|---|---|---|
| v1.0 | 2026-08-21 | First public build. English data labels, Chinese interface chrome. |
| v1.2 | 2026-08-22 | Chinese build. Ownership keys separated from display text; quick-pick item entry; step completion marks; character counter; focus moved to the failing control on validation; reset confirmation. |

The complete academic project remains in a separate private repository.
