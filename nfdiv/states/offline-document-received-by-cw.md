# Offline document received by CW

[Back to No Fault Divorce State Model](../index.md)

State ID: `OfflineDocumentReceived`

## Local state model

```mermaid
flowchart LR
    current["Offline document received by CW"]

    subgraph inbound["Inbound to Offline document received by CW"]
        in_aosdrafted["AoS drafted"]
        in_aosoverdue["AoS overdue"]
        in_awaitingadminclarification["Awaiting admin clarification"]
        in_awaitingalternativeservice["Awaiting alternative service"]
        in_awaitingamendedapplication["Awaiting amended application"]
        in_awaitinganswer["AwaitingAnswer"]
        in_awaitingaos["AoS awaiting"]
        in_awaitingbailiffreferral["Awaiting bailiff referral"]
        in_awaitingbailiffservice["Awaiting bailiff service"]
        in_awaitingclarification["Awaiting clarification"]
        in_awaitingconditionalorder["Awaiting conditional order"]
        in_awaitingdocuments["Awaiting applicant"]
        in_awaitingdwpresponse["Awaiting DWP response"]
        in_awaitingfinalorder["Awaiting final order"]
        in_awaitingfinalorderpayment["Awaiting respondent final order payment"]
        in_awaitinggenapphwfevidence["Awaiting GenAppHWF evidence"]
        in_awaitinggenapphwfpartpayment["Awaiting GenAppHWF part payment"]
        in_awaitinggeneralapplicationpayment["Awaiting general application payment"]
        in_awaitinggeneralconsideration["Awaiting general consideration"]
        in_awaitinggeneralreferralpayment["Awaiting general referral payment"]
        in_awaitinghwfdecision["Awaiting HWF decision"]
        in_awaitinghwfevidence["Awaiting HWF evidence"]
        in_awaitinghwfpartpayment["Awaiting HWF part payment"]
        in_awaitingjointfinalorder["Awaiting joint final order"]
        in_awaitingjsnullity["AwaitingJS/Nullity"]
        in_awaitingjudgeclarification["Awaiting judge clarification"]
        in_awaitinglegaladvisorreferral["Awaiting legal advisor referral"]
        in_awaitingpayment["Application awaiting payment"]
        in_awaitingpronouncement["Listed; awaiting pronouncement"]
        in_awaitingrequestedinformation["Awaiting requested information"]
        in_awaitingresponsetohwfdecision["Awaiting response to HWF Decision"]
        in_awaitingservice["Awaiting service"]
        in_awaitingserviceconsideration["Awaiting service consideration"]
        in_awaitingservicepayment["Awaiting service payment"]
        in_bailiffrefused["Bailiff service refused"]
        in_bulkcasereject["Removed from bulk case"]
        in_clarificationsubmitted["Clarification response submitted"]
        in_conditionalorderdrafted["Conditional order drafted"]
        in_conditionalorderpending["Awaiting joint conditional order"]
        in_conditionalorderpronounced["Conditional order pronounced"]
        in_conditionalorderrefused["Conditional order refused"]
        in_conditionalorderreview["Conditional order review caseworker"]
        in_finalordercomplete["Final order complete"]
        in_finalorderpending["Final order pending"]
        in_finalorderrequested["Final order requested"]
        in_generalapplicationreceived["General application received"]
        in_generalconsiderationcomplete["General consideration complete"]
        in_holding["20 week holding period"]
        in_inbulkactioncase["Case in bulk action process"]
        in_informationrequested["Information Requested"]
        in_issuedtobailiff["Issued to bailiff"]
        in_jsawaitingla["Judicial Separation, Awaiting legal advisor"]
        in_lareview["LA Review"]
        in_laservicereview["LA service app review"]
        in_newpapercase["New paper case"]
        in_pendinghearingdate["Pending hearing date"]
        in_pendinghearingoutcome["Pending hearing outcome"]
        in_pendingrefund["Pending refund"]
        in_pendingserviceappresponse["Pending service app response"]
        in_rejected["Application rejected"]
        in_requestedinformationsubmitted["Requested Information Submitted"]
        in_respondentfinalorderrequested["Respondent Final order requested"]
        in_separationordergranted["Separation order granted"]
        in_serviceadminrefusal["Service Admin Refusal"]
        in_submitted["Submitted"]
        in_welshtranslationrequested["Welsh Translation requested"]
        in_welshtranslationreview["Welsh Translation review"]
        in_withdrawn["Application withdrawn"]
    end

    subgraph outbound["Outbound from Offline document received by CW"]
        out_awaitingalternativeservice["Awaiting alternative service"]
        out_awaitingamendedapplication["Awaiting amended application"]
        out_awaitingdocuments["Awaiting applicant"]
        out_rejected["Application rejected"]
        out_withdrawn["Application withdrawn"]
    end

    in_aosdrafted -->|"Attach scanned docs"| current
    in_aosoverdue -->|"Attach scanned docs"| current
    in_awaitingadminclarification -->|"Attach scanned docs"| current
    in_awaitingalternativeservice -->|"Attach scanned docs"| current
    in_awaitingamendedapplication -->|"Attach scanned docs"| current
    in_awaitinganswer -->|"Attach scanned docs"| current
    in_awaitingaos -->|"Attach scanned docs"| current
    in_awaitingbailiffreferral -->|"Attach scanned docs"| current
    in_awaitingbailiffservice -->|"Attach scanned docs"| current
    in_awaitingclarification -->|"Attach scanned docs"| current
    in_awaitingconditionalorder -->|"Attach scanned docs"| current
    in_awaitingdocuments -->|"Attach scanned docs"| current
    in_awaitingdwpresponse -->|"Attach scanned docs"| current
    in_awaitingfinalorder -->|"Attach scanned docs"| current
    in_awaitingfinalorderpayment -->|"Attach scanned docs"| current
    in_awaitinggenapphwfevidence -->|"Attach scanned docs"| current
    in_awaitinggenapphwfpartpayment -->|"Attach scanned docs"| current
    in_awaitinggeneralapplicationpayment -->|"Attach scanned docs"| current
    in_awaitinggeneralconsideration -->|"Attach scanned docs"| current
    in_awaitinggeneralreferralpayment -->|"Attach scanned docs"| current
    in_awaitinghwfdecision -->|"Attach scanned docs"| current
    in_awaitinghwfevidence -->|"Attach scanned docs"| current
    in_awaitinghwfpartpayment -->|"Attach scanned docs"| current
    in_awaitingjointfinalorder -->|"Attach scanned docs"| current
    in_awaitingjsnullity -->|"Attach scanned docs"| current
    in_awaitingjudgeclarification -->|"Attach scanned docs"| current
    in_awaitinglegaladvisorreferral -->|"Attach scanned docs"| current
    in_awaitingpayment -->|"Attach scanned docs"| current
    in_awaitingpronouncement -->|"Attach scanned docs"| current
    in_awaitingrequestedinformation -->|"Attach scanned docs"| current
    in_awaitingresponsetohwfdecision -->|"Attach scanned docs"| current
    in_awaitingservice -->|"Attach scanned docs"| current
    in_awaitingserviceconsideration -->|"Attach scanned docs"| current
    in_awaitingservicepayment -->|"Attach scanned docs"| current
    in_bailiffrefused -->|"Attach scanned docs"| current
    in_bulkcasereject -->|"Attach scanned docs"| current
    in_clarificationsubmitted -->|"Attach scanned docs"| current
    in_conditionalorderdrafted -->|"Attach scanned docs"| current
    in_conditionalorderpending -->|"Attach scanned docs"| current
    in_conditionalorderpronounced -->|"Attach scanned docs"| current
    in_conditionalorderrefused -->|"Attach scanned docs"| current
    in_conditionalorderreview -->|"Attach scanned docs"| current
    in_finalordercomplete -->|"Attach scanned docs"| current
    in_finalorderpending -->|"Attach scanned docs"| current
    in_finalorderrequested -->|"Attach scanned docs"| current
    in_generalapplicationreceived -->|"Attach scanned docs"| current
    in_generalconsiderationcomplete -->|"Attach scanned docs"| current
    in_holding -->|"Attach scanned docs"| current
    in_inbulkactioncase -->|"Attach scanned docs"| current
    in_informationrequested -->|"Attach scanned docs"| current
    in_issuedtobailiff -->|"Attach scanned docs"| current
    in_jsawaitingla -->|"Attach scanned docs"| current
    in_lareview -->|"Attach scanned docs"| current
    in_laservicereview -->|"Attach scanned docs"| current
    in_newpapercase -->|"Attach scanned docs"| current
    in_pendinghearingdate -->|"Attach scanned docs"| current
    in_pendinghearingoutcome -->|"Attach scanned docs"| current
    in_pendingrefund -->|"Attach scanned docs"| current
    in_pendingserviceappresponse -->|"Attach scanned docs"| current
    in_rejected -->|"Attach scanned docs"| current
    in_requestedinformationsubmitted -->|"Attach scanned docs"| current
    in_respondentfinalorderrequested -->|"Attach scanned docs"| current
    in_separationordergranted -->|"Attach scanned docs"| current
    in_serviceadminrefusal -->|"Attach scanned docs"| current
    in_submitted -->|"Attach scanned docs"| current
    in_welshtranslationrequested -->|"Attach scanned docs"| current
    in_welshtranslationreview -->|"Attach scanned docs"| current
    in_withdrawn -->|"Attach scanned docs"| current
    current -->|"Serve by alternative method"| out_awaitingalternativeservice
    current -->|"Awaiting Amended Application"| out_awaitingamendedapplication
    current -->|"Awaiting Applicant"| out_awaitingdocuments
    current -->|"Reject"| out_rejected
    current -->|"Withdraw"| out_withdrawn
```

