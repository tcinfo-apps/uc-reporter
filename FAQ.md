# UC Reporter Beta — FAQ

Short answers to what testers ask most. Missing something? Ask on Telegram
(link in your welcome email) or email **traincollabinfo@gmail.com**.

## Getting started

**What is UC Reporter?**
A Windows app that connects to your Cisco Unified Communications estate (CUCM,
Unity Connection, IM&P, UCCX, Expressway, CUBE/ISR), collects inventory,
resource, and health data, and produces a clean, customer-ready **maintenance
report** — organised Region → Location → Cluster and exportable to PDF.

**What do I need to run it?**
A Windows 10/11 machine, network access to your Cisco devices, and **read-only**
credentials for each platform. That's it — no server, no cloud account.

**Do I need administrator rights to install?**
No. The installer is **per-user** — it installs for your account only.

**Windows shows an "unknown publisher" / SmartScreen warning. Is that a problem?**
No — it's expected for the beta. The build isn't code-signed yet, so Windows
shows a blue "Windows protected your PC" screen. Click **More info → Run
anyway**. Production releases will be signed and won't show this.

**Will I see a console or command window?**
No. The engine runs invisibly in the background — you'll only ever see the
UC Reporter window.

## Security & privacy

**Is my data safe? Where does it go?**
It stays on your machine. UC Reporter is **local-only and offline** — it talks to
your Cisco devices over your own network and **sends nothing to us or anyone
else**. No cloud account, no telemetry. Everything lives under
`%LOCALAPPDATA%\UCReporter\` and you can delete it anytime.

**What happens to the device credentials I enter?**
They're held **in memory only** for the duration of a collection run and are
**never written to disk**.

**Does the app send my feedback automatically?**
No. There's **no feedback tool inside the app**. Feedback goes through the
separate Google Form only when *you* choose to fill it in — so nothing about your
estate leaves your machine unless you decide to share it.

**Do you see my reports?**
No. Reports are generated and stored on your machine. We only see what you
choose to share (e.g. a screenshot in a feedback submission).

## Licensing

**How long is my license valid?**
30 days from issue. Want more time? Just ask — we'll send a fresh license file
(a single small file, no reinstall).

**What happens when it expires?**
The app shows a "license expired" screen instead of the main window. Your data
stays on your machine, untouched.

**Can I reinstall to reset the expiry?**
No. The expiry is a fixed date baked into your signed license, so reinstalling or
re-using the same file won't extend it. If you need more time, we issue a new
license — that's the intended way.

**Can I run it on more than one machine?**
Your license is personal to you. Need it on a second machine? Just ask — please
don't share your license file (it's tied to you, and your reports are watermarked
with your name).

**The app says "License required" — what do I do?**
Make sure your `.uclic` file is at `%LOCALAPPDATA%\UCReporter\license.uclic` and
restart the app. Don't edit the file (any change invalidates its signature). If
it still fails, contact us.

## Using it

**Which Cisco platforms are supported?**
CUCM (AXL + serviceability), Unity Connection (CUPI), IM&P, UCCX, Expressway, and
CUBE/ISR gateways (SSH) — over their standard read interfaces.

**How do I organise a multi-site estate?**
Model it as **Region → Location → Cluster** under **Inventory**: add regions
(e.g. EMEA/US/APAC), locations (sites) under them, then clusters placed either at
the region level (centralized) or under a specific location.

**How do I run a collection?**
**New collection → pick cluster(s) → enter read credentials when prompted →
start.** Watch progress per host.

**How do I get the report out?**
**Reports → select the finished run → Export** to PDF (or copy the Markdown).
The report is watermarked with your licensee name — that's expected for the beta.

**Why is my report watermarked?**
Every beta report carries your name so a leaked copy is traceable. It goes away
for production.

## Troubleshooting

**A collection failed against a platform — what should I capture?**
The platform type (CUCM/CUC/UCCX/…), what you entered, and the on-screen error.
Send it via the feedback form — and please **redact** live hostnames/IPs/creds.

**I forgot my password.**
Use your one-time **recovery code** from first-run setup. Lost that too? `SETUP.md`
Appendix A explains how to reset the local account (keep your license file).

**The app won't start / seems stuck on "starting…".**
Give it a few seconds on first launch (the local engine is booting). If it
persists, fully close it (Task Manager → end `uc-reporter-desktop` and
`uc-reporter-sidecar`) and relaunch. Still stuck? Tell us via the form.

**Where is my data stored?**
Under `%LOCALAPPDATA%\UCReporter\` — license, local login, inventory, reports,
knowledge base, and a local audit log. Nothing leaves your machine.

## Feedback & roadmap

**How do I report a bug or suggest something?**
The **beta feedback & ideas form** (link in your welcome email and `SETUP.md §7`).
One form covers bugs, feedback, and ideas.

**Is this production-ready?**
It's a **pre-release beta** — expect rough edges, and please don't point it at
anything you can't afford to have hiccups against. Your feedback is what makes it
better.

**What's coming next?**
See the public roadmap:
`https://github.com/tcinfo-apps/uc-reporter/blob/main/ROADMAP.md`.
