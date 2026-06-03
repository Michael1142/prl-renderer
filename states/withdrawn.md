# Withdrawn

[Back to Private Law State Model](../index.md)

State ID: `CASE_WITHDRAWN`

## Local state model

```mermaid
flowchart LR
    current["Withdrawn"]

    subgraph inbound["Inbound to Withdrawn"]
        in_awaiting_resubmission_to_hmcts["Returned"]
        in_awaiting_submission_to_hmcts["Draft"]
        in_submitted_not_paid["Pending"]
        in_submitted_paid["Submitted"]
    end

    subgraph outbound["Outbound from Withdrawn"]
        out_all_final_orders_issued["Closed"]
        out_submitted_paid["Submitted"]
    end

    in_awaiting_resubmission_to_hmcts -->|"Withdraw application"| current
    in_awaiting_submission_to_hmcts -->|"Withdraw application"| current
    in_submitted_not_paid -->|"Withdraw application<br/>Withdraw Citizen Case"| current
    in_submitted_paid -->|"Withdraw application<br/>Withdraw Citizen Case"| current
    current -->|"Manage orders<br/>Manage orders<br/>Create/upload draft order"| out_all_final_orders_issued
    current -->|"Process urgent help with fees"| out_submitted_paid
```

## Outgoing events

| Event | End state | Runnable by |
|---|---|---|
| Create/upload draft order (`draftAnOrder`) | [Closed](./closed.md) | `[C100APPLICANTBARRISTER1]`<br/>`[C100APPLICANTBARRISTER2]`<br/>`[C100APPLICANTBARRISTER3]`<br/>`[C100APPLICANTBARRISTER4]`<br/>`[C100APPLICANTBARRISTER5]`<br/>`[C100RESPONDENTBARRISTER1]`<br/>`[C100RESPONDENTBARRISTER2]`<br/>`[C100RESPONDENTBARRISTER3]`<br/>`[C100RESPONDENTBARRISTER4]`<br/>`[C100RESPONDENTBARRISTER5]`<br/>`[FL401APPLICANTBARRISTER]`<br/>`[FL401RESPONDENTBARRISTER]` |
| Manage orders (`manageOrders`) | [Closed](./closed.md) | `hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`)<br/>`caseworker-privatelaw-judge`<br/>`tribunal-caseworker`<br/>`senior-tribunal-caseworker`<br/>`allocated-legal-adviser`<br/>(`caseworker-privatelaw-la`) |
| Process urgent help with fees (`processUrgentHelpWithFees`) | [Submitted](./submitted.md) | `idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`)<br/>`hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`) |
| Manage orders (`waManageOrders`) | [Closed](./closed.md) | `hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`)<br/>`caseworker-privatelaw-judge`<br/>`tribunal-caseworker`<br/>`senior-tribunal-caseworker`<br/>`allocated-legal-adviser`<br/>(`caseworker-privatelaw-la`) |

## In-state events

