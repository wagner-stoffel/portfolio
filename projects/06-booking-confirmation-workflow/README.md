# Appointment Confirmation Workflow — CRM, Calendar and WhatsApp

**Status:** Workflow design and partial implementation completed in a Workana simulator; one new-patient test executed. The last recorded execution stopped at an unconnected free-slot branch. End-to-end booking/notification success was not verified.  
**Role:** Process mapping, conditional workflow design, node configuration and simulated execution inspection.  
**Context:** Clínica Sonría — Workana technical exercise, 10 November 2026.  
**Tools represented:** Website form · Kommo CRM · Google Calendar · Meta WhatsApp Business · Gmail

## Business challenge

A receptionist manually received appointment requests, looked up patients in Kommo, checked the requested branch's Google Calendar, created a booking and sent a WhatsApp confirmation. For occupied slots, reception had to offer another time. The automation needed to reflect both the normal path and operational exceptions.

## Workflow constructed

I configured and connected the following initial steps in the visual simulator:

1. **Website form:** trigger on appointment request.
2. **Kommo — Find contact:** check for an existing patient.
3. **Condition — Contact already exists?** branch on the CRM lookup.
4. **No:** Kommo — Create contact and lead with form name and phone.
5. **Yes and No paths:** Google Calendar — Check availability for the requested branch and date/time.
6. **Condition — The requested slot is taken:** route occupied and free slots differently.

I used the form's `{{date}}` and `{{time}}` fields for calendar lookup and prepared the reception email for the occupied-slot path.

## Intended completion path

The booking-confirmation design specifies:

```text
Website form
    |
Kommo: Find contact
    |
Contact exists?
    | Yes                     | No
    |                         Kommo: Create contact and lead
    |                          |
    +-----------+--------------+
                |
    Google Calendar: Check requested branch
                |
          Slot taken?
            | Yes                  | No
            Gmail: reception       Google Calendar: Create event
            offers another slot       |
                                  Meta WhatsApp Business:
                                  approved confirmation template
```

The approved WhatsApp template is `confirmacion_turno` and must receive the variables in exactly this order: `name`, `branch`, `date`, `time`.

Technical failures should alert reception. Failed booking writes must not trigger a misleading confirmation; a message-send failure should not create a duplicate booking.

## Observed test

The simulator processed one sample request (new patient, cleaning, Centro/Norte/Sur branch selection as supplied by the form):

| Step | Recorded outcome |
| --- | --- |
| Website request received | OK |
| Kommo contact lookup | OK; no existing contact found |
| CRM existence condition | No branch |
| New contact and lead created | OK |
| Google Calendar availability lookup | OK; requested slot free |
| Slot-taken condition | No branch |
| Next step | **Warning:** output not connected; execution ended |

The execution confirmed the initial CRM and availability logic for that sample. It did **not** establish that a calendar event was created, a confirmation was sent or the occupied-slot/error paths ran successfully.

## Design notes

- [Node mapping, field configuration and failure rules](docs/workflow-design.md)

## What this demonstrates

I modelled an appointment process as event-driven automation with CRM deduplication, conditional routing and calendar lookups. I inspected the execution trace and documented the exact incomplete branch rather than presenting the prototype as a live integration.

[Back to portfolio](../../README.md)
