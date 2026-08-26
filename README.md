# Commons Fridge Functional Prototype v1.4 · English build

Public static deployment of the Commons Fridge functional demonstrator.

## Evidence boundary

This is a researcher-tested technical demonstrator using fictional local-browser data. It has **not** been usability-tested with participants and does not establish adoption or food-waste reduction. Five interviews support the problem and habit framing only.

## What v1.4 changes

v1.4 replaces the reminder flag with a **plan the user declares about themselves**.

Earlier builds asked whether to "set a reminder" and then never reminded anyone — the interface promised something the system could not do. v1.4 removes that promise and records intent instead: *Eating soon* (3 days), *This week* (7 days), or *Not sure* (the default, which never surfaces anything).

An item is surfaced once roughly two-thirds of its own plan has passed. Nothing is inferred about the food itself, so the build needs no expiry date and makes no food-safety judgement.

There is no push notification. The reminding surface is the fridge and the next person who opens the page — records that need attention sort to the top and are named without a person as the subject.

## Routes

- Add: `#add`
- Manage: `#manage`

Both are URL hash fragments resolved in the browser. The server returns the same document for all three addresses, so a `200` response does not by itself prove that each NFC tag lands on the intended screen — that has to be confirmed on a real phone.

## Data

Demo state is stored only in the current browser under the scoped `localStorage` key `commons-fridge-functional-v1`. The page has no account, cloud database, camera, upload, analytics, timer, notification API or external runtime dependency.

Ownership is persisted as stable keys (`personal` / `shared` / `ask`) and plans as stable keys (`soon` / `week` / `open`) rather than display text, so records saved by earlier versions migrate automatically and switching interface language does not invalidate them.

Records saved by v1.0 and v1.2 carry no timestamp. On migration their plan clock starts at the moment of migration rather than at some inferred past date, so upgrading never makes a record look overdue that the user was never told about.

## Source snapshot

- Version: Functional Prototype v1.4, English build
- Source SHA-256: `9111fd3f4d63f7a8d4f6b60596fe79e7256932bbe7194d13581a8debf0b30aff`
- Published: 2026-08-26
- Supersedes: v1.2 Chinese build (`425dcda0…`, published 2026-08-22)

## Version history

| Version | Published | Notes |
|---|---|---|
| v1.0 | 2026-08-21 | First public build. English data labels, Chinese interface chrome. |
| v1.2 | 2026-08-22 | Chinese build. Ownership keys separated from display text; quick-pick item entry; step completion marks; character counter; focus moved to the failing control on validation; reset confirmation. |
| v1.4 | 2026-08-26 | English build. Reminder flag replaced by user-declared plans; batch entry replacing one-item-at-a-time logging; records needing attention sorted first; shared mascot reflecting the state of the fridge rather than an individual's performance. |

The complete academic project remains in a separate private repository.
