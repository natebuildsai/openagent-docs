# Cost

**Last tested: 2026-06-19.** This is a living document — OpenAgent's cost behavior is re-measured as new features ship and new task shapes are tested, and this page is updated with each new receipt. The date above is when the result below was measured. If you're reading this much later, check the repo history for newer measurements.

OpenAgent does not *claim* to save money. It *measures* cost transparently, as a first-class feature, and publishes what the provider's own usage console recorded — with the receipts attached so you can reproduce it. That distinction matters: everything below is a measurement with a receipt, not a marketing number.

---

## The measured result (single task, 2026-06-19)

The same task — build a working calculator — was run on three agent substrates with the **same model** (Claude Sonnet 4.6) and the **same prompt, word for word, across all three** (*"Hey Bob! Will you build me a calculator?"* — "Bob" being the example agent name; the addressing was identical on every run, so it's a controlled constant, not a variable). Cost was read from the **model provider's own usage console**, not from any number OpenAgent reports about itself.

| Substrate | Cost | API calls | Caching |
|---|---|---|---|
| **OpenAgent** | **$0.088** | 3 | uncached |
| Other substrate A | $0.183 | 4 (one unsolicited) | cached |
| Other substrate B | $0.175 | 4 | cached |

On this task, the provider console recorded roughly **half the cost** for the OpenAgent run versus the two other substrates — about **2× cheaper.**

**This is the conservative case.** OpenAgent's own prompt caching had not yet shipped when this was measured, while both comparison substrates ran *with* caching enabled. In other words: this is OpenAgent at its weakest — no caching, pure raw input — against the others at their cached baseline, and it was still about 2× cheaper. Same model, same per-token rate, same task. The gap is what the different architectures do with the same tokens at the same price.

## The receipts

The model provider's own usage console is the source of every number above. The screenshots are in [`proof/screenshots/`](proof/screenshots/).

**OpenAgent — 3 calls, uncached:**

| Request | Input tokens | Output tokens |
|---|---|---|
| call 1 | 7,125 | 158 |
| call 2 | 4,702 | 2,358 |
| call 3 | 4,627 | 54 |

The per-request cache breakdowns confirm **0 cache read and 0 cache write on every call** — the $0.088 was achieved on pure uncached input. The comparison substrates' ~$0.18 figures *include* their cache work; uncached, they would be higher. Their console screenshots (showing the cached baseline) are in the `substrate-a/` and `substrate-b/` folders alongside OpenAgent's.

## Reproduce it yourself

Run the same minimal calculator prompt, on the same model, across whatever substrates you want to compare. Then read each one's cost from the model provider's usage console for that window. Match the model, the prompt, and the task, and compare the provider-reported cost. The result is in the receipts, not in anyone's marketing.

---

## Beyond the measured task — *not yet measured*

The architecture is built so the gap should *widen* as work scales — a growing-transcript agent re-buys its whole history every step, while OpenAgent carries only small per-task state, so the longer the session and the more tasks involved, the further the two curves separate. That's the *direction* the design points, but the specific multipliers are **not measured yet**, so you won't find them quoted here as numbers. The only figure on this page with a receipt is the $0.088 single-task result above. **A projected ratio never headlines.** When the larger-scale tests are run, their numbers will appear here — dated, with receipts — and not a moment before. If you ever see a big multiplier presented as proven, that's the line being crossed, and this page is where you check it.

---

## How OpenAgent treats price in general

- **Unknown cost is shown as unknown — never as zero.** If OpenAgent doesn't have a reliable price for a route, it says so rather than pretending it's free.
- **You pay your provider directly,** at their published rates. OpenAgent doesn't sit between you and the bill, and there's no subscription on top.
- **Local routes** avoid per-call provider billing entirely — the cost is just the energy your computer uses. They depend on your hardware and setup.
- **Measured and projected live in separate rooms.** Every measured claim ships bound to its receipt. Projections are always labeled as projections.

## A separate thing: the model price index

Everything above is about what *OpenAgent* cost on a measured task. That is a different question from what the *models themselves* cost — and Nate Builds AI keeps a live, honest index of the latter: the **model price index** at [natebuildsai.com/cost-board](https://natebuildsai.com/cost-board) (machine view: [`/api/cost-board.json`](https://natebuildsai.com/api/cost-board.json)). It lists per-token prices across providers — the big three verified against their own pricing pages, the rest a dated snapshot, unknowns shown as unknown rather than zero.

Keep the two separate in your head: *this* page is OpenAgent's measured cost on a task; the *index* is the going rate for the models you might plug in. They live in different rooms on purpose, and neither one is ever quoted as the other.

## A separate thing: the model price index

Everything above is about what *OpenAgent* cost on a measured task. That is a different question from what the *models themselves* cost — and Nate Builds AI keeps a live, honest index of the latter: the **model price index** at [natebuildsai.com/cost-board](https://natebuildsai.com/cost-board) (machine view: [`/api/cost-board.json`](https://natebuildsai.com/api/cost-board.json)). It lists per-token prices across providers — the big three verified against their own pricing pages, the rest a dated snapshot, unknowns shown as unknown rather than zero.

Keep the two separate in your head: *this* page is OpenAgent's measured cost on a task; the *index* is the going rate for the models you might plug in. They live in different rooms on purpose, and neither one is ever quoted as the other.

## Scope and honesty

This is a single-task measurement (n = 1): one task shape, one model, OpenAgent at essentially v0 — prompt caching not yet shipped, no reset/resume policy on the date for the snapshot above. It demonstrates what the OpenAgent run produced on the provider's own console for this task. It is **not** a guarantee of savings for every user, task, or model. Broader validation continues as more substrates and task shapes are tested — and lands here, dated, when it does.

## The road ahead
More tests are underway, comparing cost across many calls and different task shapes. Each will be published here with its receipts — and reproducible, so anybody can run the tests themselves.
