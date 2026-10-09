# Privacy Policy — Recurring Tasks Pro for Jira

**Effective date:** 2026-10-08
**Publisher:** Furkan Karabulut, individual publisher
**Support and privacy contact:** [galadining@outlook.com](mailto:galadining@outlook.com)

This policy explains how Recurring Tasks Pro for Jira ("the App") processes
information when used on a Jira Cloud site. "We" and "us" refer to the publisher
identified above. It covers the App and support correspondence, not Atlassian's
independent operation of Jira, Forge or the Marketplace.

## 1. Information we process

The App stores information that can identify or relate to individuals. Hosting
that information on Atlassian Forge does not mean that the App stores no
personal data.

| Category | Information and purpose |
|---|---|
| User references | Atlassian account IDs of task creators and execution owners, and account references in saved field overrides. These support authorization, task ownership and issue creation on the owner's behalf. |
| Recurring-task configuration | Task names, source issue and project references, issue type, schedule, time zone, dates, status and selected field overrides. These define the issues to create and when to create them. |
| User-provided content | Saved overrides can include summaries, descriptions, assignees, labels and custom fields. This content can contain names, email addresses, mentions or other personal information supplied by users. |
| Execution records | Task and issue references, scheduled and actual times, outcomes, attempts, retry information, error details and event timelines. These support history, troubleshooting and duplicate prevention. Jira field-validation errors can contain information related to the submitted content. |
| Settings and usage events | Administrator settings and installation-level usage events with dates and deduplication identifiers. Reports show aggregate counts, but the underlying event records are not necessarily anonymous: identifiers can be linked to tasks or executions, and some are derived from account IDs using hashing. |
| Browser drafts | Unsaved editor content, including task configuration and field overrides, is stored in the browser's session storage to support draft recovery. |
| Operational diagnostics | Forge logs include event names, task and execution identifiers, error categories and correlation identifiers. Runtime or platform errors can produce additional diagnostic information. |
| Support correspondence | If you email support, your address, message and any information or attachments you choose to provide are processed to respond to your request. |

The App does not maintain a separate user-profile directory of names, email
addresses or avatars. This does **not** prevent such information from appearing
in user-entered content, field values, diagnostics or support messages.

Avoid including passwords, payment-card information or unnecessary sensitive
personal information in task configurations or support requests.

## 2. Jira access and recurring processing

The App uses Jira APIs to read source issues, project and field metadata,
permissions, the current user's time zone and assignable-user information. User
display names are used in selection controls rather than stored in a separate
profile database.

By default, the App saves references to the source issue and inherited fields.
It reads those fields again when creating an issue. Explicit overrides are
saved in the App. Content copied into a newly created Jira issue is also stored
in Jira under your site's permissions and retention settings.

Interactive operations use Forge's authenticated user context. Scheduled issue
creation uses the saved execution owner's account through Forge offline user
impersonation. Scheduling, queue processing and maintenance may run while no
user has the App open.

The App also uses Atlassian's personal-data reporting service. The limitations
of the current account-closure processing are described in section 6.

## 3. Purposes and responsibilities

App data is used to provide recurring issue creation, enforce permissions,
recover from failures, reduce duplicate creation, display history, support
users and understand reliability and usage.

Your organization determines what content to process and who may use the App.
Where data-protection law applies, it generally acts as the controller of that
content and the publisher processes it to provide the App. The publisher is
responsible for its own support correspondence and service administration.
Applicable contractual and legal obligations govern each party's role.

Where a lawful basis is required for the publisher's own support and service
administration, the relevant basis may be performing an agreement with you,
legitimate interests in responding to requests and maintaining the service, or
complying with a legal obligation, depending on the purpose. Your organization
is responsible for the lawful basis for the content it instructs the App to
process. Contact us for clarification about a particular processing activity.

Installation-level usage collection is enabled by default. A Jira administrator
can disable it in Settings. Disabling collection stops new usage-event writes;
it does not remove previously collected events or turn off operational logging.
The App has no advertising or third-party analytics integration.

## 4. Hosting, recipients and location

- **Atlassian:** The App's backend, queues and database use Forge. Persistent
  application records are held in Forge SQL, isolated by installation.
  Jira stores the source and generated issues. Atlassian also provides runtime
  logs and personal-data reporting.
- **Your browser:** The interface runs in your browser, where editor drafts
  may be held in session storage.
- **Support email:** Messages sent to the support address are processed through
  the email services used to deliver and manage that correspondence. Do not
  send production exports or sensitive attachments unless needed and agreed.
- **Public documentation:** Legal documents may be hosted on GitHub. Visiting
  those pages is subject to GitHub's own privacy practices; the App does not
  transmit your Jira records to that repository.

