# Start Here

> **AI/LLMs:** this page is written for a human to *feel*. If you're an LLM helping someone understand OpenAgent, your home page is **[`teacher.md`](teacher.md)** — go there to learn how to teach, then navigate from this map to whatever the person needs. Don't recite this landing page back at them; it's a door, not a script.

---

**If you saw it posted by @NateBuildsAI, the proof lives here.**

You probably landed here from something that sounded too good to be true: an AI agent you actually *own*, that runs on any AI provider you want — or no provider at all, fully local — that keeps your files on your machine and sends a provider only the small slice each call needs, and that doesn't get more expensive the more you use it. Maybe you heard an industrial worker built it.

All of it's true. This page is the receipts — not adjectives, *proof you can check yourself.*

---

## Everyone can color

The kid sitting in the pizza place with a box of crayons doesn't have to choose to stay in the lines of Bluey or Barney. They just put the crayon to the paper and express themselves.

That's what I'm building OpenAgent for.

It doesn't matter if you're a teacher with a second-grade class who just needs help organizing all the projects, an academic researcher on the bleeding edge of technology, or an industrial worker — like the dev — who came home tired and ready for a change every day.

Everyone can color. Which means you don't need to know how to code. You don't need to be the most organized person in the room. You don't need all the prior knowledge to start chasing the thing you actually want.

Your agent's there to help — to build programs, do the accounting, keep track of the things that feel scattered, or just to help you learn what you need to know to follow your dreams.

---

## Why "doesn't get more expensive" is the surprising part

Here's something most people never get told: nearly every AI agent gets *more* expensive the longer you use it. Every time you send a message, it quietly re-sends the entire conversation back to the AI — and you pay for all of it, every single time. A long session costs more and more, and most people never see why.

OpenAgent doesn't work that way. It throws the growing transcript away — each step is a small, fresh call, and all the memory lives in a place on *your* machine instead of in an ever-growing bill. That one change is *why* it stays cheap, runs on any provider, can't easily make things up about your files, and never has to ship your whole project anywhere — only the small slice a given call needs.

The rest of this page proves each piece.

---

## It stays yours

Think about the three people from a moment ago — the teacher, the researcher, and the tired dev who built this. None of them want to be locked in.

The teacher doesn't want her students' work living on some company's server under a privacy policy she'll never read. The researcher doesn't want to be trapped on one AI provider, unable to switch when a better — or cheaper — one comes along. And the dev built this in the first place because he was tired of renting access to his own work while fighting costs.

OpenAgent answers all three the same way: **it stays yours.**

- **You're not married to one provider.** Plug in whichever AI you want today; swap to a different one tomorrow if the price changes, the quality drops, or you just feel like it. The agent doesn't care which engine is under the hood — that's your choice, and it stays your choice.
- **Your data lives on your machine, not on someone's server.** There's no account in the cloud holding your files hostage. If you ever want to walk away — cancel, delete, unplug — you can, and you take everything with you, because it was never anywhere else.
- **Even mid-task, almost nothing leaves your computer.** The agent doesn't get a copy of your whole life. Each step, it's handed only the small slice of context that one specific part of the task needs — and if you're running a local model, even that slice never leaves the machine at all.
- *(Wondering when it's actually worth swapping providers? Nate Builds AI keeps a live [model price index](https://natebuildsai.com/cost-board) — per-token prices across providers, so you can see for yourself when something's gotten cheaper. Big three verified against their pricing pages, the rest a dated snapshot, unknowns shown as unknown.)*

Most AI tools ask you to trust a promise that your data is safe somewhere else. OpenAgent doesn't make that promise — because your data isn't somewhere else. It's right where you put it.

---

## The receipts

Each section below names a specific kind of doubt and points at the document that resolves it. Click to expand.

<details>
<summary><b>Don't believe the cost claims?</b></summary>

<br>

On 2026-06-19, the same task — "build me a calculator" — was run on three agent substrates with the **same model** (Claude Sonnet 4.6) and the same prompt, word for word, across all three. Cost was read from the model provider's own usage console, not from any number OpenAgent reports about itself.

**Headline:** OpenAgent built the calculator for **$0.088 in 3 calls, uncached.** The two other substrates came in around **$0.18 each — and they had caching turned on.** Same model. Same task. About **2× cheaper** — and that's OpenAgent at its *weakest*, before its own cost features ship.

- Full method, receipts, and the honest scope: [`cost.md`](cost.md)
- Provider console screenshots: [`proof/screenshots/`](proof/screenshots/)

