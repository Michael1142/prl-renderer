# Returned

[Back to Private Law State Model](../index.md)

State ID: `AWAITING_RESUBMISSION_TO_HMCTS`

## Local state model

```mermaid
flowchart LR
    current["Returned"]

    subgraph inbound["Inbound to Returned"]
        in_awaiting_information["Awaiting Information"]
        in_case_issued["Case Issued"]
        in_judicial_review["Gatekeeping"]
        in_submitted_paid["Submitted"]
    end

    subgraph outbound["Outbound from Returned"]
        out_all_final_orders_issued["Closed"]
        out_awaiting_submission_to_hmcts["Draft"]
        out_case_issued["Case Issued"]
        out_case_withdrawn["Withdrawn"]
        out_submitted_paid["Submitted"]
    end

    in_awaiting_information -->|"Return application"| current
    in_case_issued -->|"Return application"| current
    in_judicial_review -->|"Return application"| current
    in_submitted_paid -->|"Return application"| current
    current -->|"Record final decision<br/>Create/upload draft order<br/>Edit and serve an order<br/>Edit and serve an order"| out_all_final_orders_issued
    current -->|"Safeguarding and risk of harm"| out_awaiting_submission_to_hmcts
    current -->|"Add case number"| out_case_issued
    current -->|"Withdraw application"| out_case_withdrawn
    current -->|"Process urgent help with fees"| out_submitted_paid
```

## Outgoing events

