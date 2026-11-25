# Google Workspace: the alerts worth turning on

Companion page for the "Rules and alerts" lesson in *Taming Google Workspace (G Suite) - An Administrator Guide*.

Google Workspace ships with about 50 system defined rules. Most organisations need about a dozen of them, switched on and sending to someone who reads their mail. This page lists them in order of how much trouble they save you.

Where: Admin console > **Rules**. Click a rule, then **Edit rule** > **Actions**. Tick **Alert center**, then **Email** and either **All super admins** or named recipients.

> **Check who gets the email.** A rule can show "Active" with email turned on and still have no recipients. On our test tenant, "User granted Admin privilege" was exactly that.

Default state below is what our Enterprise Plus test tenant showed in November 2026. Yours may differ.

## Turn these on first

| # | Rule | What it tells you | Default on our tenant |
|---|---|---|---|
| 1 | Leaked password | Google found a user's credentials exposed and the password needs a reset. | Active |
| 2 | Suspicious login | A sign-in that doesn't match the user's normal behaviour, such as an unusual location. | Active |
| 3 | User suspended due to suspicious activity | Google suspended an account it believes is compromised. Someone needs to talk to that user today. | Active |
| 4 | User granted Admin privilege | Someone was given an admin role. If it wasn't you, find out who. | **Inactive** |
| 5 | Primary admin changed | The account that receives billing and account notices from Google changed. | Active |
| 6 | Domain data export initiated | A super admin started exporting your organisation's data. | Active |
| 7 | Sensitive Gmail rule updated | An admin changed a Gmail rule that could route mail outside your organisation. | Active |
| 8 | Gmail potential employee spoofing | Incoming mail uses a colleague's name but doesn't come from your domains. | Active |
| 9 | Phishing in inboxes due to bad whitelist | Mail Gmail flagged as spam reached inboxes because an Admin console allowlist overrode the filter. | Active |
| 10 | Government-backed attacks | Google warns of a likely state-sponsored attack on your users. | Active |
| 11 | Potential ransomware detected | Drive saw unusual activity and paused file syncing to limit damage. | Active |
| 12 | SSO profile added, updated or deleted | Someone changed how users sign in through a third-party identity provider. | Active |

## Worth turning on if you have more than one admin

| Rule | Why | Default on our tenant |
|---|---|---|
| User deleted | Deleted accounts take their data with them after the recovery window. | Inactive |
| Suspended user made active | A suspended account, possibly a leaver, was switched back on. | Inactive |
| User's password changed | Useful in small teams. Noisy in large ones, so send it to the alert center only. | Inactive |
| Email settings changed / Drive settings changed / Mobile settings changed | An admin changed a whole-domain setting. Good for spotting "who changed this?" | Inactive |

## One activity rule to build yourself

System rules can't watch everything. This one works on every plan:

- **Create rule > Activity**
- Data source: **Drive log events**
- Condition: Event **is** "Change document visibility"
- Actions: **Alert center**. Add email only once you know how often it fires (the preview chart shows the past month).
- Status: start on **Monitor** to collect logs without alerting, then switch to **Active**.

New rules and changes can take **up to 24 hours** to take effect.

## What your plan includes

| Feature | Plans |
|---|---|
| System defined rules, basic activity rules | All Workspace plans |
| Advanced activity rules (thresholds, actions, the investigation tool) | Enterprise Standard and Plus, Education Plus, Frontline Plus, Enterprise Essentials Plus, Cloud Identity Premium, Chrome Enterprise Premium |
| Trust rules (Drive sharing) | Enterprise Standard and Plus, Education Standard and Plus, Frontline Plus, Enterprise Essentials Plus |
| Data protection rules | Enterprise Standard and Plus, Education Fundamentals, Standard and Plus, Frontline Standard and Plus, Enterprise Essentials Plus |

Source: Google Workspace Admin Help, pages last updated 10 November 2026. Plans change; check Google's page for your edition.

## Further reading
- [Create and manage activity rules](https://knowledge.workspace.google.com/admin/security/create-and-manage-activity-rules)
- [Trust rules for Drive sharing](https://knowledge.workspace.google.com/admin/security/create-and-manage-trust-rules-for-drive-sharing)
- [Plan data protection rules](https://knowledge.workspace.google.com/admin/security/plan-data-protection-rules)

## Courses
- [Taming Google Workspace (G Suite) - An Administrator Guide](https://taming.tech/GoogleWorkspaceAdmin)
- [Taming GAM7 (GAMADV-XTD3) - A Google Workspace Admin Guide](https://taming.tech/GAMCourse)
- [Complete Google Workspace (G Suite), Beginner - Advanced](https://taming.tech/TheCompleteWorkspaceCourse)
- [Taming Regular Expressions (REGEX) - Complete Guide to Regex](https://taming.tech/TamingRegexCourse)
