<!-- README.md — Danish Ali -->

<h1 align="center">Danish Ali</h1>

<p align="center">
  Software Engineer · Manchester, UK<br>
  <sub>DataHub core contributor · 1st place, AMD × GPU MODE E2E Model Speedrun · MSc Advanced CS, University of Manchester</sub>
</p>

<p align="center">
  <a href="https://linkedin.com/in/danish-ali-lynx"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white" alt="LinkedIn"></a>
  <a href="mailto:danishlynx@gmail.com"><img src="https://img.shields.io/badge/Email-EA4335?style=flat&logo=gmail&logoColor=white" alt="Email"></a>
</p>

---

I build systems that check their own work-deterministic simulations with server-side replay, allocation with zero-oversell stress proofs, agent output gated by linters and real browsers. Previously at **Energy Web** and **AAK Tele-Science**. Open to software engineer roles in the UK.

## Open source — DataHub core

Designed and shipped incident support for ML entities (models, features, feature tables) in [DataHub](https://github.com/datahub-project/datahub) (12k+ ⭐).

| Status | Contribution |
|---|---|
| **Accepted** | [RFC #18911](https://github.com/datahub-project/datahub/issues/18911) — its per-layer analysis of how entity support drifts was adopted as the maintainers' "gates" roadmap model |
| **Merged** | [#19112](https://github.com/datahub-project/datahub/pull/19112) · [#19132](https://github.com/datahub-project/datahub/pull/19132) · [#19367](https://github.com/datahub-project/datahub/pull/19367) — metadata model, GraphQL API, authorization policies, React UI, MCP tooling |
| **In review** | Fixes for two CI flakes root-caused from logs alone: a concurrency race and a mistuned performance gate |

> Maintainer, on closing the RFC: *"full support across data model, API, UI, and MCP."*

## Projects

| Name | What I built | Stack | Links |
|---|---|---|---|
| **CivicNexus** | Governed agent fleet for municipal permit casework. Four agents on Vertex AI read the application, retrieve the municipal code, and draft a determination whose every quote is byte-checked against the committed statute  **email to human gate in 62s**. Attachments are OCR'd and re-screened before any model sees them, and only a named human can issue a permit, enforced by a write-once approval row. | Vertex AI Agent Engine · ADK · Gemini · Gemma · Cloud Run · Terraform | [Live](https://civicnexus-console-wrhx6s33dq-uc.a.run.app) · [Repo](https://github.com/Danishlynx/CivicNexus) |
| **Blast Radius** | Autonomous ML supply-chain guardian on the DataHub metadata graph. Finds every model in the blast radius of an upstream schema change, files evidence-backed incidents, opens dbt-validated fix PRs, and blocks bad deploys through a CI circuit breaker. Building this surfaced the gap behind the RFC above. | Python · DataHub · MCP · dbt | [Repo](https://github.com/Danishlynx/blast-radius) |
| **Singleton** | No-oversell allocation of scarce slots. Sharded counters under optimistic concurrency and a commit-reveal lottery anyone can re-verify in the browser — **10,000 concurrent claims on a 200-slot release, zero oversold**. | Aurora DSQL · Next.js 15 · TypeScript · Vercel | [Live](https://singleton-six.vercel.app/) |
| **GPTDesign** | Design-system-locked UI generation for coding agents. A deterministic token-drift linter hard-rejects off-system output, a sight loop has the model inspect its own render, and a Playwright gate clicks every tab, dialog and button before a run passes. 880+ tests. | TypeScript · Fastify · Playwright · MCP · SSE | [Repo](https://github.com/Danishlynx/GPT_Design) |
| **AMD GPU Kernels** | AMD × GPU MODE E2E Model Speedrun, Phase 1 — **🥇 1st overall**. Fused MoE kernel at 69.9 µs geomean on the MXFP4 track. | Triton · ROCm/HIP · AITER · FlyDSL · Python | [Repo](https://github.com/Danishlynx/gpuMode_Kernal) |
| **Precedent** | Decision-memory agent for Slack. Extracts decisions from threads with confidence gating, keeps a forward-only supersession history, and answers "what did we decide about X?" with source-thread receipts. Exposed as an MCP server. | Slack Bolt · Claude · MCP · SQLite · Railway | [Live](https://precedent-website.vercel.app/) · [Repo](https://github.com/Danishlynx/precedent) |
| **underVault** | Asymmetric-knowledge roguelike on Reddit. One shared dungeon, one life a day, rules hidden from you and learnable only from other players' corpses. Integer-only deterministic simulation with server-side replay validation. | Devvit · Phaser · Hono · Redis | [Repo](https://github.com/Danishlynx/underVault) |

<details>
<summary>Earlier projects</summary>

<br>

| Name | What I built | Stack | Links |
|---|---|---|---|
| **Web Information Decay** | Quantifying the degradation of web archival quality across modern platform architectures | Python · Playwright · Wayback Machine | [Repo](https://github.com/Danishlynx/web_information_decay_research) |
| **Ethereum Charts** | Real-time chain analytics dashboard | React · Web3.js · D3 | [Live](https://charts-using-ethereum-api-285h.vercel.app/) |
| **Proxy Wallet** | Gas-optimised smart wallet with guardian recovery | Solidity · Hardhat · ethers.js | [Live](https://proxy-smart-wallet-with-frontend.vercel.app/) |

</details>

## Stack

**Languages** TypeScript · JavaScript · Python · SQL · Solidity
**Backend** Node.js · Fastify · Express · FastAPI · GraphQL · REST · WebSockets
**Data** PostgreSQL · Aurora DSQL · Redis · MongoDB
**AI & agents** LLM APIs (OpenAI, Anthropic) · MCP servers · agent evals · Playwright automation
**Frontend** React · Next.js · Tailwind CSS
**Cloud & DevOps** AWS · Docker · Kubernetes · Terraform · GitHub Actions

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=Danishlynx&theme=tokyonight&show_icons=true&count_private=true&hide_border=true&hide=issues" alt="GitHub stats">
</p>