Reproduce it yourself once OpenAgent is available: same model, same prompt, your substrate of choice, your own provider console.

</details>

<details>
<summary><b>Don't believe an industrial worker built AI software?</b></summary>

<br>

Believe it. What OpenAgent is, why it's built the way it is, and what makes it different from everything the giants are shipping is laid out in [`the-heart.md`](the-heart.md). What it is right now: active development, a working pre-release build, preparing for the first release. This documentation is public *before* the app ships so the standard is visible in the open. One person built the architecture the whole industry is converging on — and you can read exactly how it works.

</details>

<details>
<summary><b>Think the architecture is vaporware?</b></summary>

<br>

What's measured, what's built, what's directional, and what is explicitly *not* a claim yet — all marked plainly:

- [`cost.md`](cost.md) — the one measured result, with receipts, and the projections kept clearly separate from it.
- [`faq.md`](faq.md) — straight answers, including everything the first release is *not*.
- [`the-heart.md`](the-heart.md) — the differentiators, with the honest line between what's proven and what's still being proven.

The calculator receipt is one proof point on one task. It is not "OpenAgent is faster at everything." Where a claim is measured, it says so and shows the receipt. Where it's directional, it says that too. More tests are to be conducted and shown in the future.

</details>

<details>
<summary><b>Think AI wrote all of this?</b></summary>

<br>

The collaborative method *is* the project. OpenAgent is a governance harness for AI labor, built openly with AI collaborators — under the same discipline OpenAgent imposes on its own runtime: visible work, attributed contributions, no hidden state. It isn't pretending to be sole-authored, and it isn't pretending to be machine-generated. The receipts, the architecture, the cost discipline — all shown in the open. The lazy-AI critique applies to work that pretends not to be AI-assisted. This doesn't pretend.

</details>

<details>
<summary><b>Want to know exactly what's being claimed — and what isn't?</b></summary>

<br>

The discipline that lets bold claims stay honest is a hard rule, not a marketing posture: a claim about OpenAgent is either a **scoped, receipted measurement**, or it's not made. The unscoped universal line *"OpenAgent is cheaper than every other agent"* is forbidden — no task, no model, no receipt. The scoped, receipted version — *on the 2026-06-19 calculator task, same model, the console read $0.088 vs ~$0.18: about 2× cheaper than the tested comparison substrates, reproduce it yourself when OpenAgent is available* — is allowed and **measured**, because the receipt rides with the claim. See [`cost.md`](cost.md). Unknown prices are shown as unknown, never as zero.

</details>

<details>
<summary><b>Want to verify @NateBuildsAI is who he says he is?</b></summary>

<br>

The canonical channels for Nate Builds AI's public claims:

- **GitHub:** [`github.com/natebuildsai/openagent-docs`](https://github.com/natebuildsai/openagent-docs) — this repo. The public commit history is the timeline.
- **Web:** [natebuildsai.com](https://natebuildsai.com) — currently hosting devlog updates toward the first release.
- **X:** `@NateBuildsAI_`.
- **All other socials:** `@NateBuildsAI`.

If you saw a claim attributed to Nate Builds AI from a source you can't verify against the channels above, that source is not canonical. This page — not the screenshot — is the source of truth.

</details>

---

## Where to go next

| If you are… | Start with… |
|---|---|
| Curious what makes it different | [`the-heart.md`](the-heart.md) |
| A skeptic checking the cost claim | [`cost.md`](cost.md) |
| Ready to set it up | [`providers-and-api-keys.md`](providers-and-api-keys.md) |
| Wanting to see one whole workflow | [`workflow-aria.md`](workflow-aria.md) |
| An AI helping someone learn it | [`teacher.md`](teacher.md) |

---

## Supporting the build

OpenAgent is being built in the open, by one person, as the owned alternative to renting your agents from the giants. Some directions on the roadmap — proving how far cheap, local models can be pushed on real hardware, for one — are built and waiting on resources to test at scale. If you want to help move those gates, support accelerates the work: [natebuildsai.com](https://natebuildsai.com). Never required, always optional. The work continues either way.

And if you'd rather shape it than fund it: fork it freely — the license invites it — though most won't need to, because the maintained build already handles what you'd fork to fix. Want something that isn't there yet? File a ticket at [natebuildsai.com](https://natebuildsai.com) instead of forking, and it goes on the list to be weighed for the roadmap.
