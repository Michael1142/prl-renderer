# General consideration complete

[Back to No Fault Divorce State Model](../index.md)

State ID: `GeneralConsiderationComplete`

## Local state model

```mermaid
flowchart LR
    current["General consideration complete"]

    subgraph inbound["Inbound to General consideration complete"]
        in_awaitinggeneralconsideration["Awaiting general consideration"]
    end

    subgraph outbound["Outbound from General consideration complete"]
        out_awaitingalternativeservice["Awaiting alternative service"]
        out_awaitingamendedapplication["Awaiting amended application"]
        out_awaitingaos["AoS awaiting"]
        out_awaitingdocuments["Awaiting applicant"]
        out_awaitingdwpresponse["Awaiting DWP response"]
        out_awaitingjudgeclarification["Awaiting judge clarification"]
        out_offlinedocumentreceived["Offline document received by CW"]
        out_pendinghearingdate["Pending hearing date"]
        out_pendinghearingoutcome["Pending hearing outcome"]
        out_pendingserviceappresponse["Pending service app response"]
        out_rejected["Application rejected"]
        out_withdrawn["Application withdrawn"]
    end

    in_awaitinggeneralconsideration -->|"General Consideration"| current
    current -->|"Serve by alternative method"| out_awaitingalternativeservice
    current -->|"Awaiting Amended Application"| out_awaitingamendedapplication
    current -->|"Issue amended application"| out_awaitingaos
    current -->|"Awaiting Applicant"| out_awaitingdocuments
    current -->|"Request DWP disclosure"| out_awaitingdwpresponse
    current -->|"Awaiting judge clarification"| out_awaitingjudgeclarification
    current -->|"Attach scanned docs"| out_offlinedocumentreceived
    current -->|"Pending hearing date"| out_pendinghearingdate
    current -->|"Pending hearing outcome"| out_pendinghearingoutcome
    current -->|"Pending service app response"| out_pendingserviceappresponse
    current -->|"Reject"| out_rejected
    current -->|"Withdraw"| out_withdrawn
```

## Outgoing events

