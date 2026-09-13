# Hi, I'm Akhilesh Chandewar — AI Infrastructure & Agent Platform Engineer

I build the **serving layer**, the **agent layer**, and the **product on top** — and I benchmark what I ship.

Currently at NeoSOFT: production LLM inference fleets (vLLM · SGLang · NVIDIA Dynamo KV-aware routing on Kubernetes) and agentic systems for finance-grade clients (PCI DSS / SOC 2 environments).

---

### Flagship builds

| Project | What it is | Proof |
|---|---|---|
| **[pdserve](https://github.com/Akhilesh-Chandewar/pdserve)** | Prefill/Decode-disaggregated LLM serving library in Go — KV-cache connectors + SLO-aware elastic GPU role flipping | TTFT p99 **4.1s → 0.28s**, TPOT p99 **66ms → 0.5ms** in benchmark runs |
| **[goonj](https://github.com/Akhilesh-Chandewar/goonj)** | Live-audio platform (Go + LiveKit + OpenAI Realtime) — creator speaks language A, listeners hear language B | Realtime translation at a **≤600ms latency cap**, drop-oldest backpressure at every hop |
| **[agent0](https://github.com/Akhilesh-Chandewar/agent0)** | AI agent builder — natural language → production agent code in E2B sandboxes (Inngest + Gemini) | Event-driven, audit-trailed, quota-aware |
| **[eco-policy-mcp](https://github.com/Akhilesh-Chandewar/eco-policy-mcp)** | MCP server for Indian finance data: MF NAVs, GST & income-tax calculators, RBI rates, NSE quotes | Works with any MCP client |
| **[vyaparsathi](https://github.com/Akhilesh-Chandewar/vyaparsathi)** | Agentic kirana-store OS on Telegram — POS, GST invoicing, khata credit ledger, stock guardrails | 50+ tools, live bot, idempotent by design |
| **[convo-ai](https://github.com/Akhilesh-Chandewar/convo-ai)** | Multi-model AI chat platform (Next.js 16, Vercel AI SDK 6, streaming, 100+ models) | Production-architected |

---

### Stack

**Inference & Infra:** vLLM (paged-KV, schedulers, quantization) · SGLang (RadixAttention) · NVIDIA Dynamo (KV-aware routing, NIXL/KVBM) · Kubernetes · Terraform
**Agents:** LangGraph (multi-agent, HITL) · MCP (server author) · CrewAI · Google ADK · E2B sandboxes · Ragas + LLM-as-a-Judge evals
**Languages & Backend:** Go · Python (FastAPI) · TypeScript (NestJS/Express/Next.js) · PostgreSQL + pgvector · Redis · Kafka · RabbitMQ
**Cloud:** AWS (SQS/Lambda/EventBridge/Cognito/ASG — production) · GCP (Cloud Run agent deploys) · Azure / Microsoft Foundry (fine-tuning & distillation)

---

### Now

- Building PPFAS — production wealth-advisory platform with multi-agent financial intelligence (SEC EDGAR, cross-filing signals, human-in-the-loop)
- Certifications in progress: **AWS ML Engineer–Associate** · **Azure AI-102**
- Open to AI-infrastructure and agent-platform roles — India GCC, remote, or contract

📫 akhil.chandewar00@gmail.com · [Medium @akhil.chandewar00](https://medium.com/@akhil.chandewar00) · [LinkedIn](https://www.linkedin.com/) <!-- paste your LinkedIn URL -->
