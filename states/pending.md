# Pending

[Back to Private Law State Model](../index.md)

State ID: `SUBMITTED_NOT_PAID`

## Local state model

```mermaid
flowchart LR
    current["Pending"]

    subgraph inbound["Inbound to Pending"]
        in_awaiting_submission_to_hmcts["Draft"]
    end

    subgraph outbound["Outbound from Pending"]
        out_awaiting_information["Awaiting Information"]
        out_case_withdrawn["Withdrawn"]
        out_submitted_paid["Submitted"]
    end

    in_awaiting_submission_to_hmcts -->|"Submit and pay<br/>Submit Citizen Case with HWF"| current
    current -->|"Request Further Information<br/>Further Information Reasons"| out_awaiting_information
    current -->|"Withdraw application<br/>Withdraw Citizen Case"| out_case_withdrawn
    current -->|"Process HWF for Citizen case<br/>Process urgent help with fees"| out_submitted_paid
```

## Outgoing events

| Event | End state | Runnable by |
|---|---|---|
| Withdraw application (`WithdrawApplication_Event`) | [Withdrawn](./withdrawn.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen` (`citizen`) |
| Withdraw Citizen Case (`citizenCaseWithdraw`) | [Withdrawn](./withdrawn.md) | `idam:citizen` (`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate` (`caseworker-privatelaw-systemupdate`) |
| Process HWF for Citizen case (`hwfProcessCaseUpdate`) | [Submitted](./submitted.md) | `idam:caseworker-privatelaw-systemupdate` (`caseworker-privatelaw-systemupdate`) |
| Process urgent help with fees (`processUrgentHelpWithFees`) | [Submitted](./submitted.md) | `idam:caseworker-privatelaw-systemupdate` (`caseworker-privatelaw-systemupdate`)<br/>`hearing-centre-admin`, `allocated-admin-caseworker`, `ctsc`, `allocated-ctsc-caseworker` (`caseworker-privatelaw-courtadmin`) |
| Request Further Information (`requestFurtherInformation`) | [Awaiting Information](./awaiting-information.md) | `hearing-centre-admin`, `allocated-admin-caseworker`, `ctsc`, `allocated-ctsc-caseworker` (`caseworker-privatelaw-courtadmin`)<br/>`ctsc-team-leader`<br/>`idam:caseworker-privatelaw-superuser` (`caseworker-privatelaw-superuser`)<br/>`idam:caseworker-wa-task-configuration` (`caseworker-wa-task-configuration`)<br/>`idam:caseworker-privatelaw-systemupdate` (`caseworker-privatelaw-systemupdate`)<br/>`hearing-centre-team-leader` |
| Further Information Reasons (`requestFurtherInformationHistory`) | [Awaiting Information](./awaiting-information.md) | `hearing-centre-admin`, `allocated-admin-caseworker`, `ctsc`, `allocated-ctsc-caseworker` (`caseworker-privatelaw-courtadmin`)<br/>`ctsc-team-leader`<br/>`idam:caseworker-privatelaw-superuser` (`caseworker-privatelaw-superuser`)<br/>`idam:caseworker-wa-task-configuration` (`caseworker-wa-task-configuration`)<br/>`idam:caseworker-privatelaw-systemupdate` (`caseworker-privatelaw-systemupdate`)<br/>`hearing-centre-team-leader` |

## In-state events

| Event | End state | Runnable by |
|---|---|---|
| Send and reply to messages (`sendOrReplyToMessages`) | [Pending](./pending.md) | `hearing-centre-admin`, `allocated-admin-caseworker`, `ctsc`, `allocated-ctsc-caseworker` (`caseworker-privatelaw-courtadmin`)<br/>`caseworker-privatelaw-judge`<br/>`tribunal-caseworker`, `senior-tribunal-caseworker`, `allocated-legal-adviser` (`caseworker-privatelaw-la`) |
| Send and reply to messages (`waSendOrReplyToMessages`) | [Pending](./pending.md) | `hearing-centre-admin`, `allocated-admin-caseworker`, `ctsc`, `allocated-ctsc-caseworker` (`caseworker-privatelaw-courtadmin`)<br/>`caseworker-privatelaw-judge`<br/>`tribunal-caseworker`, `senior-tribunal-caseworker`, `allocated-legal-adviser` (`caseworker-privatelaw-la`) |

## Incoming events

| Event | Start state | Runnable by |
|---|---|---|
| Submit Citizen Case with HWF (`citizenCaseSubmitWithHWF`) | [Draft](./draft.md) | `idam:citizen` (`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate` (`caseworker-privatelaw-systemupdate`) |
| Submit and pay (`submitAndPay`) | [Draft](./draft.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen` (`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate` (`caseworker-privatelaw-systemupdate`)<br/>`hearing-centre-admin`, `allocated-admin-caseworker`, `ctsc`, `allocated-ctsc-caseworker` (`caseworker-privatelaw-courtadmin`) |
