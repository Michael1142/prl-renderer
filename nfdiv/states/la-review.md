# LA Review

[Back to No Fault Divorce State Model](../index.md)

State ID: `LAReview`

## Local state model

```mermaid
flowchart LR
    current["LA Review"]

    subgraph inbound["Inbound to LA Review"]
        in_awaitingadminclarification["Awaiting admin clarification"]
        in_awaitingclarification["Awaiting clarification"]
        in_awaitinglegaladvisorreferral["Awaiting legal advisor referral"]
        in_awaitingserviceconsideration["Awaiting service consideration"]
        in_clarificationsubmitted["Clarification response submitted"]
        in_conditionalorderreview["Conditional order review caseworker"]
        in_jsawaitingla["Judicial Separation, Awaiting legal advisor"]
        in_laservicereview["LA service app review"]
    end

    subgraph outbound["Outbound from LA Review"]
        out_awaitingalternativeservice["Awaiting alternative service"]
        out_awaitingamendedapplication["Awaiting amended application"]
        out_awaitingdocuments["Awaiting applicant"]
        out_offlinedocumentreceived["Offline document received by CW"]
        out_rejected["Application rejected"]
        out_withdrawn["Application withdrawn"]
    end

    in_awaitingadminclarification -->|"LA Review"| current
    in_awaitingclarification -->|"LA Review"| current
    in_awaitinglegaladvisorreferral -->|"LA Review"| current
    in_awaitingserviceconsideration -->|"LA Review"| current
    in_clarificationsubmitted -->|"LA Review"| current
    in_conditionalorderreview -->|"LA Review"| current
    in_jsawaitingla -->|"LA Review"| current
    in_laservicereview -->|"LA Review"| current
    current -->|"Serve by alternative method"| out_awaitingalternativeservice
    current -->|"Awaiting Amended Application"| out_awaitingamendedapplication
    current -->|"Awaiting Applicant"| out_awaitingdocuments
    current -->|"Attach scanned docs"| out_offlinedocumentreceived
    current -->|"Reject"| out_rejected
    current -->|"Withdraw"| out_withdrawn
```

## Outgoing events

