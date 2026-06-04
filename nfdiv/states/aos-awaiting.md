# AoS awaiting

[Back to No Fault Divorce State Model](../index.md)

State ID: `AwaitingAos`

## Local state model

```mermaid
flowchart LR
    current["AoS awaiting"]

    subgraph inbound["Inbound to AoS awaiting"]
        in_generalconsiderationcomplete["General consideration complete"]
    end

    subgraph outbound["Outbound from AoS awaiting"]
        out_aosoverdue["AoS overdue"]
        out_awaitingalternativeservice["Awaiting alternative service"]
        out_awaitingamendedapplication["Awaiting amended application"]
        out_awaitingdocuments["Awaiting applicant"]
        out_offlinedocumentreceived["Offline document received by CW"]
        out_rejected["Application rejected"]
        out_withdrawn["Application withdrawn"]
    end

    in_generalconsiderationcomplete -->|"Issue amended application"| current
    current -->|"AoS not received within SLA"| out_aosoverdue
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
| AoS not received within SLA (`system-progress-to-aos-overdue`) | [AoS overdue](./aos-overdue.md) | `caseworker-divorce-systemupdate` | — |

## In-state events

| Event | End state | Runnable by | Enabling condition |
|---|---|---|---|
| Update contact info (`app1-solicitor-update-contact-details`) | [AoS awaiting](./aos-awaiting.md) | `[APPONESOLICITOR]` | — |
| View applicant contact info (`app1-solicitor-view-app1-contact-info`) | [AoS awaiting](./aos-awaiting.md) | `[APPONESOLICITOR]` | — |
| View respondent contact info (`app1-solicitor-view-app2-contact-info`) | [AoS awaiting](./aos-awaiting.md) | `[APPONESOLICITOR]` | — |
| Update contact info (`app2-solicitor-update-contact-details`) | [AoS awaiting](./aos-awaiting.md) | `[APPTWOSOLICITOR]` | — |
| View applicant contact info (`app2-solicitor-view-app1-contact-info`) | [AoS awaiting](./aos-awaiting.md) | `[APPTWOSOLICITOR]` | — |
| View respondent contact info (`app2-solicitor-view-app2-contact-info`) | [AoS awaiting](./aos-awaiting.md) | `[APPTWOSOLICITOR]` | — |
| Answer received (`caseworker-add-answer`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-divorce-courtadmin_beta` | — |
| Add bailiff return (`caseworker-add-bailiff-return`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-divorce-courtadmin-la`<br/>`caseworker-divorce-courtadmin_beta` | — |
| Add note (`caseworker-add-note`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Add translation (`caseworker-add-translation`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-divorce-courtadmin_beta` | — |
| Amend application type (`caseworker-amend-application-type`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-divorce-superuser` | — |
| Update case (`caseworker-amend-case`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-divorce-courtadmin_beta` | — |
| Confirm service (`caseworker-confirm-service`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-divorce-courtadmin_beta` | `issueDate="*"` |
| Create general email (`caseworker-create-general-email`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-divorce-courtadmin_beta` | — |
| Create general letter (`caseworker-create-general-letter`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-divorce-courtadmin_beta` | — |
| Create general order (`caseworker-create-general-order`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-divorce-courtadmin_beta` | — |
| Find matches (`caseworker-find-matches`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| General referral (`caseworker-general-referral`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Notice of change (`caseworker-notice-of-change`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Prepare for Case flags (`caseworker-prepare-caseflags`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-divorce-courtadmin-la`<br/>`caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-judge`<br/>`caseworker-divorce-superuser` | `caseFlagsSetupComplete!="Yes"` |
| Prepare email attachments (`caseworker-prepare-general-email`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-divorce-courtadmin_beta` | — |
| Regenerate court orders (`caseworker-regenerate-court-orders`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-divorce-superuser` | — |
| Reissue (`caseworker-reissue-application`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Reject Service Application (`caseworker-reject-service-application`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-divorce-superuser` | — |
| Remove documents (`caseworker-remove-document`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-divorce-superuser` | — |
| Remove Failed Sol NoC Request (`caseworker-remove-failed-sol-noc-request`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-divorce-superuser` | — |
| Remove general emails (`caseworker-remove-general-emails`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-divorce-superuser` | — |
| Remove general letter (`caseworker-remove-general-letter`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-divorce-superuser` | — |
| Remove General Order (`caseworker-remove-general-order`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-divorce-superuser` | — |
| Remove note (`caseworker-remove-note`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-divorce-superuser` | — |
| Remove scanned document (`caseworker-remove-scanned-document`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-divorce-courtadmin_beta` | — |
| Request Translation from WLU (`caseworker-request-translation-wlu`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-divorce-courtadmin_beta` | — |
| Response to service app (`caseworker-response-to-service-application`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Return to previous state (`caseworker-return-to-previous-state`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Service application received (`caseworker-service-received`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-divorce-courtadmin_beta` | — |
| Update App or App1 Email (`caseworker-update-app1-email`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Update Resp or App 2 Email (`caseworker-update-app2-email`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Update contact details (`caseworker-update-contact-details`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Update Date Submitted (`caseworker-update-date-submitted`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-divorce-superuser` | — |
| Update due date (`caseworker-update-due-date`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Update FinRem and Jurisdiction (`caseworker-update-fin-rem-and-jurisd-joint`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-divorce-superuser` | `applicationType="jointApplication"` |
| Update FinRem and Jurisdiction (`caseworker-update-fin-rem-and-jurisdiction`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-divorce-superuser` | `applicationType="soleApplication"` |
| Update general application (`caseworker-update-general-application`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-divorce-courtadmin_beta` | — |
| Update language preference (`caseworker-update-language-preference`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-divorce-courtadmin_beta` | — |
| Update offline status (`caseworker-update-offline-status`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-divorce-superuser` | — |
| Upload amended application (`caseworker-upload-amended-application`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Upload confidential document (`caseworker-upload-confidential-document`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-rparobot` | — |
| Upload document (`caseworker-upload-document`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-rparobot` | — |
| General application payment (`citizen-general-app-payment`) | [AoS awaiting](./aos-awaiting.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Citizen general application (`citizen-general-application`) | [AoS awaiting](./aos-awaiting.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Generate Process Server Docs (`citizen-generate-process-server-docs`) | [AoS awaiting](./aos-awaiting.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Citizen service application (`citizen-service-application`) | [AoS awaiting](./aos-awaiting.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Citizen service payment made (`citizen-service-payment-made`) | [AoS awaiting](./aos-awaiting.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Start Interim Application (`citizen-start-interim-application`) | [AoS awaiting](./aos-awaiting.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Patch case (`citizen-update-application`) | [AoS awaiting](./aos-awaiting.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Create flags (`createFlags`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-divorce-courtadmin-la`<br/>`caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-judge`<br/>`caseworker-divorce-superuser` | `caseFlagsSetupComplete="Yes"` |
| General application received (`cw-general-application-received`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-divorce-courtadmin_beta` | — |
| Draft AoS (`draft-aos`) | [AoS awaiting](./aos-awaiting.md) | `[APPLICANTTWO]`<br/>`[APPTWOSOLICITOR]` | `applicationType="soleApplication" AND aosIsDrafted!="Yes"` |
| General application refund (`general-application-refund`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-divorce-superuser` | — |
| Manage flags (`manageFlags`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-divorce-courtadmin-la`<br/>`caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-judge`<br/>`caseworker-divorce-superuser` | `caseFlagsSetupComplete="Yes"` |
| Notice Of Change Applied (`notice-of-change-applied`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-approver` | — |
| Notice Of Change Requested (`notice-of-change-requested`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-caa` | — |
| Reject general application (`reject-general-application`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-divorce-courtadmin_beta` | — |
| Remission refund (`remission-refund`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-divorce-superuser` | — |
| Service application refund (`service-application-refund`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-divorce-superuser` | — |
| Change service request (`solicitor-change-service-request`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-divorce-solicitor` | `issueDate="*" AND applicationType="soleApplication"` |
| Solicitor confirm service (`solicitor-confirm-service`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-divorce-solicitor` | `issueDate="*"` |
| General Application (`solicitor-general-application`) | [AoS awaiting](./aos-awaiting.md) | `[APPONESOLICITOR]`<br/>`[APPTWOSOLICITOR]` | — |
| Stop representing client (`solicitor-stop-representation`) | [AoS awaiting](./aos-awaiting.md) | `[APPONESOLICITOR]`<br/>`[APPTWOSOLICITOR]` | — |
| AoS disputed (`system-issue-aos-disputed`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-divorce-systemupdate` | — |
| AoS undisputed (`system-issue-aos-undisputed`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-divorce-systemupdate` | — |
| Link Resp or App 2 to case (`system-link-applicant2`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-divorce-systemupdate` | — |
| Migrate case data (`system-migrate-case`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-divorce-systemupdate` | — |
| Migrate organisation policies (`system-migrate-organisation-policies`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-divorce-systemupdate` | — |
| Remind Respondent Solicitor (`system-remind-respondent-solicitor-to-respond`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-divorce-systemupdate` | `divorceOrDissolution="NEVER_SHOW"` |
| System remove bulk case (`system-remove-bulk-case`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-divorce-superuser`<br/>`caseworker-divorce-systemupdate` | — |
| Update issue date (`system-update-issue-date`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-divorce-systemupdate` | — |
| Update details or reissue (`update-partner-details-or-reissue`) | [AoS awaiting](./aos-awaiting.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |

## Incoming events

| Event | Start state | Runnable by | Enabling condition |
|---|---|---|---|
| Issue amended application (`caseworker-issue-amended-application`) | [General consideration complete](./general-consideration-complete.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
