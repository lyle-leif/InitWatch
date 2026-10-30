# InitWatch — Product Requirements Document

**A heat-action and buddy check-in system for outdoor workers**
*Walang maiiwan sa init. No worker left unchecked in the heat.*

| | |
|---|---|
| **Team** | Team 16 — Alvarez, John Allen · Bantayaon, Jeush Samuel L. · De Galicia, Phebe A. · Esguerra, Lyle Daniel · Ordiales, Samuel |
| **Theme** | Build the Way Forward |
| **Status** | Proposal — prototype planned |
| **Document version** | 1.0 |

---

## 1. Summary

InitWatch is a mobile-first web application that helps small outdoor work teams prepare for dangerous heat, reduce avoidable heat exposure, support gradual acclimatization, and make sure no worker is left unchecked.

It follows one continuous workflow:

**Warn ahead → Prepare a shift action plan → Check on workers during high-heat hours → Notify a designated buddy → Record follow-up**

## 2. Problem

Extreme heat is a growing danger for Filipinos whose work happens outdoors.

- On May 20, 2026, PAGASA forecast 40 areas to reach a "danger" heat index (42–51 °C). On October 22, 2026, Talisay, Batangas recorded 41 °C ("extreme caution").
- DOST-PAGASA (September 23, 2026) reported a strong El Niño expected to intensify and persist into the first half of 2027, with possible record-high temperatures and heat index.
- The DOH recorded 77 heat-related illness cases, including 7 reported deaths, from January 1 to April 29, 2024. These figures are likely undercounted: many people with heat illness never reach a hospital, and a construction workers' union leader said official counts miss what happens on the ground.

Guidance already exists. DOLE Labor Advisory No. 8 (2023) recommends drinking water, adjusted breaks and work arrangements, heat-stress education, and emergency procedures. In October 2026, DOLE announced four forthcoming labor advisories for the El Niño period, including making work-related heat stroke, heat cramps and heat exhaustion compensable through the Employees' Compensation Commission (ECC).

The gaps:

1. **Coordination.** Someone has to prepare the shift, identify workers who need extra precautions, check on team members, and follow up.
2. **Workers who can't ask for help.** Heat stroke can cause confusion, disorientation and loss of consciousness (DOH). In a reported case in Dagupan City, a construction worker who complained of headaches from the heat was later found dead in the site's rest area; police suspected heat stroke.
3. **New and returning workers.** NIOSH recommends increasing heat exposure gradually over 7–14 days with close supervision. A forecast alone can't show a worker's recent exposure history.
4. **Existing tools inform but don't organize.** PAGASA's iHeatMap and the OSHA-NIOSH Heat Safety Tool provide forecasts, precautions and acclimatization information, but not shift plans, buddy checks or acknowledged follow-up.

> **Problem statement:** There is a gap between knowing that heat is dangerous and organizing protective action during an actual workday, including following up on workers who may be unable to ask for help.

## 3. Goals and non-goals

### Goals
- Warn supervisors and workers **before** heat becomes dangerous.
- Turn forecasts into **practical, shift-specific precautions**.
- Support **gradual acclimatization** for new and returning workers.
- Ensure every unanswered check-in or help request reaches **a person who acknowledges it**.
- Keep **records** that support workplace documentation in line with DOLE's heat advisories.
- Work in **Filipino and English**, with key safety guidance available offline.

### Non-goals
- Diagnosing heat illness or giving medical treatment advice beyond published first-aid guidance.
- Certifying acclimatization from a day count.
- Continuous location tracking of workers.
- Custom hardware or wearables (later extension only).
- SMS delivery in the prototype (needs a funded channel).
- Replacing emergency services. The app always directs users to seek immediate help in an emergency.

## 4. Users

| User | Description | Primary needs |
|---|---|---|
| **Worker** | Member of a small supervised outdoor team (campus grounds and maintenance, construction, agriculture) | Know when heat is dangerous, follow the shift plan, answer check-ins quickly, ask for help easily |
| **Designated buddy** | A coworker assigned to check on a worker | Be notified when a worker needs help or stops responding, acknowledge, record what was done |
| **Foreman / supervisor** | Organizes the shift and the team | Advance warning, a practical shift plan, acclimatization status, a view of unresolved cases, exportable records |

**Pilot scope:** one outdoor work team in one locality, recruited during development.
**Future beneficiaries:** students, commuters, drivers, and informal or solo outdoor workers such as delivery riders and vendors, through adaptations after the worker prototype is evaluated.

