# Settings & Your Control Surface

This page explains the controls OpenAgent puts in your hands — what each one does and how to use it well. If you're an AI helping someone, this is the page to teach the settings from: explain each control in plain language, and **never route a key, token, or password through chat** — those go in **Settings → Providers** inside the app, never to you.

The throughline of every control below: **you stay in authority.** Nothing consequential happens silently, and everything that happens leaves a record.

---

## Workspaces (scoped access)

OpenAgent is built around **scoped workspaces.** You grant an agent access to a specific folder; it can work there and nowhere else. An agent never gets unrestricted run of your computer, and the app keeps the granted scope visible so you always know what an agent can reach. Want an agent to work somewhere new? You grant it, explicitly.

## Providers (your AI connection)

**Settings → Providers** (the cog wheel, bottom-left of the sidebar) is where you connect OpenAgent to an AI — by pasting in an API key from Anthropic, Google, or OpenAI, or by setting up a local model. **This is the only place a key belongs.** It's never pasted into a chat, never shared with a teaching assistant, never typed anywhere else. Full walkthroughs: [`providers-and-api-keys.md`](providers-and-api-keys.md).

## Agents (picking each agent's model)

Pasting a key in Settings → Providers connects OpenAgent to an AI, but it doesn't yet say *which agent uses which model.* That's set per agent in **Settings → Agents.** Pick an agent's card, open its **Provider Route,** and choose three things in order:

- **Provider** — which AI service this agent calls (e.g. Anthropic).
- **Credential** — which saved key it uses (the name you gave the key when you added it).
- **Model** — the specific model that provider should run (e.g. a lighter model for routine work, a stronger one for hard tasks).

Then **Update the route,** and that agent uses it on its next send. Each agent has its own route — changing one doesn't touch the others. And this screen only sets the *route*; it never touches your saved keys, which stay in Settings → Providers. Every agent's current route, active model, and folder are shown plainly on its card, so you always know what each agent is set to.

## Approvals — and how to read them fast

When an agent wants to do something consequential, it asks first, with an **approval card** written in a plain sentence. Related actions are grouped into bounded **bundles** so you're not nagged for every tiny step — but if the scope changes materially, the agent has to ask again, and public or destructive actions are never folded into a routine approval.

Approval cards are **color-coded by stakes**, so you can read the risk before you read the words:

- **Green** — a read, or a tiny safe action.
- **Yellow** — a write: create or update a file.
- **Red** — remove, delete, run a command, or anything that leaves your machine.

## Agent status, at a glance

Next to each agent's name, a small status dot tells you what it's doing without opening the conversation:

- **Green** — working.
- **Yellow** — waiting on your approval.
- **White** — idle.
- **Red** — hit an error.

## Stop

A **Stop** control lets you halt active work at safe boundaries. While an agent is working and your message box is empty, the Send button becomes a Stop button — press it to halt the run. You get a summary of what was saved up to that point, and provider output that arrives *after* you stop is not acted on or written into future context. Clean stopping is part of the first-release standard — the design goal is that you can always halt, keep what was saved, and never have late output applied behind your back.

## Queued messages

You don't have to stop an agent to steer it. Type a message while it's working and it gets **queued** — delivered at the next safe checkpoint as guidance, without interrupting the current step. (Empty box + working agent = the button is Stop; box with text + working agent = the button is Send-for-queue. The two are never the same click.)

## Fast Mode

**Fast Mode** is optional and off by default. It reduces approval prompts for actions *inside an agent's already-granted scope* — it grants no new access, never turns off receipts, and still requires approval for anything public or destructive. It's a convenience within bounds you already set, not a loosening of the bounds.

## Receipts

After an approved action, OpenAgent records a **receipt** of what actually happened — the record of the action, not the agent's description of its intent. The explanation is not the record. This is what makes an agent's work auditable after the fact.

## Generated Programs

When an agent builds something runnable, OpenAgent registers it as a **Program** you can reopen, re-run, pin to a quick launcher, or (with your approval) add to your desktop. Desktop placement is governed like everything else: the agent proposes, OpenAgent shows an approval card, you approve, and it's receipted.

## Plugins

Plugins add capability *on top of* the OpenAgent substrate. Note one boundary that's easy to miss: **your provider connection is substrate, not a plugin** — it's part of the foundation, not something you install. Plugin categories: Surface, Personality, Appearance Studio, Program, Expertise, Internal Worker, External Worker, and Voice (planned, not in the first release). The full taxonomy with examples is in [`faq.md`](faq.md).

---

## A note for AI teachers using this page

Teach these controls as *the user's instruments* — every one of them exists to keep the person in authority. When someone is nervous about letting an AI act on their machine, this page is the reassurance: scoped access, color-coded approvals, a Stop button, and an honest receipt of everything done. Don't claim a control does more than it does, and if something isn't wired yet, say so plainly rather than implying it's live.
