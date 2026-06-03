# Proceeding in offline mode in familyman system

[Back to Private Law State Model](../index.md)

State ID: `PROCEEDS_IN_HERITAGE_SYSTEM`

## Local state model

```mermaid
flowchart LR
    current["Proceeding in offline mode in familyman system"]

    subgraph inbound["Inbound to Proceeding in offline mode in familyman system"]
        in_awaiting_information["Awaiting Information"]
        in_awaiting_submission_to_hmcts["Draft"]
        in_submitted_paid["Submitted"]
    end

    in_awaiting_information -->|"Issue and send to local court"| current
    in_awaiting_submission_to_hmcts -->|"Statement of Truth and submit"| current
    in_submitted_paid -->|"Issue and send to local court"| current
```

## Outgoing events

_No events found._

## In-state events

_No events found._

## Incoming events

| Event | Start state | Runnable by |
|---|---|---|
| Statement of Truth and submit (`fl401StatementOfTruthAndSubmit`) | [Draft](./draft.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen` (`citizen`)<br/>`hearing-centre-admin`, `allocated-admin-caseworker`, `ctsc`, `allocated-ctsc-caseworker` (`caseworker-privatelaw-courtadmin`)<br/>`idam:caseworker-privatelaw-systemupdate` (`caseworker-privatelaw-systemupdate`) |
| Issue and send to local court (`issueAndSendToLocalCourtCallback`) | [Awaiting Information](./awaiting-information.md) | `hearing-centre-admin`, `allocated-admin-caseworker`, `ctsc`, `allocated-ctsc-caseworker` (`caseworker-privatelaw-courtadmin`) |
| Issue and send to local court (`issueAndSendToLocalCourtCallback`) | [Submitted](./submitted.md) | `hearing-centre-admin`, `allocated-admin-caseworker`, `ctsc`, `allocated-ctsc-caseworker` (`caseworker-privatelaw-courtadmin`) |
