# Ready for deletion

[Back to Private Law State Model](../index.md)

State ID: `READY_FOR_DELETION`

## Local state model

```mermaid
flowchart LR
    current["Ready for deletion"]

    subgraph inbound["Inbound to Ready for deletion"]
        in_awaiting_submission_to_hmcts["Draft"]
    end

    in_awaiting_submission_to_hmcts -->|"Delete application"| current
```

## Outgoing events

_No events found._

## In-state events

_No events found._

## Incoming events

| Event | Start state | Runnable by |
|---|---|---|
| Delete application (`deleteApplication`) | [Draft](./draft.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen` (`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate` (`caseworker-privatelaw-systemupdate`) |
