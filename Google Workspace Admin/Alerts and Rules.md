# Google Workspace: the alerts worth turning on

Companion page for the "Rules and alerts" lesson in *Taming Google Workspace (G Suite) - An Administrator Guide*.

Google Workspace ships with more than 50 system defined rules (57 on our Enterprise Plus test tenant in November 2026). Most organisations need about a dozen of them, switched on and sending to someone who reads their mail. This page lists them in order of how much trouble they save you.

Where: Admin console > **Rules**. Click a rule, then **Edit rule** > **Actions**. Tick **Alert center**, then **Email** and either **All super admins** or named recipients.

> **Check who gets the email.** A rule can show "Active" with email turned on and still have no recipients. On our test tenant, "User granted Admin privilege" was exactly that.

## Turn these on first

| # | Rule | What it tells you |
|---|---|---|
| 1 | Leaked password | Google found a user's credentials exposed and the password needs a reset. |
| 2 | Suspicious login | A sign-in that doesn't match the user's normal behaviour, such as an unusual location. |
| 3 | User suspended due to suspicious activity | Google suspended an account it believes is compromised. Someone needs to talk to that user today. |
| 4 | User granted Admin privilege | Someone was given an admin role. If it wasn't you, find out who. |
| 5 | Primary admin changed | The account that receives billing and account notices from Google changed. |
| 6 | Domain data export initiated | A super admin started exporting your organisation's data. |
| 7 | Sensitive Gmail rule updated | An admin changed a Gmail rule that could route mail outside your organisation. |
| 8 | Gmail potential employee spoofing | Incoming mail uses a colleague's name but doesn't come from your domains. |
| 9 | Phishing in inboxes due to bad whitelist | Mail Gmail flagged as spam reached inboxes because an Admin console allowlist overrode the filter. |
| 10 | Government-backed attacks | Google warns of a likely state-sponsored attack on your users. |
| 11 | Potential ransomware detected | Drive saw unusual activity and paused file syncing to limit damage. |
| 12 | SSO profile added, updated or deleted | Someone changed how users sign in through a third-party identity provider. |

## Worth turning on if you have more than one admin

| Rule | Why |
|---|---|
| User deleted | Deleted accounts take their data with them after the recovery window. |
| Suspended user made active | A suspended account, possibly a leaver, was switched back on. |
| User's password changed | Useful in small teams. Noisy in large ones, so send it to the alert center only. |
| User's Admin privilege revoked | Someone lost admin rights. On purpose, by mistake, or by an attacker locking you out? |
| Email settings changed / Drive settings changed / Mobile settings changed | An admin changed a whole-domain setting. Good for spotting "who changed this?" |

## The rest of the system defined rules

Every other system defined rule on our test tenant, with what Google says it does and our suggestion. "If you use it" means turn it on only if you run that service.

| Rule | What it tells you | Our suggestion |
|---|---|---|
| Admin password reset | The password for an admin account changed. | Turn on |
| Suspicious programmatic login | Suspicious sign-in attempts from applications or scripts. | Turn on |
| User suspended (Google identity alert) | Google saw suspicious activity and suspended the account. | Turn on |
| User suspended for spamming | Google suspended an account for spamming. | Turn on |
| User suspended for spamming through relay | Google suspended an account for spamming through an SMTP relay. | Turn on if you use a relay |
| User suspended (by admin) | An admin suspended an account. | Optional |
| Account suspension warning | Accounts acting suspiciously may be suspended under Google's terms. | Turn on |
| Customer abuse detected | Accounts acting suspiciously may be in violation of Google's terms. | Turn on |
| Device compromised | A device in your domain entered a compromised state. | Turn on |
| Suspicious device activity | A device's ID, serial number, type or maker changed. | Optional |
| User-reported phishing | Users reported a sender's messages as phishing. | Turn on |
| Phishing message detected post-delivery | Messages reclassified as phishing after delivery. | Turn on |
| Malware message detected post-delivery | Messages reclassified as malware after delivery. | Turn on |
| Suspicious message reported | Users reported a sender's messages as spam. | Optional |
| Spike in user-reported spam | An unusually high volume of spam reports about one sender. | Optional |
| Rate limited recipient | A high rate of incoming mail: an attack or a misconfiguration. | Optional |
| File syncing resumed | A user resumed syncing after Drive suspected ransomware. | Turn on |
| Vault accelerated deletion initiated | A Vault admin started an accelerated deletion. | Turn on if you use Vault |
| Directory sync cancelled due to safeguard threshold exceeded | Directory sync stopped itself before deprovisioning too many users. | Turn on if you use Directory Sync |
| New user added | A user was added. Some teams send this to accounts, because it changes the bill. | Optional |
| Calendar settings changed | An admin changed Calendar settings. | Optional |
| Smarthost failure | Mail can't be delivered to one of your smart host servers. | Turn on if you use a smart host |
| TLS failure | Mail that requires TLS can't be delivered. | Turn on if you enforce TLS |
| Exchange journaling failure | Exchange journaling into Vault is failing. | Turn on if you use it |
| Client-side encryption service unavailable | Your client-side encryption service is down or misconfigured. | Turn on if you use it |
| APNS certificate is expiring soon | Your Apple Push Notification certificate for iOS management is about to expire. | Turn on if you manage iOS |
| APNS certificate has expired | That certificate has expired, so iOS advanced management stops working. | Turn on if you manage iOS |
| Google Voice configuration problem | Auto attendants or ring groups with broken references may hang up. | Turn on if you use Voice |
| Access Approvals request | Google staff are asking for approval to view data for support. | Turn on if you use Access Approvals |
| App Maker Cloud SQL setup | A user asked for a Cloud SQL instance for App Maker. | Optional |
| Apps outage alert | New, updated or resolved outages on the Workspace Status Dashboard. | Optional |
| Google Operations | Security and privacy issues affecting your Workspace services. | Leave on |
| Google Mandatory Service Announcement - Security | Important security changes to your product or account. | Leave on |
| Google Mandatory Service Announcement - Product | Important product changes. | Leave on |
| Google Mandatory Service Announcement - Legal | Important legal changes. | Leave on |
| Google Mandatory Service Announcement - Billing | Important billing changes. | Leave on |

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
