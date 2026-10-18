<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0B1020,45:312E81,100:7C3AED&height=230&section=header&text=Santhana%20Krishna&fontSize=48&fontColor=F8FAFC&animation=fadeIn&fontAlignY=36&desc=AI%20ENGINEERING%20%7C%20AGENT%20WORKFLOWS%20%7C%20SYSTEMS%20THINKING&descAlignY=57&descSize=15" width="100%" alt="Santhana Krishna — AI Engineering, Agent Workflows, Systems Thinking" />

<a href="https://github.com/Santa-Cruz1654/TaskPilot"><img src="https://img.shields.io/badge/Flagship-TaskPilot-7C3AED?style=for-the-badge&logo=github&logoColor=white" alt="TaskPilot flagship project" /></a>
<a href="https://github.com/Santa-Cruz1654/AI"><img src="https://img.shields.io/badge/Explore-AI%20Learning%20Lab-4F46E5?style=for-the-badge&logo=github&logoColor=white" alt="AI learning lab" /></a>
<a href="https://www.linkedin.com/in/b-santhana-krishna-9575bb22a"><img src="https://img.shields.io/badge/Connect-LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn" /></a>
<a href="mailto:bsanthanakrishna@gmail.com"><img src="https://img.shields.io/badge/Contact-Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Email" /></a>

<br/>

