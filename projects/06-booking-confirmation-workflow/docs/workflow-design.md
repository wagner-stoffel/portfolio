# Booking workflow — implementation and failure rules

**Environment:** Workana visual workflow simulator. This is a design and partial execution record, not a production integration.

## Input

The website form provides:

- `{{name}}`
- `{{phone}}`
- `{{branch}}`
- `{{treatment}}`
- `{{period}}`
- `{{date}}`
- `{{time}}`

The calendar must be selected **by the requested branch**. Use `{{date}} {{time}}` in the availability check; do not substitute unrelated field names such as `fecha` and `hora`.

## CRM logic

1. Find a contact in Kommo using the request's phone number.
2. If the contact exists, do not create a duplicate.
3. If it does not exist, create a contact and lead with the supplied name and phone number.
4. Continue to availability checking after either outcome.

## Availability and booking logic

- Select the corresponding branch Google Calendar.
- Check the requested slot.
- Condition: “The requested slot is taken.”
  - **Yes:** Notify reception to propose a different appointment. Do not book or confirm.
  - **No:** Create the Google Calendar event; only once that succeeds, send the approved Meta WhatsApp confirmation.

## WhatsApp template contract

- Template name: `confirmacion_turno`.
- Recipient: `{{phone}}`.
- Variable order: `{{name}}`, `{{branch}}`, `{{date}}`, `{{time}}`.
- No confirmation should go out if event creation fails.

## Reception notification (occupied slot)

**To:** `recepcion@sonria.example`  
**Subject:** `Appointment request - Time slot unavailable`

```text
A patient has requested an appointment, but the selected time slot is already taken.

Patient: {{name}}
Phone: {{phone}}
Branch: {{branch}}
Treatment: {{treatment}}
Date: {{date}}
Time: {{time}}

Please contact the patient to offer an alternative appointment.

Status: Pending rescheduling.
```

## Suggested failure handling

| Failure | Response |
| --- | --- |
| CRM search unavailable | Alert reception; do not silently create potential duplicates. |
| Contact creation fails | Alert reception; do not claim successful CRM registration. |
| Calendar check fails | Alert reception; do not assume the slot is free. |
| Event creation fails | Stop confirmation; alert reception. |
| WhatsApp send fails after event creation | Retain the booking, alert reception and retry messaging safely without a second booking. |

## Recorded execution boundary

The single captured sample confirmed a new CRM contact and a free calendar slot. The simulator then warned that the **No** output of the slot-taken condition had no next node. Later implementation or successful reruns were not evidenced in the captured session.
