# Inbound Intel

Every new inbound lead, researched before the first call.

I built this in 2026 for the SDR team I led at JumpCloud, covering APAC and EMEA. A new lead comes in. Before anyone picks up the phone, Inbound Intel has already looked up the person, the company, its size and any recent news. It works out whether this is a partner (an MSP, a company that manages IT for other businesses) or a direct buyer, because those go to different teams. Then it finds the one hook worth opening with, drafts the first email, and gives a verdict the rep can act on in seconds. The whole batch goes back into Salesforce.

## Why it exists

Inbound leads go cold fast. A good SDR spends 15 to 20 minutes researching each one properly, and on a busy day nobody has that time. So reps either call blind or send a generic email. Both waste a lead that raised its hand.

## What it does for each lead

1. **Reads the signal.** Which form did they fill? What did they search for? A "Contact Sales" form after searching a competitor's name is a very different lead from a free trial signup.
2. **Identifies the person and the company.** Title, tenure, location, company size, industry, funding.
3. **Checks fit.** Partner or direct buyer, which segment, and whether it fits the ideal customer at all.
4. **Finds the hook.** Job posts, careers pages, news and the person's own posts. The best hooks come from what the company is hiring for, because job posts name the tools they use today.
5. **Writes it up.** A verdict (qualify, nurture or reject), the hook, a short first email, and the sources behind every claim.

## The rules that make it trustworthy

* **Never guess an email or phone number.** A field counts as verified only if a data tool returned it. Everything else is marked unverified.
* **Every claim needs a source.** If the hook can't be traced to a real page, it isn't used.
* **"Conflicting" is a valid answer.** When two sources disagree, it says so instead of picking one.
* **Research only.** It never sends an email or writes to the CRM on its own. A person reviews first.

## How it is built

It is an agent (an AI that works through steps on its own), run in Claude Code. It searches the web with Exa and checks contact details against Apollo, LeadIQ and Clay. Leads go in as a spreadsheet export from Salesforce and come back as an enriched sheet, one row per lead. Several leads are researched at once by parallel helper agents.

See [AGENT.md](AGENT.md) for the full instructions the agent follows, and [example/](example/) for a worked lead.

## A note on data

This public version contains no real leads and no company material. The example uses a made up person and company.

Built by [Vandana Agarwal Nik](https://vandanaagarwal.in), with Claude.
