# Welsh Translation requested

[Back to No Fault Divorce State Model](../index.md)

State ID: `WelshTranslationRequested`

## Local state model

```mermaid
flowchart LR
    current["Welsh Translation requested"]

    subgraph outbound["Outbound from Welsh Translation requested"]
        out_awaitingalternativeservice["Awaiting alternative service"]
        out_awaitingamendedapplication["Awaiting amended application"]
        out_awaitingdocuments["Awaiting applicant"]
        out_offlinedocumentreceived["Offline document received by CW"]
        out_rejected["Application rejected"]
        out_withdrawn["Application withdrawn"]
    end

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
| Update contact info (`app1-solicitor-update-contact-details`) | [Welsh Translation requested](./welsh-translation-requested.md) | `[APPONESOLICITOR]` | — |
| View applicant contact info (`app1-solicitor-view-app1-contact-info`) | [Welsh Translation requested](./welsh-translation-requested.md) | `[APPONESOLICITOR]` | — |
| View respondent contact info (`app1-solicitor-view-app2-contact-info`) | [Welsh Translation requested](./welsh-translation-requested.md) | `[APPONESOLICITOR]` | — |
| Update contact info (`app2-solicitor-update-contact-details`) | [Welsh Translation requested](./welsh-translation-requested.md) | `[APPTWOSOLICITOR]` | — |
| View applicant contact info (`app2-solicitor-view-app1-contact-info`) | [Welsh Translation requested](./welsh-translation-requested.md) | `[APPTWOSOLICITOR]` | — |
| View respondent contact info (`app2-solicitor-view-app2-contact-info`) | [Welsh Translation requested](./welsh-translation-requested.md) | `[APPTWOSOLICITOR]` | — |
| Add note (`caseworker-add-note`) | [Welsh Translation requested](./welsh-translation-requested.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Add translation (`caseworker-add-translation`) | [Welsh Translation requested](./welsh-translation-requested.md) | `caseworker-divorce-courtadmin_beta` | — |
| Amend application type (`caseworker-amend-application-type`) | [Welsh Translation requested](./welsh-translation-requested.md) | `caseworker-divorce-superuser` | — |
| Update case (`caseworker-amend-case`) | [Welsh Translation requested](./welsh-translation-requested.md) | `caseworker-divorce-courtadmin_beta` | — |
| Confirm service (`caseworker-confirm-service`) | [Welsh Translation requested](./welsh-translation-requested.md) | `caseworker-divorce-courtadmin_beta` | `issueDate="*"` |
| Create general email (`caseworker-create-general-email`) | [Welsh Translation requested](./welsh-translation-requested.md) | `caseworker-divorce-courtadmin_beta` | — |
| Create general letter (`caseworker-create-general-letter`) | [Welsh Translation requested](./welsh-translation-requested.md) | `caseworker-divorce-courtadmin_beta` | — |
| Create general order (`caseworker-create-general-order`) | [Welsh Translation requested](./welsh-translation-requested.md) | `caseworker-divorce-courtadmin_beta` | — |
| Find matches (`caseworker-find-matches`) | [Welsh Translation requested](./welsh-translation-requested.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| General referral (`caseworker-general-referral`) | [Welsh Translation requested](./welsh-translation-requested.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Notice of change (`caseworker-notice-of-change`) | [Welsh Translation requested](./welsh-translation-requested.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Prepare for Case flags (`caseworker-prepare-caseflags`) | [Welsh Translation requested](./welsh-translation-requested.md) | `caseworker-divorce-courtadmin-la`<br/>`caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-judge`<br/>`caseworker-divorce-superuser` | `caseFlagsSetupComplete!="Yes"` |
| Prepare email attachments (`caseworker-prepare-general-email`) | [Welsh Translation requested](./welsh-translation-requested.md) | `caseworker-divorce-courtadmin_beta` | — |
| Regenerate court orders (`caseworker-regenerate-court-orders`) | [Welsh Translation requested](./welsh-translation-requested.md) | `caseworker-divorce-superuser` | — |
| Reject Service Application (`caseworker-reject-service-application`) | [Welsh Translation requested](./welsh-translation-requested.md) | `caseworker-divorce-superuser` | — |
| Remove documents (`caseworker-remove-document`) | [Welsh Translation requested](./welsh-translation-requested.md) | `caseworker-divorce-superuser` | — |
| Remove Failed Sol NoC Request (`caseworker-remove-failed-sol-noc-request`) | [Welsh Translation requested](./welsh-translation-requested.md) | `caseworker-divorce-superuser` | — |
| Remove general emails (`caseworker-remove-general-emails`) | [Welsh Translation requested](./welsh-translation-requested.md) | `caseworker-divorce-superuser` | — |
| Remove general letter (`caseworker-remove-general-letter`) | [Welsh Translation requested](./welsh-translation-requested.md) | `caseworker-divorce-superuser` | — |
| Remove General Order (`caseworker-remove-general-order`) | [Welsh Translation requested](./welsh-translation-requested.md) | `caseworker-divorce-superuser` | — |
| Remove note (`caseworker-remove-note`) | [Welsh Translation requested](./welsh-translation-requested.md) | `caseworker-divorce-superuser` | — |
| Remove scanned document (`caseworker-remove-scanned-document`) | [Welsh Translation requested](./welsh-translation-requested.md) | `caseworker-divorce-courtadmin_beta` | — |
| Request Translation from WLU (`caseworker-request-translation-wlu`) | [Welsh Translation requested](./welsh-translation-requested.md) | `caseworker-divorce-courtadmin_beta` | — |
| Welsh Translation Resolved (`caseworker-resolve-welsh-translation`) | [Welsh Translation requested](./welsh-translation-requested.md) | `caseworker-divorce-courtadmin_beta` | — |
| Return to previous state (`caseworker-return-to-previous-state`) | [Welsh Translation requested](./welsh-translation-requested.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Update App or App1 Email (`caseworker-update-app1-email`) | [Welsh Translation requested](./welsh-translation-requested.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Update Resp or App 2 Email (`caseworker-update-app2-email`) | [Welsh Translation requested](./welsh-translation-requested.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Update contact details (`caseworker-update-contact-details`) | [Welsh Translation requested](./welsh-translation-requested.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Update Date Submitted (`caseworker-update-date-submitted`) | [Welsh Translation requested](./welsh-translation-requested.md) | `caseworker-divorce-superuser` | — |
| Update due date (`caseworker-update-due-date`) | [Welsh Translation requested](./welsh-translation-requested.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Update FinRem and Jurisdiction (`caseworker-update-fin-rem-and-jurisd-joint`) | [Welsh Translation requested](./welsh-translation-requested.md) | `caseworker-divorce-superuser` | `applicationType="jointApplication"` |
| Update FinRem and Jurisdiction (`caseworker-update-fin-rem-and-jurisdiction`) | [Welsh Translation requested](./welsh-translation-requested.md) | `caseworker-divorce-superuser` | `applicationType="soleApplication"` |
| Update general application (`caseworker-update-general-application`) | [Welsh Translation requested](./welsh-translation-requested.md) | `caseworker-divorce-courtadmin_beta` | — |
| Update language preference (`caseworker-update-language-preference`) | [Welsh Translation requested](./welsh-translation-requested.md) | `caseworker-divorce-courtadmin_beta` | — |
| Update offline status (`caseworker-update-offline-status`) | [Welsh Translation requested](./welsh-translation-requested.md) | `caseworker-divorce-superuser` | — |
| Upload amended application (`caseworker-upload-amended-application`) | [Welsh Translation requested](./welsh-translation-requested.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Upload confidential document (`caseworker-upload-confidential-document`) | [Welsh Translation requested](./welsh-translation-requested.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-rparobot` | — |
| Upload document (`caseworker-upload-document`) | [Welsh Translation requested](./welsh-translation-requested.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-rparobot` | — |
| General application payment (`citizen-general-app-payment`) | [Welsh Translation requested](./welsh-translation-requested.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Citizen general application (`citizen-general-application`) | [Welsh Translation requested](./welsh-translation-requested.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Generate Process Server Docs (`citizen-generate-process-server-docs`) | [Welsh Translation requested](./welsh-translation-requested.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Citizen service application (`citizen-service-application`) | [Welsh Translation requested](./welsh-translation-requested.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Citizen service payment made (`citizen-service-payment-made`) | [Welsh Translation requested](./welsh-translation-requested.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Start Interim Application (`citizen-start-interim-application`) | [Welsh Translation requested](./welsh-translation-requested.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Patch case (`citizen-update-application`) | [Welsh Translation requested](./welsh-translation-requested.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Create flags (`createFlags`) | [Welsh Translation requested](./welsh-translation-requested.md) | `caseworker-divorce-courtadmin-la`<br/>`caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-judge`<br/>`caseworker-divorce-superuser` | `caseFlagsSetupComplete="Yes"` |
| General application received (`cw-general-application-received`) | [Welsh Translation requested](./welsh-translation-requested.md) | `caseworker-divorce-courtadmin_beta` | — |
| General application refund (`general-application-refund`) | [Welsh Translation requested](./welsh-translation-requested.md) | `caseworker-divorce-superuser` | — |
| Manage flags (`manageFlags`) | [Welsh Translation requested](./welsh-translation-requested.md) | `caseworker-divorce-courtadmin-la`<br/>`caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-judge`<br/>`caseworker-divorce-superuser` | `caseFlagsSetupComplete="Yes"` |
| Notice Of Change Applied (`notice-of-change-applied`) | [Welsh Translation requested](./welsh-translation-requested.md) | `caseworker-approver` | — |
| Notice Of Change Requested (`notice-of-change-requested`) | [Welsh Translation requested](./welsh-translation-requested.md) | `caseworker-caa` | — |
| Reject general application (`reject-general-application`) | [Welsh Translation requested](./welsh-translation-requested.md) | `caseworker-divorce-courtadmin_beta` | — |
| Remission refund (`remission-refund`) | [Welsh Translation requested](./welsh-translation-requested.md) | `caseworker-divorce-superuser` | — |
| Service application refund (`service-application-refund`) | [Welsh Translation requested](./welsh-translation-requested.md) | `caseworker-divorce-superuser` | — |
| General Application (`solicitor-general-application`) | [Welsh Translation requested](./welsh-translation-requested.md) | `[APPONESOLICITOR]`<br/>`[APPTWOSOLICITOR]` | — |
| Stop representing client (`solicitor-stop-representation`) | [Welsh Translation requested](./welsh-translation-requested.md) | `[APPONESOLICITOR]`<br/>`[APPTWOSOLICITOR]` | — |
| Link Resp or App 2 to case (`system-link-applicant2`) | [Welsh Translation requested](./welsh-translation-requested.md) | `caseworker-divorce-systemupdate` | — |
| Migrate case data (`system-migrate-case`) | [Welsh Translation requested](./welsh-translation-requested.md) | `caseworker-divorce-systemupdate` | — |
| Migrate organisation policies (`system-migrate-organisation-policies`) | [Welsh Translation requested](./welsh-translation-requested.md) | `caseworker-divorce-systemupdate` | — |
| System remove bulk case (`system-remove-bulk-case`) | [Welsh Translation requested](./welsh-translation-requested.md) | `caseworker-divorce-superuser`<br/>`caseworker-divorce-systemupdate` | — |
| Update issue date (`system-update-issue-date`) | [Welsh Translation requested](./welsh-translation-requested.md) | `caseworker-divorce-systemupdate` | — |

## Incoming events

_No events found._
