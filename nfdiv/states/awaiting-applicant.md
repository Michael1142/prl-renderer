# Awaiting applicant

[Back to No Fault Divorce State Model](../index.md)

State ID: `AwaitingDocuments`

## Local state model

```mermaid
flowchart LR
    current["Awaiting applicant"]

    subgraph inbound["Inbound to Awaiting applicant"]
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
        in_offlinedocumentreceived["Offline document received by CW"]
        in_pendinghearingdate["Pending hearing date"]
        in_pendinghearingoutcome["Pending hearing outcome"]
        in_pendingrefund["Pending refund"]
        in_pendingserviceappresponse["Pending service app response"]
        in_requestedinformationsubmitted["Requested Information Submitted"]
        in_respondentfinalorderrequested["Respondent Final order requested"]
        in_separationordergranted["Separation order granted"]
        in_serviceadminrefusal["Service Admin Refusal"]
        in_submitted["Submitted"]
        in_welshtranslationrequested["Welsh Translation requested"]
        in_welshtranslationreview["Welsh Translation review"]
    end

    subgraph outbound["Outbound from Awaiting applicant"]
        out_archived["Archived"]
        out_awaitingalternativeservice["Awaiting alternative service"]
        out_awaitingamendedapplication["Awaiting amended application"]
        out_awaitinghwfevidence["Awaiting HWF evidence"]
        out_awaitinghwfpartpayment["Awaiting HWF part payment"]
        out_awaitingresponsetohwfdecision["Awaiting response to HWF Decision"]
        out_offlinedocumentreceived["Offline document received by CW"]
        out_rejected["Application rejected"]
        out_submitted["Submitted"]
        out_withdrawn["Application withdrawn"]
    end

    in_aosdrafted -->|"Awaiting Applicant"| current
    in_aosoverdue -->|"Awaiting Applicant"| current
    in_awaitingadminclarification -->|"Awaiting Applicant"| current
    in_awaitingalternativeservice -->|"Awaiting Applicant"| current
    in_awaitingamendedapplication -->|"Awaiting Applicant"| current
    in_awaitinganswer -->|"Awaiting Applicant"| current
    in_awaitingaos -->|"Awaiting Applicant"| current
    in_awaitingbailiffreferral -->|"Awaiting Applicant"| current
    in_awaitingbailiffservice -->|"Awaiting Applicant"| current
    in_awaitingclarification -->|"Awaiting Applicant"| current
    in_awaitingconditionalorder -->|"Awaiting Applicant"| current
    in_awaitingdwpresponse -->|"Awaiting Applicant"| current
    in_awaitingfinalorder -->|"Awaiting Applicant"| current
    in_awaitingfinalorderpayment -->|"Awaiting Applicant"| current
    in_awaitinggenapphwfevidence -->|"Awaiting Applicant"| current
    in_awaitinggenapphwfpartpayment -->|"Awaiting Applicant"| current
    in_awaitinggeneralapplicationpayment -->|"Awaiting Applicant"| current
    in_awaitinggeneralconsideration -->|"Awaiting Applicant"| current
    in_awaitinggeneralreferralpayment -->|"Awaiting Applicant"| current
    in_awaitinghwfdecision -->|"Awaiting Applicant<br/>Awaiting documents"| current
    in_awaitinghwfevidence -->|"Awaiting Applicant"| current
    in_awaitinghwfpartpayment -->|"Awaiting Applicant"| current
    in_awaitingjointfinalorder -->|"Awaiting Applicant"| current
    in_awaitingjsnullity -->|"Awaiting Applicant"| current
    in_awaitingjudgeclarification -->|"Awaiting Applicant"| current
    in_awaitinglegaladvisorreferral -->|"Awaiting Applicant"| current
    in_awaitingpayment -->|"Awaiting Applicant<br/>Awaiting documents"| current
    in_awaitingpronouncement -->|"Awaiting Applicant"| current
    in_awaitingrequestedinformation -->|"Awaiting Applicant"| current
    in_awaitingresponsetohwfdecision -->|"Awaiting Applicant"| current
    in_awaitingservice -->|"Awaiting Applicant"| current
    in_awaitingserviceconsideration -->|"Awaiting Applicant"| current
    in_awaitingservicepayment -->|"Awaiting Applicant"| current
    in_bailiffrefused -->|"Awaiting Applicant"| current
    in_bulkcasereject -->|"Awaiting Applicant"| current
    in_clarificationsubmitted -->|"Awaiting Applicant"| current
    in_conditionalorderdrafted -->|"Awaiting Applicant"| current
    in_conditionalorderpending -->|"Awaiting Applicant"| current
    in_conditionalorderpronounced -->|"Awaiting Applicant"| current
    in_conditionalorderrefused -->|"Awaiting Applicant"| current
    in_conditionalorderreview -->|"Awaiting Applicant"| current
    in_finalordercomplete -->|"Awaiting Applicant"| current
    in_finalorderpending -->|"Awaiting Applicant"| current
    in_finalorderrequested -->|"Awaiting Applicant"| current
    in_generalapplicationreceived -->|"Awaiting Applicant"| current
    in_generalconsiderationcomplete -->|"Awaiting Applicant"| current
    in_holding -->|"Awaiting Applicant"| current
    in_inbulkactioncase -->|"Awaiting Applicant"| current
    in_informationrequested -->|"Awaiting Applicant"| current
    in_issuedtobailiff -->|"Awaiting Applicant"| current
    in_jsawaitingla -->|"Awaiting Applicant"| current
    in_lareview -->|"Awaiting Applicant"| current
    in_laservicereview -->|"Awaiting Applicant"| current
    in_newpapercase -->|"Awaiting Applicant"| current
    in_offlinedocumentreceived -->|"Awaiting Applicant"| current
    in_pendinghearingdate -->|"Awaiting Applicant"| current
    in_pendinghearingoutcome -->|"Awaiting Applicant"| current
    in_pendingrefund -->|"Awaiting Applicant"| current
    in_pendingserviceappresponse -->|"Awaiting Applicant"| current
    in_requestedinformationsubmitted -->|"Awaiting Applicant"| current
    in_respondentfinalorderrequested -->|"Awaiting Applicant"| current
    in_separationordergranted -->|"Awaiting Applicant"| current
    in_serviceadminrefusal -->|"Awaiting Applicant"| current
    in_submitted -->|"Awaiting Applicant<br/>Awaiting documents"| current
    in_welshtranslationrequested -->|"Awaiting Applicant"| current
    in_welshtranslationreview -->|"Awaiting Applicant"| current
    current -->|"Archive Case"| out_archived
    current -->|"Serve by alternative method"| out_awaitingalternativeservice
    current -->|"Awaiting Amended Application"| out_awaitingamendedapplication
    current -->|"HWF evidence required"| out_awaitinghwfevidence
    current -->|"HWF part payment required"| out_awaitinghwfpartpayment
    current -->|"HWF refused"| out_awaitingresponsetohwfdecision
    current -->|"Attach scanned docs"| out_offlinedocumentreceived
    current -->|"Reject"| out_rejected
    current -->|"HWF part payment made"| out_submitted
    current -->|"Withdraw<br/>Withdraw"| out_withdrawn
```