| Event | End state | Runnable by | Enabling condition |
|---|---|---|---|
| Attach scanned docs (`attachScannedDocs`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Awaiting Amended Application (`caseworker-awaiting-amended-application`) | [Awaiting amended application](./awaiting-amended-application.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-courtadmin_beta` | — |
| Reject (`caseworker-rejected`) | [Application rejected](./application-rejected.md) | `caseworker-divorce-courtadmin_beta` | — |
| Serve by alternative method (`caseworker-serve-by-alternative-method`) | [Awaiting alternative service](./awaiting-alternative-service.md) | `caseworker-divorce-courtadmin_beta` | — |
| Withdraw (`caseworker-withdrawn`) | [Application withdrawn](./application-withdrawn.md) | `caseworker-divorce-courtadmin_beta` | — |

## In-state events

| Event | End state | Runnable by | Enabling condition |
|---|---|---|---|
| Update contact info (`app1-solicitor-update-contact-details`) | [LA Review](./la-review.md) | `[APPONESOLICITOR]` | — |
| View applicant contact info (`app1-solicitor-view-app1-contact-info`) | [LA Review](./la-review.md) | `[APPONESOLICITOR]` | — |
| View respondent contact info (`app1-solicitor-view-app2-contact-info`) | [LA Review](./la-review.md) | `[APPONESOLICITOR]` | — |
| Update contact info (`app2-solicitor-update-contact-details`) | [LA Review](./la-review.md) | `[APPTWOSOLICITOR]` | — |
| View applicant contact info (`app2-solicitor-view-app1-contact-info`) | [LA Review](./la-review.md) | `[APPTWOSOLICITOR]` | — |
| View respondent contact info (`app2-solicitor-view-app2-contact-info`) | [LA Review](./la-review.md) | `[APPTWOSOLICITOR]` | — |
| Add note (`caseworker-add-note`) | [LA Review](./la-review.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Add translation (`caseworker-add-translation`) | [LA Review](./la-review.md) | `caseworker-divorce-courtadmin_beta` | — |
| Amend application type (`caseworker-amend-application-type`) | [LA Review](./la-review.md) | `caseworker-divorce-superuser` | — |
| Update case (`caseworker-amend-case`) | [LA Review](./la-review.md) | `caseworker-divorce-courtadmin_beta` | — |
| Confirm service (`caseworker-confirm-service`) | [LA Review](./la-review.md) | `caseworker-divorce-courtadmin_beta` | `issueDate="*"` |
| Create general email (`caseworker-create-general-email`) | [LA Review](./la-review.md) | `caseworker-divorce-courtadmin_beta` | — |
| Create general letter (`caseworker-create-general-letter`) | [LA Review](./la-review.md) | `caseworker-divorce-courtadmin_beta` | — |
| Create general order (`caseworker-create-general-order`) | [LA Review](./la-review.md) | `caseworker-divorce-courtadmin_beta` | — |
| Find matches (`caseworker-find-matches`) | [LA Review](./la-review.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| General referral (`caseworker-general-referral`) | [LA Review](./la-review.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Notice of change (`caseworker-notice-of-change`) | [LA Review](./la-review.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Prepare for Case flags (`caseworker-prepare-caseflags`) | [LA Review](./la-review.md) | `caseworker-divorce-courtadmin-la`<br/>`caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-judge`<br/>`caseworker-divorce-superuser` | `caseFlagsSetupComplete!="Yes"` |
| Prepare email attachments (`caseworker-prepare-general-email`) | [LA Review](./la-review.md) | `caseworker-divorce-courtadmin_beta` | — |
| Regenerate court orders (`caseworker-regenerate-court-orders`) | [LA Review](./la-review.md) | `caseworker-divorce-superuser` | — |
| Reject Service Application (`caseworker-reject-service-application`) | [LA Review](./la-review.md) | `caseworker-divorce-superuser` | — |
| Remove documents (`caseworker-remove-document`) | [LA Review](./la-review.md) | `caseworker-divorce-superuser` | — |
| Remove Failed Sol NoC Request (`caseworker-remove-failed-sol-noc-request`) | [LA Review](./la-review.md) | `caseworker-divorce-superuser` | — |
| Remove general emails (`caseworker-remove-general-emails`) | [LA Review](./la-review.md) | `caseworker-divorce-superuser` | — |
| Remove general letter (`caseworker-remove-general-letter`) | [LA Review](./la-review.md) | `caseworker-divorce-superuser` | — |
| Remove General Order (`caseworker-remove-general-order`) | [LA Review](./la-review.md) | `caseworker-divorce-superuser` | — |
| Remove note (`caseworker-remove-note`) | [LA Review](./la-review.md) | `caseworker-divorce-superuser` | — |
| Remove scanned document (`caseworker-remove-scanned-document`) | [LA Review](./la-review.md) | `caseworker-divorce-courtadmin_beta` | — |
| Request Translation from WLU (`caseworker-request-translation-wlu`) | [LA Review](./la-review.md) | `caseworker-divorce-courtadmin_beta` | — |
| Return to previous state (`caseworker-return-to-previous-state`) | [LA Review](./la-review.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Update App or App1 Email (`caseworker-update-app1-email`) | [LA Review](./la-review.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Update Resp or App 2 Email (`caseworker-update-app2-email`) | [LA Review](./la-review.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Update contact details (`caseworker-update-contact-details`) | [LA Review](./la-review.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Update Date Submitted (`caseworker-update-date-submitted`) | [LA Review](./la-review.md) | `caseworker-divorce-superuser` | — |
| Update due date (`caseworker-update-due-date`) | [LA Review](./la-review.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Update FinRem and Jurisdiction (`caseworker-update-fin-rem-and-jurisd-joint`) | [LA Review](./la-review.md) | `caseworker-divorce-superuser` | `applicationType="jointApplication"` |
| Update FinRem and Jurisdiction (`caseworker-update-fin-rem-and-jurisdiction`) | [LA Review](./la-review.md) | `caseworker-divorce-superuser` | `applicationType="soleApplication"` |
| Update general application (`caseworker-update-general-application`) | [LA Review](./la-review.md) | `caseworker-divorce-courtadmin_beta` | — |
| Update language preference (`caseworker-update-language-preference`) | [LA Review](./la-review.md) | `caseworker-divorce-courtadmin_beta` | — |
| Update offline status (`caseworker-update-offline-status`) | [LA Review](./la-review.md) | `caseworker-divorce-superuser` | — |
| Upload amended application (`caseworker-upload-amended-application`) | [LA Review](./la-review.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Upload confidential document (`caseworker-upload-confidential-document`) | [LA Review](./la-review.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-rparobot` | — |
| Upload document (`caseworker-upload-document`) | [LA Review](./la-review.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-rparobot` | — |
| General application payment (`citizen-general-app-payment`) | [LA Review](./la-review.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Citizen general application (`citizen-general-application`) | [LA Review](./la-review.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Generate Process Server Docs (`citizen-generate-process-server-docs`) | [LA Review](./la-review.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Citizen service application (`citizen-service-application`) | [LA Review](./la-review.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Citizen service payment made (`citizen-service-payment-made`) | [LA Review](./la-review.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Start Interim Application (`citizen-start-interim-application`) | [LA Review](./la-review.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Patch case (`citizen-update-application`) | [LA Review](./la-review.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Create flags (`createFlags`) | [LA Review](./la-review.md) | `caseworker-divorce-courtadmin-la`<br/>`caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-judge`<br/>`caseworker-divorce-superuser` | `caseFlagsSetupComplete="Yes"` |
| General application received (`cw-general-application-received`) | [LA Review](./la-review.md) | `caseworker-divorce-courtadmin_beta` | — |
| General application refund (`general-application-refund`) | [LA Review](./la-review.md) | `caseworker-divorce-superuser` | — |
| Make a decision (`legal-advisor-make-decision`) | [LA Review](./la-review.md) | `caseworker-divorce-courtadmin-la` | — |
| Manage flags (`manageFlags`) | [LA Review](./la-review.md) | `caseworker-divorce-courtadmin-la`<br/>`caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-judge`<br/>`caseworker-divorce-superuser` | `caseFlagsSetupComplete="Yes"` |
| Notice Of Change Applied (`notice-of-change-applied`) | [LA Review](./la-review.md) | `caseworker-approver` | — |
| Notice Of Change Requested (`notice-of-change-requested`) | [LA Review](./la-review.md) | `caseworker-caa` | — |
| Reject general application (`reject-general-application`) | [LA Review](./la-review.md) | `caseworker-divorce-courtadmin_beta` | — |
| Remission refund (`remission-refund`) | [LA Review](./la-review.md) | `caseworker-divorce-superuser` | — |
| Service application refund (`service-application-refund`) | [LA Review](./la-review.md) | `caseworker-divorce-superuser` | — |
| General Application (`solicitor-general-application`) | [LA Review](./la-review.md) | `[APPONESOLICITOR]`<br/>`[APPTWOSOLICITOR]` | — |
| Stop representing client (`solicitor-stop-representation`) | [LA Review](./la-review.md) | `[APPONESOLICITOR]`<br/>`[APPTWOSOLICITOR]` | — |
| Link Resp or App 2 to case (`system-link-applicant2`) | [LA Review](./la-review.md) | `caseworker-divorce-systemupdate` | — |
| Migrate case data (`system-migrate-case`) | [LA Review](./la-review.md) | `caseworker-divorce-systemupdate` | — |
| Migrate organisation policies (`system-migrate-organisation-policies`) | [LA Review](./la-review.md) | `caseworker-divorce-systemupdate` | — |
| System remove bulk case (`system-remove-bulk-case`) | [LA Review](./la-review.md) | `caseworker-divorce-superuser`<br/>`caseworker-divorce-systemupdate` | — |
| Update issue date (`system-update-issue-date`) | [LA Review](./la-review.md) | `caseworker-divorce-systemupdate` | — |

## Incoming events

| Event | Start state | Runnable by | Enabling condition |
|---|---|---|---|
| LA Review (`legal-advisor-review`) | [Awaiting admin clarification](./awaiting-admin-clarification.md) | `caseworker-divorce-courtadmin-la` | — |
| LA Review (`legal-advisor-review`) | [Awaiting clarification](./awaiting-clarification.md) | `caseworker-divorce-courtadmin-la` | — |
| LA Review (`legal-advisor-review`) | [Awaiting legal advisor referral](./awaiting-legal-advisor-referral.md) | `caseworker-divorce-courtadmin-la` | — |
| LA Review (`legal-advisor-review`) | [Awaiting service consideration](./awaiting-service-consideration.md) | `caseworker-divorce-courtadmin-la` | — |
| LA Review (`legal-advisor-review`) | [Clarification response submitted](./clarification-response-submitted.md) | `caseworker-divorce-courtadmin-la` | — |
| LA Review (`legal-advisor-review`) | [Conditional order review caseworker](./conditional-order-review-caseworker.md) | `caseworker-divorce-courtadmin-la` | — |
| LA Review (`legal-advisor-review`) | [Judicial Separation, Awaiting legal advisor](./judicial-separation-awaiting-legal-advisor.md) | `caseworker-divorce-courtadmin-la` | — |
| LA Review (`legal-advisor-review`) | [LA service app review](./la-service-app-review.md) | `caseworker-divorce-courtadmin-la` | — |