| Event | End state | Runnable by |
|---|---|---|
| Remove barrister (`adminRemoveBarrister`) | [Withdrawn](./withdrawn.md) | `hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`)<br/>`idam:caseworker-privatelaw-superuser`<br/>(`caseworker-privatelaw-superuser`) |
| Remove legal representative (`adminRemoveLegalRepresentativeC100`) | [Withdrawn](./withdrawn.md) | `hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`)<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`) |
| Remove legal representative (`adminRemoveLegalRepresentativeFL401`) | [Withdrawn](./withdrawn.md) | `hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`)<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`) |
| Remove local authority (`adminRemoveLocalAuthority`) | [Withdrawn](./withdrawn.md) | `hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`)<br/>`idam:caseworker-privatelaw-superuser`<br/>(`caseworker-privatelaw-superuser`) |
| Stop representing client (`barristerStopRepresenting`) | [Withdrawn](./withdrawn.md) | `[C100APPLICANTBARRISTER1]`<br/>`[C100APPLICANTBARRISTER2]`<br/>`[C100APPLICANTBARRISTER3]`<br/>`[C100APPLICANTBARRISTER4]`<br/>`[C100APPLICANTBARRISTER5]`<br/>`[C100RESPONDENTBARRISTER1]`<br/>`[C100RESPONDENTBARRISTER2]`<br/>`[C100RESPONDENTBARRISTER3]`<br/>`[C100RESPONDENTBARRISTER4]`<br/>`[C100RESPONDENTBARRISTER5]`<br/>`[FL401APPLICANTBARRISTER]`<br/>`[FL401RESPONDENTBARRISTER]` |
| Link cases (`createCaseLink`) | [Withdrawn](./withdrawn.md) | — |
| Manage case links (`maintainCaseLink`) | [Withdrawn](./withdrawn.md) | — |
| Manage documents (`manageDocuments`) | [Withdrawn](./withdrawn.md) | — |
| Manage documents (`manageDocumentsNew`) | [Withdrawn](./withdrawn.md) | `idam:caseworker-privatelaw-solicitor`<br/>(`caseworker-privatelaw-solicitor`)<br/>`idam:citizen`<br/>(`citizen`)<br/>`hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`)<br/>`caseworker-privatelaw-judge`<br/>`tribunal-caseworker`<br/>`senior-tribunal-caseworker`<br/>`allocated-legal-adviser`<br/>(`caseworker-privatelaw-la`)<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`)<br/>`listed-hearing-viewer`<br/>`caseworker-privatelaw-externaluser-viewonly`<br/>(`caseworker-privatelaw-externaluser-viewonly`)<br/>`[C100APPLICANTBARRISTER1]`<br/>`[C100APPLICANTBARRISTER2]`<br/>`[C100APPLICANTBARRISTER3]`<br/>`[C100APPLICANTBARRISTER4]`<br/>`[C100APPLICANTBARRISTER5]`<br/>`[C100RESPONDENTBARRISTER1]`<br/>`[C100RESPONDENTBARRISTER2]`<br/>`[C100RESPONDENTBARRISTER3]`<br/>`[C100RESPONDENTBARRISTER4]`<br/>`[C100RESPONDENTBARRISTER5]`<br/>`[FL401APPLICANTBARRISTER]`<br/>`[FL401RESPONDENTBARRISTER]`<br/>`[LASOCIALWORKER]`<br/>`[LASOLICITOR]` |
| Review Additional Application (`reviewAdditionalApplication`) | [Withdrawn](./withdrawn.md) | `hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`)<br/>`caseworker-privatelaw-judge`<br/>`tribunal-caseworker`<br/>`senior-tribunal-caseworker`<br/>`allocated-legal-adviser`<br/>(`caseworker-privatelaw-la`)<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`)<br/>`idam:caseworker-privatelaw-superuser`<br/>(`caseworker-privatelaw-superuser`) |
| Send and reply to messages (`sendOrReplyToMessages`) | [Withdrawn](./withdrawn.md) | `hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`)<br/>`caseworker-privatelaw-judge`<br/>`tribunal-caseworker`<br/>`senior-tribunal-caseworker`<br/>`allocated-legal-adviser`<br/>(`caseworker-privatelaw-la`) |
| Remove barrister (`solicitorRemoveBarrister`) | [Withdrawn](./withdrawn.md) | `[C100RESPONDENTSOLICITOR1]`<br/>`[C100RESPONDENTSOLICITOR2]`<br/>`[C100RESPONDENTSOLICITOR3]`<br/>`[C100RESPONDENTSOLICITOR4]`<br/>`[C100RESPONDENTSOLICITOR5]`<br/>`[C100APPLICANTSOLICITOR1]`<br/>`[C100APPLICANTSOLICITOR2]`<br/>`[C100APPLICANTSOLICITOR3]`<br/>`[C100APPLICANTSOLICITOR4]`<br/>`[C100APPLICANTSOLICITOR5]`<br/>`[FL401RESPONDENTSOLICITOR]`<br/>`[FL401APPLICANTSOLICITOR]`<br/>`[APPLICANTSOLICITOR]` |
| Stop representing client (`solicitorStopRepresentingLiP`) | [Withdrawn](./withdrawn.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`[C100APPLICANTSOLICITOR1]`<br/>`[C100APPLICANTSOLICITOR2]`<br/>`[C100APPLICANTSOLICITOR3]`<br/>`[C100APPLICANTSOLICITOR4]`<br/>`[C100APPLICANTSOLICITOR5]`<br/>`[C100RESPONDENTSOLICITOR1]`<br/>`[C100RESPONDENTSOLICITOR2]`<br/>`[C100RESPONDENTSOLICITOR3]`<br/>`[C100RESPONDENTSOLICITOR4]`<br/>`[C100RESPONDENTSOLICITOR5]`<br/>`[FL401APPLICANTSOLICITOR]`<br/>`[FL401RESPONDENTSOLICITOR]`<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`) |
| Upload additional applications (`uploadAdditionalApplications`) | [Withdrawn](./withdrawn.md) | `[APPLICANTSOLICITOR]`<br/>`[C100APPLICANTSOLICITOR1]`<br/>`[C100APPLICANTSOLICITOR2]`<br/>`[C100APPLICANTSOLICITOR3]`<br/>`[C100APPLICANTSOLICITOR4]`<br/>`[C100APPLICANTSOLICITOR5]`<br/>`[C100RESPONDENTSOLICITOR1]`<br/>`[C100RESPONDENTSOLICITOR2]`<br/>`[C100RESPONDENTSOLICITOR3]`<br/>`[C100RESPONDENTSOLICITOR4]`<br/>`[C100RESPONDENTSOLICITOR5]`<br/>`[FL401APPLICANTSOLICITOR]`<br/>`[FL401RESPONDENTSOLICITOR]`<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`) |
| Send and reply to messages (`waSendOrReplyToMessages`) | [Withdrawn](./withdrawn.md) | `hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`)<br/>`caseworker-privatelaw-judge`<br/>`tribunal-caseworker`<br/>`senior-tribunal-caseworker`<br/>`allocated-legal-adviser`<br/>(`caseworker-privatelaw-la`) |

## Incoming events

| Event | Start state | Runnable by |
|---|---|---|
| Withdraw application (`WithdrawApplication_Event`) | [Returned](./returned.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen`<br/>(`citizen`) |
| Withdraw application (`WithdrawApplication_Event`) | [Draft](./draft.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen`<br/>(`citizen`) |
| Withdraw application (`WithdrawApplication_Event`) | [Pending](./pending.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen`<br/>(`citizen`) |
| Withdraw application (`WithdrawApplication_Event`) | [Submitted](./submitted.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen`<br/>(`citizen`) |
| Withdraw Citizen Case (`citizenCaseWithdraw`) | [Pending](./pending.md) | `idam:citizen`<br/>(`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`) |
| Withdraw Citizen Case (`citizenCaseWithdraw`) | [Submitted](./submitted.md) | `idam:citizen`<br/>(`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`) |
