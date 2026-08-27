# Commons Fridge Functional Prototype v1.6 · bilingual build

Public static deployment of the Commons Fridge functional demonstrator.

## Evidence boundary

This is a researcher-tested technical demonstrator using fictional local-browser data. It has **not** been usability-tested with participants and does not establish adoption or food-waste reduction. Five interviews support the problem and habit framing only.

## English and Chinese in one file

Both language tables ship inside the same single HTML file and are switched at runtime from the button beside the reset control in the header. The first visit follows the browser language; after that the choice is remembered locally. Switching re-seeds the fictional demo records so they read naturally in either language — anything a viewer typed themselves is left exactly as written, because that is content, not interface.

## What v1.6 adds

v1.5 brought location in as the carrier of ownership. v1.6 completes the lifecycle around it.

- **Move to freezer** — the most common salvage move described in the interviews. It cancels the current plan and the record goes quiet. Nothing is claimed about how long frozen food keeps; that is about the food, not the plan.
- **Anyone can take this** — offering something for a day, two days, or with no limit. This never changes ownership: *shared* means the thing belongs to everyone, *anyone can take this* means it is still mine and you may have it. When the window closes the record simply returns to normal — no notice, no prompt, no trace.
- **Moving out** — a four-step handover: tick what you will finish, hand the rest over for anyone to take, mark your zones as freeing up, then see what the house sees. Anything nobody takes does not quietly vanish; it becomes *not sure whose* and stays visible, which is what actually happened in the interviews.
- **Fridge setup** — a three-step pass for the start of a tenancy: name the places in your own words, say what kind each is, and optionally agree three things. Agreements are shown at the foot of the house view as what the household said, never as a rule the app enforces.
- **Before you shop** — a read-only screen answering three questions before leaving: what to eat first, what the house already has, and where there is still room. Nothing on it changes anything.
- **Days in the fridge** on every record, and a **this one is full** marker per zone that a person sets themselves — there is no sensor and none is implied.
- Quick entry is split into **things I usually eat soon** and **things I leave open**, with different defaults. The two headings describe how someone plans to note things, never what the food is doing.

Throughout, the subject of every sentence is a plan or a thing, never a person, and there are no names, avatars or initials anywhere in the build.

## Not synced, and it says so

The House view shows fictional records held in **this one browser**. There is no server and no account, for the same reason the project dropped writable NFC tags: they would create access logs, timestamps and device data. The interface states this on screen, permanently and unfoldably — and the build refuses to compile if the House view is present without that disclosure, in either language.

## Routes

`#add` · `#found` · `#manage` · `#shop` · `#moveout` · `#setup`

All are URL hash fragments resolved in the browser. The server returns the same document for every address, so a `200` response does not by itself prove that each NFC tag lands on the intended screen — that has to be confirmed on a real phone.

## Data

Stored only in the current browser under `commons-fridge-functional-v1` (records), `…-v1-zones` (areas), `…-v1-settings` (agreements), `…-v1-fish` and `…-v1-lang`. No account, cloud database, camera, upload, analytics, timer or notification API.

Ownership, plan and zone kind are persisted as stable keys rather than display text, so records saved by earlier versions migrate automatically and switching language never invalidates them. Fields introduced in later versions stay empty on older records rather than being guessed.

## Source snapshot

- Version: Functional Prototype v1.6, bilingual build
- Source SHA-256: `16c6ebe7f49eced82484939f4d330b0aad0f984311777fc9dd33eedde4d5eefa`
- Published: 2026-08-26, re-published 2026-08-27 (illustration only — see below)
- Previous build: `b42d3f9f…`
- Supersedes: v1.5 English build (`c423db7c…`, published 2026-08-26)

## Version history

| Version | Published | Notes |
|---|---|---|
| v1.0 | 2026-08-21 | First public build. English data labels, Chinese interface chrome. |
| v1.2 | 2026-08-22 | Chinese build. Ownership keys separated from display text; quick-pick entry; reset confirmation. |
| v1.4 | 2026-08-26 | English build. Reminder flag replaced by user-declared plans; batch entry; attention-first sorting; shared mascot. |
| v1.5 | 2026-08-26 | Zones carrying ownership; House view grouped by area; found-something entry; 48-hour grace period and self-erasing receipt; opened-restarts-the-plan; away mode. |
| v1.6 | 2026-08-26 | Bilingual in one file, switchable from the header. Freezer, time-limited offering, move-out handover, tenancy setup, before-you-shop view, days in the fridge, per-zone fullness, split quick entry. |
| v1.6 · re-published | 2026-08-27 | Illustration only. *Before you shop* and *found something* had shipped with typographic glyphs (`◷` and `?`) while the two original entries carried the penguin; all four home entries now carry the character. No route, record, string or capability changed, so the version number did not move — but the file did, and that is why this row exists. |

The complete academic project remains in a separate private repository.
