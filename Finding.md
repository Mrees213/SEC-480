# Finding

Dana,

The available evidence shows that `\finance\Q3-working` was still present at 08:31:19 on Monday, 14 September, when `mreyes` successfully read `notes.docx` inside the folder. [C1] By 13:15:11, an attempt to access `\finance\Q3-working` failed with `PATH_NOT_FOUND`. [C2] The supported disappearance window is therefore after 08:31:19 and before 13:15:11. [C3]

Object-access auditing was disabled at 08:58:41 and re-enabled at 13:04:12. [C4, C5] No events were recorded during that interval. [C6] The audit export explicitly warns that the gap must not be treated as evidence that no activity occurred. [C7] Because most of the disappearance window overlaps this unaudited period, the removal most likely happened during the gap, but that remains an inference rather than a proven fact. [C9]

The deletion events that are present in the audit log do not involve `Q3-working`. [C10, C11] They involve directories under `Q3-archive`, and `Q3-working` was still accessible afterward. [C12]

`jcontractor` was logged on to fs02 and stated that cleanup work was being performed. [C13, C14] The contractor later stated that old material had been cleared. [C15] The supplied asset record lists the contractor group with Read access to `Q3-working`, not Modify access. [C16, C17] These facts make the contractor's activity relevant to the investigation, but the evidence does not establish that `jcontractor` removed the folder. [C18]

The finance team had Modify access to `Q3-working`, and Domain Admins had Full access. [C19, C21] Those permissions establish possible capability, but they do not identify any specific person or account as responsible for the disappearance. [C20, C22]

Your ticket says you opened `Q3-draft-v4.xlsx` Monday afternoon. [C23] The audit log shows morning access by your account, but your afternoon recollection is not disproved because object-access auditing was disabled until 13:04:12. [C24, C25] You were also told by 13:20 Monday that the folder could no longer be seen. [C26]

The share recycle bin was disabled, so checking it would not have been expected to recover the missing folder. [C34] The evidence also shows that the approved CHG-2211 audit-maintenance window was 09:00 to 13:00, while the actual audit-disable period extended slightly outside that window. [C35, C36]

## Cannot determine from this evidence

The evidence does not identify who removed `\finance\Q3-working`.

The evidence does not establish the exact time of removal beyond the interval after 08:31:19 and before 13:15:11.

The evidence does not establish whether the folder was deleted, moved, or renamed.

The evidence does not establish what activity occurred during the audit-disabled period.

The evidence does not establish whether the documented access list reflects every effective permission that existed at the time of the incident.

A record of the actual file-system operation, or another logging source covering the missing interval, would be needed to identify the responsible account or process with confidence.