| Event | End state | Runnable by | Enabling condition |
|---|---|---|---|
| Attach scanned docs (`attachScannedDocs`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Awaiting Amended Application (`caseworker-awaiting-amended-application`) | [Awaiting amended application](./awaiting-amended-application.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting judge clarification (`caseworker-awaiting-judge-clarification`) | [Awaiting judge clarification](./awaiting-judge-clarification.md) | `caseworker-divorce-courtadmin_beta` | — |
| Issue amended application (`caseworker-issue-amended-application`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Pending hearing date (`caseworker-pending-hearing-date`) | [Pending hearing date](./pending-hearing-date.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Pending hearing outcome (`caseworker-pending-hearing-outcome`) | [Pending hearing outcome](./pending-hearing-outcome.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Reject (`caseworker-rejected`) | [Application rejected](./application-rejected.md) | `caseworker-divorce-courtadmin_beta` | — |
| Request DWP disclosure (`caseworker-request-dwp-disclosure`) | [Awaiting DWP response](./awaiting-dwp-response.md) | `caseworker-divorce-courtadmin_beta` | — |
| Serve by alternative method (`caseworker-serve-by-alternative-method`) | [Awaiting alternative service](./awaiting-alternative-service.md) | `caseworker-divorce-courtadmin_beta` | — |
| Withdraw (`caseworker-withdrawn`) | [Application withdrawn](./application-withdrawn.md) | `caseworker-divorce-courtadmin_beta` | — |
| Pending service app response (`pending-service-app-response`) | [Pending service app response](./pending-service-app-response.md) | `caseworker-divorce-courtadmin_beta` | — |

## In-state events

| Event | End state | Runnable by | Enabling condition |
|---|---|---|---|
| Update contact info (`app1-solicitor-update-contact-details`) | [General consideration complete](./general-consideration-complete.md) | `[APPONESOLICITOR]` | — |
| View applicant contact info (`app1-solicitor-view-app1-contact-info`) | [General consideration complete](./general-consideration-complete.md) | `[APPONESOLICITOR]` | — |
| View respondent contact info (`app1-solicitor-view-app2-contact-info`) | [General consideration complete](./general-consideration-complete.md) | `[APPONESOLICITOR]` | — |
| Update contact info (`app2-solicitor-update-contact-details`) | [General consideration complete](./general-consideration-complete.md) | `[APPTWOSOLICITOR]` | — |
| View applicant contact info (`app2-solicitor-view-app1-contact-info`) | [General consideration complete](./general-consideration-complete.md) | `[APPTWOSOLICITOR]` | — |
| View respondent contact info (`app2-solicitor-view-app2-contact-info`) | [General consideration complete](./general-consideration-complete.md) | `[APPTWOSOLICITOR]` | — |
| Add note (`caseworker-add-note`) | [General consideration complete](./general-consideration-complete.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Add translation (`caseworker-add-translation`) | [General consideration complete](./general-consideration-complete.md) | `caseworker-divorce-courtadmin_beta` | — |
| Amend application type (`caseworker-amend-application-type`) | [General consideration complete](./general-consideration-complete.md) | `caseworker-divorce-superuser` | — |
| Update case (`caseworker-amend-case`) | [General consideration complete](./general-consideration-complete.md) | `caseworker-divorce-courtadmin_beta` | — |
| Confirm service (`caseworker-confirm-service`) | [General consideration complete](./general-consideration-complete.md) | `caseworker-divorce-courtadmin_beta` | `issueDate="*"` |
| Create general email (`caseworker-create-general-email`) | [General consideration complete](./general-consideration-complete.md) | `caseworker-divorce-courtadmin_beta` | — |
| Create general letter (`caseworker-create-general-letter`) | [General consideration complete](./general-consideration-complete.md) | `caseworker-divorce-courtadmin_beta` | — |
| Create general order (`caseworker-create-general-order`) | [General consideration complete](./general-consideration-complete.md) | `caseworker-divorce-courtadmin_beta` | — |
| Expedite Final order (`caseworker-expedite-final-order`) | [General consideration complete](./general-consideration-complete.md) | `caseworker-divorce-courtadmin_beta` | — |
| Find matches (`caseworker-find-matches`) | [General consideration complete](./general-consideration-complete.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| General referral (`caseworker-general-referral`) | [General consideration complete](./general-consideration-complete.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Grant Final order (`caseworker-grant-final-order`) | [General consideration complete](./general-consideration-complete.md) | `caseworker-divorce-courtadmin_beta` | — |
| Notice of change (`caseworker-notice-of-change`) | [General consideration complete](./general-consideration-complete.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Prepare for Case flags (`caseworker-prepare-caseflags`) | [General consideration complete](./general-consideration-complete.md) | `caseworker-divorce-courtadmin-la`<br/>`caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-judge`<br/>`caseworker-divorce-superuser` | `caseFlagsSetupComplete!="Yes"` |
| Prepare email attachments (`caseworker-prepare-general-email`) | [General consideration complete](./general-consideration-complete.md) | `caseworker-divorce-courtadmin_beta` | — |
| Regenerate court orders (`caseworker-regenerate-court-orders`) | [General consideration complete](./general-consideration-complete.md) | `caseworker-divorce-superuser` | — |
| Reject Service Application (`caseworker-reject-service-application`) | [General consideration complete](./general-consideration-complete.md) | `caseworker-divorce-superuser` | — |
| Remove documents (`caseworker-remove-document`) | [General consideration complete](./general-consideration-complete.md) | `caseworker-divorce-superuser` | — |
| Remove Failed Sol NoC Request (`caseworker-remove-failed-sol-noc-request`) | [General consideration complete](./general-consideration-complete.md) | `caseworker-divorce-superuser` | — |
| Remove general emails (`caseworker-remove-general-emails`) | [General consideration complete](./general-consideration-complete.md) | `caseworker-divorce-superuser` | — |
| Remove general letter (`caseworker-remove-general-letter`) | [General consideration complete](./general-consideration-complete.md) | `caseworker-divorce-superuser` | — |
| Remove General Order (`caseworker-remove-general-order`) | [General consideration complete](./general-consideration-complete.md) | `caseworker-divorce-superuser` | — |
| Remove note (`caseworker-remove-note`) | [General consideration complete](./general-consideration-complete.md) | `caseworker-divorce-superuser` | — |
| Remove scanned document (`caseworker-remove-scanned-document`) | [General consideration complete](./general-consideration-complete.md) | `caseworker-divorce-courtadmin_beta` | — |
| Request Translation from WLU (`caseworker-request-translation-wlu`) | [General consideration complete](./general-consideration-complete.md) | `caseworker-divorce-courtadmin_beta` | — |
| Return to previous state (`caseworker-return-to-previous-state`) | [General consideration complete](./general-consideration-complete.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Update App or App1 Email (`caseworker-update-app1-email`) | [General consideration complete](./general-consideration-complete.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Update Resp or App 2 Email (`caseworker-update-app2-email`) | [General consideration complete](./general-consideration-complete.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Update contact details (`caseworker-update-contact-details`) | [General consideration complete](./general-consideration-complete.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Update Date Submitted (`caseworker-update-date-submitted`) | [General consideration complete](./general-consideration-complete.md) | `caseworker-divorce-superuser` | — |
| Update due date (`caseworker-update-due-date`) | [General consideration complete](./general-consideration-complete.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Update FinRem and Jurisdiction (`caseworker-update-fin-rem-and-jurisd-joint`) | [General consideration complete](./general-consideration-complete.md) | `caseworker-divorce-superuser` | `applicationType="jointApplication"` |
| Update FinRem and Jurisdiction (`caseworker-update-fin-rem-and-jurisdiction`) | [General consideration complete](./general-consideration-complete.md) | `caseworker-divorce-superuser` | `applicationType="soleApplication"` |
| Update general application (`caseworker-update-general-application`) | [General consideration complete](./general-consideration-complete.md) | `caseworker-divorce-courtadmin_beta` | — |
| Update language preference (`caseworker-update-language-preference`) | [General consideration complete](./general-consideration-complete.md) | `caseworker-divorce-courtadmin_beta` | — |
| Update offline status (`caseworker-update-offline-status`) | [General consideration complete](./general-consideration-complete.md) | `caseworker-divorce-superuser` | — |
| Upload amended application (`caseworker-upload-amended-application`) | [General consideration complete](./general-consideration-complete.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Upload confidential document (`caseworker-upload-confidential-document`) | [General consideration complete](./general-consideration-complete.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-rparobot` | — |
| Upload document (`caseworker-upload-document`) | [General consideration complete](./general-consideration-complete.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-rparobot` | — |
| Patch a joint case (`citizen-applicant2-update-application`) | [General consideration complete](./general-consideration-complete.md) | `[APPLICANTTWO]` | `divorceOrDissolution="NEVER_SHOW"` |
| General application payment (`citizen-general-app-payment`) | [General consideration complete](./general-consideration-complete.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Citizen general application (`citizen-general-application`) | [General consideration complete](./general-consideration-complete.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Generate Process Server Docs (`citizen-generate-process-server-docs`) | [General consideration complete](./general-consideration-complete.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Citizen service application (`citizen-service-application`) | [General consideration complete](./general-consideration-complete.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Citizen service payment made (`citizen-service-payment-made`) | [General consideration complete](./general-consideration-complete.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Start Interim Application (`citizen-start-interim-application`) | [General consideration complete](./general-consideration-complete.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Patch case (`citizen-update-application`) | [General consideration complete](./general-consideration-complete.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Create flags (`createFlags`) | [General consideration complete](./general-consideration-complete.md) | `caseworker-divorce-courtadmin-la`<br/>`caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-judge`<br/>`caseworker-divorce-superuser` | `caseFlagsSetupComplete="Yes"` |
| General application received (`cw-general-application-received`) | [General consideration complete](./general-consideration-complete.md) | `caseworker-divorce-courtadmin_beta` | — |
| Draft AoS (`draft-aos`) | [General consideration complete](./general-consideration-complete.md) | `[APPLICANTTWO]`<br/>`[APPTWOSOLICITOR]` | `applicationType="soleApplication" AND aosIsDrafted!="Yes"` |
| General application refund (`general-application-refund`) | [General consideration complete](./general-consideration-complete.md) | `caseworker-divorce-superuser` | — |
| Manage flags (`manageFlags`) | [General consideration complete](./general-consideration-complete.md) | `caseworker-divorce-courtadmin-la`<br/>`caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-judge`<br/>`caseworker-divorce-superuser` | `caseFlagsSetupComplete="Yes"` |
| Notice Of Change Applied (`notice-of-change-applied`) | [General consideration complete](./general-consideration-complete.md) | `caseworker-approver` | — |
| Notice Of Change Requested (`notice-of-change-requested`) | [General consideration complete](./general-consideration-complete.md) | `caseworker-caa` | — |
| Reject general application (`reject-general-application`) | [General consideration complete](./general-consideration-complete.md) | `caseworker-divorce-courtadmin_beta` | — |
| Remission refund (`remission-refund`) | [General consideration complete](./general-consideration-complete.md) | `caseworker-divorce-superuser` | — |
| Rescind Conditional order (`rescind-conditional-order`) | [General consideration complete](./general-consideration-complete.md) | `caseworker-divorce-courtadmin_beta` | — |
| Service application refund (`service-application-refund`) | [General consideration complete](./general-consideration-complete.md) | `caseworker-divorce-superuser` | — |
| General Application (`solicitor-general-application`) | [General consideration complete](./general-consideration-complete.md) | `[APPONESOLICITOR]`<br/>`[APPTWOSOLICITOR]` | — |
| Stop representing client (`solicitor-stop-representation`) | [General consideration complete](./general-consideration-complete.md) | `[APPONESOLICITOR]`<br/>`[APPTWOSOLICITOR]` | — |
| Submit AoS (`submit-aos`) | [General consideration complete](./general-consideration-complete.md) | `[APPLICANTTWO]`<br/>`[APPTWOSOLICITOR]` | `applicationType="soleApplication" AND aosIsDrafted="Yes"` |
| AoS disputed (`system-issue-aos-disputed`) | [General consideration complete](./general-consideration-complete.md) | `caseworker-divorce-systemupdate` | — |
| AoS undisputed (`system-issue-aos-undisputed`) | [General consideration complete](./general-consideration-complete.md) | `caseworker-divorce-systemupdate` | — |
| Link Resp or App 2 to case (`system-link-applicant2`) | [General consideration complete](./general-consideration-complete.md) | `caseworker-divorce-systemupdate` | — |
| Migrate case data (`system-migrate-case`) | [General consideration complete](./general-consideration-complete.md) | `caseworker-divorce-systemupdate` | — |
| Migrate organisation policies (`system-migrate-organisation-policies`) | [General consideration complete](./general-consideration-complete.md) | `caseworker-divorce-systemupdate` | — |
| System remove bulk case (`system-remove-bulk-case`) | [General consideration complete](./general-consideration-complete.md) | `caseworker-divorce-superuser`<br/>`caseworker-divorce-systemupdate` | — |
| Unlink Applicant from case (`system-unlink-applicant`) | [General consideration complete](./general-consideration-complete.md) | `citizen` | — |
| Update issue date (`system-update-issue-date`) | [General consideration complete](./general-consideration-complete.md) | `caseworker-divorce-systemupdate` | — |

## Incoming events

| Event | Start state | Runnable by | Enabling condition |
|---|---|---|---|
| General Consideration (`legal-advisor-general-consideration`) | [Awaiting general consideration](./awaiting-general-consideration.md) | `caseworker-divorce-courtadmin-la` | — |
