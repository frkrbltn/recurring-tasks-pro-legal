# Recurring Tasks Pro for Jira Cloud

## User guide

Last updated: October 9, 2026.

Recurring Tasks Pro creates new Jira issues from recurring schedules. An
existing Jira issue acts as a reusable, live template: the app reads its
supported fields again when a run executes, unless you have configured
overrides.

This is general documentation for the current Jira Cloud app. Jira may use
"work item" instead of "issue" in its navigation.

## Before you start

- A Jira administrator must install and authorize the app on your Jira Cloud
  site.
- To manage a schedule, you need Jira administration or project administration
  permission, plus Browse Projects and Create Issues in the destination project.
  You also need access to the source issue.
- Start with a standard Jira issue in that project. Subtasks and issues with an
  issue security level cannot be used as templates.
- If the app displays a licensing restriction, ask your Jira administrator to
  check the app's license.

You do not need to configure a separate server or provide an API token to use
the installed app.

## Create your first recurring task

1. **Prepare a template issue.** Create a normal Jira issue with the summary,
   description, and supported fields you want future issues to inherit. You
   can also reuse an existing issue.
2. **Open the app.** In Jira's Apps navigation, open **Recurring Tasks Pro**,
   select **Recurring tasks**, and choose **Create recurring task**. Alternatively,
   open a Jira issue and choose **Make recurring** from its issue actions.
3. **Choose template.** Search by the issue key or words from its summary,
   select the issue, and enter a recognizable recurring task name. Search needs
   at least two characters. Select **Continue**.
4. **Set schedule.** Choose Daily, Weekly, Monthly, or Yearly; configure the
   interval, relevant days, local time, timezone, and start date. For Monday
   through Friday, choose Weekly and **Select weekdays**. Review the upcoming
   dates in the preview. Under **End conditions**, optionally set an end date
   or a limit on successful scheduled runs. Without an end condition, the
   schedule has no configured end.
5. **Configure issue fields.** Confirm the destination project and issue type.
   Leave a field inherited to use its current template value at execution time,
   or enable **Override** to set a different value. Resolve any required-field
   errors and review warnings about unsupported fields.
6. **Review and activate.** Check the template, fields, and upcoming dates, then
   select **Activate recurring task**.
7. **Confirm the result.** After a scheduled occurrence, open **Execution
   history**, select the execution, and follow the Jira issue link when the run
   is successful.

For a first trial, use non-sensitive demonstration content and set **Stop after
successful scheduled runs** to `1`. This limits successful scheduled runs; it
does not stop you from separately requesting a manual run.

## Understand templates and scheduling

### Live templates

The template is an ordinary Jira issue, not a separate template object that you
must create in another app. Changing a supported field on that issue can change
what future runs create. An explicit override takes precedence for that field.
Issues already created are not rewritten when you edit the template.

Keep the source issue available and in the destination project. Moving it to a
different project, restricting access, or changing required fields can prevent
future runs.

### Timezones and timing

Each schedule has its own named timezone, such as `America/New_York`. Check the
preview rather than assuming that the schedule follows your browser timezone.
The preview displays upcoming local dates and timezone offset changes.

The scheduler checks for due work every five minutes. Issue creation is not
instantaneous or guaranteed at the exact scheduled minute; platform delays,
Jira availability, and retries can add time. You do not need to keep the app
or browser open for scheduled runs.

Weekly weekday selection and monthly first/last weekday patterns mean Monday
through Friday. They do not apply a public-holiday calendar.

## Manage existing schedules

Open **Recurring tasks**, select a task, and use the available controls.

| Action | What it does |
| --- | --- |
| Edit | Change the configuration and select **Save changes**. Review the updated preview. |
| Pause | Stop future scheduled runs until the task is resumed. |
| Resume | Continue at the next future occurrence. Dates missed while paused are not replayed. |
| Skip next occurrence | Skip the next scheduled occurrence of an active task without creating an issue for it. |
| Run now | Request an additional issue immediately without changing the regular schedule. |
| Duplicate | Open a new configuration based on the existing task; review it before activating it as a separate schedule. |
| Delete | Remove the recurring task and its execution history. Jira issues already created are kept. Review the confirmation carefully. |

Some controls are unavailable while an execution is in progress or its Jira
outcome is uncertain. A completed schedule needs its end conditions adjusted
before it can be resumed.

Scheduled work uses the Jira permissions of the administrator who created,
last saved, or resumed the task. Saving or resuming makes that administrator
the execution owner. If the owner's access changes, runs can fail or require
attention. Installation-wide **Settings** are restricted to Jira administrators.

## Check results and resolve problems

**Overview** summarizes upcoming work, recent executions, and tasks requiring
attention. **Execution history** lets you inspect run status, timing, attempts,
and errors. Successful executions include a link to the created Jira issue.

| Problem | What to check |
| --- | --- |
| The app or project is unavailable | Confirm installation and your Jira/project administration, browse, and create permissions with a Jira administrator. |
| No template search results | Try the exact issue key and confirm that you can access the issue. Create a normal Jira issue first if no template exists. |
| Activation is blocked | Resolve required fields, unsupported template/type restrictions, invalid schedule dates, or the licensing message shown in the app. |
| A scheduled issue has not appeared | Check the schedule's timezone, next occurrence, end conditions, and Active/Paused/Completed state. Allow for the five-minute check and platform delays, then inspect execution history. |
| An execution failed | Read its error and correct the underlying permission, template, or field problem. Use **Retry execution** when offered. |
| The Jira outcome is uncertain | Check whether an issue already exists and use **Reconcile with Jira** when offered. This checks the original execution's outcome. Do not use **Run now** as a replacement for reconciliation: it requests a separate issue. |
| An edit conflicts with another change | Refresh the task, review the current configuration, and apply your change again. |

The app includes duplicate-protection and reconciliation mechanisms, but this
guide does not promise that every outage or external failure will be resolved
automatically. Contact support if an execution remains unresolved.

## Current boundaries

- Source and destination must remain in the same Jira project.
- Subtasks and source issues with issue security levels are unsupported.
- Only supported issue fields are copied. This is not a complete issue clone:
  attachments, comments, and arbitrary third-party field structures are not
  reproduced.
- Review field warnings and required-field errors before activation.
- A schedule creates new issues; it does not reopen or update the original
  template issue as a substitute for creating a new issue.

## Data, terms, and support

See the [Privacy Policy](PRIVACY.md) for storage, retention, deletion, and current
limitations. Deleting a schedule does not delete Jira issues it created or
necessarily erase every associated data category. Use the privacy contact for
data-related requests.

The [Terms of Service](TERMS.md) describe the terms for using the app.

**Support:** [galadining@outlook.com](mailto:galadining@outlook.com)

When reporting a problem, include the action you attempted, the execution status
or error text, and the relevant date and timezone. Redact customer information
from screenshots. Do not send passwords, API tokens, or other secrets.
