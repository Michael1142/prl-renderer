# Information Requested

[Back to No Fault Divorce State Model](../index.md)

State ID: `InformationRequested`

## Local state model

```mermaid
flowchart LR
    current["Information Requested"]

    subgraph outbound["Outbound from Information Requested"]
        out_awaitingalternativeservice["Awaiting alternative service"]
        out_awaitingamendedapplication["Awaiting amended application"]
        out_awaitingdocuments["Awaiting applicant"]
        out_awaitinghwfevidence["Awaiting HWF evidence"]
        out_awaitinghwfpartpayment["Awaiting HWF part payment"]
        out_awaitingresponsetohwfdecision["Awaiting response to HWF Decision"]
        out_offlinedocumentreceived["Offline document received by CW"]
        out_rejected["Application rejected"]
        out_submitted["Submitted"]
        out_withdrawn["Application withdrawn"]
    end

    current -->|"Serve by alternative method"| out_awaitingalternativeservice
    current -->|"Awaiting Amended Application"| out_awaitingamendedapplication
    current -->|"Awaiting Applicant"| out_awaitingdocuments
    current -->|"HWF evidence required"| out_awaitinghwfevidence
    current -->|"HWF part payment required"| out_awaitinghwfpartpayment
    current -->|"HWF refused"| out_awaitingresponsetohwfdecision
    current -->|"Attach scanned docs"| out_offlinedocumentreceived
    current -->|"Reject"| out_rejected
    current -->|"HWF part payment made"| out_submitted
    current -->|"Withdraw"| out_withdrawn
```

## Outgoing events

