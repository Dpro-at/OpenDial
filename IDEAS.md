# IDEAS.md — the parking lot

Everything discussed but not in v1 goes here.

This file matters more than it looks. Every good idea that arrives mid-build gets
written down here **instead of into the code**. It is the mechanism that gets this
project finished. The ideas will still be here when they are needed, and they will
not distract now.

**The one rule:** nothing gets built until the first call works.
Not the UI. Not the rules engine. Not the second provider. Not MCP.

---

## How to add an entry

Append to the right section with a one-line description and, where it matters, the
reason it is deferred. No estimates, no priorities — this is a list, not a roadmap.
Items graduate out of this file only when an earlier milestone is finished.

---

## Deferred from the specification

These are already described in `docs/SPEC.md` and scheduled, just not now.

- **Provider abstraction** (§B3) — Milestone 1. One implementation each of STT / LLM /
  TTS first; the second implementation comes only after the first call works.
- **Additional providers** (§B3) — Ollama, local Whisper, Piper, Cartesia. Many will
  arrive as community pull requests.
- **PostgreSQL persistence** (§B5) — Milestone 2.
- **Routing rules engine** (§A6.5, §B11) — Milestone 3.
- **Web dashboard** (§A6) — Milestone 4, starting with the call detail screen.
- **Webhooks and public REST API** (§B6) — Milestone 5.
- **Built-in tools** (§B7) — Milestone 6.
- **Live intervention: whisper, then takeover** (§A6.7) — Milestone 7. Whisper first:
  highest value, lowest complexity.
- **Health checks and alerting** (§B8) — Milestone 8.
- **Docker packaging** (§B10) — Milestone 9.
- **MCP server** (§B11) — Milestone 10. A thin layer over the REST API, with hard
  limits: an external model that can start real calls spends real money.
- **Buying phone numbers in-app** (§A6.1) — v1 connects a number the user already
  bought, or an existing SIP extension. Provisioning from inside the UI comes later.
- **`NumberProvider` interface** — *promoted out of this file on 2026-08-17.* Now
  specified in §B3.1, because Milestone 0 depends on it: the first call arrives on a
  provider number rather than a PBX extension. The interface itself is still written
  at Milestone 1 with the other provider interfaces; what changed is that the shape
  and the ordering of its implementations are now decided rather than deferred.
- **Knowledge sources and embeddings** (§A6.6, §B5) — `search_knowledge` is expected
  to become the most used tool, but not before the call works.
- **Contacts and per-caller history** (§A6.9).
- **Arabic RTL layout** (§A4) — the locale files exist from day one; the mirrored
  layout work lands with the UI.

---

## Distribution

- **n8n community node for OpenDial** — one of the strongest distribution channels
  available; a large community actively looks for new nodes.
- **A 30-second video of a real call** — carries more weight than any README section.
- **Launches on Hacker News and r/selfhosted** — an excellent project nobody finds is
  a dead project.
- **Importable n8n workflow examples** under `examples/workflows/`.

---

## Open questions

- **Trademark position on "OpenDial"** (EUIPO classes 9 and 42). An older academic
  dialogue-systems framework shares the name. Confirm before committing to a logo.
  *Not legal advice.*
- ~~**How SIP is handled in Milestone 0**~~ — **answered 2026-08-17: LiveKit Cloud
  SIP.** Once the first call arrives on a provider number rather than an on-premises
  PBX, the audio crosses the internet regardless, and the "same LAN, no NAT" objection
  to LiveKit Cloud no longer applies. See `CLAUDE.md`. The self-hosted media path is
  not abandoned — it returns at Milestone 9.
- **Does a forwarded call carry the original caller's number?** Carrier-dependent, and
  Milestone 3's routing rules are worthless if the answer is no. Measured on the first
  forwarded call in Milestone 0 rather than discussed here.

---

## Ideas raised during the build

*(Add new entries below. Date them.)*

**2026-08-17 — Selling numbers to customers (OpenDial Cloud only).**
Dpro GmbH holds numbers at Twilio and assigns them to customers, who then forward
their existing line to the assigned number on no-answer after a set number of seconds.
Onboarding collapses to one button instead of a provider account, a document upload
and a trunk configuration.

Deferred, and deliberately so:

- It is a compliance function before it is a feature — per-country regulatory bundles,
  in-country addresses for geographic numbers, emergency-service questions where the
  number fronts somebody's main line, and being holder of record when a customer ports
  away. Detail in §B3.1.
- The margin is negligible. A number is €1–3 per month against TTS at €0.06–0.10 per
  minute, so this is a conversion improvement, not a revenue line. Revenue comes from
  the subscription and the per-minute AI.
- It must never enter the open edition. What lands in the repository is a generic
  provider into which a user pastes their own credentials.

What was *not* deferred, because it is cheap now and expensive later: `numbers.owner`,
`numbers.provider_account_ref`, and per-call usage metering — all in §B5.

**2026-08-17 — Onboarding cost disclosure.**
Whoever forwards a call usually pays for the forwarded leg in the EU. A surprise on
the first invoice costs more trust than it saves in setup friction, so this belongs in
the onboarding copy, not in a support article.

**2026-08-20 — Redraw the logo as clean vector, and draw a 16 px icon.**
Everything in `docs/brand/opendial_logo/` is traced from raster artwork, not drawn.
It renders correctly and scales, but the full-colour marks are ~200 colour-band
paths each, so they cannot be recoloured or edited.

Single-colour treatments now exist — knockout, outline and silhouette, each in
purple, white and black — and the knockout mark is readable down to about 32 px.
Two things are still missing, and both are deferred:

- A hand-drawn vector version with real editable paths, so a colour is one value.
- A purpose-drawn 16 px icon. Every current treatment is a smudge at that size,
  and 16 px is what the browser tab actually shows.

Deferred because Milestone 0 is a two-week time box and no call has been answered
yet. A logo blocks nothing. Revisit once the phone rings and the agent replies.
