# Dental WhatsApp AI Assistant — Instructions and Safety Validation

**Status:** Completed prompt-engineering simulation; five scripted patient scenarios tested successfully after iteration. Not a live clinic deployment.  
**Role:** Requirements analysis, policy reconciliation, AI behaviour design, test execution and refinement.  
**Context:** Clínica Sonría — Workana technical exercise, 10 November 2026.  
**Focus:** Conversational AI · System prompts · Knowledge reconciliation · Human handoff · Medical-safety boundaries

## Business challenge

A dental clinic wanted a WhatsApp assistant to answer administrative questions and handle appointment requests. The available material was inconsistent: a 2024 website FAQ, an emergency protocol, management and clinical-director emails, team chat updates, and undated reception notes. A safe assistant had to follow the most authoritative, recent instructions without inventing bookings or providing clinical advice.

## Work completed

I reviewed six source groups, extracted operational rules, resolved conflicting guidance and wrote the system instructions. The prompt defines:

- Reception hours: Monday–Friday 08:00–19:00; Saturday 09:00–13:00; Sunday closed.
- Three branches (Centro, Norte and Sur), routine price information and rules on promotions.
- Appointment-request intake without pretending to have calendar access or confirming availability.
- Emergency recognition, appropriate escalation during reception hours and the updated after-hours line.
- A strict boundary against medical diagnosis, prescriptions and medicine recommendations.
- Human handoff for emergencies, booking changes, treatment quotes and ambiguous cases.
- Concise, empathetic patient-facing language, with a more formal register for older patients.

I also corrected the interpretation of the emergency phone number and removed assumptions about which day reception would next be open.

## Verification

I ran the five built-in simulated patient conversations and reviewed the replies:

| Scenario | Observed behaviour |
| --- | --- |
| Cleaning request at Norte on Saturday morning | Quoted USD 40, collected intake details and did not claim a confirmed slot. |
| Broken tooth with bleeding during reception hours | Directed the patient to reception for urgent handling and mentioned the 15-minute callback protocol without claiming a callback had been arranged. |
| Severe pain and facial swelling at 23:40 | Gave the revised after-hours dental emergency number and identified potentially serious symptoms. |
| Request for an implant price | Did not invent a treatment quote; explained that the USD 25 assessment precedes a clinician's estimate. |
| Question about ibuprofen | Avoided personalised medicine advice and directed the patient to an appropriate professional. |

**Result:** Five satisfactory simulated outcomes after refining two responses. The test establishes prompt behaviour within the exercise, not actual WhatsApp routing, emergency-service integration or appointment bookings.

## Technical artefact

- [Assistant behaviour specification and test record](docs/assistant-specification.md)

## What this demonstrates

I translated conflicting business documents into explicit AI operating rules, then checked safety-critical scenarios and improved the prompt based on observed responses. The work combines process analysis, conversational design, test-driven refinement and responsible human escalation.

[Back to portfolio](../../README.md)
