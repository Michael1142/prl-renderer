# Draft

[Back to Private Law State Model](../index.md)

State ID: `AWAITING_SUBMISSION_TO_HMCTS`

## Local state model

```mermaid
flowchart LR
    current["Draft"]

    subgraph inbound["Inbound to Draft"]
        in_awaiting_resubmission_to_hmcts["Returned"]
        in_start["Start"]
    end

    subgraph outbound["Outbound from Draft"]
        out_all_final_orders_issued["Closed"]
        out_case_withdrawn["Withdrawn"]
        out_proceeds_in_heritage_system["Proceeding in offline mode in familyman system"]
        out_ready_for_deletion["Ready for deletion"]
        out_submitted_not_paid["Pending"]
        out_submitted_paid["Submitted"]
    end

    in_awaiting_resubmission_to_hmcts -->|"Safeguarding and risk of harm"| current
    in_start -->|"Solicitor application<br/>Citizen Create Case<br/>Court admin application"| current
    current -->|"Create/upload draft order"| out_all_final_orders_issued
    current -->|"Withdraw application"| out_case_withdrawn
    current -->|"Statement of Truth and submit"| out_proceeds_in_heritage_system
    current -->|"Delete application"| out_ready_for_deletion
    current -->|"Submit and pay<br/>Submit Citizen Case with HWF"| out_submitted_not_paid
    current -->|"Statement of Truth and submit<br/>Submit Citizen Case"| out_submitted_paid
```

## Outgoing events