## 5. User stories

- As a **supervisor**, I get an alert the evening before a dangerous day so I can adjust tomorrow's plan.
- As a **worker**, I get a morning briefing in Filipino or English with peak hours, my buddy, and water and shade locations.
- As a **supervisor**, I enter the work area, hours, tasks and exposure conditions and get suggested precautions and lower-heat task windows.
- As a **new worker**, my exposure is increased gradually and my buddy checks on me more often.
- As a **worker**, I answer a check-in with one tap, or request help without filling out a form.
- As a **buddy**, I'm notified when my coworker asks for help or misses a check-in, and I can acknowledge and record what I did.
- As a **supervisor**, I'm alerted if a buddy doesn't acknowledge in time, and I can see every unresolved case.
- As a **supervisor**, I can export incident records for workplace documentation.

## 6. Functional requirements

Heat information uses **PAGASA heat index categories**: Caution 27–32 °C · Extreme caution 33–41 °C · Danger 42–51 °C · Extreme danger 52 °C and above.

### A. Location-based heat outlook
- Show forecast heat index for the work location by hour, classified by PAGASA category.
- Highlight periods that need extra precautions.
- Always show the **data source and update time**; clearly mark missing or outdated data.
- Link to PAGASA's official heat index information.
- Label forecast-derived estimates separately from official observations.

### B. Advance heat alerts
- Send an **evening-before alert** to supervisors for forecast dangerous periods.
- Send a **morning briefing** to workers.
- Send a **reminder before each high-heat period**.
- **Automatically start check-ins** when the forecast heat index reaches the Danger level.

### C. Shift heat-action planner
- Inputs: working hours, planned tasks and their intensity, exposure conditions (e.g. direct sun, strenuous work), and each worker's acclimatization record.
- Outputs: suggested precautions, including lower-heat task windows, shaded rest, drinking-water arrangements and buddy checks.
- Supervisors can schedule rest and buddy checks, confirm water and shade, and record task adjustments.

### D. Guided acclimatization tracker
- Plans gradual heat exposure using published NIOSH guidance.
- Records planned and completed exposure duration across shifts.
- Highlights interruptions for supervisor review.
- Prompts additional precautions during onboarding; recorded progress informs the next shift's plan.

### E. Worker check-ins and assistance requests
- Simple check-in screen: "Okay ako / I'm okay" or "Kailangan ko ng tulong / I need help". No lengthy forms.
- Check-ins run only during high-heat periods to avoid unnecessary interruptions.

### F. SOS location share
- A help request attaches a **one-time location pin** for the buddy and supervisor.
- Location is captured only at the moment of the request, with consent given at registration. **Never tracked continuously.**
- If location is unavailable, the registered worksite location is sent instead.
- Shared locations are deleted at the end of the shift unless attached to an incident record.

### G. Buddy notifications and acknowledged follow-up
- Route help requests and overdue check-ins to the designated buddy or supervisor.
- Distinguish an **explicit help request** (immediate notification) from an **unanswered check-in**, which may be a connectivity problem.
- Unanswered check-in flow: reminder to the worker → after a configured grace period, the buddy is asked to check in person → if not acknowledged within a set time, escalate to the supervisor.
- Recipients acknowledge and record their response. Unresolved cases stay visible.

### H. Supervisor action dashboard
- Shows active shifts, planned precautions, acclimatization progress, check-in status, unresolved requests and follow-up records.
- Access limited to authorized team members.

### I. Incident record
- Logs each assistance request and unanswered check-in with time, heat index level, action taken and responder.
- Records can be exported to support workplace documentation, in line with DOLE's forthcoming heat advisories.

### J. Filipino and English safety guide
- Concise prevention information, emergency warning signs and immediate-action guidance, based on published resources.
- Saved guidance is available offline. Sending check-ins and notifications requires connectivity.
- Emergency instructions direct users to seek immediate assistance rather than wait for an app response.

## 7. Non-functional requirements

| Area | Requirement |
|---|---|
| **Privacy** | One-time location only on help requests; consent at registration; location deleted at end of shift unless part of an incident record; dashboard limited to authorized team members |
| **Safety** | Heat index is an initial screening indicator; guidance supports supervisor decisions and does not diagnose illness; occupational-safety review before field use |
| **Offline** | Selected safety guidance cached for offline use (PWA) |
| **Language** | Full Filipino and English interface and guidance |
| **Reliability** | Missing or stale forecast data clearly flagged; unanswered notifications escalate rather than fail silently |
| **Transparency** | Rule-based, explainable guidance drawn from published heat-prevention resources |
| **Accessibility** | Large, simple check-in controls; works on the phones workers already use, in a browser |

