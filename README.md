# Hi, I'm Akhilesh Chandewar — AI Infrastructure & Agent Platform Engineer

![Go](https://img.shields.io/badge/Go-00ADD8?logo=go&logoColor=white) ![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white) ![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?logo=typescript&logoColor=white) ![vLLM](https://img.shields.io/badge/vLLM-inference%20fleet-red) ![LangGraph](https://img.shields.io/badge/LangGraph-agents-8A2BE2) ![MCP](https://img.shields.io/badge/MCP-server%20author-black) ![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?logo=kubernetes&logoColor=white) ![Terraform](https://img.shields.io/badge/Terraform-7B42BC?logo=terraform&logoColor=white)

I build the **serving layer**, the **agent layer**, and the **product on top** — and I benchmark what I ship.

Currently at NeoSOFT: production LLM inference fleets (vLLM · SGLang · NVIDIA Dynamo KV-aware routing on Kubernetes) and agentic systems for finance-grade clients (PCI DSS / SOC 2 environments) — including a RAG platform gated by a quantified eval suite: **15-case golden dataset, 87% faithfulness, 93% tool-correctness, 100% adversarial-input blocking**.

---

### 🏆 Flagship builds

| Project | What it is | Proof |
|---|---|---|
| **[pdserve](https://github.com/Akhilesh-Chandewar/pdserve)** | Prefill/Decode-disaggregated LLM serving library in Go — KV-cache connectors (Mooncake/NIXL-style) + SLO-aware elastic GPU role flipping, on a deterministic discrete-event simulator | Under 6× burst: colocated TPOT p99 inflates **~264×** (0.25ms → **65.4ms**) while disaggregated holds **0.25ms flat**; TTFT p99 cut **4.1s → 1.72s** (elastic 1.56s). Byte-identical repro via `make repro` · real-GPU validation notebook in-repo |
| **[cadence](https://github.com/Akhilesh-Chandewar/cadence)** | Agentic time-series forecasting harness — five-agent control loop (Ingest → Diagnose → Plan → Forecast → Report) on a LangGraph state machine, four backtested model tiers with strict winner-selection | **209 network-free tests** · FastAPI + SSE + Streamlit + Docker · evals that refuse to declare victory without evidence |
| **[goonj](https://github.com/Akhilesh-Chandewar/goonj)** | Live-audio platform (Go + LiveKit + OpenAI Realtime) — creator speaks language A, listeners hear language B/C/D | Realtime translation at a **≤600ms latency cap**, drop-oldest backpressure at every hop — degradation hits quality, never latency |
| **[agent0](https://github.com/Akhilesh-Chandewar/agent0)** | AI agent builder — natural language → production agent code written, executed, and validated in E2B sandboxes (Inngest + Gemini) | Event-driven orchestration, quota-aware retry/backoff, full audit trail |
| **[eco-policy-mcp](https://github.com/Akhilesh-Chandewar/eco-policy-mcp)** | MCP server for Indian finance data: MF NAVs, GST & income-tax calculators, RBI rates, NSE quotes | Works with any MCP client — spec-level fluency, authored end-to-end |
| **[vyaparsathi](https://github.com/Akhilesh-Chandewar/vyaparsathi)** | Agentic kirana-store OS on Telegram — POS, GST invoicing, khata credit ledger, stock guardrails | 50+ tools, live bot at [t.me/Vyaparsathi_bot](https://t.me/Vyaparsathi_bot), idempotent by design |

### 🌊 Open-source contributions

Upstream engineering on the exact stacks I build on:

| Repo | Contribution |
|---|---|
| **[vLLM](https://github.com/vllm-project/vllm)** | Deep triage of ROCm FP8 loading bug [#58688](https://github.com/vllm-project/vllm/issues/58688) — built a CPU dev env, ran the PLE test suite, programmatically verified the FP8 method registration on current main, and established release skew with repro evidence instead of shipping a redundant fix |
| **[Ollama](https://github.com/ollama/ollama)** | [PR #18643](https://github.com/ollama/ollama/pull/18643) — replaced a filename-prefix check with a `filepath.Rel` directory-containment fix for nested `/Applications` installs; 12 table-driven unit tests, gofmt/vet clean |
| **[Pydantic AI](https://github.com/pydantic/pydantic-ai)** | Reproduced the `stream_text()` teardown race [#8767](https://github.com/pydantic/pydantic-ai/issues/8767) on Python 3.10 after automated triage failed — verified it still fails on current `main`, unblocking the "needs information" state |
| **[LangGraph](https://github.com/langchain-ai/langgraph)** | Independently reproduced the `InMemoryStore` per-item `index=["$"]` bug [#9059](https://github.com/langchain-ai/langgraph/issues/9059) on sync and async paths; offered complementary regression coverage |
| **[Plane](https://github.com/makeplane/plane)** | [PR #9879](https://github.com/makeplane/plane/pull/9879) — root-caused nested sub-work-item sorting (bug #9101) and fixed it through the shared sorting pipeline; React/TS/MobX, pnpm/Turborepo, strict tsc 0 errors |

### 🧪 Client-grade systems (engagement level)

- **Enterprise Agentic RAG** — 4 Cloud Run microservices, LangGraph Planner→Retriever→Responder, NeMo Guardrails + Portkey two-gate safety, Terraform-managed, blue-green Cloud Build → Cloud Run delivery
- **Custodian (AI governance)** — prompt-injection guardrail classifier gating all agent input + dual-agent cross-provider adversarial critic (disagreement hard-stops payment); proven against 20 documented attack scenarios
- **PPFAS wealth platform** — 5-specialist LangGraph system over SEC EDGAR filings with human-in-the-loop gating; cross-filing signals in <5 minutes
- **MOSAIC** — 6 parallel agents detecting research-integrity signals across 400K+ clinical trial records on GCP

---

### Stack

**Inference & Infra:** vLLM (paged-KV, schedulers, quantization) · SGLang (RadixAttention) · NVIDIA Dynamo (KV-aware routing, NIXL/KVBM) · Kubernetes · GPU cost/latency benchmarking
**Agents & Evals:** LangGraph (multi-agent, HITL) · MCP (server author) · Google ADK · CrewAI · golden-dataset eval suites · RAGAS + LLM-as-a-Judge · NeMo Guardrails · Portkey
**Languages & Backend:** Go · Python (FastAPI) · TypeScript (NestJS/Express/Next.js) · PostgreSQL + pgvector · Redis · Kafka · RabbitMQ
**Cloud & IaC:** Terraform multi-cloud (GCP: Cloud Run/SQL stacks · AWS: VPC/ALB/ASG/Route53/CodeDeploy) · Azure data services (Blob Storage, Azure Database for PostgreSQL) · AWS (Lambda, SQS, EventBridge, ECS Fargate) · GCP (Cloud Run, Eventarc) · Azure / Microsoft Foundry (fine-tuning & distillation)

---

### Now

- Building production wealth-platform intelligence at PPFAS — SEC EDGAR multi-agent systems, human-in-the-loop gating
- Open to AI-infrastructure and agent-platform roles — India GCC, remote, or contract

📫 akhil.chandewar00@gmail.com · [Medium @akhil.chandewar00](https://medium.com/@akhil.chandewar00) · [LinkedIn — akhilesh-chandewar](https://www.linkedin.com/in/akhilesh-chandewar)