| Event | End state | Runnable by |
|---|---|---|
| Withdraw application (`WithdrawApplication_Event`) | [Withdrawn](./withdrawn.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen` (`citizen`) |
| Edit and serve an order (`adminEditAndApproveAnOrder`) | [Closed](./closed.md) | — |
| Create/upload draft order (`draftAnOrder`) | [Closed](./closed.md) | `[C100APPLICANTBARRISTER1]`<br/>`[C100APPLICANTBARRISTER2]`<br/>`[C100APPLICANTBARRISTER3]`<br/>`[C100APPLICANTBARRISTER4]`<br/>`[C100APPLICANTBARRISTER5]`<br/>`[C100RESPONDENTBARRISTER1]`<br/>`[C100RESPONDENTBARRISTER2]`<br/>`[C100RESPONDENTBARRISTER3]`<br/>`[C100RESPONDENTBARRISTER4]`<br/>`[C100RESPONDENTBARRISTER5]`<br/>`[FL401APPLICANTBARRISTER]`<br/>`[FL401RESPONDENTBARRISTER]` |
| Add case number (`fl401AddCaseNumber`) | [Case Issued](./case-issued.md) | `hearing-centre-admin`, `allocated-admin-caseworker`, `ctsc`, `allocated-ctsc-caseworker` (`caseworker-privatelaw-courtadmin`) |
| Edit and serve an order (`hearingEditAndApproveAnOrder`) | [Closed](./closed.md) | — |
| Process urgent help with fees (`processUrgentHelpWithFees`) | [Submitted](./submitted.md) | `idam:caseworker-privatelaw-systemupdate` (`caseworker-privatelaw-systemupdate`)<br/>`hearing-centre-admin`, `allocated-admin-caseworker`, `ctsc`, `allocated-ctsc-caseworker` (`caseworker-privatelaw-courtadmin`) |
| Record final decision (`recordFinalDecision`) | [Closed](./closed.md) | `idam:caseworker-privatelaw-systemupdate` (`caseworker-privatelaw-systemupdate`)<br/>`hearing-centre-admin`, `allocated-admin-caseworker`, `ctsc`, `allocated-ctsc-caseworker` (`caseworker-privatelaw-courtadmin`) |
| Safeguarding and risk of harm (`safeguardingAndRiskOfHarm`) | [Draft](./draft.md) | — |

## In-state events

| Event | End state | Runnable by |
|---|---|---|
| Add local authority (`adminAddLocalAuthority`) | [Returned](./returned.md) | `hearing-centre-admin`, `allocated-admin-caseworker`, `ctsc`, `allocated-ctsc-caseworker` (`caseworker-privatelaw-courtadmin`)<br/>`idam:caseworker-privatelaw-superuser` (`caseworker-privatelaw-superuser`) |
| Remove barrister (`adminRemoveBarrister`) | [Returned](./returned.md) | `hearing-centre-admin`, `allocated-admin-caseworker`, `ctsc`, `allocated-ctsc-caseworker` (`caseworker-privatelaw-courtadmin`)<br/>`idam:caseworker-privatelaw-superuser` (`caseworker-privatelaw-superuser`) |
| Remove legal representative (`adminRemoveLegalRepresentativeC100`) | [Returned](./returned.md) | `hearing-centre-admin`, `allocated-admin-caseworker`, `ctsc`, `allocated-ctsc-caseworker` (`caseworker-privatelaw-courtadmin`)<br/>`idam:caseworker-privatelaw-systemupdate` (`caseworker-privatelaw-systemupdate`) |
| Remove legal representative (`adminRemoveLegalRepresentativeFL401`) | [Returned](./returned.md) | `hearing-centre-admin`, `allocated-admin-caseworker`, `ctsc`, `allocated-ctsc-caseworker` (`caseworker-privatelaw-courtadmin`)<br/>`idam:caseworker-privatelaw-systemupdate` (`caseworker-privatelaw-systemupdate`) |
| Remove local authority (`adminRemoveLocalAuthority`) | [Returned](./returned.md) | `hearing-centre-admin`, `allocated-admin-caseworker`, `ctsc`, `allocated-ctsc-caseworker` (`caseworker-privatelaw-courtadmin`)<br/>`idam:caseworker-privatelaw-superuser` (`caseworker-privatelaw-superuser`) |
| Allegations of harm (`allegationsOfHarm`) | [Returned](./returned.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen` (`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate` (`caseworker-privatelaw-systemupdate`) |
| Allegations of harm (`allegationsOfHarmRevised`) | [Returned](./returned.md) | — |
| Amend court details (`amendCourtDetails`) | [Returned](./returned.md) | `hearing-centre-admin`, `allocated-admin-caseworker`, `ctsc`, `allocated-ctsc-caseworker` (`caseworker-privatelaw-courtadmin`) |
| Applicant details (`applicantsDetails`) | [Returned](./returned.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen` (`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate` (`caseworker-privatelaw-systemupdate`) |
| Attach scanned docs (`attachScannedDocs`) | [Returned](./returned.md) | `caseworker-privatelaw-bulkscansystemupdate`<br/>`idam:caseworker-privatelaw-systemupdate` (`caseworker-privatelaw-systemupdate`)<br/>`caseworker-privatelaw-bulkscan`<br/>`hearing-centre-admin`, `allocated-admin-caseworker`, `ctsc`, `allocated-ctsc-caseworker` (`caseworker-privatelaw-courtadmin`) |
| Attending the hearing (`attendingTheHearing`) | [Returned](./returned.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen` (`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate` (`caseworker-privatelaw-systemupdate`) |
| Stop representing client (`barristerStopRepresenting`) | [Returned](./returned.md) | `[C100APPLICANTBARRISTER1]`<br/>`[C100APPLICANTBARRISTER2]`<br/>`[C100APPLICANTBARRISTER3]`<br/>`[C100APPLICANTBARRISTER4]`<br/>`[C100APPLICANTBARRISTER5]`<br/>`[C100RESPONDENTBARRISTER1]`<br/>`[C100RESPONDENTBARRISTER2]`<br/>`[C100RESPONDENTBARRISTER3]`<br/>`[C100RESPONDENTBARRISTER4]`<br/>`[C100RESPONDENTBARRISTER5]`<br/>`[FL401APPLICANTBARRISTER]`<br/>`[FL401RESPONDENTBARRISTER]` |
| Add case number (`caseNumber`) | [Returned](./returned.md) | `hearing-centre-admin`, `allocated-admin-caseworker`, `ctsc`, `allocated-ctsc-caseworker` (`caseworker-privatelaw-courtadmin`) |
| Child details (`childDetails`) | [Returned](./returned.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen` (`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate` (`caseworker-privatelaw-systemupdate`) |
| Child details (`childDetailsRevised`) | [Returned](./returned.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen` (`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate` (`caseworker-privatelaw-systemupdate`) |
| Children and applicants (`childrenAndApplicants`) | [Returned](./returned.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen` (`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate` (`caseworker-privatelaw-systemupdate`) |
| Children and other people (`childrenAndOtherPeople`) | [Returned](./returned.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen` (`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate` (`caseworker-privatelaw-systemupdate`) |
| Children and respondents (`childrenAndRespondents`) | [Returned](./returned.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen` (`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate` (`caseworker-privatelaw-systemupdate`) |
| Applicant’s family (`fl401ApplicantFamilyDetails`) | [Returned](./returned.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen` (`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate` (`caseworker-privatelaw-systemupdate`) |
| The home (`fl401Home`) | [Returned](./returned.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen` (`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate` (`caseworker-privatelaw-systemupdate`) |
| Other proceedings (`fl401OtherProceedings`) | [Returned](./returned.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen` (`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate` (`caseworker-privatelaw-systemupdate`) |
| Type of application (`fl401TypeOfApplication`) | [Returned](./returned.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen` (`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate` (`caseworker-privatelaw-systemupdate`) |
| Upload documents (`fl401UploadDocuments`) | [Returned](./returned.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen` (`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate` (`caseworker-privatelaw-systemupdate`) |
| Statement of Truth and submit (`fl401resubmit`) | [Returned](./returned.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen` (`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate` (`caseworker-privatelaw-systemupdate`) |
| Hearing urgency (`hearingUrgency`) | [Returned](./returned.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen` (`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate` (`caseworker-privatelaw-systemupdate`) |
| International element (`internationalElement`) | [Returned](./returned.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen` (`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate` (`caseworker-privatelaw-systemupdate`) |
| Litigation capacity (`litigationCapacity`) | [Returned](./returned.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen` (`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate` (`caseworker-privatelaw-systemupdate`) |
| Manage documents (`manageDocuments`) | [Returned](./returned.md) | — |
| Manage documents (`manageDocumentsNew`) | [Returned](./returned.md) | `idam:caseworker-privatelaw-solicitor` (`caseworker-privatelaw-solicitor`)<br/>`idam:citizen` (`citizen`)<br/>`hearing-centre-admin`, `allocated-admin-caseworker`, `ctsc`, `allocated-ctsc-caseworker` (`caseworker-privatelaw-courtadmin`)<br/>`caseworker-privatelaw-judge`<br/>`tribunal-caseworker`, `senior-tribunal-caseworker`, `allocated-legal-adviser` (`caseworker-privatelaw-la`)<br/>`idam:caseworker-privatelaw-systemupdate` (`caseworker-privatelaw-systemupdate`)<br/>`listed-hearing-viewer`, `caseworker-privatelaw-externaluser-viewonly` (`caseworker-privatelaw-externaluser-viewonly`)<br/>`[C100APPLICANTBARRISTER1]`<br/>`[C100APPLICANTBARRISTER2]`<br/>`[C100APPLICANTBARRISTER3]`<br/>`[C100APPLICANTBARRISTER4]`<br/>`[C100APPLICANTBARRISTER5]`<br/>`[C100RESPONDENTBARRISTER1]`<br/>`[C100RESPONDENTBARRISTER2]`<br/>`[C100RESPONDENTBARRISTER3]`<br/>`[C100RESPONDENTBARRISTER4]`<br/>`[C100RESPONDENTBARRISTER5]`<br/>`[FL401APPLICANTBARRISTER]`<br/>`[FL401RESPONDENTBARRISTER]`<br/>`[LASOCIALWORKER]`<br/>`[LASOLICITOR]` |
| MIAM (`miam`) | [Returned](./returned.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen` (`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate` (`caseworker-privatelaw-systemupdate`) |
| MIAM (`miamPolicyUpgrade`) | [Returned](./returned.md) | `[CREATOR]`<br/>`[APPLICANTSOLICITOR]`<br/>`idam:citizen` (`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate` (`caseworker-privatelaw-systemupdate`) |
| Other children not in the case (`otherChildNotInTheCase`) | [Returned](./returned.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen` (`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate` (`caseworker-privatelaw-systemupdate`) |
| Other people in the case (`otherPeopleInTheCase`) | [Returned](./returned.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen` (`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate` (`caseworker-privatelaw-systemupdate`) |
| Other people in the case (`otherPeopleInTheCaseRevised`) | [Returned](./returned.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen` (`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate` (`caseworker-privatelaw-systemupdate`) |
| Other proceedings (`otherProceedings`) | [Returned](./returned.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen` (`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate` (`caseworker-privatelaw-systemupdate`) |
| Respondent's behaviour (`respondentBehaviour`) | [Returned](./returned.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen` (`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate` (`caseworker-privatelaw-systemupdate`) |
| Relationship to respondent (`respondentRelationship`) | [Returned](./returned.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen` (`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate` (`caseworker-privatelaw-systemupdate`) |
| Respondent details (`respondentsDetails`) | [Returned](./returned.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen` (`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate` (`caseworker-privatelaw-systemupdate`) |
| Review Additional Application (`reviewAdditionalApplication`) | [Returned](./returned.md) | `hearing-centre-admin`, `allocated-admin-caseworker`, `ctsc`, `allocated-ctsc-caseworker` (`caseworker-privatelaw-courtadmin`)<br/>`caseworker-privatelaw-judge`<br/>`tribunal-caseworker`, `senior-tribunal-caseworker`, `allocated-legal-adviser` (`caseworker-privatelaw-la`)<br/>`idam:caseworker-privatelaw-systemupdate` (`caseworker-privatelaw-systemupdate`)<br/>`idam:caseworker-privatelaw-superuser` (`caseworker-privatelaw-superuser`) |
| Review documents (`reviewDocuments`) | [Returned](./returned.md) | `hearing-centre-admin`, `allocated-admin-caseworker`, `ctsc`, `allocated-ctsc-caseworker` (`caseworker-privatelaw-courtadmin`)<br/>`idam:caseworker-privatelaw-systemupdate` (`caseworker-privatelaw-systemupdate`) |
| Type of application (`selectApplicationType`) | [Returned](./returned.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen` (`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate` (`caseworker-privatelaw-systemupdate`) |
| Send and reply to messages (`sendOrReplyToMessages`) | [Returned](./returned.md) | `hearing-centre-admin`, `allocated-admin-caseworker`, `ctsc`, `allocated-ctsc-caseworker` (`caseworker-privatelaw-courtadmin`)<br/>`caseworker-privatelaw-judge`<br/>`tribunal-caseworker`, `senior-tribunal-caseworker`, `allocated-legal-adviser` (`caseworker-privatelaw-la`) |
| Remove barrister (`solicitorRemoveBarrister`) | [Returned](./returned.md) | `[C100RESPONDENTSOLICITOR1]`<br/>`[C100RESPONDENTSOLICITOR2]`<br/>`[C100RESPONDENTSOLICITOR3]`<br/>`[C100RESPONDENTSOLICITOR4]`<br/>`[C100RESPONDENTSOLICITOR5]`<br/>`[C100APPLICANTSOLICITOR1]`<br/>`[C100APPLICANTSOLICITOR2]`<br/>`[C100APPLICANTSOLICITOR3]`<br/>`[C100APPLICANTSOLICITOR4]`<br/>`[C100APPLICANTSOLICITOR5]`<br/>`[FL401RESPONDENTSOLICITOR]`<br/>`[FL401APPLICANTSOLICITOR]`<br/>`[APPLICANTSOLICITOR]` |
| Stop representing client (`solicitorStopRepresentingLiP`) | [Returned](./returned.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`[C100APPLICANTSOLICITOR1]`<br/>`[C100APPLICANTSOLICITOR2]`<br/>`[C100APPLICANTSOLICITOR3]`<br/>`[C100APPLICANTSOLICITOR4]`<br/>`[C100APPLICANTSOLICITOR5]`<br/>`[C100RESPONDENTSOLICITOR1]`<br/>`[C100RESPONDENTSOLICITOR2]`<br/>`[C100RESPONDENTSOLICITOR3]`<br/>`[C100RESPONDENTSOLICITOR4]`<br/>`[C100RESPONDENTSOLICITOR5]`<br/>`[FL401APPLICANTSOLICITOR]`<br/>`[FL401RESPONDENTSOLICITOR]`<br/>`idam:caseworker-privatelaw-systemupdate` (`caseworker-privatelaw-systemupdate`) |
| Submit (`submit`) | [Returned](./returned.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen` (`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate` (`caseworker-privatelaw-systemupdate`) |
| Upload additional applications (`uploadAdditionalApplications`) | [Returned](./returned.md) | `[APPLICANTSOLICITOR]`<br/>`[C100APPLICANTSOLICITOR1]`<br/>`[C100APPLICANTSOLICITOR2]`<br/>`[C100APPLICANTSOLICITOR3]`<br/>`[C100APPLICANTSOLICITOR4]`<br/>`[C100APPLICANTSOLICITOR5]`<br/>`[C100RESPONDENTSOLICITOR1]`<br/>`[C100RESPONDENTSOLICITOR2]`<br/>`[C100RESPONDENTSOLICITOR3]`<br/>`[C100RESPONDENTSOLICITOR4]`<br/>`[C100RESPONDENTSOLICITOR5]`<br/>`[FL401APPLICANTSOLICITOR]`<br/>`[FL401RESPONDENTSOLICITOR]`<br/>`idam:caseworker-privatelaw-systemupdate` (`caseworker-privatelaw-systemupdate`) |
| Upload documents (`uploadDocuments`) | [Returned](./returned.md) | — |
| View PDF application (`viewPdfDocument`) | [Returned](./returned.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen` (`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate` (`caseworker-privatelaw-systemupdate`) |
| Send and reply to messages (`waSendOrReplyToMessages`) | [Returned](./returned.md) | `hearing-centre-admin`, `allocated-admin-caseworker`, `ctsc`, `allocated-ctsc-caseworker` (`caseworker-privatelaw-courtadmin`)<br/>`caseworker-privatelaw-judge`<br/>`tribunal-caseworker`, `senior-tribunal-caseworker`, `allocated-legal-adviser` (`caseworker-privatelaw-la`) |
| Welsh language requirements (`welshLanguageRequirements`) | [Returned](./returned.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen` (`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate` (`caseworker-privatelaw-systemupdate`) |
| Without notice order (`withoutNoticeOrderDetails`) | [Returned](./returned.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen` (`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate` (`caseworker-privatelaw-systemupdate`) |

## Incoming events

| Event | Start state | Runnable by |
|---|---|---|
| Return application (`returnApplication`) | [Awaiting Information](./awaiting-information.md) | `hearing-centre-admin`, `allocated-admin-caseworker`, `ctsc`, `allocated-ctsc-caseworker` (`caseworker-privatelaw-courtadmin`) |
| Return application (`returnApplication`) | [Case Issued](./case-issued.md) | `hearing-centre-admin`, `allocated-admin-caseworker`, `ctsc`, `allocated-ctsc-caseworker` (`caseworker-privatelaw-courtadmin`) |
| Return application (`returnApplication`) | [Gatekeeping](./gatekeeping.md) | `hearing-centre-admin`, `allocated-admin-caseworker`, `ctsc`, `allocated-ctsc-caseworker` (`caseworker-privatelaw-courtadmin`) |
| Return application (`returnApplication`) | [Submitted](./submitted.md) | `hearing-centre-admin`, `allocated-admin-caseworker`, `ctsc`, `allocated-ctsc-caseworker` (`caseworker-privatelaw-courtadmin`) |
