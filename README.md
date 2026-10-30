# InitWatch

**A heat-action and buddy check-in system for outdoor workers.**
*Walang maiiwan sa init. No worker left unchecked in the heat.*

**Live presentation:** https://lyle-leif.github.io/InitWatch/

---

## About

Extreme heat is a growing danger for Filipinos who work outdoors. PAGASA's "danger" heat index (42–51 °C) is being forecast across the country, and a strong El Niño is expected to last into the first half of 2027. Guidance exists, but someone still has to organize protection during an actual workday and check on workers who may be unable to ask for help.

InitWatch is a mobile-first web app for small outdoor work teams that turns heat forecasts into protective action:

**Warn ahead → Plan the shift → Check in during high-heat hours → Notify a buddy → Record follow-up**

## Key features

| | Feature | What it does |
|---|---|---|
| A | Location-based heat outlook | Hourly heat index with PAGASA categories, sources and update times |
| B | Advance heat alerts | Evening-before alert, morning briefing, pre-peak reminders; check-ins start automatically at Danger |
| C | Shift heat-action planner | Suggests lower-heat task windows, shaded rest, water and buddy checks |
| D | Guided acclimatization tracker | Gradual exposure for new and returning workers, based on NIOSH guidance |
| E | Worker check-ins and assistance requests | "Okay ako" or "I need help", no lengthy forms |
| F | SOS location share | One-time location pin on a help request, never continuous tracking |
| G | Buddy notifications and follow-up | Missed check-ins and help requests reach a person; unacknowledged ones escalate to the supervisor |
| H | Supervisor action dashboard | Active shifts, precautions, acclimatization progress, unresolved cases |
| I | Incident record | Exportable logs to support DOLE workplace documentation |
| J | Filipino and English safety guide | Warning signs and first steps, available offline |

## Planned technology

- **Frontend:** React + TypeScript, Progressive Web App
- **Backend:** Node.js + PostgreSQL
- **Weather:** Open-Meteo hourly forecasts, classified with PAGASA heat index categories
- **Notifications:** In-app and Telegram bot (Facebook Messenger planned)
- **Location:** Browser geolocation, one-time only on help requests

No custom hardware required. Full details are in the [Product Requirements Document](PRD.md).

## Repository contents

| File | Description |
|---|---|
| `index.html` | The proposal presentation: a single self-contained web deck |
| `PRD.md` | Product requirements: problem, users, features, requirements, evaluation |
| `README.md` | This file |
| `.nojekyll` | Tells GitHub Pages to serve the files as-is |

## Viewing the presentation

Open the [live presentation](https://lyle-leif.github.io/InitWatch/), or download `index.html` and open it in any browser.

| Key | Action |
|---|---|
| Scroll, ← → ↑ ↓, Space | Next / previous slide |
| O | All slides |
| N | Speaker notes |
| F | Fullscreen |
| Esc | Close notes or overview |

On phones and portrait tablets the deck becomes a scrolling page.

## Status

Proposal stage. The next step is a prototype covering one complete worker–buddy–supervisor workflow, evaluated through a small pilot with one outdoor team and controlled scenarios.

## Team 16

- Alvarez, John Allen
- Bantayaon, Jeush Samuel L.
- De Galicia, Phebe A.
- Esguerra, Lyle Daniel
- Ordiales, Samuel

*Theme: Build the Way Forward*
