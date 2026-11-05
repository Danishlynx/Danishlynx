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

## Open source: DataHub core

Contributor to [DataHub](https://github.com/datahub-project/datahub) (12k+ ⭐), the open-source metadata platform. Designed and shipped incident support for ML entities and keyless Snowflake authentication, with 8 PRs merged and 2 approved across the metadata model, GraphQL API, React UI and Python ingestion connectors.

| Status | Contribution |
|---|---|
| **Accepted** | [RFC #18911](https://github.com/datahub-project/datahub/issues/18911): per-layer analysis of how entity support drifts, adopted as the maintainers' "gates" roadmap model |
| **Merged** | [#19112](https://github.com/datahub-project/datahub/pull/19112) · [#19132](https://github.com/datahub-project/datahub/pull/19132) · [#19367](https://github.com/datahub-project/datahub/pull/19367): incident support for ML models, features and feature tables across the metadata model, GraphQL API, authorization policies, React UI and MCP tooling |
| **Merged** | [#19889](https://github.com/datahub-project/datahub/pull/19889): keyless Snowflake login through workload identity federation, so ingestion on AWS, Azure or GCP uses its own cloud identity and stores no password or key. Verified live on AWS |
| **Merged** | [#19539](https://github.com/datahub-project/datahub/pull/19539): a single undecryptable secret no longer fails the whole batch, backported by maintainers into the v1.6.0.3 release |
| **Merged** | [#19540](https://github.com/datahub-project/datahub/pull/19540): structured property values containing a URN no longer crash the entity page |
| **Merged** | [#19278](https://github.com/datahub-project/datahub/pull/19278) · [#19537](https://github.com/datahub-project/datahub/pull/19537): a CI flake fix and API docs corrections |
| **Approved** | [#19627](https://github.com/datahub-project/datahub/pull/19627): health status for ML entities across lineage, search and entity pages |
| **Approved** | [#19879](https://github.com/datahub-project/datahub/pull/19879): platform instance support for Superset and Preset dashboards, charts and datasets |
| **In review** | [#19629](https://github.com/datahub-project/datahub/pull/19629): a CI test that fails when incident support disagrees between the write, summary and GraphQL read layers, picked up at a maintainer's request |
| **In review** | [#19535](https://github.com/datahub-project/datahub/pull/19535) · [#19536](https://github.com/datahub-project/datahub/pull/19536): deterministic replacements for two timing-based CI tests, root-caused from CI logs |

> Maintainer, on closing the RFC: *"full support across data model, API, UI, and MCP."*
>
> Snowflake auth maintainer, approving #19889: *"I broke each new guard on purpose again [...], and a test caught every one."*
>
> Maintainer, approving #19540: *"nice fix and a really clear writeup."*

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