| Event | End state | Runnable by |
|---|---|---|
| Withdraw application (`WithdrawApplication_Event`) | [Withdrawn](./withdrawn.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen`<br/>(`citizen`) |
| Submit Citizen Case (`citizen-case-submit`) | [Submitted](./submitted.md) | `idam:citizen`<br/>(`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`) |
| Submit Citizen Case with HWF (`citizenCaseSubmitWithHWF`) | [Pending](./pending.md) | `idam:citizen`<br/>(`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`) |
| Delete application (`deleteApplication`) | [Ready for deletion](./ready-for-deletion.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen`<br/>(`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`) |
| Create/upload draft order (`draftAnOrder`) | [Closed](./closed.md) | `[C100APPLICANTBARRISTER1]`<br/>`[C100APPLICANTBARRISTER2]`<br/>`[C100APPLICANTBARRISTER3]`<br/>`[C100APPLICANTBARRISTER4]`<br/>`[C100APPLICANTBARRISTER5]`<br/>`[C100RESPONDENTBARRISTER1]`<br/>`[C100RESPONDENTBARRISTER2]`<br/>`[C100RESPONDENTBARRISTER3]`<br/>`[C100RESPONDENTBARRISTER4]`<br/>`[C100RESPONDENTBARRISTER5]`<br/>`[FL401APPLICANTBARRISTER]`<br/>`[FL401RESPONDENTBARRISTER]` |
| Statement of Truth and submit (`fl401StatementOfTruthAndSubmit`) | [Proceeding in offline mode in familyman system](./proceeding-in-offline-mode-in-familyman-system.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen`<br/>(`citizen`)<br/>`hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`)<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`) |
| Statement of Truth and submit (`fl401StatementOfTruthAndSubmit`) | [Submitted](./submitted.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen`<br/>(`citizen`)<br/>`hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`)<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`) |
| Submit and pay (`submitAndPay`) | [Pending](./pending.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen`<br/>(`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`)<br/>`hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`) |

## In-state events

| Event | End state | Runnable by |
|---|---|---|
| Allegations of harm (`allegationsOfHarm`) | [Draft](./draft.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen`<br/>(`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`) |
| Allegations of harm (`allegationsOfHarmRevised`) | [Draft](./draft.md) | — |
| Applicant details (`applicantsDetails`) | [Draft](./draft.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen`<br/>(`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`) |
| Attending the hearing (`attendingTheHearing`) | [Draft](./draft.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen`<br/>(`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`) |
| Child details (`childDetails`) | [Draft](./draft.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen`<br/>(`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`) |
| Child details (`childDetailsRevised`) | [Draft](./draft.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen`<br/>(`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`) |
| Children and applicants (`childrenAndApplicants`) | [Draft](./draft.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen`<br/>(`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`) |
| Children and other people (`childrenAndOtherPeople`) | [Draft](./draft.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen`<br/>(`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`) |
| Children and respondents (`childrenAndRespondents`) | [Draft](./draft.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen`<br/>(`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`) |
| Citizen saving C100 draft (`citizenSaveC100DraftInternal`) | [Draft](./draft.md) | `idam:citizen`<br/>(`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`) |
| Applicant’s family (`fl401ApplicantFamilyDetails`) | [Draft](./draft.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen`<br/>(`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`) |
| The home (`fl401Home`) | [Draft](./draft.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen`<br/>(`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`) |
| Other proceedings (`fl401OtherProceedings`) | [Draft](./draft.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen`<br/>(`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`) |
| Type of application (`fl401TypeOfApplication`) | [Draft](./draft.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen`<br/>(`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`) |
| Upload documents (`fl401UploadDocuments`) | [Draft](./draft.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen`<br/>(`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`) |
| Hearing urgency (`hearingUrgency`) | [Draft](./draft.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen`<br/>(`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`) |
| International element (`internationalElement`) | [Draft](./draft.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen`<br/>(`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`) |
| Litigation capacity (`litigationCapacity`) | [Draft](./draft.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen`<br/>(`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`) |
| MIAM (`miam`) | [Draft](./draft.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen`<br/>(`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`) |
| MIAM (`miamPolicyUpgrade`) | [Draft](./draft.md) | `[CREATOR]`<br/>`[APPLICANTSOLICITOR]`<br/>`idam:citizen`<br/>(`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`) |
| Other children not in the case (`otherChildNotInTheCase`) | [Draft](./draft.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen`<br/>(`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`) |
| Other people in the case (`otherPeopleInTheCase`) | [Draft](./draft.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen`<br/>(`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`) |
| Other people in the case (`otherPeopleInTheCaseRevised`) | [Draft](./draft.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen`<br/>(`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`) |
| Other proceedings (`otherProceedings`) | [Draft](./draft.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen`<br/>(`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`) |
| Respondent's behaviour (`respondentBehaviour`) | [Draft](./draft.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen`<br/>(`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`) |
| Relationship to respondent (`respondentRelationship`) | [Draft](./draft.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen`<br/>(`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`) |
| Respondent details (`respondentsDetails`) | [Draft](./draft.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen`<br/>(`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`) |
| Safeguarding and risk of harm (`safeguardingAndRiskOfHarm`) | [Draft](./draft.md) | — |
| Type of application (`selectApplicationType`) | [Draft](./draft.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen`<br/>(`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`) |
| Upload documents (`uploadDocuments`) | [Draft](./draft.md) | — |
| View PDF application (`viewPdfDocument`) | [Draft](./draft.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen`<br/>(`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`) |
| Welsh language requirements (`welshLanguageRequirements`) | [Draft](./draft.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen`<br/>(`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`) |
| Without notice order (`withoutNoticeOrderDetails`) | [Draft](./draft.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen`<br/>(`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`) |

## Incoming events

| Event | Start state | Runnable by |
|---|---|---|
| Court admin application (`adminCreate`) | `__START__` | `idam:citizen`<br/>(`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`)<br/>`idam:caseworker-privatelaw-courtadmin-casecreator`<br/>(`caseworker-privatelaw-courtadmin-casecreator`) |
| Citizen Create Case (`citizenCreate`) | `__START__` | — |
| Safeguarding and risk of harm (`safeguardingAndRiskOfHarm`) | [Returned](./returned.md) | — |
| Solicitor application (`solicitorCreate`) | `__START__` | `idam:citizen`<br/>(`citizen`)<br/>`idam:caseworker-privatelaw-solicitor`<br/>(`caseworker-privatelaw-solicitor`)<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`) |
