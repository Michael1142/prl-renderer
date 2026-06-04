# 20 week holding period

[Back to No Fault Divorce State Model](../index.md)

State ID: `Holding`

## Local state model

```mermaid
flowchart LR
    current["20 week holding period"]

    subgraph outbound["Outbound from 20 week holding period"]
        out_awaitingalternativeservice["Awaiting alternative service"]
        out_awaitingamendedapplication["Awaiting amended application"]
        out_awaitingconditionalorder["Awaiting conditional order"]
        out_awaitingdocuments["Awaiting applicant"]
        out_offlinedocumentreceived["Offline document received by CW"]
        out_rejected["Application rejected"]
        out_withdrawn["Application withdrawn"]
    end

    current -->|"Serve by alternative method"| out_awaitingalternativeservice
    current -->|"Awaiting Amended Application"| out_awaitingamendedapplication
    current -->|"Awaiting Conditional Order"| out_awaitingconditionalorder
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
| Awaiting Conditional Order (`system-progress-held-case`) | [Awaiting conditional order](./awaiting-conditional-order.md) | `caseworker-divorce-systemupdate` | — |

## In-state events

| Event | End state | Runnable by | Enabling condition |
|---|---|---|---|
| Update contact info (`app1-solicitor-update-contact-details`) | [20 week holding period](./20-week-holding-period.md) | `[APPONESOLICITOR]` | — |
| View applicant contact info (`app1-solicitor-view-app1-contact-info`) | [20 week holding period](./20-week-holding-period.md) | `[APPONESOLICITOR]` | — |
| View respondent contact info (`app1-solicitor-view-app2-contact-info`) | [20 week holding period](./20-week-holding-period.md) | `[APPONESOLICITOR]` | — |
| Update contact info (`app2-solicitor-update-contact-details`) | [20 week holding period](./20-week-holding-period.md) | `[APPTWOSOLICITOR]` | — |
| View applicant contact info (`app2-solicitor-view-app1-contact-info`) | [20 week holding period](./20-week-holding-period.md) | `[APPTWOSOLICITOR]` | — |
| View respondent contact info (`app2-solicitor-view-app2-contact-info`) | [20 week holding period](./20-week-holding-period.md) | `[APPTWOSOLICITOR]` | — |
| Applicant 1 Confirm Receipt (`applicant1-confirm-receipt`) | [20 week holding period](./20-week-holding-period.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Applicant 2 Confirm Receipt (`applicant2-confirm-receipt`) | [20 week holding period](./20-week-holding-period.md) | `[APPLICANTTWO]` | `divorceOrDissolution="NEVER_SHOW"` |
| Answer received (`caseworker-add-answer`) | [20 week holding period](./20-week-holding-period.md) | `caseworker-divorce-courtadmin_beta` | — |
| Add bailiff return (`caseworker-add-bailiff-return`) | [20 week holding period](./20-week-holding-period.md) | `caseworker-divorce-courtadmin-la`<br/>`caseworker-divorce-courtadmin_beta` | — |
| Add note (`caseworker-add-note`) | [20 week holding period](./20-week-holding-period.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Add translation (`caseworker-add-translation`) | [20 week holding period](./20-week-holding-period.md) | `caseworker-divorce-courtadmin_beta` | — |
| Amend application type (`caseworker-amend-application-type`) | [20 week holding period](./20-week-holding-period.md) | `caseworker-divorce-superuser` | — |
| Update case (`caseworker-amend-case`) | [20 week holding period](./20-week-holding-period.md) | `caseworker-divorce-courtadmin_beta` | — |
| Confirm service (`caseworker-confirm-service`) | [20 week holding period](./20-week-holding-period.md) | `caseworker-divorce-courtadmin_beta` | `issueDate="*"` |
| Create general email (`caseworker-create-general-email`) | [20 week holding period](./20-week-holding-period.md) | `caseworker-divorce-courtadmin_beta` | — |
| Create general letter (`caseworker-create-general-letter`) | [20 week holding period](./20-week-holding-period.md) | `caseworker-divorce-courtadmin_beta` | — |
| Create general order (`caseworker-create-general-order`) | [20 week holding period](./20-week-holding-period.md) | `caseworker-divorce-courtadmin_beta` | — |
| Find matches (`caseworker-find-matches`) | [20 week holding period](./20-week-holding-period.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| General referral (`caseworker-general-referral`) | [20 week holding period](./20-week-holding-period.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Notice of change (`caseworker-notice-of-change`) | [20 week holding period](./20-week-holding-period.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Prepare for Case flags (`caseworker-prepare-caseflags`) | [20 week holding period](./20-week-holding-period.md) | `caseworker-divorce-courtadmin-la`<br/>`caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-judge`<br/>`caseworker-divorce-superuser` | `caseFlagsSetupComplete!="Yes"` |
| Prepare email attachments (`caseworker-prepare-general-email`) | [20 week holding period](./20-week-holding-period.md) | `caseworker-divorce-courtadmin_beta` | — |
| Regenerate court orders (`caseworker-regenerate-court-orders`) | [20 week holding period](./20-week-holding-period.md) | `caseworker-divorce-superuser` | — |
| Reissue (`caseworker-reissue-application`) | [20 week holding period](./20-week-holding-period.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Reject Service Application (`caseworker-reject-service-application`) | [20 week holding period](./20-week-holding-period.md) | `caseworker-divorce-superuser` | — |
| Remove documents (`caseworker-remove-document`) | [20 week holding period](./20-week-holding-period.md) | `caseworker-divorce-superuser` | — |
| Remove Failed Sol NoC Request (`caseworker-remove-failed-sol-noc-request`) | [20 week holding period](./20-week-holding-period.md) | `caseworker-divorce-superuser` | — |
| Remove general emails (`caseworker-remove-general-emails`) | [20 week holding period](./20-week-holding-period.md) | `caseworker-divorce-superuser` | — |
| Remove general letter (`caseworker-remove-general-letter`) | [20 week holding period](./20-week-holding-period.md) | `caseworker-divorce-superuser` | — |
| Remove General Order (`caseworker-remove-general-order`) | [20 week holding period](./20-week-holding-period.md) | `caseworker-divorce-superuser` | — |
| Remove note (`caseworker-remove-note`) | [20 week holding period](./20-week-holding-period.md) | `caseworker-divorce-superuser` | — |
| Remove scanned document (`caseworker-remove-scanned-document`) | [20 week holding period](./20-week-holding-period.md) | `caseworker-divorce-courtadmin_beta` | — |
| Request Translation from WLU (`caseworker-request-translation-wlu`) | [20 week holding period](./20-week-holding-period.md) | `caseworker-divorce-courtadmin_beta` | — |
| Return to previous state (`caseworker-return-to-previous-state`) | [20 week holding period](./20-week-holding-period.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Update App or App1 Email (`caseworker-update-app1-email`) | [20 week holding period](./20-week-holding-period.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Update Resp or App 2 Email (`caseworker-update-app2-email`) | [20 week holding period](./20-week-holding-period.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Update contact details (`caseworker-update-contact-details`) | [20 week holding period](./20-week-holding-period.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Update Date Submitted (`caseworker-update-date-submitted`) | [20 week holding period](./20-week-holding-period.md) | `caseworker-divorce-superuser` | — |
| Update due date (`caseworker-update-due-date`) | [20 week holding period](./20-week-holding-period.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Update FinRem and Jurisdiction (`caseworker-update-fin-rem-and-jurisd-joint`) | [20 week holding period](./20-week-holding-period.md) | `caseworker-divorce-superuser` | `applicationType="jointApplication"` |
| Update FinRem and Jurisdiction (`caseworker-update-fin-rem-and-jurisdiction`) | [20 week holding period](./20-week-holding-period.md) | `caseworker-divorce-superuser` | `applicationType="soleApplication"` |
| Update general application (`caseworker-update-general-application`) | [20 week holding period](./20-week-holding-period.md) | `caseworker-divorce-courtadmin_beta` | — |
| Update language preference (`caseworker-update-language-preference`) | [20 week holding period](./20-week-holding-period.md) | `caseworker-divorce-courtadmin_beta` | — |
| Update offline status (`caseworker-update-offline-status`) | [20 week holding period](./20-week-holding-period.md) | `caseworker-divorce-superuser` | — |
| Upload amended application (`caseworker-upload-amended-application`) | [20 week holding period](./20-week-holding-period.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Upload confidential document (`caseworker-upload-confidential-document`) | [20 week holding period](./20-week-holding-period.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-rparobot` | — |
| Upload document (`caseworker-upload-document`) | [20 week holding period](./20-week-holding-period.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-rparobot` | — |
| Patch a joint case (`citizen-applicant2-update-application`) | [20 week holding period](./20-week-holding-period.md) | `[APPLICANTTWO]` | `divorceOrDissolution="NEVER_SHOW"` |
| General application payment (`citizen-general-app-payment`) | [20 week holding period](./20-week-holding-period.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Citizen general application (`citizen-general-application`) | [20 week holding period](./20-week-holding-period.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Generate Process Server Docs (`citizen-generate-process-server-docs`) | [20 week holding period](./20-week-holding-period.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Citizen service application (`citizen-service-application`) | [20 week holding period](./20-week-holding-period.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Citizen service payment made (`citizen-service-payment-made`) | [20 week holding period](./20-week-holding-period.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Start Interim Application (`citizen-start-interim-application`) | [20 week holding period](./20-week-holding-period.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Patch case (`citizen-update-application`) | [20 week holding period](./20-week-holding-period.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Confirm Receipt (`confirm-receipt`) | [20 week holding period](./20-week-holding-period.md) | `[APPTWOSOLICITOR]`<br/>`caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-solicitor` | `applicationType="jointApplication"` |
| Create flags (`createFlags`) | [20 week holding period](./20-week-holding-period.md) | `caseworker-divorce-courtadmin-la`<br/>`caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-judge`<br/>`caseworker-divorce-superuser` | `caseFlagsSetupComplete="Yes"` |
| General application received (`cw-general-application-received`) | [20 week holding period](./20-week-holding-period.md) | `caseworker-divorce-courtadmin_beta` | — |
| Draft AoS (`draft-aos`) | [20 week holding period](./20-week-holding-period.md) | `[APPLICANTTWO]`<br/>`[APPTWOSOLICITOR]` | `applicationType="soleApplication" AND aosIsDrafted!="Yes"` |
| General application refund (`general-application-refund`) | [20 week holding period](./20-week-holding-period.md) | `caseworker-divorce-superuser` | — |
| Manage flags (`manageFlags`) | [20 week holding period](./20-week-holding-period.md) | `caseworker-divorce-courtadmin-la`<br/>`caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-judge`<br/>`caseworker-divorce-superuser` | `caseFlagsSetupComplete="Yes"` |
| Notice Of Change Applied (`notice-of-change-applied`) | [20 week holding period](./20-week-holding-period.md) | `caseworker-approver` | — |
| Notice Of Change Requested (`notice-of-change-requested`) | [20 week holding period](./20-week-holding-period.md) | `caseworker-caa` | — |
| Reject general application (`reject-general-application`) | [20 week holding period](./20-week-holding-period.md) | `caseworker-divorce-courtadmin_beta` | — |
| Remission refund (`remission-refund`) | [20 week holding period](./20-week-holding-period.md) | `caseworker-divorce-superuser` | — |
| Service application refund (`service-application-refund`) | [20 week holding period](./20-week-holding-period.md) | `caseworker-divorce-superuser` | — |
| Solicitor confirm service (`solicitor-confirm-service`) | [20 week holding period](./20-week-holding-period.md) | `caseworker-divorce-solicitor` | `issueDate="*"` |
| General Application (`solicitor-general-application`) | [20 week holding period](./20-week-holding-period.md) | `[APPONESOLICITOR]`<br/>`[APPTWOSOLICITOR]` | — |
| Stop representing client (`solicitor-stop-representation`) | [20 week holding period](./20-week-holding-period.md) | `[APPONESOLICITOR]`<br/>`[APPTWOSOLICITOR]` | — |
| Submit AoS (`submit-aos`) | [20 week holding period](./20-week-holding-period.md) | `[APPLICANTTWO]`<br/>`[APPTWOSOLICITOR]` | `applicationType="soleApplication" AND aosIsDrafted="Yes"` |
| AoS disputed (`system-issue-aos-disputed`) | [20 week holding period](./20-week-holding-period.md) | `caseworker-divorce-systemupdate` | — |
| AoS undisputed (`system-issue-aos-undisputed`) | [20 week holding period](./20-week-holding-period.md) | `caseworker-divorce-systemupdate` | — |
| Link Resp or App 2 to case (`system-link-applicant2`) | [20 week holding period](./20-week-holding-period.md) | `caseworker-divorce-systemupdate` | — |
| Migrate case data (`system-migrate-case`) | [20 week holding period](./20-week-holding-period.md) | `caseworker-divorce-systemupdate` | — |
| Migrate organisation policies (`system-migrate-organisation-policies`) | [20 week holding period](./20-week-holding-period.md) | `caseworker-divorce-systemupdate` | — |
| Dispute Form Overdue (`system-notify-applicant-dispute-form-overdue`) | [20 week holding period](./20-week-holding-period.md) | `caseworker-divorce-systemupdate` | — |
| System remove bulk case (`system-remove-bulk-case`) | [20 week holding period](./20-week-holding-period.md) | `caseworker-divorce-superuser`<br/>`caseworker-divorce-systemupdate` | — |
| Unlink Applicant from case (`system-unlink-applicant`) | [20 week holding period](./20-week-holding-period.md) | `citizen` | — |
| Update issue date (`system-update-issue-date`) | [20 week holding period](./20-week-holding-period.md) | `caseworker-divorce-systemupdate` | — |

## Incoming events

_No events found._
