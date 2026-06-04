# General application received

[Back to No Fault Divorce State Model](../index.md)

State ID: `GeneralApplicationReceived`

## Local state model

```mermaid
flowchart LR
    current["General application received"]

    subgraph outbound["Outbound from General application received"]
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
| Update contact info (`app1-solicitor-update-contact-details`) | [General application received](./general-application-received.md) | `[APPONESOLICITOR]` | — |
| View applicant contact info (`app1-solicitor-view-app1-contact-info`) | [General application received](./general-application-received.md) | `[APPONESOLICITOR]` | — |
| View respondent contact info (`app1-solicitor-view-app2-contact-info`) | [General application received](./general-application-received.md) | `[APPONESOLICITOR]` | — |
| Update contact info (`app2-solicitor-update-contact-details`) | [General application received](./general-application-received.md) | `[APPTWOSOLICITOR]` | — |
| View applicant contact info (`app2-solicitor-view-app1-contact-info`) | [General application received](./general-application-received.md) | `[APPTWOSOLICITOR]` | — |
| View respondent contact info (`app2-solicitor-view-app2-contact-info`) | [General application received](./general-application-received.md) | `[APPTWOSOLICITOR]` | — |
| Add note (`caseworker-add-note`) | [General application received](./general-application-received.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Add translation (`caseworker-add-translation`) | [General application received](./general-application-received.md) | `caseworker-divorce-courtadmin_beta` | — |
| Amend application type (`caseworker-amend-application-type`) | [General application received](./general-application-received.md) | `caseworker-divorce-superuser` | — |
| Update case (`caseworker-amend-case`) | [General application received](./general-application-received.md) | `caseworker-divorce-courtadmin_beta` | — |
| Confirm service (`caseworker-confirm-service`) | [General application received](./general-application-received.md) | `caseworker-divorce-courtadmin_beta` | `issueDate="*"` |
| Create general email (`caseworker-create-general-email`) | [General application received](./general-application-received.md) | `caseworker-divorce-courtadmin_beta` | — |
| Create general letter (`caseworker-create-general-letter`) | [General application received](./general-application-received.md) | `caseworker-divorce-courtadmin_beta` | — |
| Create general order (`caseworker-create-general-order`) | [General application received](./general-application-received.md) | `caseworker-divorce-courtadmin_beta` | — |
| Find matches (`caseworker-find-matches`) | [General application received](./general-application-received.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| General referral (`caseworker-general-referral`) | [General application received](./general-application-received.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Notice of change (`caseworker-notice-of-change`) | [General application received](./general-application-received.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Prepare for Case flags (`caseworker-prepare-caseflags`) | [General application received](./general-application-received.md) | `caseworker-divorce-courtadmin-la`<br/>`caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-judge`<br/>`caseworker-divorce-superuser` | `caseFlagsSetupComplete!="Yes"` |
| Prepare email attachments (`caseworker-prepare-general-email`) | [General application received](./general-application-received.md) | `caseworker-divorce-courtadmin_beta` | — |
| Regenerate court orders (`caseworker-regenerate-court-orders`) | [General application received](./general-application-received.md) | `caseworker-divorce-superuser` | — |
| Reject Service Application (`caseworker-reject-service-application`) | [General application received](./general-application-received.md) | `caseworker-divorce-superuser` | — |
| Remove documents (`caseworker-remove-document`) | [General application received](./general-application-received.md) | `caseworker-divorce-superuser` | — |
| Remove Failed Sol NoC Request (`caseworker-remove-failed-sol-noc-request`) | [General application received](./general-application-received.md) | `caseworker-divorce-superuser` | — |
| Remove general emails (`caseworker-remove-general-emails`) | [General application received](./general-application-received.md) | `caseworker-divorce-superuser` | — |
| Remove general letter (`caseworker-remove-general-letter`) | [General application received](./general-application-received.md) | `caseworker-divorce-superuser` | — |
| Remove General Order (`caseworker-remove-general-order`) | [General application received](./general-application-received.md) | `caseworker-divorce-superuser` | — |
| Remove note (`caseworker-remove-note`) | [General application received](./general-application-received.md) | `caseworker-divorce-superuser` | — |
| Remove scanned document (`caseworker-remove-scanned-document`) | [General application received](./general-application-received.md) | `caseworker-divorce-courtadmin_beta` | — |
| Request Translation from WLU (`caseworker-request-translation-wlu`) | [General application received](./general-application-received.md) | `caseworker-divorce-courtadmin_beta` | — |
| Return to previous state (`caseworker-return-to-previous-state`) | [General application received](./general-application-received.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Service application received (`caseworker-service-received`) | [General application received](./general-application-received.md) | `caseworker-divorce-courtadmin_beta` | — |
| Update App or App1 Email (`caseworker-update-app1-email`) | [General application received](./general-application-received.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Update Resp or App 2 Email (`caseworker-update-app2-email`) | [General application received](./general-application-received.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Update contact details (`caseworker-update-contact-details`) | [General application received](./general-application-received.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Update Date Submitted (`caseworker-update-date-submitted`) | [General application received](./general-application-received.md) | `caseworker-divorce-superuser` | — |
| Update due date (`caseworker-update-due-date`) | [General application received](./general-application-received.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Update FinRem and Jurisdiction (`caseworker-update-fin-rem-and-jurisd-joint`) | [General application received](./general-application-received.md) | `caseworker-divorce-superuser` | `applicationType="jointApplication"` |
| Update FinRem and Jurisdiction (`caseworker-update-fin-rem-and-jurisdiction`) | [General application received](./general-application-received.md) | `caseworker-divorce-superuser` | `applicationType="soleApplication"` |
| Update general application (`caseworker-update-general-application`) | [General application received](./general-application-received.md) | `caseworker-divorce-courtadmin_beta` | — |
| Update language preference (`caseworker-update-language-preference`) | [General application received](./general-application-received.md) | `caseworker-divorce-courtadmin_beta` | — |
| Update offline status (`caseworker-update-offline-status`) | [General application received](./general-application-received.md) | `caseworker-divorce-superuser` | — |
| Upload amended application (`caseworker-upload-amended-application`) | [General application received](./general-application-received.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Upload confidential document (`caseworker-upload-confidential-document`) | [General application received](./general-application-received.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-rparobot` | — |
| Upload document (`caseworker-upload-document`) | [General application received](./general-application-received.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-rparobot` | — |
| Patch a joint case (`citizen-applicant2-update-application`) | [General application received](./general-application-received.md) | `[APPLICANTTWO]` | `divorceOrDissolution="NEVER_SHOW"` |
| General application payment (`citizen-general-app-payment`) | [General application received](./general-application-received.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Citizen general application (`citizen-general-application`) | [General application received](./general-application-received.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Generate Process Server Docs (`citizen-generate-process-server-docs`) | [General application received](./general-application-received.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Citizen service application (`citizen-service-application`) | [General application received](./general-application-received.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Citizen service payment made (`citizen-service-payment-made`) | [General application received](./general-application-received.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Start Interim Application (`citizen-start-interim-application`) | [General application received](./general-application-received.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Patch case (`citizen-update-application`) | [General application received](./general-application-received.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Create flags (`createFlags`) | [General application received](./general-application-received.md) | `caseworker-divorce-courtadmin-la`<br/>`caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-judge`<br/>`caseworker-divorce-superuser` | `caseFlagsSetupComplete="Yes"` |
| General application received (`cw-general-application-received`) | [General application received](./general-application-received.md) | `caseworker-divorce-courtadmin_beta` | — |
| Draft AoS (`draft-aos`) | [General application received](./general-application-received.md) | `[APPLICANTTWO]`<br/>`[APPTWOSOLICITOR]` | `applicationType="soleApplication" AND aosIsDrafted!="Yes"` |
| General application refund (`general-application-refund`) | [General application received](./general-application-received.md) | `caseworker-divorce-superuser` | — |
| Manage flags (`manageFlags`) | [General application received](./general-application-received.md) | `caseworker-divorce-courtadmin-la`<br/>`caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-judge`<br/>`caseworker-divorce-superuser` | `caseFlagsSetupComplete="Yes"` |
| Notice Of Change Applied (`notice-of-change-applied`) | [General application received](./general-application-received.md) | `caseworker-approver` | — |
| Notice Of Change Requested (`notice-of-change-requested`) | [General application received](./general-application-received.md) | `caseworker-caa` | — |
| Reject general application (`reject-general-application`) | [General application received](./general-application-received.md) | `caseworker-divorce-courtadmin_beta` | — |
| Remission refund (`remission-refund`) | [General application received](./general-application-received.md) | `caseworker-divorce-superuser` | — |
| Service application refund (`service-application-refund`) | [General application received](./general-application-received.md) | `caseworker-divorce-superuser` | — |
| General Application (`solicitor-general-application`) | [General application received](./general-application-received.md) | `[APPONESOLICITOR]`<br/>`[APPTWOSOLICITOR]` | — |
| Stop representing client (`solicitor-stop-representation`) | [General application received](./general-application-received.md) | `[APPONESOLICITOR]`<br/>`[APPTWOSOLICITOR]` | — |
| Submit AoS (`submit-aos`) | [General application received](./general-application-received.md) | `[APPLICANTTWO]`<br/>`[APPTWOSOLICITOR]` | `applicationType="soleApplication" AND aosIsDrafted="Yes"` |
| AoS disputed (`system-issue-aos-disputed`) | [General application received](./general-application-received.md) | `caseworker-divorce-systemupdate` | — |
| AoS undisputed (`system-issue-aos-undisputed`) | [General application received](./general-application-received.md) | `caseworker-divorce-systemupdate` | — |
| Link Resp or App 2 to case (`system-link-applicant2`) | [General application received](./general-application-received.md) | `caseworker-divorce-systemupdate` | — |
| Migrate case data (`system-migrate-case`) | [General application received](./general-application-received.md) | `caseworker-divorce-systemupdate` | — |
| Migrate organisation policies (`system-migrate-organisation-policies`) | [General application received](./general-application-received.md) | `caseworker-divorce-systemupdate` | — |
| System remove bulk case (`system-remove-bulk-case`) | [General application received](./general-application-received.md) | `caseworker-divorce-superuser`<br/>`caseworker-divorce-systemupdate` | — |
| Unlink Applicant from case (`system-unlink-applicant`) | [General application received](./general-application-received.md) | `citizen` | — |
| Update issue date (`system-update-issue-date`) | [General application received](./general-application-received.md) | `caseworker-divorce-systemupdate` | — |

## Incoming events

_No events found._
