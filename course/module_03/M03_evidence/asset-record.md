**ASSET RECORD** fs02
**Exported** Tue 15 Sep 2026 14:40 by IT Operations
**Record owner** Infrastructure

---

| Field | Value |
|---|---|
| Hostname | fs02 |
| Role | Departmental file share, Finance and Legal |
| Backup | Nightly snapshot, 02:00, 14-day retention |
| Last snapshot verified | Fri 11 Sep 2026 |
| Share recycle bin | Disabled on this share. Disabled at Finance's request, 2024, "kept filling up" |
| Audit policy | Object access auditing. See change below |

## Change history, last 30 days

| Change | Date | Detail |
|---|---|---|
| CHG-2211 | Mon 14 Sep 2026 | Audit subsystem reconfiguration. Object access auditing disabled for the duration. Approved window 09:00 to 13:00. Executed by `svc-config` |
| CHG-2198 | Thu 10 Sep 2026 | `svc-archive` scheduled task retention window changed from 36 months to 12 months |

## Access, `\finance\Q3-working`

| Principal | Rights |
|---|---|
| `DOMAIN\finance-team` | Modify. Four members: dokafor, mreyes, tlin, pashford |
| `DOMAIN\svc-archive` | Modify, scoped to `\finance\Q3-archive` by a separate ACL |
| `DOMAIN\contractors-legal` | Read. One member: jcontractor |
| `DOMAIN\Domain Admins` | Full |