## Outgoing events

| Event | End state | Runnable by | Enabling condition |
|---|---|---|---|
| Attach scanned docs (`attachScannedDocs`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Awaiting Amended Application (`caseworker-awaiting-amended-application`) | [Awaiting amended application](./awaiting-amended-application.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| HWF evidence required (`caseworker-hwf-evidence-requested`) | [Awaiting HWF evidence](./awaiting-hwf-evidence.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| HWF part payment made (`caseworker-hwf-part-payment-made`) | [Submitted](./submitted.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| HWF part payment required (`caseworker-hwf-part-payment-required`) | [Awaiting HWF part payment](./awaiting-hwf-part-payment.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| HWF refused (`caseworker-hwf-refused`) | [Awaiting response to HWF Decision](./awaiting-response-to-hwf-decision.md) | `caseworker-divorce-courtadmin_beta` | — |
| Reject (`caseworker-rejected`) | [Application rejected](./application-rejected.md) | `caseworker-divorce-courtadmin_beta` | — |
| Serve by alternative method (`caseworker-serve-by-alternative-method`) | [Awaiting alternative service](./awaiting-alternative-service.md) | `caseworker-divorce-courtadmin_beta` | — |
| Withdraw (`caseworker-withdrawn`) | [Application withdrawn](./application-withdrawn.md) | `caseworker-divorce-courtadmin_beta` | — |
| Archive Case (`solicitor-archive-case`) | [Archived](./archived.md) | `[APPONESOLICITOR]` | — |
| Withdraw (`superuser-withdrawn`) | [Application withdrawn](./application-withdrawn.md) | `caseworker-divorce-superuser` | — |

## In-state events

| Event | End state | Runnable by | Enabling condition |
|---|---|---|---|
| Update contact info (`app1-solicitor-update-contact-details`) | [Awaiting applicant](./awaiting-applicant.md) | `[APPONESOLICITOR]` | — |
| View applicant contact info (`app1-solicitor-view-app1-contact-info`) | [Awaiting applicant](./awaiting-applicant.md) | `[APPONESOLICITOR]` | — |
| View respondent contact info (`app1-solicitor-view-app2-contact-info`) | [Awaiting applicant](./awaiting-applicant.md) | `[APPONESOLICITOR]` | — |
| Update contact info (`app2-solicitor-update-contact-details`) | [Awaiting applicant](./awaiting-applicant.md) | `[APPTWOSOLICITOR]` | — |
| View applicant contact info (`app2-solicitor-view-app1-contact-info`) | [Awaiting applicant](./awaiting-applicant.md) | `[APPTWOSOLICITOR]` | — |
| View respondent contact info (`app2-solicitor-view-app2-contact-info`) | [Awaiting applicant](./awaiting-applicant.md) | `[APPTWOSOLICITOR]` | — |
| Add bailiff return (`caseworker-add-bailiff-return`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-courtadmin-la`<br/>`caseworker-divorce-courtadmin_beta` | — |
| Add note (`caseworker-add-note`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Add translation (`caseworker-add-translation`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-courtadmin_beta` | — |
| Amend application type (`caseworker-amend-application-type`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-superuser` | — |
| Update case (`caseworker-amend-case`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-courtadmin_beta` | — |
| Change service request (`caseworker-change-service-request`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Confirm service (`caseworker-confirm-service`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-courtadmin_beta` | `issueDate="*"` |
| Create general email (`caseworker-create-general-email`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-courtadmin_beta` | — |
| Create general letter (`caseworker-create-general-letter`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-courtadmin_beta` | — |
| Create general order (`caseworker-create-general-order`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-courtadmin_beta` | — |
| Find matches (`caseworker-find-matches`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| General referral (`caseworker-general-referral`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| HWF application accepted (`caseworker-hwf-application-accepted`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-courtadmin_beta` | — |
| Application issue (`caseworker-issue-application`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-courtadmin_beta` | — |
| Notice of change (`caseworker-notice-of-change`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Payment made (`caseworker-payment-made`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-courtadmin_beta` | — |
| Prepare for Case flags (`caseworker-prepare-caseflags`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-courtadmin-la`<br/>`caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-judge`<br/>`caseworker-divorce-superuser` | `caseFlagsSetupComplete!="Yes"` |
| Prepare email attachments (`caseworker-prepare-general-email`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-courtadmin_beta` | — |
| Regenerate court orders (`caseworker-regenerate-court-orders`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-superuser` | — |
| Reissue (`caseworker-reissue-application`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-systemupdate` | — |
| Reject Service Application (`caseworker-reject-service-application`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-superuser` | — |
| Remove documents (`caseworker-remove-document`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-superuser` | — |
| Remove Failed Sol NoC Request (`caseworker-remove-failed-sol-noc-request`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-superuser` | — |
| Remove general emails (`caseworker-remove-general-emails`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-superuser` | — |
| Remove general letter (`caseworker-remove-general-letter`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-superuser` | — |
| Remove General Order (`caseworker-remove-general-order`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-superuser` | — |
| Remove note (`caseworker-remove-note`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-superuser` | — |
| Remove scanned document (`caseworker-remove-scanned-document`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-courtadmin_beta` | — |
| Request For Information (`caseworker-request-for-information`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-courtadmin_beta` | — |
| Add RFI Response (`caseworker-request-for-information-response`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-bulkscan`<br/>`caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Request Translation from WLU (`caseworker-request-translation-wlu`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-courtadmin_beta` | — |
| Return to previous state (`caseworker-return-to-previous-state`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Service application received (`caseworker-service-received`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-courtadmin_beta` | — |
| Applicant responded (`caseworker-submit-from-awaitingdocuments-app1resp`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-courtadmin_beta` | — |
| Update App or App1 Email (`caseworker-update-app1-email`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Update Resp or App 2 Email (`caseworker-update-app2-email`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Update contact details (`caseworker-update-contact-details`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Update Date Submitted (`caseworker-update-date-submitted`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-superuser` | — |
| Update due date (`caseworker-update-due-date`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Update FinRem and Jurisdiction (`caseworker-update-fin-rem-and-jurisd-joint`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-superuser` | `applicationType="jointApplication"` |
| Update FinRem and Jurisdiction (`caseworker-update-fin-rem-and-jurisdiction`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-superuser` | `applicationType="soleApplication"` |
| Update language preference (`caseworker-update-language-preference`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-courtadmin_beta` | — |
| Update offline status (`caseworker-update-offline-status`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-superuser` | — |
| Upload amended application (`caseworker-upload-amended-application`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | — |
| Upload confidential document (`caseworker-upload-confidential-document`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-rparobot` | — |
| Upload document (`caseworker-upload-document`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-rparobot` | — |
| Upload documents and submit (`caseworker-upload-documents-and-submit`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-courtadmin_beta` | — |
| Patch a joint case (`citizen-applicant2-update-application`) | [Awaiting applicant](./awaiting-applicant.md) | `[APPLICANTTWO]` | `divorceOrDissolution="NEVER_SHOW"` |
| General application payment (`citizen-general-app-payment`) | [Awaiting applicant](./awaiting-applicant.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Citizen general application (`citizen-general-application`) | [Awaiting applicant](./awaiting-applicant.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Citizen service application (`citizen-service-application`) | [Awaiting applicant](./awaiting-applicant.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Citizen service payment made (`citizen-service-payment-made`) | [Awaiting applicant](./awaiting-applicant.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Start Interim Application (`citizen-start-interim-application`) | [Awaiting applicant](./awaiting-applicant.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Patch case (`citizen-update-application`) | [Awaiting applicant](./awaiting-applicant.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Create flags (`createFlags`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-courtadmin-la`<br/>`caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-judge`<br/>`caseworker-divorce-superuser` | `caseFlagsSetupComplete="Yes"` |
| General application received (`cw-general-application-received`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-courtadmin_beta` | — |
| Upload service app docs (`cw-upload-service-app-docs`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-superuser` | `alternativeServiceType="*"` |
| Draft AoS (`draft-aos`) | [Awaiting applicant](./awaiting-applicant.md) | `[APPLICANTTWO]`<br/>`[APPTWOSOLICITOR]` | `applicationType="soleApplication" AND aosIsDrafted!="Yes"` |
| General application refund (`general-application-refund`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-superuser` | — |
| Manage flags (`manageFlags`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-courtadmin-la`<br/>`caseworker-divorce-courtadmin_beta`<br/>`caseworker-divorce-judge`<br/>`caseworker-divorce-superuser` | `caseFlagsSetupComplete="Yes"` |
| Reject general application (`reject-general-application`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-courtadmin_beta` | — |
| Remission refund (`remission-refund`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-superuser` | — |
| Service application refund (`service-application-refund`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-superuser` | — |
| General Application (`solicitor-general-application`) | [Awaiting applicant](./awaiting-applicant.md) | `[APPONESOLICITOR]`<br/>`[APPTWOSOLICITOR]` | — |
| Stop representing client (`solicitor-stop-representation`) | [Awaiting applicant](./awaiting-applicant.md) | `[APPONESOLICITOR]`<br/>`[APPTWOSOLICITOR]` | — |
| Submit AoS (`submit-aos`) | [Awaiting applicant](./awaiting-applicant.md) | `[APPLICANTTWO]`<br/>`[APPTWOSOLICITOR]` | `applicationType="soleApplication" AND aosIsDrafted="Yes"` |
| AoS disputed (`system-issue-aos-disputed`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-systemupdate` | — |
| AoS undisputed (`system-issue-aos-undisputed`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-systemupdate` | — |
| Link Resp or App 2 to case (`system-link-applicant2`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-systemupdate` | — |
| Migrate case data (`system-migrate-case`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-systemupdate` | — |
| Migrate organisation policies (`system-migrate-organisation-policies`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-systemupdate` | — |
| System remove bulk case (`system-remove-bulk-case`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-superuser`<br/>`caseworker-divorce-systemupdate` | — |
| Unlink Applicant from case (`system-unlink-applicant`) | [Awaiting applicant](./awaiting-applicant.md) | `citizen` | — |
| Update issue date (`system-update-issue-date`) | [Awaiting applicant](./awaiting-applicant.md) | `caseworker-divorce-systemupdate` | — |
| Update details or reissue (`update-partner-details-or-reissue`) | [Awaiting applicant](./awaiting-applicant.md) | `[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |

## Incoming events

| Event | Start state | Runnable by | Enabling condition |
|---|---|---|---|
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [AoS drafted](./aos-drafted.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [AoS overdue](./aos-overdue.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [Awaiting admin clarification](./awaiting-admin-clarification.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [Awaiting alternative service](./awaiting-alternative-service.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [Awaiting amended application](./awaiting-amended-application.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [AwaitingAnswer](./awaitinganswer.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [AoS awaiting](./aos-awaiting.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [Awaiting bailiff referral](./awaiting-bailiff-referral.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [Awaiting bailiff service](./awaiting-bailiff-service.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [Awaiting clarification](./awaiting-clarification.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [Awaiting conditional order](./awaiting-conditional-order.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [Awaiting DWP response](./awaiting-dwp-response.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [Awaiting final order](./awaiting-final-order.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [Awaiting respondent final order payment](./awaiting-respondent-final-order-payment.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [Awaiting GenAppHWF evidence](./awaiting-genapphwf-evidence.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [Awaiting GenAppHWF part payment](./awaiting-genapphwf-part-payment.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [Awaiting general application payment](./awaiting-general-application-payment.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [Awaiting general consideration](./awaiting-general-consideration.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [Awaiting general referral payment](./awaiting-general-referral-payment.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [Awaiting HWF decision](./awaiting-hwf-decision.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [Awaiting HWF evidence](./awaiting-hwf-evidence.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [Awaiting HWF part payment](./awaiting-hwf-part-payment.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [Awaiting joint final order](./awaiting-joint-final-order.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [AwaitingJS/Nullity](./awaitingjs-nullity.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [Awaiting judge clarification](./awaiting-judge-clarification.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [Awaiting legal advisor referral](./awaiting-legal-advisor-referral.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [Application awaiting payment](./application-awaiting-payment.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [Listed; awaiting pronouncement](./listed-awaiting-pronouncement.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [Awaiting requested information](./awaiting-requested-information.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [Awaiting response to HWF Decision](./awaiting-response-to-hwf-decision.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [Awaiting service](./awaiting-service.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [Awaiting service consideration](./awaiting-service-consideration.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [Awaiting service payment](./awaiting-service-payment.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [Bailiff service refused](./bailiff-service-refused.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [Removed from bulk case](./removed-from-bulk-case.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [Clarification response submitted](./clarification-response-submitted.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [Conditional order drafted](./conditional-order-drafted.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [Awaiting joint conditional order](./awaiting-joint-conditional-order.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [Conditional order pronounced](./conditional-order-pronounced.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [Conditional order refused](./conditional-order-refused.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [Conditional order review caseworker](./conditional-order-review-caseworker.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [Final order complete](./final-order-complete.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [Final order pending](./final-order-pending.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [Final order requested](./final-order-requested.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [General application received](./general-application-received.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [General consideration complete](./general-consideration-complete.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [20 week holding period](./20-week-holding-period.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [Case in bulk action process](./case-in-bulk-action-process.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [Information Requested](./information-requested.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [Issued to bailiff](./issued-to-bailiff.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [Judicial Separation, Awaiting legal advisor](./judicial-separation-awaiting-legal-advisor.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [LA Review](./la-review.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [LA service app review](./la-service-app-review.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [New paper case](./new-paper-case.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [Offline document received by CW](./offline-document-received-by-cw.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [Pending hearing date](./pending-hearing-date.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [Pending hearing outcome](./pending-hearing-outcome.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [Pending refund](./pending-refund.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [Pending service app response](./pending-service-app-response.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [Requested Information Submitted](./requested-information-submitted.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [Respondent Final order requested](./respondent-final-order-requested.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [Separation order granted](./separation-order-granted.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [Service Admin Refusal](./service-admin-refusal.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [Submitted](./submitted.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [Welsh Translation requested](./welsh-translation-requested.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting Applicant (`caseworker-awaiting-applicant`) | [Welsh Translation review](./welsh-translation-review.md) | `caseworker-divorce-courtadmin_beta` | — |
| Awaiting documents (`caseworker-awaiting-documents`) | [Awaiting HWF decision](./awaiting-hwf-decision.md) | — | — |
| Awaiting documents (`caseworker-awaiting-documents`) | [Application awaiting payment](./application-awaiting-payment.md) | — | — |
| Awaiting documents (`caseworker-awaiting-documents`) | [Submitted](./submitted.md) | — | — |
