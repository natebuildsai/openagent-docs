# Providers & API Keys

This page walks you through connecting an AI provider to OpenAgent so your agent can actually do work. If you've never done this before, it's simpler than it sounds — read through once first; the whole thing takes about ten minutes.

> **The one rule, up front:** an API key goes into OpenAgent's **Settings → Providers** screen (the cog wheel in the bottom-left of the sidebar), or stays on the provider's own website. It does **not** get pasted into a chat — not into an AI assistant, not anywhere else. Your OpenAgent agent will never ask you to paste your key into a conversation.

---

## What an API key even is

An **API key** is a string of characters a provider gives you so their servers know requests are coming from your account — and so they can bill you for what you use. You create it once on the provider's website and paste it into OpenAgent's Settings → Providers screen. After that, your agent uses it quietly in the background. Keep an eye on **both** OpenAgent's own Cost meter **and** your provider's billing page, so you always know what you're spending and how much credit you have left.

It's roughly like a password for one specific app talking to one specific service. It is *not* your account password — it's a separate thing you generate from inside your account, specifically for OpenAgent to use, and you can revoke it any time.

## Why OpenAgent doesn't include the AI

OpenAgent doesn't bundle model access. You bring your own provider account, which means:

- **You pay providers directly** at their published rates. OpenAgent never sits between you and the bill.
- **Your usage is yours.** There's no OpenAgent subscription stacked on top of provider costs.
- **You can switch providers any time,** or use several, without changing anything about OpenAgent.

This is part of how OpenAgent stays a tool you *operate* rather than a service you *rent*.

---

## The three main providers

*(June 2026 snapshot — pricing and model names change; verify on each provider's own pricing page before signing up.)*

- **Anthropic — Claude.** Strong all-around capability and cost-efficiency. Lighter models for simple things, mid models for everyday work, the top model for long, hard problems. → [console.anthropic.com](https://console.anthropic.com/)
- **Google — Gemini.** Often the most affordable per token, especially at high volume. Flash-class models for simple and everyday work, Pro-class for the most demanding tasks. → [aistudio.google.com/apikey](https://aistudio.google.com/apikey)
- **OpenAI — GPT.** Mini models for simple things, standard for everyday work, the top models for long, hard problems. → [platform.openai.com/api-keys](https://platform.openai.com/api-keys)

## Small models vs. large models

The same everyday question — "what's the weather?", "summarize this email", "a good chicken recipe?" — can be answered just as well by a small, nearly-free model as by an expensive flagship. The big models earn their cost on the hard stuff: long documents, careful reasoning, multi-step work.

Choosing a smaller model for routine work and a larger one for hard tasks is a real way to keep costs low. OpenAgent's *direction* is to make that choice automatic — routine work to small models, hard work to large ones, so you pick a provider once and let the agent choose wisely. **That automatic routing is direction, not yet shipped** — for now, OpenAgent uses the model you set on the Providers screen.

---

## Comparing prices: the live model index

Provider prices and model names move constantly — which is why every price on this page is a snapshot you should verify before relying on it. To make that easier, Nate Builds AI keeps a **live model price index**: what each model costs per token, across providers, in one place.

- **Human view:** [natebuildsai.com/cost-board](https://natebuildsai.com/cost-board)
- **Machine view (JSON):** [natebuildsai.com/api/cost-board.json](https://natebuildsai.com/api/cost-board.json)

The big three (Anthropic, OpenAI, Google) are verified against their own pricing pages; the rest are a dated snapshot, and anything without a reliable rate is shown as **unknown — never as $0.** Use it to compare before you pick a provider, or to spot when a model you already use has gotten cheaper somewhere else.

Note what it is and isn't: it's an index of what the *models* cost. That's separate from what *OpenAgent* costs to run a task — which is measured, with receipts, in [`cost.md`](cost.md). Different question, different page.

---

## Step-by-step

*(Key prefixes like `sk-ant-` and `sk-`, signup URLs, and console button names are a June 2026 snapshot. Providers change their consoles and key formats on their own schedule — if a button has moved or a prefix looks different, look for the equivalent on their site; the overall flow is the same.)*

**Anthropic (Claude):**
1. Go to [console.anthropic.com](https://console.anthropic.com/) and sign up or sign in.
2. Add a payment method — Anthropic requires a card on file before generating keys. (Usage can be pennies per task up to larger amounts, billed directly by Anthropic, no monthly fee.)
3. Find **API Keys**, create a new key, and name it "OpenAgent" so you remember what it's for.
4. Copy the key. It starts with `sk-ant-` and is a long string. **You only see the full key once** — if you lose it, make a new one.
5. In OpenAgent, open **Settings → Providers** (cog wheel, bottom-left of the sidebar), add Anthropic, paste the key, and confirm. Done.

**Google (Gemini):**
1. Go to [aistudio.google.com/apikey](https://aistudio.google.com/apikey) and sign in with a Google account (a regular Gmail account works).
2. Click **Create API key.** If asked about a Google Cloud project, the default is fine for personal use.
3. Copy the key (a long string, no particular prefix).
4. In OpenAgent, open **Settings → Providers**, add Google, paste, and confirm. *(Google's pricing varies by use and region; check the Gemini API pricing page before high-volume use.)*

**OpenAI (GPT):**
1. Go to [platform.openai.com/api-keys](https://platform.openai.com/api-keys) and sign up or sign in.
2. Add a payment method (required before keys can be created). Pennies per task, billed directly, no monthly fee.
3. Click **Create new secret key,** name it "OpenAgent."
4. Copy the key. It starts with `sk-` and is a long string — **shown once.**
5. In OpenAgent, open **Settings → Providers**, add OpenAI, paste, and confirm.

---

## If you'd rather not use a cloud provider at all

You can run a model **locally**, on your own machine — no API key, no per-call cost, just the energy your computer uses while it runs. Local models are usually less capable than the flagship cloud models, but they're improving fast and are already strong enough for many everyday tasks. And OpenAgent is built so a local model can punch above its weight — the substrate keeps it honest about your real files, so a smaller model stays more reliable than it would alone. (How far that goes on modest hardware is actively being tested; it's an honest direction, not a benchmark claim.)

Running local needs a reasonably capable computer — a recent GPU helps a lot, though the smaller models don't strictly require one. For most first-time users, the cloud route is the gentler start unless you have a specific reason to go local.

---

## Keeping your key safe

- **Never paste your key into a chat with an AI.** Provider chats (Claude.ai, ChatGPT, Gemini) are not the place for credentials. Your OpenAgent agent never asks for your key in a conversation — it goes in Settings → Providers.
- **Don't share it.** It's tied to your billing. Anyone with the key can spend on your account until you revoke it.
- **If you think it leaked, revoke it.** Every provider's console has a delete/revoke action. Make a new one, paste it into OpenAgent, and you're back in two minutes.
