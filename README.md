<h1 align="center">Danish Ali</h1>

<p align="center">
  Software Engineer · Manchester, UK<br>
  <sub>3rd place, AWS Trainium Frontier Competition (1st in Round 1) · 1st in the qualifiers, AMD × GPU MODE E2E Model Speedrun</sub><br>
  <sub>DataHub contributor · MSc Advanced CS, University of Manchester</sub>
</p>

<p align="center">
  <a href="https://linkedin.com/in/danish-ali-lynx"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white" alt="LinkedIn"></a>
  <a href="mailto:danishlynx@gmail.com"><img src="https://img.shields.io/badge/Email-EA4335?style=flat&logo=gmail&logoColor=white" alt="Email"></a>
</p>

---

I work on ML training and inference performance, and I build systems that check their own work: deterministic simulations with server-side replay, allocation stress-tested for zero oversell, agent output gated by linters and real browsers. Previously at **Energy Web** and **AAK Tele-Science**. Open to software engineering and ML performance roles in the UK.

## ML performance

| Name | What I built | Stack | Links |
|---|---|---|---|
| **AWS Trainium Frontier Competition** | Training a language model from random weights on Trainium2 chips inside a fixed time budget. **3rd overall of 100 teams, and 1st in Round 1.** Round 1 (1 chip, 30 minutes): 0.9328 bits per byte, with throughput up from about 42k to 340k tokens a second, mostly from custom NKI kernels (attention, the loss head, fused elementwise blocks) and fp8 matmuls. Round 2 (16 chips, 4 hours): a 3.68B-parameter mixture-of-experts model (0.71B active per token), step time down from the kit's 2.41 s to 0.86 s, and the lowest validation loss of the ten finalists. | NKI · Neuron SDK · PyTorch · Python | [Repo](https://github.com/Danishlynx/trainium-frontier-them-bones) |
| **AMD × GPU MODE E2E Model Speedrun** | Qualifiers: **1st overall**, with a fused MoE kernel at 69.9 µs geomean on the MXFP4 track. Finals: DeepSeek-R1 serving on 4x MI355X, time per output token down from 6.30 ms to 5.64 ms, 2 of 4 gates passed. | Triton · ROCm/HIP · AITER · FlyDSL · Python | [Kernels](https://github.com/Danishlynx/gpuMode_Kernel) · [Finals](https://github.com/Danishlynx/AMD_DSR_CONC4/tree/submission) |

## Open source: DataHub core

Contributor to [DataHub](https://github.com/datahub-project/datahub) (12k+ stars), the open-source metadata platform. Designed and shipped incident support for ML entities and keyless Snowflake authentication, with 8 PRs merged and 2 approved across the metadata model, GraphQL API, React UI and Python ingestion connectors.

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

> Maintainer, on closing the RFC: *"We now have full support for incidents on these 3 entities across data model, API, UI, and MCP."*
>
> Snowflake auth maintainer, approving #19889: *"I broke each new guard on purpose again [...], and a test caught every one."*
>
> Maintainer, approving #19540: *"nice fix and a really clear writeup."*

## Projects

| Name | What I built | Stack | Links |
|---|---|---|---|
| **CivicNexus** | Governed agent fleet for municipal permit casework. Four agents on Vertex AI read the application, retrieve the municipal code, and draft a determination whose every quote is byte-checked against the committed statute. **Email to human gate in about 62 seconds.** Attachments are OCR'd and re-screened before any model sees them, and only a named human can issue a permit, enforced by a write-once approval row. | Vertex AI Agent Engine · ADK · Gemini · Gemma · Cloud Run · Terraform | [Live](https://civicnexus-console-wrhx6s33dq-uc.a.run.app) · [Repo](https://github.com/Danishlynx/CivicNexus) |
| **Blast Radius** | ML supply-chain agent on the DataHub metadata graph. Finds every model in the blast radius of an upstream schema change, files evidence-backed incidents, opens dbt-validated fix PRs, and blocks bad deploys through a CI circuit breaker. Building this surfaced the gap behind the RFC above. | Python · DataHub · MCP · dbt | [Repo](https://github.com/Danishlynx/blast-radius) |
| **Singleton** | No-oversell allocation of scarce slots. Sharded counters under optimistic concurrency and a commit-reveal lottery anyone can re-verify in the browser. **10,000 concurrent claims on a 200-slot release, zero oversold.** | Aurora DSQL · Next.js 15 · TypeScript · Vercel | [Live](https://singleton-six.vercel.app/) |
| **GPTDesign** | Design-system-locked UI generation for coding agents. A deterministic token-drift linter hard-rejects off-system output, a sight loop has the model inspect its own render, and a Playwright gate clicks every tab, dialog and button before a run passes. 880+ tests. | TypeScript · Fastify · Playwright · MCP · SSE | [Repo](https://github.com/Danishlynx/GPT_Design) |
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

**Languages** TypeScript · JavaScript · Python · SQL · Solidity<br>
**ML performance** NKI (AWS Trainium) · Triton · ROCm/HIP · FP8 and MXFP4 · PyTorch<br>
**Backend** Node.js · Fastify · Express · FastAPI · GraphQL · REST · WebSockets<br>
**Data** PostgreSQL · Aurora DSQL · Redis · MongoDB<br>
**AI & agents** LLM APIs (OpenAI, Anthropic) · MCP servers · agent evals · Playwright automation<br>
**Frontend** React · Next.js · Tailwind CSS<br>
**Cloud & DevOps** AWS · Docker · Kubernetes · Terraform · GitHub Actions
