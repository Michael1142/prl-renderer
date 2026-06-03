# Submitted

[Back to Private Law State Model](../index.md)

State ID: `SUBMITTED_PAID`

## Local state model

```mermaid
flowchart LR
    current["Submitted"]

    subgraph inbound["Inbound to Submitted"]
        in_all_final_orders_issued["Closed"]
        in_awaiting_information["Awaiting Information"]
        in_awaiting_resubmission_to_hmcts["Returned"]
        in_awaiting_submission_to_hmcts["Draft"]
        in_any["Any"]
        in_case_issued["Case Issued"]
        in_case_withdrawn["Withdrawn"]
        in_decision_outcome["Hearing Outcome"]
        in_judicial_review["Gatekeeping"]
        in_prepare_for_hearing_conduct_hearing["Hearing"]
        in_submitted_not_paid["Pending"]
        in_start["Start"]
    end

    subgraph outbound["Outbound from Submitted"]
        out_all_final_orders_issued["Closed"]
        out_awaiting_information["Awaiting Information"]
        out_awaiting_resubmission_to_hmcts["Returned"]
        out_case_issued["Case Issued"]
        out_case_withdrawn["Withdrawn"]
        out_judicial_review["Gatekeeping"]
        out_proceeds_in_heritage_system["Proceeding in offline mode in familyman system"]
    end

    in_all_final_orders_issued -->|"Process urgent help with fees"| current
    in_awaiting_information -->|"Process HWF for Citizen case<br/>Process urgent help with fees"| current
    in_awaiting_resubmission_to_hmcts -->|"Process urgent help with fees"| current
    in_awaiting_submission_to_hmcts -->|"Statement of Truth and submit<br/>Submit Citizen Case"| current
    in_any -->|"Payment confirmation"| current
    in_case_issued -->|"Process urgent help with fees"| current
    in_case_withdrawn -->|"Process urgent help with fees"| current
    in_decision_outcome -->|"Process urgent help with fees"| current
    in_judicial_review -->|"Process urgent help with fees"| current
    in_prepare_for_hearing_conduct_hearing -->|"Process urgent help with fees"| current
    in_submitted_not_paid -->|"Process HWF for Citizen case<br/>Process urgent help with fees"| current
    in_start -->|"Case created by courtnav"| current
    current -->|"Record final decision<br/>Create/upload draft order"| out_all_final_orders_issued
    current -->|"Request Further Information<br/>Further Information Reasons"| out_awaiting_information
    current -->|"Return application"| out_awaiting_resubmission_to_hmcts
    current -->|"Issue and send to local court<br/>Add case number"| out_case_issued
    current -->|"Withdraw application<br/>Withdraw Citizen Case"| out_case_withdrawn
    current -->|"Send to gatekeeper"| out_judicial_review
    current -->|"Issue and send to local court"| out_proceeds_in_heritage_system
```

## Outgoing events

| Event | End state | Runnable by |
|---|---|---|
| Withdraw application (`WithdrawApplication_Event`) | [Withdrawn](./withdrawn.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen`<br/>(`citizen`) |
| Withdraw Citizen Case (`citizenCaseWithdraw`) | [Withdrawn](./withdrawn.md) | `idam:citizen`<br/>(`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`) |
| Create/upload draft order (`draftAnOrder`) | [Closed](./closed.md) | `[C100APPLICANTBARRISTER1]`<br/>`[C100APPLICANTBARRISTER2]`<br/>`[C100APPLICANTBARRISTER3]`<br/>`[C100APPLICANTBARRISTER4]`<br/>`[C100APPLICANTBARRISTER5]`<br/>`[C100RESPONDENTBARRISTER1]`<br/>`[C100RESPONDENTBARRISTER2]`<br/>`[C100RESPONDENTBARRISTER3]`<br/>`[C100RESPONDENTBARRISTER4]`<br/>`[C100RESPONDENTBARRISTER5]`<br/>`[FL401APPLICANTBARRISTER]`<br/>`[FL401RESPONDENTBARRISTER]` |
| Add case number (`fl401AddCaseNumber`) | [Case Issued](./case-issued.md) | `hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`) |
| Send to gatekeeper (`fl401SendToGateKeeper`) | [Gatekeeping](./gatekeeping.md) | `hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`)<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`) |
| Issue and send to local court (`issueAndSendToLocalCourtCallback`) | [Case Issued](./case-issued.md) | `hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`) |
| Issue and send to local court (`issueAndSendToLocalCourtCallback`) | [Proceeding in offline mode in familyman system](./proceeding-in-offline-mode-in-familyman-system.md) | `hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`) |
| Record final decision (`recordFinalDecision`) | [Closed](./closed.md) | `idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`)<br/>`hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`) |
| Request Further Information (`requestFurtherInformation`) | [Awaiting Information](./awaiting-information.md) | `hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`)<br/>`ctsc-team-leader`<br/>`idam:caseworker-privatelaw-superuser`<br/>(`caseworker-privatelaw-superuser`)<br/>`idam:caseworker-wa-task-configuration`<br/>(`caseworker-wa-task-configuration`)<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`)<br/>`hearing-centre-team-leader` |
| Further Information Reasons (`requestFurtherInformationHistory`) | [Awaiting Information](./awaiting-information.md) | `hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`)<br/>`ctsc-team-leader`<br/>`idam:caseworker-privatelaw-superuser`<br/>(`caseworker-privatelaw-superuser`)<br/>`idam:caseworker-wa-task-configuration`<br/>(`caseworker-wa-task-configuration`)<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`)<br/>`hearing-centre-team-leader` |
| Return application (`returnApplication`) | [Returned](./returned.md) | `hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`) |

