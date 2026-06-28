# One Whole Workflow: Aria Updates a Repo

This is one complete OpenAgent workflow, start to finish, so you can see how the pieces — scope, request, approval, governed action, receipt — fit together in practice. It's the workflow this documentation repo is intended to be maintained through.

**Aria** is an OpenAgent agent. In this example she's routed through Google's Gemini — but that's just an example. OpenAgent is provider-agnostic; Aria could run on any provider you plug in.

---

## Step 1 — Scope the workspace

The user grants Aria access to **the docs repo only.** Aria does not get unrestricted access to the rest of the computer — she can see and work in exactly the folder she was granted, and nothing else. You can always see what scope an agent has been given.

## Step 2 — Ask for the work

A plain request, in normal language:

```
Aria, read the docs repo, refresh the cost page with the latest receipt,
and prepare the files for publishing.
```

## Step 3 — Aria asks for approval before she writes or publishes

Before changing anything, Aria proposes a bounded **approval bundle** — a clear summary of exactly what she's about to do:

```
Approval request: Documentation update bundle
  In scope:     cost.md, README.md
  Actions:      update the cost receipt, run link checks, prepare to publish
  Not included: deleting files, changing the license, publishing without a final OK
```

You read it, and you approve or deny. If the work changes materially partway through, Aria has to ask again. And **publishing is never silently folded into the write approval** — sending something out to the world is a separate, public action that carries its own, higher-stakes approval.

## Step 4 — Governed publishing

Publishing to a public repo is treated as the highest-stakes action class — effectively worldwide and hard to undo — so before anything leaves your machine, OpenAgent shows you a review surface: the repo, the changed files, a summary and a diff, and a clear public/private warning. Only after you approve does OpenAgent write and publish. The approval card for a public action like this is visually marked as public/external, so you can read the stakes before you even read the words.

## Step 5 — The receipt

After the action, OpenAgent records a receipt of what actually happened — not the agent's *explanation* of what it meant to do, but the record of what was done:

```
agent:        Aria (Gemini route)
workspace:    docs repo (scoped)
approved:     documentation update bundle
files changed: cost.md, README.md
action:        published to repo
cost/usage:    recorded
timestamp:     recorded
```

---

## What this example shows — and what it doesn't

It shows the spine of every OpenAgent workflow: **scoped access, a plain request, an approval you control, a governed action, and an honest receipt.** The agent reasons and proposes; you approve; OpenAgent acts; the record tells the truth about what happened.

It does **not** mean OpenAgent is already publicly released, that every publishing feature is finished, or that agents ever publish without your approval. None of those are true. This is the first-release standard, shown as a workflow.
