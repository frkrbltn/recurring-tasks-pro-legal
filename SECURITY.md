# Security Policy - Recurring Tasks Pro for Jira

**Effective date:** October 9, 2026

**Publisher:** Furkan Karabulut, individual publisher

**Security contact:** [galadining@outlook.com](mailto:galadining@outlook.com)

## Scope

This policy describes the current security approach and vulnerability-reporting
process for Recurring Tasks Pro for Jira Cloud ("the App"). Although this
policy is hosted in our public documentation repository, it applies to the App.
It does not replace Atlassian's policies for Jira, Forge, or the Marketplace.

This document is not evidence of a completed independent security audit,
penetration test, security certification, or Atlassian Marketplace approval.

## Current security controls

- **Hosting and storage:** The App's backend, scheduled functions, queues, and
  persistent application database use Atlassian Forge and Forge SQL.
  Application records are isolated by installation. Browser editor drafts are
  stored separately in browser session storage.
- **Authentication:** Interactive operations use the authenticated Jira user
  context supplied by Forge. Users do not provide a separate App password or
  Jira API token to use the installed App.
- **Authorization:** Schedule-management operations check Jira or project
  administration permission together with Browse Projects and Create Issues
  permissions. Installation settings and aggregate usage reports require Jira
  administrator permission.
- **Scheduled execution:** Scheduled Jira requests use the saved execution
  owner's account through Forge offline user impersonation. The App rechecks
  the owner's project-management permissions before creating issues. A loss of
  access can prevent a scheduled run.
- **Template restrictions:** Source and destination remain in the same project.
  Source issues with issue security levels are rejected to avoid creating less
  restricted copies. Jira field requirements and supported-field restrictions
  are checked during configuration and execution.
- **Input and execution controls:** The App validates operation inputs and uses
  version checks, execution identities, and reconciliation to reduce conflicting
  changes and duplicate issue creation. These controls are not a guarantee
  against every failure or outage.
- **Network destinations:** The deployed App declares no non-Atlassian external
  network destinations and uses no separately operated application backend.
  Support email and this public GitHub documentation are separate services
  outside Forge.

Atlassian operates the underlying hosted platform and its infrastructure
protections. This policy does not make an independent guarantee about every
platform control or imply that browser drafts, email, and App storage have
identical protections.

## Administrator and user responsibilities

Jira administrators control installation, site access, project permissions,
and access to source and generated issues. Review these permissions and the
execution owner's continued access when staff or project responsibilities
change.

Use only the issue content needed for the recurring task. Do not place
passwords, API tokens, payment-card details, or unnecessary sensitive
information in templates, overrides, or support messages. Review failed or
uncertain executions before requesting another manual run.

For data categories, retention, uninstall behavior, and current limitations
of automated account-data deletion, see the [Privacy Policy](PRIVACY.md).
This security policy does not promise complete automatic erasure.

## Report a suspected vulnerability privately

Email **[galadining@outlook.com](mailto:galadining@outlook.com)** with the subject
**Security report - Recurring Tasks Pro**.

Please include:

- The affected feature and a clear description of the suspected problem.
- Steps to reproduce using a test installation you own or are authorized to use.
- The potential impact and minimal, redacted evidence.
- When you observed the behavior, including timezone, and the App version if known.
- A way to contact you for clarification.

Do **not** publish vulnerability details in public GitHub issues, Marketplace
reviews, or other public channels. Do not send credentials, full production
exports, or other users' personal data. If sensitive evidence is necessary,
contact us first to agree on an appropriate way to share it.

## Responsible testing

Test only installations and data you own or have explicit permission to test.
This policy does not authorize testing Atlassian infrastructure, third-party
services, or other customers' sites.

Avoid destructive actions, service disruption, excessive traffic, social
engineering, and access to information beyond what is necessary to demonstrate
the issue. If you encounter another person's information, stop testing and
report the concern without copying or exposing that information.

## Report handling and updates

We review reports, may request clarification, and prioritize confirmed issues
according to their severity and impact. A response may involve an App update,
configuration guidance, or coordination with Atlassian where its platform is
involved. Keep technical details private while remediation and any appropriate
disclosure are coordinated.

We do not currently publish a guaranteed acknowledgement, remediation, or
support-response deadline. This policy does not establish a paid bug-bounty
program or promise compensation.

The policy covers the currently maintained Jira Cloud App. Administrators
should review App updates and any permission approvals requested through Jira.
For ordinary setup and troubleshooting, see the [User guide](DOCUMENTATION.md).

## Security incidents

If an App-related security incident is identified, we will assess its impact,
take appropriate containment and remediation steps within our control, and
coordinate with relevant service providers when necessary.

Notifications to affected parties or authorities will follow applicable legal
and contractual obligations and the facts of the incident. No service can
guarantee absolute security or uninterrupted availability.

The [Terms of Service](TERMS.md) and [Privacy Policy](PRIVACY.md) provide
additional information about service responsibilities and data processing.