## In-state events

| Event | End state | Runnable by |
|---|---|---|
| Remove legal representative (`adminRemoveLegalRepresentativeC100`) | [Submitted](./submitted.md) | `hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`)<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`) |
| Remove legal representative (`adminRemoveLegalRepresentativeFL401`) | [Submitted](./submitted.md) | `hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`)<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`) |
| Amend Allegations of harm (`amendAllegationsOfHarm`) | [Submitted](./submitted.md) | `hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`)<br/>`idam:caseworker-privatelaw-superuser`<br/>(`caseworker-privatelaw-superuser`) |
| Amend Allegations of harm (`amendAllegationsOfHarmRevised`) | [Submitted](./submitted.md) | — |
| Amend applicant details (`amendApplicantsDetails`) | [Submitted](./submitted.md) | `hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`)<br/>`caseworker-privatelaw-judge`<br/>`tribunal-caseworker`<br/>`senior-tribunal-caseworker`<br/>`allocated-legal-adviser`<br/>(`caseworker-privatelaw-la`)<br/>`idam:caseworker-privatelaw-superuser`<br/>(`caseworker-privatelaw-superuser`)<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`) |
| Amend attending the hearing (`amendAttendingTheHearing`) | [Submitted](./submitted.md) | `hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`)<br/>`idam:caseworker-privatelaw-superuser`<br/>(`caseworker-privatelaw-superuser`) |
| Amend Child details (`amendChildDetails`) | [Submitted](./submitted.md) | `hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`)<br/>`caseworker-privatelaw-judge`<br/>`tribunal-caseworker`<br/>`senior-tribunal-caseworker`<br/>`allocated-legal-adviser`<br/>(`caseworker-privatelaw-la`)<br/>`idam:caseworker-privatelaw-superuser`<br/>(`caseworker-privatelaw-superuser`) |
| Amend Child details (`amendChildDetailsRevised`) | [Submitted](./submitted.md) | `hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`)<br/>`caseworker-privatelaw-judge`<br/>`tribunal-caseworker`<br/>`senior-tribunal-caseworker`<br/>`allocated-legal-adviser`<br/>(`caseworker-privatelaw-la`)<br/>`idam:caseworker-privatelaw-superuser`<br/>(`caseworker-privatelaw-superuser`) |
| Amend children and applicants (`amendChildrenAndApplicants`) | [Submitted](./submitted.md) | `hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`)<br/>`caseworker-privatelaw-judge`<br/>`tribunal-caseworker`<br/>`senior-tribunal-caseworker`<br/>`allocated-legal-adviser`<br/>(`caseworker-privatelaw-la`)<br/>`idam:caseworker-privatelaw-superuser`<br/>(`caseworker-privatelaw-superuser`) |
| Amend children/other people (`amendChildrenAndOtherPeople`) | [Submitted](./submitted.md) | `hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`)<br/>`idam:caseworker-privatelaw-superuser`<br/>(`caseworker-privatelaw-superuser`) |
| Amend children and respondents (`amendChildrenAndRespondents`) | [Submitted](./submitted.md) | `hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`)<br/>`caseworker-privatelaw-judge`<br/>`tribunal-caseworker`<br/>`senior-tribunal-caseworker`<br/>`allocated-legal-adviser`<br/>(`caseworker-privatelaw-la`)<br/>`idam:caseworker-privatelaw-superuser`<br/>(`caseworker-privatelaw-superuser`) |
| Amend court details (`amendCourtDetails`) | [Submitted](./submitted.md) | `hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`) |
| Amend Hearing urgency (`amendHearingUrgency`) | [Submitted](./submitted.md) | `hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`)<br/>`idam:caseworker-privatelaw-superuser`<br/>(`caseworker-privatelaw-superuser`) |
| Amend International element (`amendInternationalElement`) | [Submitted](./submitted.md) | `hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`)<br/>`idam:caseworker-privatelaw-superuser`<br/>(`caseworker-privatelaw-superuser`) |
| Amend Litigation capacity (`amendLitigationCapacity`) | [Submitted](./submitted.md) | `hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`)<br/>`idam:caseworker-privatelaw-superuser`<br/>(`caseworker-privatelaw-superuser`) |
| Amend MIAM (`amendMiam`) | [Submitted](./submitted.md) | `hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`)<br/>`idam:caseworker-privatelaw-superuser`<br/>(`caseworker-privatelaw-superuser`) |
| Amend MIAM (`amendMiamPolicyUpgrade`) | [Submitted](./submitted.md) | `hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`)<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`) |
| Amend children not in the case (`amendOtherChildNotInTheCase`) | [Submitted](./submitted.md) | `hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`)<br/>`idam:caseworker-privatelaw-superuser`<br/>(`caseworker-privatelaw-superuser`) |
| Amend Other people in the case (`amendOtherPeopleInTheCase`) | [Submitted](./submitted.md) | `caseworker-privatelaw-judge`<br/>`hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`)<br/>`idam:caseworker-privatelaw-superuser`<br/>(`caseworker-privatelaw-superuser`) |
| Amend Other people in the case (`amendOtherPeopleInTheCaseRevised`) | [Submitted](./submitted.md) | `hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`)<br/>`idam:caseworker-privatelaw-superuser`<br/>(`caseworker-privatelaw-superuser`) |
| Amend Other proceedings (`amendOtherProceedings`) | [Submitted](./submitted.md) | `hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`)<br/>`idam:caseworker-privatelaw-superuser`<br/>(`caseworker-privatelaw-superuser`) |
| Amend respondent's behaviour (`amendRespondentBehaviour`) | [Submitted](./submitted.md) | `hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`)<br/>`idam:caseworker-privatelaw-superuser`<br/>(`caseworker-privatelaw-superuser`) |
| Amend respondent relationship (`amendRespondentRelationship`) | [Submitted](./submitted.md) | `hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`)<br/>`idam:caseworker-privatelaw-superuser`<br/>(`caseworker-privatelaw-superuser`) |
| Amend respondent details (`amendRespondentsDetails`) | [Submitted](./submitted.md) | `hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`)<br/>`caseworker-privatelaw-judge`<br/>`tribunal-caseworker`<br/>`senior-tribunal-caseworker`<br/>`allocated-legal-adviser`<br/>(`caseworker-privatelaw-la`)<br/>`idam:caseworker-privatelaw-superuser`<br/>(`caseworker-privatelaw-superuser`) |
| Amend Type of application (`amendSelectApplicationType`) | [Submitted](./submitted.md) | `hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`)<br/>`idam:caseworker-privatelaw-superuser`<br/>(`caseworker-privatelaw-superuser`) |
| Welsh language requirements (`amendWelshLanguageRequirements`) | [Submitted](./submitted.md) | `hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`)<br/>`idam:caseworker-privatelaw-superuser`<br/>(`caseworker-privatelaw-superuser`) |
| Amend without notice order (`amendWithoutNoticeOrderDetails`) | [Submitted](./submitted.md) | `hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`)<br/>`idam:caseworker-privatelaw-superuser`<br/>(`caseworker-privatelaw-superuser`) |
| Attach scanned docs (`attachScannedDocs`) | [Submitted](./submitted.md) | `caseworker-privatelaw-bulkscansystemupdate`<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`)<br/>`caseworker-privatelaw-bulkscan`<br/>`hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`) |
| Manage support (`c100ManageSupport`) | [Submitted](./submitted.md) | `idam:citizen`<br/>(`citizen`)<br/>`[CREATOR]`<br/>`[APPLICANTSOLICITOR]`<br/>`[C100APPLICANTSOLICITOR1]`<br/>`[C100APPLICANTSOLICITOR2]`<br/>`[C100APPLICANTSOLICITOR3]`<br/>`[C100APPLICANTSOLICITOR4]`<br/>`[C100APPLICANTSOLICITOR5]`<br/>`[C100RESPONDENTSOLICITOR1]`<br/>`[C100RESPONDENTSOLICITOR2]`<br/>`[C100RESPONDENTSOLICITOR3]`<br/>`[C100RESPONDENTSOLICITOR4]`<br/>`[C100RESPONDENTSOLICITOR5]`<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`) |
| Request support (`c100RequestSupport`) | [Submitted](./submitted.md) | `idam:citizen`<br/>(`citizen`)<br/>`[CREATOR]`<br/>`[APPLICANTSOLICITOR]`<br/>`[C100APPLICANTSOLICITOR1]`<br/>`[C100APPLICANTSOLICITOR2]`<br/>`[C100APPLICANTSOLICITOR3]`<br/>`[C100APPLICANTSOLICITOR4]`<br/>`[C100APPLICANTSOLICITOR5]`<br/>`[C100RESPONDENTSOLICITOR1]`<br/>`[C100RESPONDENTSOLICITOR2]`<br/>`[C100RESPONDENTSOLICITOR3]`<br/>`[C100RESPONDENTSOLICITOR4]`<br/>`[C100RESPONDENTSOLICITOR5]`<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`) |
| Link cases (`createCaseLink`) | [Submitted](./submitted.md) | — |
| Amend applicant’s family (`fl401AmendApplicantFamilyDetails`) | [Submitted](./submitted.md) | `hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`)<br/>`idam:caseworker-privatelaw-superuser`<br/>(`caseworker-privatelaw-superuser`) |
| Amend the home details (`fl401AmendHome`) | [Submitted](./submitted.md) | `hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`)<br/>`idam:caseworker-privatelaw-superuser`<br/>(`caseworker-privatelaw-superuser`) |
| Amend other proceedings (`fl401AmendOtherProceedings`) | [Submitted](./submitted.md) | `hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`)<br/>`idam:caseworker-privatelaw-superuser`<br/>(`caseworker-privatelaw-superuser`) |
| Amend type of application (`fl401AmendTypeOfApplication`) | [Submitted](./submitted.md) | `hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`)<br/>`idam:caseworker-privatelaw-superuser`<br/>(`caseworker-privatelaw-superuser`) |
| Manage support (`fl401ManageSupport`) | [Submitted](./submitted.md) | `idam:citizen`<br/>(`citizen`)<br/>`[CREATOR]`<br/>`[APPLICANTSOLICITOR]`<br/>`[FL401APPLICANTSOLICITOR]`<br/>`[FL401RESPONDENTSOLICITOR]`<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`) |
| Request support (`fl401RequestSupport`) | [Submitted](./submitted.md) | `idam:citizen`<br/>(`citizen`)<br/>`[CREATOR]`<br/>`[APPLICANTSOLICITOR]`<br/>`[FL401APPLICANTSOLICITOR]`<br/>`[FL401RESPONDENTSOLICITOR]`<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`) |
| Manage case links (`maintainCaseLink`) | [Submitted](./submitted.md) | — |
| Manage documents (`manageDocuments`) | [Submitted](./submitted.md) | — |
| Manage documents (`manageDocumentsNew`) | [Submitted](./submitted.md) | `idam:caseworker-privatelaw-solicitor`<br/>(`caseworker-privatelaw-solicitor`)<br/>`idam:citizen`<br/>(`citizen`)<br/>`hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`)<br/>`caseworker-privatelaw-judge`<br/>`tribunal-caseworker`<br/>`senior-tribunal-caseworker`<br/>`allocated-legal-adviser`<br/>(`caseworker-privatelaw-la`)<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`)<br/>`listed-hearing-viewer`<br/>`caseworker-privatelaw-externaluser-viewonly`<br/>(`caseworker-privatelaw-externaluser-viewonly`)<br/>`[C100APPLICANTBARRISTER1]`<br/>`[C100APPLICANTBARRISTER2]`<br/>`[C100APPLICANTBARRISTER3]`<br/>`[C100APPLICANTBARRISTER4]`<br/>`[C100APPLICANTBARRISTER5]`<br/>`[C100RESPONDENTBARRISTER1]`<br/>`[C100RESPONDENTBARRISTER2]`<br/>`[C100RESPONDENTBARRISTER3]`<br/>`[C100RESPONDENTBARRISTER4]`<br/>`[C100RESPONDENTBARRISTER5]`<br/>`[FL401APPLICANTBARRISTER]`<br/>`[FL401RESPONDENTBARRISTER]`<br/>`[LASOCIALWORKER]`<br/>`[LASOLICITOR]` |
| Process urgent help with fees (`processUrgentHelpWithFees`) | [Submitted](./submitted.md) | `idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`)<br/>`hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`) |
| Review Additional Application (`reviewAdditionalApplication`) | [Submitted](./submitted.md) | `hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`)<br/>`caseworker-privatelaw-judge`<br/>`tribunal-caseworker`<br/>`senior-tribunal-caseworker`<br/>`allocated-legal-adviser`<br/>(`caseworker-privatelaw-la`)<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`)<br/>`idam:caseworker-privatelaw-superuser`<br/>(`caseworker-privatelaw-superuser`) |
| Review documents (`reviewDocuments`) | [Submitted](./submitted.md) | `hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`)<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`) |
| Send and reply to messages (`sendOrReplyToMessages`) | [Submitted](./submitted.md) | `hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`)<br/>`caseworker-privatelaw-judge`<br/>`tribunal-caseworker`<br/>`senior-tribunal-caseworker`<br/>`allocated-legal-adviser`<br/>(`caseworker-privatelaw-la`) |
| Transfer to another court (`transferToAnotherCourt`) | [Submitted](./submitted.md) | `hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`)<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`) |
| Upload additional applications (`uploadAdditionalApplications`) | [Submitted](./submitted.md) | `[APPLICANTSOLICITOR]`<br/>`[C100APPLICANTSOLICITOR1]`<br/>`[C100APPLICANTSOLICITOR2]`<br/>`[C100APPLICANTSOLICITOR3]`<br/>`[C100APPLICANTSOLICITOR4]`<br/>`[C100APPLICANTSOLICITOR5]`<br/>`[C100RESPONDENTSOLICITOR1]`<br/>`[C100RESPONDENTSOLICITOR2]`<br/>`[C100RESPONDENTSOLICITOR3]`<br/>`[C100RESPONDENTSOLICITOR4]`<br/>`[C100RESPONDENTSOLICITOR5]`<br/>`[FL401APPLICANTSOLICITOR]`<br/>`[FL401RESPONDENTSOLICITOR]`<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`) |
| Send and reply to messages (`waSendOrReplyToMessages`) | [Submitted](./submitted.md) | `hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`)<br/>`caseworker-privatelaw-judge`<br/>`tribunal-caseworker`<br/>`senior-tribunal-caseworker`<br/>`allocated-legal-adviser`<br/>(`caseworker-privatelaw-la`) |