## Outgoing events

| Event | End state | Runnable by | Enabling condition |
|---|---|---|---|
| Awaiting Amended Application (`caseworker-awaiting-amended-application`) | [Awaiting amended application](./awaiting-amended-application.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-courtadmin_beta` | — |
| Reject (`caseworker-rejected`) | [Application rejected](./application-rejected.md) | `caseworker-divorce-courtadmin_beta` | — |
| Serve by alternative method (`caseworker-serve-by-alternative-method`) | [Awaiting alternative service](./awaiting-alternative-service.md) | `caseworker-divorce-courtadmin_beta` | — |
| Withdraw (`caseworker-withdrawn`) | [Application withdrawn](./application-withdrawn.md) | `caseworker-divorce-courtadmin_beta` | — |

## In-state events

| Event | End state | Runnable by | Enabling condition |
|---|---|---|---|
| Update contact info (`app1-solicitor-update-contact-details`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `[APPONESOLICITOR]` | — |
| View applicant contact info (`app1-solicitor-view-app1-contact-info`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `[APPONESOLICITOR]` | — |
| View respondent contact info (`app1-solicitor-view-app2-contact-info`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `[APPONESOLICITOR]` | — |
| Update contact info (`app2-solicitor-update-contact-details`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `[APPTWOSOLICITOR]` | — |
| View applicant contact info (`app2-solicitor-view-app1-contact-info`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `[APPTWOSOLICITOR]` | — |
| View respondent contact info (`app2-solicitor-view-app2-contact-info`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `[APPTWOSOLICITOR]` | — |
| Attach scanned docs (`attachScannedDocs`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Add note (`caseworker-add-note`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Add translation (`caseworker-add-translation`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-divorce-courtadmin_beta` | — |
| Amend application type (`caseworker-amend-application-type`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-divorce-superuser` | — |
| Update case (`caseworker-amend-case`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-divorce-courtadmin_beta` | — |
| Confirm service (`caseworker-confirm-service`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-divorce-courtadmin_beta` | `issueDate="*"` |
| Create general email (`caseworker-create-general-email`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-divorce-courtadmin_beta` | — |
| Create general letter (`caseworker-create-general-letter`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-divorce-courtadmin_beta` | — |
| Create general order (`caseworker-create-general-order`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-divorce-courtadmin_beta` | — |
| Find matches (`caseworker-find-matches`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| General referral (`caseworker-general-referral`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Notice of change (`caseworker-notice-of-change`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Offline Document Verified (`caseworker-offline-document-verified`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-divorce-bulkscan`<br/>`caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Prepare for Case flags (`caseworker-prepare-caseflags`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-divorce-courtadmin-la`<br/>`caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-judge`<br/>`caseworker-divorce-superuser` | `caseFlagsSetupComplete!="Yes"` |
| Prepare email attachments (`caseworker-prepare-general-email`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-divorce-courtadmin_beta` | — |
| Regenerate court orders (`caseworker-regenerate-court-orders`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-divorce-superuser` | — |
| Reject Service Application (`caseworker-reject-service-application`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-divorce-superuser` | — |
| Remove documents (`caseworker-remove-document`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-divorce-superuser` | — |
| Remove Failed Sol NoC Request (`caseworker-remove-failed-sol-noc-request`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-divorce-superuser` | — |
| Remove general emails (`caseworker-remove-general-emails`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-divorce-superuser` | — |
| Remove general letter (`caseworker-remove-general-letter`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-divorce-superuser` | — |
| Remove General Order (`caseworker-remove-general-order`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-divorce-superuser` | — |
| Remove note (`caseworker-remove-note`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-divorce-superuser` | — |
| Remove scanned document (`caseworker-remove-scanned-document`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-divorce-courtadmin_beta` | — |
| Request Translation from WLU (`caseworker-request-translation-wlu`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-divorce-courtadmin_beta` | — |
| Return to previous state (`caseworker-return-to-previous-state`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Update App or App1 Email (`caseworker-update-app1-email`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Update Resp or App 2 Email (`caseworker-update-app2-email`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Update contact details (`caseworker-update-contact-details`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Update Date Submitted (`caseworker-update-date-submitted`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-divorce-superuser` | — |
| Update due date (`caseworker-update-due-date`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Update FinRem and Jurisdiction (`caseworker-update-fin-rem-and-jurisd-joint`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-divorce-superuser` | `applicationType="jointApplication"` |
| Update FinRem and Jurisdiction (`caseworker-update-fin-rem-and-jurisdiction`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-divorce-superuser` | `applicationType="soleApplication"` |
| Update general application (`caseworker-update-general-application`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-divorce-courtadmin_beta` | — |
| Update language preference (`caseworker-update-language-preference`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-divorce-courtadmin_beta` | — |
| Update offline status (`caseworker-update-offline-status`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-divorce-superuser` | — |
| Upload amended application (`caseworker-upload-amended-application`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Upload confidential document (`caseworker-upload-confidential-document`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-rparobot` | — |
| Upload document (`caseworker-upload-document`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-rparobot` | — |
| Patch a joint case (`citizen-applicant2-update-application`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `[APPLICANTTWO]` | `divorceOrDissolution="NEVER_SHOW"` |
| General application payment (`citizen-general-app-payment`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Citizen general application (`citizen-general-application`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Generate Process Server Docs (`citizen-generate-process-server-docs`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Citizen service application (`citizen-service-application`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Citizen service payment made (`citizen-service-payment-made`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Start Interim Application (`citizen-start-interim-application`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Patch case (`citizen-update-application`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Create flags (`createFlags`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-divorce-courtadmin-la`<br/>`caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-judge`<br/>`caseworker-divorce-superuser` | `caseFlagsSetupComplete="Yes"` |
| General application received (`cw-general-application-received`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-divorce-courtadmin_beta` | — |
| Draft AoS (`draft-aos`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `[APPLICANTTWO]`<br/>`[APPTWOSOLICITOR]` | `applicationType="soleApplication" AND aosIsDrafted!="Yes"` |
| General application refund (`general-application-refund`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-divorce-superuser` | — |
| Manage flags (`manageFlags`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-divorce-courtadmin-la`<br/>`caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-judge`<br/>`caseworker-divorce-superuser` | `caseFlagsSetupComplete="Yes"` |
| Notice Of Change Applied (`notice-of-change-applied`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-approver` | — |
| Notice Of Change Requested (`notice-of-change-requested`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-caa` | — |
| Reject general application (`reject-general-application`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-divorce-courtadmin_beta` | — |
| Remission refund (`remission-refund`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-divorce-superuser` | — |
| Service application refund (`service-application-refund`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-divorce-superuser` | — |
| General Application (`solicitor-general-application`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `[APPONESOLICITOR]`<br/>`[APPTWOSOLICITOR]` | — |
| Stop representing client (`solicitor-stop-representation`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `[APPONESOLICITOR]`<br/>`[APPTWOSOLICITOR]` | — |
| Submit AoS (`submit-aos`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `[APPLICANTTWO]`<br/>`[APPTWOSOLICITOR]` | `applicationType="soleApplication" AND aosIsDrafted="Yes"` |
| AoS disputed (`system-issue-aos-disputed`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-divorce-systemupdate` | — |
| AoS undisputed (`system-issue-aos-undisputed`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-divorce-systemupdate` | — |
| Link Resp or App 2 to case (`system-link-applicant2`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-divorce-systemupdate` | — |
| Migrate case data (`system-migrate-case`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-divorce-systemupdate` | — |
| Migrate organisation policies (`system-migrate-organisation-policies`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-divorce-systemupdate` | — |
| System pronounce case (`system-pronounce-case`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-divorce-superuser`<br/>`caseworker-divorce-systemupdate` | — |
| System remove bulk case (`system-remove-bulk-case`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-divorce-superuser`<br/>`caseworker-divorce-systemupdate` | — |
| Unlink Applicant from case (`system-unlink-applicant`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `citizen` | — |
| Update case with court hearing (`system-update-case-court-hearing`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-divorce-systemupdate` | `divorceOrDissolution="NEVER_SHOW"` |
| Update pronouncement judge (`system-update-case-pronouncement-judge`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-divorce-systemupdate` | — |
| Update issue date (`system-update-issue-date`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-divorce-systemupdate` | — |

## Incoming events

| Event | Start state | Runnable by | Enabling condition |
|---|---|---|---|
| Attach scanned docs (`attachScannedDocs`) | [AoS drafted](./aos-drafted.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [AoS overdue](./aos-overdue.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [Awaiting admin clarification](./awaiting-admin-clarification.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [Awaiting alternative service](./awaiting-alternative-service.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [Awaiting amended application](./awaiting-amended-application.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [AwaitingAnswer](./awaitinganswer.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [Awaiting bailiff referral](./awaiting-bailiff-referral.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [Awaiting bailiff service](./awaiting-bailiff-service.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [Awaiting clarification](./awaiting-clarification.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [Awaiting conditional order](./awaiting-conditional-order.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [Awaiting DWP response](./awaiting-dwp-response.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [Awaiting final order](./awaiting-final-order.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [Awaiting respondent final order payment](./awaiting-respondent-final-order-payment.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [Awaiting GenAppHWF evidence](./awaiting-genapphwf-evidence.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [Awaiting GenAppHWF part payment](./awaiting-genapphwf-part-payment.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [Awaiting general application payment](./awaiting-general-application-payment.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [Awaiting general consideration](./awaiting-general-consideration.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [Awaiting general referral payment](./awaiting-general-referral-payment.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [Awaiting HWF decision](./awaiting-hwf-decision.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [Awaiting HWF evidence](./awaiting-hwf-evidence.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [Awaiting HWF part payment](./awaiting-hwf-part-payment.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [Awaiting joint final order](./awaiting-joint-final-order.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [AwaitingJS/Nullity](./awaitingjs-nullity.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [Awaiting judge clarification](./awaiting-judge-clarification.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [Awaiting legal advisor referral](./awaiting-legal-advisor-referral.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [Application awaiting payment](./application-awaiting-payment.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [Listed; awaiting pronouncement](./listed-awaiting-pronouncement.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [Awaiting requested information](./awaiting-requested-information.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [Awaiting response to HWF Decision](./awaiting-response-to-hwf-decision.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [Awaiting service](./awaiting-service.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [Awaiting service consideration](./awaiting-service-consideration.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [Awaiting service payment](./awaiting-service-payment.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [Bailiff service refused](./bailiff-service-refused.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [Removed from bulk case](./removed-from-bulk-case.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [Clarification response submitted](./clarification-response-submitted.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [Conditional order drafted](./conditional-order-drafted.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [Conditional order pronounced](./conditional-order-pronounced.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [Conditional order refused](./conditional-order-refused.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [Conditional order review caseworker](./conditional-order-review-caseworker.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [Final order complete](./final-order-complete.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [Final order pending](./final-order-pending.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [Final order requested](./final-order-requested.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [General application received](./general-application-received.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [General consideration complete](./general-consideration-complete.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [20 week holding period](./20-week-holding-period.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [Case in bulk action process](./case-in-bulk-action-process.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [Information Requested](./information-requested.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [Issued to bailiff](./issued-to-bailiff.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [Judicial Separation, Awaiting legal advisor](./judicial-separation-awaiting-legal-advisor.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [LA Review](./la-review.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [LA service app review](./la-service-app-review.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [New paper case](./new-paper-case.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [Pending hearing date](./pending-hearing-date.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [Pending hearing outcome](./pending-hearing-outcome.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [Pending refund](./pending-refund.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [Pending service app response](./pending-service-app-response.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [Application rejected](./application-rejected.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [Requested Information Submitted](./requested-information-submitted.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [Respondent Final order requested](./respondent-final-order-requested.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [Separation order granted](./separation-order-granted.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [Service Admin Refusal](./service-admin-refusal.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [Submitted](./submitted.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [Welsh Translation requested](./welsh-translation-requested.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [Welsh Translation review](./welsh-translation-review.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Attach scanned docs (`attachScannedDocs`) | [Application withdrawn](./application-withdrawn.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
