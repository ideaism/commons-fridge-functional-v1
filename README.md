# Commons Fridge Functional Prototype v1.5 · English build

Public static deployment of the Commons Fridge functional demonstrator.

## Evidence boundary

This is a researcher-tested technical demonstrator using fictional local-browser data. It has **not** been usability-tested with participants and does not establish adoption or food-waste reduction. Five interviews support the problem and habit framing only.

## What v1.5 changes

v1.4 recorded a plan the user declared about themselves. That works for one person on one device — but the failures described in the interviews are almost all between people: the leaking vegetables nobody owned, the bottle of milk nobody claimed for three months, the frozen food a departing housemate left behind. None of those things had ever been logged by anyone.

v1.5 brings **location** back in, and lets it carry ownership.

Housemates already use position to decide whose food is whose — a personal shelf, a shared door, a first-come freezer drawer. v1.5 puts that existing arrangement on screen instead of inventing a new one.

- **Zones** — records can name the area they are in. Areas are typed as personal, shared or first-come, and each type behaves differently: something placed in a shared area starts as *not sure whose* and is nudged once for an owner, because that is exactly where things stop being traceable.
- **House view** — the list can be grouped by area rather than kept private to whoever typed it in. Groups are areas, never people.
- **Found something** — a third entry point for noting an item you did not put there and cannot attribute. Ownership is locked to *not sure whose*. The record does not tag anyone and nobody is chased to claim it; claiming is a single voluntary button.
- **Grace period and receipt** — anyone can say *I will handle this*, which holds the record for 48 hours so anyone else can say *leave it*. After that the clear action becomes primary. A handled record leaves a receipt that erases itself after 48 hours, so the system never accumulates a record of who did what.
- **Opened** — restarts the plan from the moment something is opened, which is where most of the described accidents actually happened.
- **I'm away** — pauses plans while someone is travelling or overloaded. Paused time is not counted, so coming home does not mean coming home to a screen of overdue labels.

Throughout, the subject of every sentence is a plan or a thing, never a person. There are no names, avatars or initials anywhere in the build.

## Not synced, and it says so

The House view shows fictional records held in **this one browser**. There is no server and no account, for the same reason the project dropped writable NFC tags: they would create access logs, timestamps and device data. The interface states this on screen, permanently and unfoldably, rather than in a footnote — and the build refuses to compile if the House view is present without that disclosure.

## Routes

- Add: `#add`
- Found something: `#found`
- Manage: `#manage`

All are URL hash fragments resolved in the browser. The server returns the same document for every address, so a `200` response does not by itself prove that each NFC tag lands on the intended screen — that has to be confirmed on a real phone.

## Data

Stored only in the current browser under `commons-fridge-functional-v1` (records), `…-v1-zones` (areas) and `…-v1-fish`. No account, cloud database, camera, upload, analytics, timer or notification API.

Ownership, plan and zone kind are persisted as stable keys rather than display text, so records saved by earlier versions migrate automatically and switching interface language does not invalidate them. Records saved before v1.5 have no area, no opened time and no paused time; those stay empty rather than being guessed.

## Source snapshot

- Version: Functional Prototype v1.5, English build
- Source SHA-256: `c423db7cd87397b1584316ff551d54a889690a2f3850394dda08ecf670fc2c0d`
- Published: 2026-08-26
- Supersedes: v1.4 English build (`9111fd3f…`, published 2026-08-26)

## Version history

| Version | Published | Notes |
|---|---|---|
| v1.0 | 2026-08-21 | First public build. English data labels, Chinese interface chrome. |
| v1.2 | 2026-08-22 | Chinese build. Ownership keys separated from display text; quick-pick entry; step marks; character counter; reset confirmation. |
| v1.4 | 2026-08-26 | English build. Reminder flag replaced by user-declared plans; batch entry; records needing attention sorted first; shared mascot reflecting the fridge rather than an individual. |
| v1.5 | 2026-08-26 | Zones carrying ownership; House view grouped by area; a found-something entry point for unattributable items; 48-hour grace period and self-erasing handled receipt; opened-restarts-the-plan; away mode that does not count paused time. |

The complete academic project remains in a separate private repository.
