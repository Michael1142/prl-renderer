# Any state

[Back to No Fault Divorce State Model](../index.md)

These events are allowed from any state and preserve the current state.

| Event | Runnable by | Enabling condition |
|---|---|---|
| Update respondent contact info (`citizen-applicant2-update-contact-details`) | `[APPLICANTTWO]`<br/>`citizen` | `divorceOrDissolution="NEVER_SHOW"` |
| Send certificate of service (`citizen-evidence-certificate-of-service`) | `citizen` | `divorceOrDissolution="NEVER_SHOW"` |
| Save and close application (`citizen-save-and-close`) | `[APPLICANTTWO]`<br/>`citizen` | `divorceOrDissolution="NEVER_SHOW"` |
| Patch a case contact details (`citizen-update-contact-details`) | `[APPLICANTTWO]`<br/>`citizen` | `divorceOrDissolution="NEVER_SHOW"` |
| Citizen Withdraw (`citizen-withdrawn`) | `[APPLICANTTWO]`<br/>`[CREATOR]` | `divorceOrDissolution="NEVER_SHOW"` |
| Regenerate D8 (`regenerate-application`) | `caseworker-divorce-systemupdate` | — |
| Regenerate NoP (`regenerate-notice-of-proceedings`) | `caseworker-divorce-systemupdate` | — |
| Update applicant contact info (`solicitor-update-applicant1-contact-details`) | `[APPONESOLICITOR]` | — |
| Update applicant contact info (`solicitor-update-applicant2-contact-details`) | `[APPTWOSOLICITOR]` | — |
| Cancel User Case Invite (`system-cancel-case-invite`) | `caseworker-divorce-systemupdate` | — |
| Correct case TTL (`system-correct-ttl`) | `TTL_profile` | — |
| Link App or App 1 to case (`system-link-applicant1`) | `caseworker-divorce-systemupdate` | — |
| Regen JS Citizen AoS Response (`system-regen-js-citizen-aos-response-cover-letter`) | `caseworker-divorce-systemupdate` | — |