## 8. Technology

| Layer | Choice |
|---|---|
| Frontend | React + TypeScript, mobile-first Progressive Web App (browser access, offline storage of selected guidance) |
| Backend & database | Node.js + PostgreSQL — team profiles, shift plans, exposure logs, check-ins, incident and follow-up records |
| Weather | Open-Meteo hourly temperature and humidity → documented heat-index calculation → PAGASA categories; PAGASA advisories and iHeatMap as official reference |
| Notifications | In-app updates and a Telegram bot for opted-in pilot participants; scheduled server tasks for alerts, check-ins and overdue notifications; Facebook Messenger planned after Meta's app review |
| Location | Browser geolocation, captured once on a help request, with map links for buddies and supervisors |
| Guidance logic | Transparent rule-based alerts, planning and acclimatization prompts, supported by daily exposure logs and supervisor review |

**Later extensions:** SMS delivery (requires a funded channel), additional user modes, wearable integration.

## 9. Evaluation and success metrics

Evaluated through a **small pilot** (one outdoor team, one locality) and **controlled scenarios**.

| Metric | What it shows |
|---|---|
| Alert timing | Alerts arrive before dangerous periods |
| Completion of planned precautions and exposure logs | The plan is actually followed |
| Understanding of guidance | Workers and supervisors understand the advice |
| Successful assistance routing | Every help request and missed check-in reaches a person |
| Time to acknowledgment | How fast a person responds |
| Usability | The app is simple enough to use during work |

**Controlled scenarios** test missed responses, connectivity failures, and unresolved-case handling.

## 10. Risks and mitigations

| Risk | Mitigation |
|---|---|
| Connectivity loss looks like an emergency | Missed check-ins get a reminder first; explicit help requests are handled separately |
| A buddy misses the notification | Unacknowledged notifications escalate to the supervisor |
| Forecast data missing or outdated | Flagged clearly with source and update time; link to PAGASA |
| Over-reliance on the app in an emergency | Guidance tells users to seek immediate help instead of waiting for the app |
| Privacy concerns about location | One-time pin, consent at registration, automatic deletion |
| Guidance quality | Rule-based from published resources; occupational-safety review before field use |

## 11. Open questions

- Default length of the check-in grace period and the escalation window for the pilot.
- Check-in frequency during Danger vs. Extreme danger periods.
- Which outdoor team and locality will join the pilot.
- Format of exported incident records that best fits DOLE documentation needs.

## 12. References

1. DZRH (2026, May 20). 40 areas under 'danger' heat index on May 20, 2026 – PAGASA.
2. Philippine Daily Inquirer (2026, October 22). Extreme heat gripped Calamba City; Talisay, Batangas.
3. DOST-PAGASA (2026, September 23). Climate Advisory for "Very Strong" El Niño.
4. GMA News (2026, September 8). Warmer temperatures expected during Amihan season as El Niño strengthens – PAGASA.
5. GMA News (2024, May 4). Heat-related illness cases rise to 77, DOH says.
6. ABS-CBN News (2024, April 30). DOH verifying 6 deaths due to intense heat.
7. Fernandez, H. A. (2024, May 24). Feeling the heat: Who are the most vulnerable workers impacted by the Philippines' record-breaking heatwaves? Eco-Business.
8. Philippine News Agency (2024, March 22). DOLE reminds employers of safety measures for heat stress.
9. DOLE Bureau of Working Conditions (2026, April 13). DOLE Strengthens Workplace Protection Against Heat Stress Through Webinar Episode.
10. NewsWatch Plus (2026, October 18). DOLE to enforce labor advisories amid El Niño health risks.
11. Philippine Daily Inquirer (2024, April 22). DOH logs 34 cases of heat-related illness so far this year.
12. GMA News (2022, April 8). Construction worker, hinihinalang namatay sa heat stroke.
13. CDC NIOSH. Workplace Recommendations: Heat Stress.
14. DOST-PAGASA (2025, April 4). DOST-PAGASA Launches iHeatMap: An Online Heat Index Monitoring Platform.
15. CDC NIOSH. Heat Safety Tool App (OSHA-NIOSH).
16. Occupational Safety and Health Administration. Heat Hazard Recognition.
17. Open-Meteo. Weather Forecast API Documentation.