![Profile Views](https://komarev.com/ghpvc/?username=Santa-Cruz1654&style=flat-square&color=7C3AED&label=PROFILE+VIEWS)
![Followers](https://img.shields.io/github/followers/Santa-Cruz1654?style=flat-square&color=4F46E5&label=FOLLOWERS)

</div>

---

## Hey, I'm Santhana Krishna 👋

I'm an **AI Engineer who learns by building real systems**. I'm interested in what sits around the model call: workflow state, data validation, retrieval, tool boundaries, API design, approvals, failure handling, and verification.

I don't want to learn technologies as a checklist. I build small, testable systems to understand how a concept works, where it breaks, and what trade-offs it introduces. My work spans LLM applications and agents, backend and inference infrastructure, AI security, and systems fundamentals. My Electronics and Communication Engineering background in Cyber-Physical Systems also shaped my interest in monitoring and securing systems that interact with the real world.

**The theme across my projects:** make the system's behavior understandable, bounded, and verifiable—not just make a demo produce an answer.

## 01 · Flagship project — TaskPilot

<a href="https://github.com/Santa-Cruz1654/TaskPilot"><img src="https://img.shields.io/badge/OPEN%20PROJECT-TaskPilot-7C3AED?style=for-the-badge&logo=github&logoColor=white" alt="Open TaskPilot on GitHub" /></a>

### TaskPilot — Autonomous AI Task Worker

TaskPilot is my main end-to-end engineering project: a **local prototype that turns a natural-language invoice request into a controlled, reviewable workflow** against a synthetic inbox and finance application.

Instead of letting an LLM freely operate the whole system, TaskPilot separates interpretation from execution and adds explicit validation, a human approval step, and read-back verification.

**Workflow at a glance**

The LLM-planning path is orchestrated with LangGraph; deterministic mode follows a separate worker path. Both use the same invoice-processing checks and approval boundary.

```text
Natural-language request
          ↓
FastAPI task interface
          ↓
Deterministic or LLM-based planning
          ↓
Observe the synthetic inbox with Playwright
          ↓
Download PDF → extract fields → validate with Pydantic
          ↓
Check for an existing finance record
          ↓
If new: persist proposal → wait for human approval
          ↓
Submit approved record → read it back → verify saved fields
```

**What I'm exploring through TaskPilot**

- **Agent workflow design:** a LangGraph workflow for the LLM-planning path, with explicit state and transitions.
- **LLM boundaries:** the planner can propose a constrained invoice selection or ask for clarification; it doesn't make the finance write itself.
- **Deterministic checks:** validate invoice fields and compare extracted document data with the selected inbox record.
- **Human-in-the-loop control:** new finance writes wait for a persisted approval that must match the exact proposal.
- **Duplicate handling:** inspect existing records instead of blindly creating another one.
- **Independent verification:** read the saved record back and check the required fields before reporting success.
- **Inspectable behavior:** task status, events, decisions, and results are persisted for review.

<sub>Stack: Python · FastAPI · LangGraph · Playwright · Pydantic · pypdf · SQLite · Pytest · uv</sub>

> **Scope note:** TaskPilot is a local engineering prototype using synthetic invoice and finance data. It is not a production accounting system or a general-purpose computer-use agent, and it is not connected to real finance systems.

---

## 02 · AI Engineering Learning Lab

The [`AI` repository](https://github.com/Santa-Cruz1654/AI) is a **collection of focused implementations and experiments**. Each folder represents a concept I'm trying to understand by building it—not a claim that every item is a standalone production product.

| Learning project | What I'm learning by implementing it |
|---|---|
| [**Pydantic Structured Extraction**](https://github.com/Santa-Cruz1654/AI/tree/main/01.%20Pydantic%20Structured%20Extraction) | Turning model output into typed, validated data instead of trusting free-form text. |
| [**Stateful AI Workflow with LangGraph**](https://github.com/Santa-Cruz1654/AI/tree/main/02.%20Stateful%20AI%20Workflow%20with%20LangGraph) | Representing a workflow as state, nodes, transitions, and explicit control flow. |
| [**RAGForge**](https://github.com/Santa-Cruz1654/AI/tree/main/03.RAGFORGE) | Understanding the pieces of retrieval-augmented generation and how retrieval affects grounded answers. |
| [**Context-Aware Production Agent**](https://github.com/Santa-Cruz1654/AI/tree/main/04%20Context-Aware%20Production%20Agent) | Assembling relevant context and defining boundaries for context-aware agent behavior. |
| [**LLM Processor**](https://github.com/Santa-Cruz1654/AI/tree/main/05.LLM%20Processor) | Exploring reusable LLM-processing abstractions and separation between application code and model calls. |
| [**AI Inference Service**](https://github.com/Santa-Cruz1654/AI/tree/main/06.AI-INFERENCE-SERVICE) | Learning how to structure a service around inference requests and model execution. |

### Related AI systems I'm building

These are separate application-level projects that extend the same learning into backend and workflow engineering.

- **[Production AI Inference Gateway](https://github.com/Santa-Cruz1654/production-ai-inference-gateway)** — an incremental engineering project exploring a provider abstraction, model routing, authentication, rate limiting, request handling, and reliability concerns around LLM inference. It is actively being developed; the repository documents capabilities that remain future work.
- **[ITSM AI Platform](https://github.com/Santa-Cruz1654/itsm-ai-platform)** — a full-stack helpdesk automation prototype covering intelligent ticket intake, knowledge retrieval, self-healing workflows, a self-service interface, and software provisioning flows. ServiceNow and provisioning integrations are mocked, so the project demonstrates workflow design rather than live enterprise integration.

---

## 03 · Learning how systems work

I keep these repositories because I want to understand the mechanics behind software systems. **They are first-principles learning projects, not the main products I use to define my profile.** I work through the design, implement the core ideas, and document the trade-offs so I can reason about systems beyond using a framework.

<details>
<summary><strong>Distributed Cache Router — learning distributed systems from the inside</strong></summary>

[Open repository](https://github.com/Santa-Cruz1654/Distributed-Cache-Router)

I implemented a cache router in Python to understand the steps behind distributed key placement and replication: SHA-256 hashing, a consistent-hash ring, binary-search routing, virtual nodes, and clockwise replica selection. The repository also includes unit tests, benchmarks, and notes showing how the design evolves from modulo hashing to replication.

**The learning goal:** understand why key distribution changes when nodes are added or removed, and how virtual nodes and replicas affect balance and availability.

</details>

<details>
<summary><strong>Low-Level Design — learning to structure code and responsibilities</strong></summary>

[Open repository](https://github.com/Santa-Cruz1654/low-level-design)

A set of Python design exercises for practicing object-oriented design, responsibility boundaries, SOLID principles, and design patterns. The purpose is to get more deliberate about how classes and components collaborate and how design choices affect changeability and testing.

</details>

<details>
<summary><strong>High-Level Design — learning architecture and trade-offs</strong></summary>

[Open repository](https://github.com/Santa-Cruz1654/HLD)

System-design exercises such as Pastebin and a distributed job scheduling and execution platform. I use these to think through components, responsibilities, data flow, bottlenecks, and trade-offs before getting lost in implementation details.

</details>

<details>
<summary><strong>Docker Task Platform — learning container and runtime boundaries</strong></summary>

[Open repository](https://github.com/Santa-Cruz1654/docker-task-platform)

A hands-on project for learning API containerization, Docker Compose, Redis integration, persistence, networking, health checks, and container hardening. I use it to understand what the container runtime and deployment configuration contribute beyond the application code itself.

</details>

---

## 04 · AI security, cybersecurity, and CPS

AI engineering is my primary direction, but security is an important part of how I think about system design. I have also explored:

- **GuardrailOps — AWS Bedrock Guardrails-as-Code:** exploring reusable AI safety policies and provisioning guardrails through Python-based AWS CDK rather than relying only on manual console configuration.
- **PromptWarden — prompt-injection and jailbreak detection:** developing a detection-and-decision approach for suspicious prompts, informed by the OWASP Top 10 for LLM Applications and adversarial test cases.
- **Water-infrastructure digital twin / SCADA anomaly detection:** combining sensor observations, a dashboard, model-based predictions, and anomaly alerts in a cyber-physical systems setting.
- **ML-based network threat detection:** exploring feature-based network traffic classification for IoT/CPS-style environments.
- **Secure RFID authentication:** working with Raspberry Pi, MFRC522, AES-128-CBC encryption, and a Flask/WebSocket data path.

These projects connect my AI engineering interests with the security, networking, and cyber-physical systems background that shaped how I think about reliability and system behavior.

---

## 05 · Technical toolkit

<div align="center">

**AI applications and workflows**  
<img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python" />
<img src="https://img.shields.io/badge/LangChain-1C3C3C?style=flat-square&logo=langchain&logoColor=white" alt="LangChain" />
<img src="https://img.shields.io/badge/LangGraph-1C3C3C?style=flat-square&logo=langgraph&logoColor=white" alt="LangGraph" />
<img src="https://img.shields.io/badge/RAG-6D28D9?style=flat-square" alt="RAG" />
<img src="https://img.shields.io/badge/Pydantic-E92063?style=flat-square&logo=pydantic&logoColor=white" alt="Pydantic" />
<img src="https://img.shields.io/badge/LLM%20Evaluation-4F46E5?style=flat-square" alt="LLM Evaluation" />

**Backend, automation, and data**  
<img src="https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white" alt="FastAPI" />
<img src="https://img.shields.io/badge/Flask-000000?style=flat-square&logo=flask&logoColor=white" alt="Flask" />
<img src="https://img.shields.io/badge/Playwright-2EAD33?style=flat-square&logo=playwright&logoColor=white" alt="Playwright" />
<img src="https://img.shields.io/badge/SQLite-003B57?style=flat-square&logo=sqlite&logoColor=white" alt="SQLite" />
<img src="https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white" alt="Redis" />
<img src="https://img.shields.io/badge/pytest-0A9EDC?style=flat-square&logo=pytest&logoColor=white" alt="pytest" />
<img src="https://img.shields.io/badge/pypdf-334155?style=flat-square" alt="pypdf" />

**AI infrastructure and cloud**  
<img src="https://img.shields.io/badge/Qdrant-DC244C?style=flat-square" alt="Qdrant" />
<img src="https://img.shields.io/badge/Groq-111827?style=flat-square" alt="Groq" />
<img src="https://img.shields.io/badge/Vertex%20AI-4285F4?style=flat-square&logo=googlecloud&logoColor=white" alt="Vertex AI" />
<img src="https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazonaws&logoColor=white" alt="AWS" />
<img src="https://img.shields.io/badge/AWS%20CDK-FF9900?style=flat-square&logo=amazonaws&logoColor=white" alt="AWS CDK" />
<img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white" alt="Docker" />

**Systems, data, and security**  
<img src="https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black" alt="Linux" />
<img src="https://img.shields.io/badge/SQL-4479A1?style=flat-square&logo=mysql&logoColor=white" alt="SQL" />
<img src="https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white" alt="NumPy" />
<img src="https://img.shields.io/badge/Pandas-150458?style=flat-square&logo=pandas&logoColor=white" alt="Pandas" />
<img src="https://img.shields.io/badge/scikit--learn-F7931E?style=flat-square&logo=scikitlearn&logoColor=white" alt="scikit-learn" />
<img src="https://img.shields.io/badge/Wireshark-1679A7?style=flat-square&logo=wireshark&logoColor=white" alt="Wireshark" />
<img src="https://img.shields.io/badge/Nmap-4B8BBE?style=flat-square" alt="Nmap" />
<img src="https://img.shields.io/badge/TCP%2FIP-334155?style=flat-square" alt="TCP/IP" />
<img src="https://img.shields.io/badge/Raspberry%20Pi-C51A4A?style=flat-square&logo=raspberrypi&logoColor=white" alt="Raspberry Pi" />
<img src="https://img.shields.io/badge/ESP32-007ACC?style=flat-square" alt="ESP32" />

</div>

---

## Background

**B.Tech, Electronics & Communication Engineering — Cyber-Physical Systems**  
SASTRA Deemed University · 2022–2026 · CGPA: 8.00

The combination of software, networks, security, and physical systems made me curious about how complex systems behave. Today, that curiosity shows up most in AI applications: I want to understand not just model behavior, but also the application, tools, data, control flow, and safeguards around it.

### Certifications and learning

- Google Cybersecurity Specialization
- Deloitte Australia Cyber Job Simulation
- Mastercard Cybersecurity Job Simulation

## What I'm learning next

- How retrieval quality, reranking, context assembly, and evaluation affect RAG applications.
- How to combine LLM flexibility with deterministic validation and predictable workflow control.
- How inference services should handle provider boundaries, timeouts, retries, security, and observability.
- How human approval and independent verification make agentic workflows easier to trust.
- How to reason about architecture by implementing core systems and measuring their trade-offs.

## Beyond the code

I enjoy working through a concept until I can explain why it behaves the way it does, then writing down the result so I can revisit it and improve it. I also play violin: I trained in Carnatic violin for more than six years and am now exploring Western violin.

<div align="center">

<a href="https://www.linkedin.com/in/b-santhana-krishna-9575bb22a"><img src="https://img.shields.io/badge/LinkedIn-Let's%20connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="Connect on LinkedIn" /></a>
<a href="mailto:bsanthanakrishna@gmail.com"><img src="https://img.shields.io/badge/Email-Get%20in%20touch-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Email me" /></a>

<br/><br/>

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:7C3AED,50:312E81,100:0B1020&height=110&section=footer" width="100%" alt="" />

</div>
