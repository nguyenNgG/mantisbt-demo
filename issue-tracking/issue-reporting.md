# Working with Issues

Issue tracking is the nuts and bolts of MantisBT.

Here are a few tips to help you get started with working with them.

---

## Creating an Issue Report

...

---

## Issue Properties

### Statuses

The official definition for issue statuses from [MantisBT Admin Guide](https://mantisbt.org/docs/master/en-US/Admin_Guide/html-desktop/#admin.lifecycle.status) :

- New

This is the landing status for new issues. Issues stay in this status until they are assigned, acknowledged, confirmed or resolved. 

The next status can be "acknowledged", "confirmed", "assigned" or "resolved".

- Acknowledged

This status is used by the development team to reflect their agreement to the suggested feature request. Or to agree with what the reporter is suggesting in an issue report, although they didn't yet attempt to reproduce what the reporter is referring to.

The next status is typically "assigned" or "confirmed".

- Confirmed

This status is typically used by the development team to mention that they agree with what the reporter is suggesting in the issue and that they have confirmed and reproduced the issue.

The next status is typically "assigned".

- Assigned

This status is used to reflect that the issue has been assigned to one of the team members and that such team member is actively working on the issue.

The next status is typically "resolved".

- Resolved

This status is used to reflect that the issue has been resolved. An issue can be resolved with one of many resolutions (customizable). For example, an issue can be resolved as "fixed", "duplicate", "won't fix", "no change required", etc.

The next statuses are typically "closed" or in case of the issue being re-opened, then it would be "feedback".

- Closed

This status reflects that the issue is completely closed and no further actions are required on it. It also typically hides the issue from the View Issues page. Some teams use "closed" to reflect sign-off by the reporter and others use it to reflect the fact that the fix has been released to customers.

---

## Resolution

Normally, resolutions are set when an issue status is resolved or closed.

For other cases, when a new issue is reported, its resolution will be "open".

Should an issue arise again after closing, its resolution can be set to "reopened".

Typically, resolutions would be one of the following:

- Fixed

Usually set when the defect given by the issue is corrected.

- Unable to reproduce

The issue failed to be reproduced and thus couldn't be examined to find the defect.

- Not fixable

The defect couldn't be corrected.

- Duplicate

A similar issue has already been reported.

A "duplicate of" relationship with another issue could be created to strengthen the notation.

- No change required

It is deemed that no change are needed after examining the issue.

- Suspended

The issue is temporarily or permanently stopped from being resolved.

- Won't fix

The issue is refused to be fixed for any reason.

---
