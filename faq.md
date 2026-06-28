# FAQ

## Is OpenAgent released?

No. OpenAgent is in active development as a working pre-release build. This repo is public *before* release so the standard it's being built to meet is visible in the open.

## What is OpenAgent?

A desktop-native, user-orchestrated AI workstation: you create agents, they come scoped to a workspace folder, connect a provider (or run local), and watch them do governed local work — building programs, editing files, running commands, adaptable to most workflows — with approvals, receipts, and visible cost. One framing: it's a **governance harness for AI labor** — it makes an agent's work structurally honest about what it did, what it cost, and what it can't claim. Why it's built this way: [`the-heart.md`](the-heart.md).

## What's the main thing it does?

You ask an agent to build a program, and you watch it happen through visible, approval-gated steps. The agent reasons and writes code; OpenAgent asks before it writes; the result becomes a runnable Program you can open, run, and ask to change. In the pre-release build this was proven by building a working calculator from an ordinary chat request — measured cost published with receipts ([`cost.md`](cost.md)). More will be proven and posted there.

## What's the difference between "Chat," the "Workspace" tab, and "Agent's Files"?

Three different things, easy to mix up:

- **Chat** is where you *talk* to the agent and ask for work. You reach it by selecting the agent, which opens its Chat view.
- The **Workspace** is where you *watch* the work happen — files being written, commands running, build output, approvals — with the active project's files alongside. You switch to it using the **Chat | Workspace** tabs at the top of the agent's view.
- **Agent's Files** is the *folder* you grant an agent access to — the scope of what that agent can reach. It lives in the left sidebar under the **AGENT'S FILES** heading, listed per agent (for example, *Bob's Files*).

Chat and the Workspace are two views of the same task; **Agent's Files** is the scoped folder that task runs in.

## What happens to something an agent builds?

It's registered as a **Program** you can reopen, re-run, pin to a quick launcher, or (with your approval) add to your desktop. Desktop placement is governed: the agent proposes, you approve, it's receipted.

Main programs can be found in the bottom left-hand corner of the sidebar where it says "Home Programs". There is a little plus sign to the right of home programs, where you can access built programs by your agents.

## Does OpenAgent include AI model access?

No — it's provider-flexible, not provider-included. Remote routes usually need your own provider account, key, and billing. Local routes need your hardware and setup. See [`providers-and-api-keys.md`](providers-and-api-keys.md).

## Should I paste an API key into an AI chat?

**No.** Keys, tokens, passwords, and billing details belong only in OpenAgent's Providers screen or the provider's own site — never in a chat.

## What should I try first?

Open OpenAgent, choose a provider route, create one agent, and ask it to build something small, such as a  budget tracker program or a file organizer. Watch the work in the Workspace, approve the governed writes, open and run the resulting Program, and look at the receipt and cost records in the agent's files.

## Does my agent learn about me over time?

That's the direction, through **memory, not plugins.** You teach your agent in plain words; it files what matters into per-topic notes *in your workspace, on your machine* — your agent is the steward of that memory, not its owner — and uses those notes to be more helpful over time. Because the always-on part stays small and the actual knowledge is loaded selectively, what your agent knows about you doesn't bloat what it costs to use. This is the intended shape of the first release, described honestly as direction.

## Does OpenAgent need a giant context window?

No — it deliberately doesn't depend on a long-context provider mode. One message may produce one model call or many. The whole design point is that long-task continuity lives in task records, workspace state, approvals, and receipts — *not* in an ever-growing transcript. ([`the-heart.md`](the-heart.md) explains why that matters.)

## Does it prove cheaper AI workflows?

It doesn't *claim* to save money; it *measures* cost transparently. One single-task measurement is published with receipts: same model, a calculator build, about half the cost of two other substrates. That's a measured single-task result with stated scope — [`cost.md`](cost.md). Larger ratios anywhere are projections, not measurements.

More testing will be published over time at [`cost.md`](cost.md).

## Can it publish to GitHub?

Governed GitHub publishing is part of the first release: an agent can publish or update a repo under approval, with a diff/summary and a public/private warning shown first, and a receipt afterward. Publishing to a public repo is the highest-stakes action class. This docs repo is intended to be maintained that way — see [`workflow-aria.md`](workflow-aria.md).

## Are provider connections plugins?

No. Provider connections are **substrate** — part of the foundation. Plugins ride on top.

## What are the plugin categories?

1. Surface Plugins
Surface Plugins = ways humans/systems reach an agent

Examples:
Telegram, Discord, Slack, future email/chat surfaces

2. Personality Plugins
Personality Plugins = response style / presentation overlays

Examples:
Sherlock, Dracula

3. Appearance Studio
Appearance Studio = advanced visual customization surface

Portable unit:
Display Packages (Full Appearance Customization )

Examples:
theme tokens, saved visual setups, future static backgrounds, future live backgrounds / Terrarium

4. Program Plugins
Program Plugins = agent-native programs made to work directly inside OpenAgent

Examples:
Notes, Mail, Sheets, Docs, Slides, Calculator, Dayboard.

5. Expertise Plugins
Expertise Plugins = user-facing skill/domain bundles that make the agent smarter at a subject or app

Examples:
Excel Expert, Word Expert, Outlook Expert, PowerPoint Expert.

Important:
They may bundle tied Internal Worker capabilities, but those capabilities still require activation/permission.

6. Internal Worker Plugins
Internal Worker Plugins = concrete capability units/tools inside OpenAgent

Examples:
read .xlsx, write .docx, parse PDF, convert CSV, send email with approval, publish to GitHub with approval

7. External Worker Plugins
External Worker Plugins = outside agents/services OpenAgent delegates work to.

Examples:
Codex, Claude Code.

8. Voice (planned, not in the first release)
Voice plug-ins = text-to-speech 

Examples:
Generic AI assistant, custom-made voices. 

## Can it use local models?

Yes — the first release includes at least one local route at first-run quality. Local routes avoid per-call provider billing but depend on your hardware and setup.

## Can an agent access my whole computer?

No. OpenAgent is built around scoped workspaces and access you grant explicitly.

## Is it fully autonomous?

No. The goal is governed capability under your control, not silent autonomy. Consequential actions are approval-gated, and a Stop control lets you halt active work at safe boundaries.

## What's the website status?

Under construction — currently hosting devlog updates toward the first release at [natebuildsai.com](https://natebuildsai.com). Accounts, plugin upload, signing, update downloads, and pricing endpoints are first-release direction, not yet fully available.

## What are external AI chats good for, then?

Explaining these docs, workshopping ideas, troubleshooting, and walking you through setup. The in-app OpenAgent agent is the real teacher *inside* OpenAgent, and OpenAgent itself is where the governed work actually happens. An outside chat can explain it; it can't *be* it.