| Event | End state | Runnable by | Enabling condition |
|---|---|---|---|
| Attach scanned docs (`attachScannedDocs`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Awaiting Amended Application (`caseworker-awaiting-amended-application`) | [Awaiting amended application](./awaiting-amended-application.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-courtadmin_beta` | — |
| HWF evidence required (`caseworker-hwf-evidence-requested`) | [Awaiting HWF evidence](./awaiting-hwf-evidence.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| HWF part payment made (`caseworker-hwf-part-payment-made`) | [Submitted](./submitted.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| HWF part payment required (`caseworker-hwf-part-payment-required`) | [Awaiting HWF part payment](./awaiting-hwf-part-payment.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| HWF refused (`caseworker-hwf-refused`) | [Awaiting response to HWF Decision](./awaiting-response-to-hwf-decision.md) | `caseworker-divorce-courtadmin_beta` | — |
| Reject (`caseworker-rejected`) | [Application rejected](./application-rejected.md) | `caseworker-divorce-courtadmin_beta` | — |
| Serve by alternative method (`caseworker-serve-by-alternative-method`) | [Awaiting alternative service](./awaiting-alternative-service.md) | `caseworker-divorce-courtadmin_beta` | — |
| Withdraw (`caseworker-withdrawn`) | [Application withdrawn](./application-withdrawn.md) | `caseworker-divorce-courtadmin_beta` | — |

## In-state events

| Event | End state | Runnable by | Enabling condition |
|---|---|---|---|
| Submit Response (`app1-solicitor-respond-request-info`) | [Information Requested](./information-requested.md) | `[APPONESOLICITOR]` | `requestForInformationAuthParty="applicant1" OR requestForInformationAuthParty="both"` |
| Update contact info (`app1-solicitor-update-contact-details`) | [Information Requested](./information-requested.md) | `[APPONESOLICITOR]` | — |
| View applicant contact info (`app1-solicitor-view-app1-contact-info`) | [Information Requested](./information-requested.md) | `[APPONESOLICITOR]` | — |
| View respondent contact info (`app1-solicitor-view-app2-contact-info`) | [Information Requested](./information-requested.md) | `[APPONESOLICITOR]` | — |
| Submit Response (`app2-solicitor-respond-request-info`) | [Information Requested](./information-requested.md) | `[APPTWOSOLICITOR]` | `requestForInformationAuthParty="applicant2" OR requestForInformationAuthParty="both"` |
| Update contact info (`app2-solicitor-update-contact-details`) | [Information Requested](./information-requested.md) | `[APPTWOSOLICITOR]` | — |
| View applicant contact info (`app2-solicitor-view-app1-contact-info`) | [Information Requested](./information-requested.md) | `[APPTWOSOLICITOR]` | — |
| View respondent contact info (`app2-solicitor-view-app2-contact-info`) | [Information Requested](./information-requested.md) | `[APPTWOSOLICITOR]` | — |
| Add bailiff return (`caseworker-add-bailiff-return`) | [Information Requested](./information-requested.md) | `caseworker-divorce-courtadmin-la`<br/>`caseworker-divorce-courtadmin_beta` | — |
| Add note (`caseworker-add-note`) | [Information Requested](./information-requested.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Add translation (`caseworker-add-translation`) | [Information Requested](./information-requested.md) | `caseworker-divorce-courtadmin_beta` | — |
| Amend application type (`caseworker-amend-application-type`) | [Information Requested](./information-requested.md) | `caseworker-divorce-superuser` | — |
| Update case (`caseworker-amend-case`) | [Information Requested](./information-requested.md) | `caseworker-divorce-courtadmin_beta` | — |
| Change service request (`caseworker-change-service-request`) | [Information Requested](./information-requested.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Confirm service (`caseworker-confirm-service`) | [Information Requested](./information-requested.md) | `caseworker-divorce-courtadmin_beta` | `issueDate="*"` |
| Create general email (`caseworker-create-general-email`) | [Information Requested](./information-requested.md) | `caseworker-divorce-courtadmin_beta` | — |
| Create general letter (`caseworker-create-general-letter`) | [Information Requested](./information-requested.md) | `caseworker-divorce-courtadmin_beta` | — |
| Create general order (`caseworker-create-general-order`) | [Information Requested](./information-requested.md) | `caseworker-divorce-courtadmin_beta` | — |
| Find matches (`caseworker-find-matches`) | [Information Requested](./information-requested.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| General referral (`caseworker-general-referral`) | [Information Requested](./information-requested.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| HWF application accepted (`caseworker-hwf-application-accepted`) | [Information Requested](./information-requested.md) | `caseworker-divorce-courtadmin_beta` | — |
| Application issue (`caseworker-issue-application`) | [Information Requested](./information-requested.md) | `caseworker-divorce-courtadmin_beta` | — |
| Notice of change (`caseworker-notice-of-change`) | [Information Requested](./information-requested.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Payment made (`caseworker-payment-made`) | [Information Requested](./information-requested.md) | `caseworker-divorce-courtadmin_beta` | — |
| Prepare for Case flags (`caseworker-prepare-caseflags`) | [Information Requested](./information-requested.md) | `caseworker-divorce-courtadmin-la`<br/>`caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-judge`<br/>`caseworker-divorce-superuser` | `caseFlagsSetupComplete!="Yes"` |
| Prepare email attachments (`caseworker-prepare-general-email`) | [Information Requested](./information-requested.md) | `caseworker-divorce-courtadmin_beta` | — |
| Regenerate court orders (`caseworker-regenerate-court-orders`) | [Information Requested](./information-requested.md) | `caseworker-divorce-superuser` | — |
| Reissue (`caseworker-reissue-application`) | [Information Requested](./information-requested.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Reject Service Application (`caseworker-reject-service-application`) | [Information Requested](./information-requested.md) | `caseworker-divorce-superuser` | — |
| Remove documents (`caseworker-remove-document`) | [Information Requested](./information-requested.md) | `caseworker-divorce-superuser` | — |
| Remove Failed Sol NoC Request (`caseworker-remove-failed-sol-noc-request`) | [Information Requested](./information-requested.md) | `caseworker-divorce-superuser` | — |
| Remove general emails (`caseworker-remove-general-emails`) | [Information Requested](./information-requested.md) | `caseworker-divorce-superuser` | — |
| Remove general letter (`caseworker-remove-general-letter`) | [Information Requested](./information-requested.md) | `caseworker-divorce-superuser` | — |
| Remove General Order (`caseworker-remove-general-order`) | [Information Requested](./information-requested.md) | `caseworker-divorce-superuser` | — |
| Remove note (`caseworker-remove-note`) | [Information Requested](./information-requested.md) | `caseworker-divorce-superuser` | — |
| Remove scanned document (`caseworker-remove-scanned-document`) | [Information Requested](./information-requested.md) | `caseworker-divorce-courtadmin_beta` | — |
| Request For Information (`caseworker-request-for-information`) | [Information Requested](./information-requested.md) | `caseworker-divorce-courtadmin_beta` | — |
| Add RFI Response (`caseworker-request-for-information-response`) | [Information Requested](./information-requested.md) | `caseworker-divorce-bulkscan`<br/>`caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Request Translation from WLU (`caseworker-request-translation-wlu`) | [Information Requested](./information-requested.md) | `caseworker-divorce-courtadmin_beta` | — |
| Return to previous state (`caseworker-return-to-previous-state`) | [Information Requested](./information-requested.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Service application received (`caseworker-service-received`) | [Information Requested](./information-requested.md) | `caseworker-divorce-courtadmin_beta` | — |
| Applicant responded (`caseworker-submit-from-awaitingdocuments-app1resp`) | [Information Requested](./information-requested.md) | `caseworker-divorce-courtadmin_beta` | — |
| Update App or App1 Email (`caseworker-update-app1-email`) | [Information Requested](./information-requested.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Update Resp or App 2 Email (`caseworker-update-app2-email`) | [Information Requested](./information-requested.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Update contact details (`caseworker-update-contact-details`) | [Information Requested](./information-requested.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Update Date Submitted (`caseworker-update-date-submitted`) | [Information Requested](./information-requested.md) | `caseworker-divorce-superuser` | — |
| Update due date (`caseworker-update-due-date`) | [Information Requested](./information-requested.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Update FinRem and Jurisdiction (`caseworker-update-fin-rem-and-jurisd-joint`) | [Information Requested](./information-requested.md) | `caseworker-divorce-superuser` | `applicationType="jointApplication"` |
| Update FinRem and Jurisdiction (`caseworker-update-fin-rem-and-jurisdiction`) | [Information Requested](./information-requested.md) | `caseworker-divorce-superuser` | `applicationType="soleApplication"` |
| Update general application (`caseworker-update-general-application`) | [Information Requested](./information-requested.md) | `caseworker-divorce-courtadmin_beta` | — |
| Update language preference (`caseworker-update-language-preference`) | [Information Requested](./information-requested.md) | `caseworker-divorce-courtadmin_beta` | — |
| Update offline status (`caseworker-update-offline-status`) | [Information Requested](./information-requested.md) | `caseworker-divorce-superuser` | — |
| Upload amended application (`caseworker-upload-amended-application`) | [Information Requested](./information-requested.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Upload confidential document (`caseworker-upload-confidential-document`) | [Information Requested](./information-requested.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-rparobot` | — |
| Upload document (`caseworker-upload-document`) | [Information Requested](./information-requested.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-rparobot` | — |
| Upload documents and submit (`caseworker-upload-documents-and-submit`) | [Information Requested](./information-requested.md) | `caseworker-divorce-courtadmin_beta` | — |
| Patch a joint case (`citizen-applicant2-update-application`) | [Information Requested](./information-requested.md) | `[APPLICANTTWO]` | `divorceOrDissolution="NEVER_SHOW"` |
| General application payment (`citizen-general-app-payment`) | [Information Requested](./information-requested.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Citizen general application (`citizen-general-application`) | [Information Requested](./information-requested.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Generate Process Server Docs (`citizen-generate-process-server-docs`) | [Information Requested](./information-requested.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Submit response for rfi (`citizen-respond-request-for-information`) | [Information Requested](./information-requested.md) | `[APPLICANTTWO]`<br/>`[CREATOR]` | — |
| Citizen service application (`citizen-service-application`) | [Information Requested](./information-requested.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Citizen service payment made (`citizen-service-payment-made`) | [Information Requested](./information-requested.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Start Interim Application (`citizen-start-interim-application`) | [Information Requested](./information-requested.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Patch case (`citizen-update-application`) | [Information Requested](./information-requested.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Create flags (`createFlags`) | [Information Requested](./information-requested.md) | `caseworker-divorce-courtadmin-la`<br/>`caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-judge`<br/>`caseworker-divorce-superuser` | `caseFlagsSetupComplete="Yes"` |
| General application received (`cw-general-application-received`) | [Information Requested](./information-requested.md) | `caseworker-divorce-courtadmin_beta` | — |
| General application refund (`general-application-refund`) | [Information Requested](./information-requested.md) | `caseworker-divorce-superuser` | — |
| Manage flags (`manageFlags`) | [Information Requested](./information-requested.md) | `caseworker-divorce-courtadmin-la`<br/>`caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-judge`<br/>`caseworker-divorce-superuser` | `caseFlagsSetupComplete="Yes"` |
| Notice Of Change Applied (`notice-of-change-applied`) | [Information Requested](./information-requested.md) | `caseworker-approver` | — |
| Notice Of Change Requested (`notice-of-change-requested`) | [Information Requested](./information-requested.md) | `caseworker-caa` | — |
| Reject general application (`reject-general-application`) | [Information Requested](./information-requested.md) | `caseworker-divorce-courtadmin_beta` | — |
| Remission refund (`remission-refund`) | [Information Requested](./information-requested.md) | `caseworker-divorce-superuser` | — |
| Service application refund (`service-application-refund`) | [Information Requested](./information-requested.md) | `caseworker-divorce-superuser` | — |
| General Application (`solicitor-general-application`) | [Information Requested](./information-requested.md) | `[APPONESOLICITOR]`<br/>`[APPTWOSOLICITOR]` | — |
| Stop representing client (`solicitor-stop-representation`) | [Information Requested](./information-requested.md) | `[APPONESOLICITOR]`<br/>`[APPTWOSOLICITOR]` | — |
| Link Resp or App 2 to case (`system-link-applicant2`) | [Information Requested](./information-requested.md) | `caseworker-divorce-systemupdate` | — |
| Migrate case data (`system-migrate-case`) | [Information Requested](./information-requested.md) | `caseworker-divorce-systemupdate` | — |
| Migrate organisation policies (`system-migrate-organisation-policies`) | [Information Requested](./information-requested.md) | `caseworker-divorce-systemupdate` | — |
| System remove bulk case (`system-remove-bulk-case`) | [Information Requested](./information-requested.md) | `caseworker-divorce-superuser`<br/>`caseworker-divorce-systemupdate` | — |
| Update issue date (`system-update-issue-date`) | [Information Requested](./information-requested.md) | `caseworker-divorce-systemupdate` | — |

## Incoming events

_No events found._
