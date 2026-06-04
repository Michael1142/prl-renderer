# Awaiting applicant 2 response

[Back to No Fault Divorce State Model](../index.md)

State ID: `AwaitingApplicant2Response`

## Local state model

```mermaid
flowchart LR
    current["Awaiting applicant 2 response"]

    subgraph inbound["Inbound to Awaiting applicant 2 response"]
        in_archived["Archived"]
        in_draft["Draft"]
    end

    subgraph outbound["Outbound from Awaiting applicant 2 response"]
        out_applicant2approved["Applicant 2 approved"]
        out_archived["Archived"]
        out_awaitingapplicant1response["Awaiting applicant 1 response"]
    end

    in_archived -->|"Invite Applicant 2"| current
    in_draft -->|"Invite Applicant 2"| current
    current -->|"Applicant 2 approve"| out_applicant2approved
    current -->|"Archive Case"| out_archived
    current -->|"Applicant 2 not broken<br/>Applicant 2 Request Changes"| out_awaitingapplicant1response
```

## Outgoing events

| Event | End state | Runnable by | Enabling condition |
|---|---|---|---|
| Applicant 2 approve (`applicant2-approve`) | [Applicant 2 approved](./applicant-2-approved.md) | `[APPLICANTTWO]`<br/>`caseworker-divorce-systemupdate` | — |
| Applicant 2 not broken (`applicant2-not-broken`) | [Awaiting applicant 1 response](./awaiting-applicant-1-response.md) | `[APPLICANTTWO]` | `divorceOrDissolution="NEVER_SHOW"` |
| Applicant 2 Request Changes (`applicant2-request-changes`) | [Awaiting applicant 1 response](./awaiting-applicant-1-response.md) | `[APPLICANTTWO]`<br/>`caseworker-divorce-systemupdate` | — |
| Archive Case (`solicitor-archive-case`) | [Archived](./archived.md) | `[APPONESOLICITOR]` | — |

## In-state events

| Event | End state | Runnable by | Enabling condition |
|---|---|---|---|
| View applicant contact info (`app1-solicitor-view-app1-contact-info`) | [Awaiting applicant 2 response](./awaiting-applicant-2-response.md) | `[APPONESOLICITOR]` | — |
| View respondent contact info (`app1-solicitor-view-app2-contact-info`) | [Awaiting applicant 2 response](./awaiting-applicant-2-response.md) | `[APPONESOLICITOR]` | — |
| View applicant contact info (`app2-solicitor-view-app1-contact-info`) | [Awaiting applicant 2 response](./awaiting-applicant-2-response.md) | `[APPTWOSOLICITOR]` | — |
| View respondent contact info (`app2-solicitor-view-app2-contact-info`) | [Awaiting applicant 2 response](./awaiting-applicant-2-response.md) | `[APPTWOSOLICITOR]` | — |
| Patch a joint case (`citizen-applicant2-update-application`) | [Awaiting applicant 2 response](./awaiting-applicant-2-response.md) | `[APPLICANTTWO]` | `divorceOrDissolution="NEVER_SHOW"` |
| Update applicant 2 email (`citizen-resend-invite`) | [Awaiting applicant 2 response](./awaiting-applicant-2-response.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Review and submit application (`solicitor-submit-joint-application`) | [Awaiting applicant 2 response](./awaiting-applicant-2-response.md) | `[APPTWOSOLICITOR]` | — |
| Withdraw application (`solicitor-withdrawn`) | [Awaiting applicant 2 response](./awaiting-applicant-2-response.md) | `[APPONESOLICITOR]` | — |
| Application switched to sole (`switch-to-sole`) | [Awaiting applicant 2 response](./awaiting-applicant-2-response.md) | `[APPLICANTTWO]`<br/>`[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Alert Applicant 1 (`system-application-not-reviewed`) | [Awaiting applicant 2 response](./awaiting-applicant-2-response.md) | `caseworker-divorce-systemupdate` | — |
| Link Resp or App 2 to case (`system-link-applicant2`) | [Awaiting applicant 2 response](./awaiting-applicant-2-response.md) | `caseworker-divorce-systemupdate` | — |
| Migrate case data (`system-migrate-case`) | [Awaiting applicant 2 response](./awaiting-applicant-2-response.md) | `caseworker-divorce-systemupdate` | — |
| Migrate organisation policies (`system-migrate-organisation-policies`) | [Awaiting applicant 2 response](./awaiting-applicant-2-response.md) | `caseworker-divorce-systemupdate` | — |
| Remind Applicant 2 (`system-remind-applicant2`) | [Awaiting applicant 2 response](./awaiting-applicant-2-response.md) | `caseworker-divorce-systemupdate` | — |
| Unlink Applicant from case (`system-unlink-applicant`) | [Awaiting applicant 2 response](./awaiting-applicant-2-response.md) | `citizen` | — |
| Update issue date (`system-update-issue-date`) | [Awaiting applicant 2 response](./awaiting-applicant-2-response.md) | `caseworker-divorce-systemupdate` | — |

## Incoming events

| Event | Start state | Runnable by | Enabling condition |
|---|---|---|---|
| Invite Applicant 2 (`invite-applicant2`) | [Archived](./archived.md) | `[APPONESOLICITOR]`<br/>`citizen` | `applicationType="jointApplication"` |
| Invite Applicant 2 (`invite-applicant2`) | [Draft](./draft.md) | `[APPONESOLICITOR]`<br/>`citizen` | `applicationType="jointApplication"` |