The deployed App declares no non-Atlassian external network destinations and
uses no separately operated application backend. This statement does not mean
that support email or public documentation is hosted inside Forge.

According to Atlassian's
[Forge-hosted storage lifecycle documentation](https://developer.atlassian.com/platform/forge/storage-reference/hosted-storage-data-lifecycle/),
Forge SQL storage follows the location of the host Atlassian app and its data
residency migrations. This is not a guarantee that browser drafts, support
email, operational logs or every processing activity occur in that location.
Atlassian and other service providers apply their own infrastructure,
retention and transfer arrangements.

The App does not send Jira content to advertising services or data brokers.
Disclosure may also be necessary to comply with applicable law or respond to
a valid legal request.

## 5. Retention

| Information | Current retention behavior |
|---|---|
| Recurring-task configurations | Remain until deleted through an authorized action; pausing or completing a task does not delete its configuration. |
| Execution details | Administrators choose 30, 90 (default) or 365 days, measured from execution creation. Hourly maintenance removes timelines and detailed errors from eligible terminal executions in batches. Processing delays or backlogs can extend that period; unresolved executions are not automatically expired by this rule. |
| Execution receipts | Other execution metadata remains after detail cleanup, including task and issue references, times, status, attempts and limited error metadata. These receipts prevent replay; they have no separate automatic expiry and remain linkable to tasks and Jira issues. |
| Deleted-task records | Successful task deletion clears the configuration and removes related execution records from active App storage. A tombstone with identifiers and operational metadata remains. Existing usage events and platform logs are not purged by task deletion. |
| Usage events | There is currently no automatic age-based deletion of stored usage events. The execution-history retention setting does not apply to them. |
| Browser drafts | Draft expiry is checked when a draft is loaded: drafts older than 24 hours are discarded then, not by a continuous deletion timer. Save/discard controls can clear drafts. Browser session behavior and session restoration may also affect retention. |
| Logs, platform copies and backups | Atlassian controls their retention; the App's history setting does not configure it. |
| Support messages | Managed separately from the App database and not automatically removed by task deletion or uninstall. Contact support for access or deletion requests; applicable legal retention obligations may apply. |

Uninstalling is not an immediate purge of every platform copy. Atlassian's
storage lifecycle governs soft deletion, retention, backups and recovery.
Reinstallation does not automatically restore prior data. Atlassian currently
requires a recovery request within 21 days for possible relinking; recovery
is not guaranteed. Consult its
[current storage lifecycle](https://developer.atlassian.com/platform/forge/storage-reference/hosted-storage-data-lifecycle/)
for details.

## 6. Deletion, corrections and account closure

Authorized users can edit task configurations or delete tasks through the App.
Deletion is blocked while a task has a pending execution. If a deletion
operation fails, use the reported error to seek assistance rather than assume
all records were removed.

Deleting a recurring task or uninstalling the App does **not** delete source
issues, previously created Jira issues or their execution-marker properties.
Your Jira administrator must handle those records using Jira's controls.
Browser drafts, usage events, support correspondence and platform-retained
copies must also be considered separately.

**Current automation limitation:** A daily background job attempts to report
stored account references and remove matching references when Atlassian reports
an account as closed. It can pause affected owners' tasks. This is not a
complete account-wide erasure or correction service: it does not cover all
stored content or records, can defer changes to tasks with pending work, and
does not currently handle every account-update response. Do not rely on
account closure alone to remove all related data.

For a request concerning access, correction or deletion, contact your Jira
administrator and [galadining@outlook.com](mailto:galadining@outlook.com).
Include the site URL and a description of the request. We may need your account
ID and proportionate confirmation of identity or authority to locate records
and avoid disclosing another person's data. Do not send credentials.

## 7. Security and access

The App uses Forge authentication, Jira permission checks, validated inputs and
concurrency controls. Settings and aggregate usage reports require Jira
administrator permission. App content is displayed through the user's browser.
Operational logs are available to authorized app operators through Atlassian's
tools.

No service can guarantee absolute security. Security concerns can be reported
to the support address. Any required breach notifications are subject to
applicable law and the facts of the incident.

## 8. Your rights

Depending on applicable law, you may have rights to access, correct, erase,
restrict or obtain a copy of your personal data, to object to processing, and
to complain to a data-protection authority. Where your organization controls
the data, requests may need to be coordinated with its administrator. These
rights are subject to applicable limitations and verification requirements.

The App is intended for workplace use, not for use directed at children.

## 9. Changes and contact

We will update this policy when processing practices change.
Material changes will be communicated through the available product,
Marketplace or documentation channels as required by law.

**Support and privacy:** [galadining@outlook.com](mailto:galadining@outlook.com)
