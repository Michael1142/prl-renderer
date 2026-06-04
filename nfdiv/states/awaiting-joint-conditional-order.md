# Awaiting joint conditional order

[Back to No Fault Divorce State Model](../index.md)

State ID: `ConditionalOrderPending`

## Local state model

```mermaid
flowchart LR
    current["Awaiting joint conditional order"]

    subgraph outbound["Outbound from Awaiting joint conditional order"]
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
| Switch To Sole CO (`app1-sol-switch-to-sole-co`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `[APPONESOLICITOR]` | `coApplicant1EnableSolicitorSwitchToSoleCo="Yes" AND coApplicant2IsSubmitted!="Yes"` |
| Update contact info (`app1-solicitor-update-contact-details`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `[APPONESOLICITOR]` | — |
| View applicant contact info (`app1-solicitor-view-app1-contact-info`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `[APPONESOLICITOR]` | — |
| View respondent contact info (`app1-solicitor-view-app2-contact-info`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `[APPONESOLICITOR]` | — |
| Switch To Sole CO (`app2-sol-switch-to-sole-co`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `[APPTWOSOLICITOR]` | `coApplicant2EnableSolicitorSwitchToSoleCo="Yes" AND coApplicant1IsSubmitted!="Yes"` |
| Update contact info (`app2-solicitor-update-contact-details`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `[APPTWOSOLICITOR]` | — |
| View applicant contact info (`app2-solicitor-view-app1-contact-info`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `[APPTWOSOLICITOR]` | — |
| View respondent contact info (`app2-solicitor-view-app2-contact-info`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `[APPTWOSOLICITOR]` | — |
| Add note (`caseworker-add-note`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Add translation (`caseworker-add-translation`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `caseworker-divorce-courtadmin_beta` | — |
| Amend application type (`caseworker-amend-application-type`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `caseworker-divorce-superuser` | — |
| Update case (`caseworker-amend-case`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `caseworker-divorce-courtadmin_beta` | — |
| Confirm service (`caseworker-confirm-service`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `caseworker-divorce-courtadmin_beta` | `issueDate="*"` |
| Create general email (`caseworker-create-general-email`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `caseworker-divorce-courtadmin_beta` | — |
| Create general letter (`caseworker-create-general-letter`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `caseworker-divorce-courtadmin_beta` | — |
| Create general order (`caseworker-create-general-order`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `caseworker-divorce-courtadmin_beta` | — |
| Find matches (`caseworker-find-matches`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| General referral (`caseworker-general-referral`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Notice of change (`caseworker-notice-of-change`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Prepare for Case flags (`caseworker-prepare-caseflags`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `caseworker-divorce-courtadmin-la`<br/>`caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-judge`<br/>`caseworker-divorce-superuser` | `caseFlagsSetupComplete!="Yes"` |
| Prepare email attachments (`caseworker-prepare-general-email`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `caseworker-divorce-courtadmin_beta` | — |
| Regenerate court orders (`caseworker-regenerate-court-orders`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `caseworker-divorce-superuser` | — |
| Reject Service Application (`caseworker-reject-service-application`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `caseworker-divorce-superuser` | — |
| Remove documents (`caseworker-remove-document`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `caseworker-divorce-superuser` | — |
| Remove Failed Sol NoC Request (`caseworker-remove-failed-sol-noc-request`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `caseworker-divorce-superuser` | — |
| Remove general emails (`caseworker-remove-general-emails`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `caseworker-divorce-superuser` | — |
| Remove general letter (`caseworker-remove-general-letter`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `caseworker-divorce-superuser` | — |
| Remove General Order (`caseworker-remove-general-order`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `caseworker-divorce-superuser` | — |
| Remove note (`caseworker-remove-note`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `caseworker-divorce-superuser` | — |
| Remove scanned document (`caseworker-remove-scanned-document`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `caseworker-divorce-courtadmin_beta` | — |
| Request Translation from WLU (`caseworker-request-translation-wlu`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `caseworker-divorce-courtadmin_beta` | — |
| Return to previous state (`caseworker-return-to-previous-state`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Update App or App1 Email (`caseworker-update-app1-email`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Update Resp or App 2 Email (`caseworker-update-app2-email`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Update contact details (`caseworker-update-contact-details`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Update Date Submitted (`caseworker-update-date-submitted`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `caseworker-divorce-superuser` | — |
| Update due date (`caseworker-update-due-date`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Update FinRem and Jurisdiction (`caseworker-update-fin-rem-and-jurisd-joint`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `caseworker-divorce-superuser` | `applicationType="jointApplication"` |
| Update FinRem and Jurisdiction (`caseworker-update-fin-rem-and-jurisdiction`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `caseworker-divorce-superuser` | `applicationType="soleApplication"` |
| Update general application (`caseworker-update-general-application`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `caseworker-divorce-courtadmin_beta` | — |
| Update language preference (`caseworker-update-language-preference`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `caseworker-divorce-courtadmin_beta` | — |
| Update offline status (`caseworker-update-offline-status`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `caseworker-divorce-superuser` | — |
| Upload amended application (`caseworker-upload-amended-application`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Upload confidential document (`caseworker-upload-confidential-document`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-rparobot` | — |
| Upload document (`caseworker-upload-document`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-rparobot` | — |
| Patch a joint case (`citizen-applicant2-update-application`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `[APPLICANTTWO]` | `divorceOrDissolution="NEVER_SHOW"` |
| General application payment (`citizen-general-app-payment`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Citizen general application (`citizen-general-application`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Generate Process Server Docs (`citizen-generate-process-server-docs`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Citizen service application (`citizen-service-application`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Citizen service payment made (`citizen-service-payment-made`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Start Interim Application (`citizen-start-interim-application`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Patch case (`citizen-update-application`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Create flags (`createFlags`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `caseworker-divorce-courtadmin-la`<br/>`caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-judge`<br/>`caseworker-divorce-superuser` | `caseFlagsSetupComplete="Yes"` |
| General application received (`cw-general-application-received`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `caseworker-divorce-courtadmin_beta` | — |
| Draft conditional order (`draft-conditional-order`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `[APPLICANTTWO]`<br/>`[APPONESOLICITOR]`<br/>`[CREATOR]` | `coApplicant1IsDrafted!="Yes"` |
| Draft conditional order (`draft-joint-conditional-order`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `[APPLICANTTWO]`<br/>`[APPTWOSOLICITOR]`<br/>`[CREATOR]` | `applicationType="jointApplication" AND coApplicant2IsDrafted!="Yes"` |
| General application refund (`general-application-refund`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `caseworker-divorce-superuser` | — |
| Manage flags (`manageFlags`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `caseworker-divorce-courtadmin-la`<br/>`caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-judge`<br/>`caseworker-divorce-superuser` | `caseFlagsSetupComplete="Yes"` |
| Notice Of Change Applied (`notice-of-change-applied`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `caseworker-approver` | — |
| Notice Of Change Requested (`notice-of-change-requested`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `caseworker-caa` | — |
| Reject general application (`reject-general-application`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `caseworker-divorce-courtadmin_beta` | — |
| Remission refund (`remission-refund`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `caseworker-divorce-superuser` | — |
| Service application refund (`service-application-refund`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `caseworker-divorce-superuser` | — |
| General Application (`solicitor-general-application`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `[APPONESOLICITOR]`<br/>`[APPTWOSOLICITOR]` | — |
| Stop representing client (`solicitor-stop-representation`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `[APPONESOLICITOR]`<br/>`[APPTWOSOLICITOR]` | — |
| Submit Conditional Order (`submit-conditional-order`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `[APPLICANTTWO]`<br/>`[APPONESOLICITOR]`<br/>`[CREATOR]` | `coApplicant1IsDrafted="Yes" AND coApplicant1IsSubmitted!="Yes"` |
| Submit Conditional Order (`submit-joint-conditional-order`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `[APPTWOSOLICITOR]` | `applicationType="jointApplication" AND coApplicant2IsDrafted="Yes" AND coApplicant2IsSubmitted!="Yes"` |
| SwitchedToSoleCO (`switch-to-sole-co`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `[APPLICANTTWO]`<br/>`[CREATOR]`<br/>`caseworker-divorce-systemupdate` | — |
| Link Resp or App 2 to case (`system-link-applicant2`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `caseworker-divorce-systemupdate` | — |
| Migrate case data (`system-migrate-case`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `caseworker-divorce-systemupdate` | — |
| Migrate organisation policies (`system-migrate-organisation-policies`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `caseworker-divorce-systemupdate` | — |
| Notify Switch To Sole (`system-notify-joint-applicant-switch-to-sole`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `caseworker-divorce-systemupdate` | — |
| Remind Applicants Apply for CO (`system-remind-applicants-conditional-order`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `caseworker-divorce-systemupdate` | — |
| System remove bulk case (`system-remove-bulk-case`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `caseworker-divorce-superuser`<br/>`caseworker-divorce-systemupdate` | — |
| Update issue date (`system-update-issue-date`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `caseworker-divorce-systemupdate` | — |
| Update conditional order (`update-conditional-order`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `[APPONESOLICITOR]`<br/>`[CREATOR]` | `coApplicant1IsDrafted="Yes" AND coApplicant1IsSubmitted!="Yes"` |
| Update conditional order (`update-joint-conditional-order`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `[APPTWOSOLICITOR]` | `applicationType="jointApplication" AND coApplicant2IsDrafted="Yes" AND coApplicant2IsSubmitted!="Yes"` |

## Incoming events

_No events found._