## Incoming events

| Event | Start state | Runnable by |
|---|---|---|
| Submit Citizen Case (`citizen-case-submit`) | [Draft](./draft.md) | `idam:citizen`<br/>(`citizen`)<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`) |
| Case created by courtnav (`courtnav-case-creation`) | `__START__` | `idam:courtnav`<br/>(`courtnav`)<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`) |
| Statement of Truth and submit (`fl401StatementOfTruthAndSubmit`) | [Draft](./draft.md) | `[APPLICANTSOLICITOR]`<br/>`[CREATOR]`<br/>`idam:citizen`<br/>(`citizen`)<br/>`hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`)<br/>`idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`) |
| Process HWF for Citizen case (`hwfProcessCaseUpdate`) | [Awaiting Information](./awaiting-information.md) | `idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`) |
| Process HWF for Citizen case (`hwfProcessCaseUpdate`) | [Pending](./pending.md) | `idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`) |
| Payment confirmation (`paymentSuccessCallback`) | `Any` | `idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`) |
| Process urgent help with fees (`processUrgentHelpWithFees`) | [Closed](./closed.md) | `idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`)<br/>`hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`) |
| Process urgent help with fees (`processUrgentHelpWithFees`) | [Awaiting Information](./awaiting-information.md) | `idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`)<br/>`hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`) |
| Process urgent help with fees (`processUrgentHelpWithFees`) | [Returned](./returned.md) | `idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`)<br/>`hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`) |
| Process urgent help with fees (`processUrgentHelpWithFees`) | [Case Issued](./case-issued.md) | `idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`)<br/>`hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`) |
| Process urgent help with fees (`processUrgentHelpWithFees`) | [Withdrawn](./withdrawn.md) | `idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`)<br/>`hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`) |
| Process urgent help with fees (`processUrgentHelpWithFees`) | [Hearing Outcome](./hearing-outcome.md) | `idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`)<br/>`hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`) |
| Process urgent help with fees (`processUrgentHelpWithFees`) | [Gatekeeping](./gatekeeping.md) | `idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`)<br/>`hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`) |
| Process urgent help with fees (`processUrgentHelpWithFees`) | [Hearing](./hearing.md) | `idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`)<br/>`hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`) |
| Process urgent help with fees (`processUrgentHelpWithFees`) | [Pending](./pending.md) | `idam:caseworker-privatelaw-systemupdate`<br/>(`caseworker-privatelaw-systemupdate`)<br/>`hearing-centre-admin`<br/>`allocated-admin-caseworker`<br/>`ctsc`<br/>`allocated-ctsc-caseworker`<br/>(`caseworker-privatelaw-courtadmin`) |
