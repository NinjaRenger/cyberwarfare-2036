# AI Capabilities in Cybersecurity — 2026

## Purpose

This research documents what artificial intelligence can realistically do in cybersecurity as of 2026.

The objective is to establish an evidence-based technical baseline before making projections toward 2036.

The analysis focuses on demonstrated capabilities rather than hypothetical future scenarios. Claims are separated into observed evidence, emerging capabilities, reasonable projections, and speculation.

---

## Research Questions

1. What can modern AI systems actually do today?
2. What can AI agents do autonomously?
3. How capable are AI systems at cybersecurity tasks?
4. How can AI assist offensive security?
5. How can AI assist defensive security?
6. What limitations still prevent reliable autonomous cyber operations?
7. Which capabilities are already operational?
8. Which capabilities are emerging?
9. What capabilities could realistically become more powerful by 2036?
10. At what point does AI stop being a tool and become an active participant in cyber operations?

---

# 1. AI Reasoning and Planning

## Capability

Modern AI systems can process complex instructions, decompose tasks into subtasks, generate plans, use tools, inspect results, and revise actions based on feedback.

Reasoning should not be treated as a single measurable capability. In practice, performance depends on the model, task, available context, tools, environment, and evaluation method.

## Evidence

### Evidence 1 — AI Agent Autonomy

**Source:** NIST, AI Agent Standards Initiative, February 2026.

NIST reports that AI agents can now work autonomously for hours, write and debug code, and interact with external systems.

**What this demonstrates:**

- Multi-step task execution
- Code generation and debugging
- Interaction with external systems
- Extended autonomous operation

**Limitation:** NIST also identifies reliability and interoperability as constraints on practical agent deployment.

**Classification:** Observed

### Evidence 2 — Agentic Cyber Operations

**Source:** Google Threat Intelligence Group, September 2026.

GTIG observed adversaries moving beyond simple prompting toward agentic workflows and AI-enabled automation. In one Q2 2026 case, threat actors compromised a cloud resource and then used an agent-enabled workflow to plan, build, and execute a mass credential-harvesting campaign in under six hours.

**What this demonstrates:**

- Task decomposition
- Dynamic workflow execution
- Error handling
- Automation across multiple stages
- Reduced human-in-the-loop latency

**Important qualification:** This does not establish that AI systems can independently conduct every type of cyber operation. GTIG explicitly distinguishes current agentic automation from fully autonomous zero-day discovery and exploitation in the wild.

**Classification:** Observed

## Assessment

| Dimension | 2026 status | Evidence |
|---|---|---|
| Multi-step planning | Observed | Strong |
| Tool integration | Observed | Strong |
| Error handling / adaptation | Observed | Moderate–Strong |
| Long-horizon planning | Emerging | Moderate |
| Novel strategy discovery | Emerging | Limited |
| General autonomous reasoning | Emerging | Context-dependent |

## Cybersecurity Implications

The important development is not simply that AI can answer security questions. It is that agents can connect reasoning to tools and external systems. This changes AI from an advisory interface into an operational component.

---

# 2. AI Coding Capability

## Capability

Modern AI systems can assist with:

- Writing code
- Debugging
- Code analysis
- Refactoring
- Script generation
- Understanding unfamiliar codebases
- Test generation
- Documentation
- Iterative modification

## Evidence

AI coding systems are now integrated into development workflows and can perform multi-step coding tasks.

Threat-intelligence reporting in 2026 also documents adversaries using AI for malware development, exploit research, code modification, and other software-engineering tasks.

Anthropic reported cases in which threat actors used Claude as part of offensive engineering and orchestration workflows. GTIG separately observed adversaries using AI coding capabilities in vulnerability research and malware/tool development.

## Limitations

AI-generated code can:

- Contain vulnerabilities
- Misunderstand requirements
- Produce incorrect assumptions
- Fail in unfamiliar environments
- Require human debugging
- Introduce dependency and supply-chain risk

Coding ability therefore does not automatically imply reliable autonomous software engineering.

## Cybersecurity Implications

AI coding capability lowers the cost of creating and modifying software. For attackers, this can reduce the expertise required for tooling development. For defenders, it can accelerate secure-code review, detection engineering, automation, and security tooling.

**Classification:** Observed

---

# 3. AI Agents

## Definition

An AI agent is a system in which a model can interact with tools or external systems, maintain state, execute multi-step workflows, observe results, and choose subsequent actions.

A useful conceptual architecture is:

```text
User / Objective
       ↓
      LLM
       ↓
   Planning
       ↓
 Tool Selection
       ↓
 Tool Execution
       ↓
 Environment Observation
       ↓
 Evaluation / Memory
       ↓
   Next Action
```

## Important Agent Components

### Model

Provides language understanding, reasoning, and decision-making.

### Tools

Allow the agent to interact with:

- APIs
- Browsers
- Terminals
- Files
- Databases
- Security tools
- Cloud systems

### Memory / State

Allows information from previous steps or sessions to influence later actions.

### Planning

Allows the system to decompose objectives into multiple actions.

### Permissions

Determine what the agent is actually capable of affecting.

### Environment

Provides feedback that allows the agent to adapt.

## Evidence

NIST describes AI agents as systems capable of planning and taking autonomous actions that affect real-world systems or environments. NIST also emphasizes the security implications of giving agents access to diverse data, tools, and applications.

Google GTIG has documented threat actors using agentic workflows for reconnaissance, vulnerability research, credential harvesting, and other operational tasks.

Anthropic's September 2026 threat report describes cases involving multi-agent cyber workflows, persistent campaign memory, autonomous collection, and adaptive tooling.

## Agent-to-Agent Collaboration

Multi-agent architectures can divide a larger task among specialized agents.

For example:

```text
             Lead Agent
            /    |     \
           /     |      \
       Recon   Analysis  Reporting
         ↓        ↓         ↓
      Agent     Agent     Agent
```

This can increase parallelism and reduce the amount of work one agent must perform sequentially.

## Limitations

Agent capability depends heavily on:

- Tool permissions
- Model quality
- Environment complexity
- Context availability
- Error recovery
- Authentication
- Network access
- Safety controls
- Human oversight

An agent with no tools is fundamentally different from an agent with unrestricted access to a terminal, cloud APIs, credentials, and production infrastructure.

**Classification:** Observed

---

# 4. AI-Assisted Offensive Security

## Areas of Capability

Investigate and assess:

- Reconnaissance
- OSINT
- Attack-surface analysis
- Enumeration
- Vulnerability discovery
- Exploit research
- Exploit generation
- Credential attacks
- Social engineering
- Malware development
- Malware modification
- Attack automation
- Post-exploitation assistance

## Reconnaissance and OSINT

AI can assist with:

- Target research
- Information extraction
- Organization profiling
- Technology identification
- Social-media analysis
- Translation
- Social-engineering preparation

GTIG documented threat actors using AI for target intelligence and social-engineering workflows.

**Classification:** Observed

## Vulnerability Discovery

AI can assist with:

- Source-code analysis
- Vulnerability triage
- Fuzzing support
- Patch analysis
- Vulnerability research
- Exploit prototyping

The capability is not uniform. It depends on vulnerability class, target complexity, context, tools, and model quality.

**Classification:** Observed / Emerging

## Exploit Development

AI can generate and modify exploit-related code, but reliable exploitation remains highly environment-dependent.

The distinction between:

> generating exploit code

and:

> reliably discovering, adapting, validating, and deploying an exploit against an unknown real target

is critical.

**Classification:** Emerging

## Social Engineering

AI can automate or accelerate:

- Target research
- Personalized messages
- Translation
- Phishing content
- Conversational interaction

AI increases scale and reduces language barriers, but successful social engineering still depends on target behavior and operational context.

**Classification:** Observed

## Malware Development and Adaptation

Threat-intelligence reporting documents AI-assisted malware development and workflows in which AI systems monitor detections and modify tooling in response.

**Classification:** Observed

## Overall Offensive Assessment

AI is already being used across multiple stages of the attack lifecycle. The strongest evidence is for assistance and automation in reconnaissance, social engineering, coding, credential operations, and parts of post-exploitation.

Full autonomous exploitation against arbitrary real-world targets remains less established.

---

# 5. AI-Assisted Defensive Security

This section is intentionally expanded because defensive capability is necessary for a balanced assessment.

## Security Operations

AI can assist with:

- Alert triage
- Log summarization
- Incident investigation
- Threat-intelligence analysis
- Security-ticket generation
- Detection-rule development
- Case prioritization

## Threat Hunting

AI can help analysts:

- Query large datasets
- Correlate events
- Identify unusual behavior
- Generate hypotheses
- Search for indicators
- Explain suspicious activity

## Malware Analysis

AI can assist with:

- Static code analysis
- Reverse-engineering assistance
- Behavioral interpretation
- Classification
- Extracting indicators
- Explaining suspicious functions

Human validation remains important because incorrect interpretation can produce false conclusions.

## Detection Engineering

AI can assist in:

- Writing detection rules
- Translating detection logic between formats
- Generating test cases
- Mapping behaviors to ATT&CK techniques
- Reviewing detection coverage

## Incident Response

AI can support:

```text
Alert
 ↓
Triage
 ↓
Investigation
 ↓
Hypothesis
 ↓
Evidence collection
 ↓
Containment recommendation
 ↓
Human decision
```

The strongest current role is generally decision support and workflow acceleration rather than unrestricted autonomous incident response.

## Vulnerability Management

AI can help prioritize vulnerabilities using:

- Asset criticality
- Exposure
- Exploitability
- Known exploitation
- Business context
- Available remediation information

## Defensive Assessment

AI is already useful as a force multiplier for defenders, but defensive autonomy faces the same reliability and authorization problems as offensive autonomy.

**Classification:** Observed

---

# 6. Autonomous Cyber Operations

## Definition

Autonomous cyber operation means that an AI system can execute multiple stages of a cyber workflow with limited human intervention, rather than merely providing advice.

The following model is used for assessment:

```text
Reconnaissance
      ↓
Enumeration
      ↓
Vulnerability Discovery
      ↓
Exploitation
      ↓
Credential Access
      ↓
Lateral Movement
      ↓
Collection
      ↓
Exfiltration
```

## Stage-by-Stage Assessment

| Stage | 2026 assessment | Evidence level | Main limitation |
|---|---|---|---|
| Reconnaissance | High autonomy | Strong | Target/environment context |
| Enumeration | High autonomy | Strong | Environment-specific complexity |
| Vulnerability discovery | Medium autonomy | Moderate | Novelty and reliability |
| Exploitation | Medium / emerging | Moderate | Real-world transfer |
| Credential access | High automation | Strong | Permission and access constraints |
| Lateral movement | Medium / emerging | Moderate | Strategic context |
| Collection | Medium / emerging | Moderate | Target prioritization |
| Exfiltration | Automatable | Moderate | Detection / operational security |
| End-to-end autonomous operation | Emerging | Moderate | Human objectives and reliability |

## Important Conclusion

The evidence does **not** justify saying that AI can currently perform arbitrary end-to-end cyberattacks autonomously.

A more defensible conclusion is:

> AI has already demonstrated autonomous or highly automated behavior across multiple individual stages of cyber operations, and real-world operations increasingly combine these capabilities into multi-stage workflows. However, fully autonomous end-to-end operations against arbitrary real-world targets remain insufficiently demonstrated.

This distinction is central to the 2036 research question.

---

# 7. AI Security Limitations

Current limitations include:

## Hallucination

AI systems can generate incorrect technical claims, code, commands, or assumptions.

## Reliability

A system may succeed on one task and fail on a similar task because of changes in context or environment.

## Context Limitations

Long workflows create challenges in maintaining relevant state and avoiding information loss.

## Tool-Use Errors

An agent may choose the wrong tool, use incorrect parameters, misunderstand results, or take an unsafe action.

## Planning Failure

Long-horizon plans can break when the environment deviates from expected conditions.

## Simulation-to-Reality Gap

Performance in CTFs, benchmarks, or controlled environments does not necessarily transfer to arbitrary real-world systems.

## Benchmark Fragmentation

Different studies use different tasks, models, environments, and success definitions, making direct comparisons difficult.

## Security Guardrails

Model-level safeguards can reduce misuse, but threat actors can attempt to bypass them through indirect instructions, task decomposition, compromised accounts, or alternative models.

## Authentication and Authorization

Agents can become high-impact systems when granted access to credentials, APIs, cloud resources, code repositories, or production systems.

NIST specifically identifies identity, authorization, auditing, and controlling agent access as important security concerns.

## Situational Awareness

AI can process large amounts of information but may still lack the robust contextual understanding humans use when interpreting ambiguous real-world situations.

---

# 8. AI Attack Surface

AI systems introduce security risks at several layers.

## Model Layer

- Model extraction
- Distillation
- Training-data attacks
- Model manipulation
- Adversarial inputs

## Application Layer

- Prompt injection
- Indirect prompt injection
- Unsafe output handling
- Sensitive-information disclosure

## Agent Layer

- Goal hijacking
- Tool misuse
- Excessive agency
- Identity and privilege abuse
- Memory poisoning
- Rogue agents
- Cascading failures
- Human-agent trust exploitation

## Tool / Integration Layer

- Insecure APIs
- Malicious tools
- MCP-related risks
- Insecure plugins
- Excessive permissions

## Supply Chain

- Malicious dependencies
- Compromised repositories
- Compromised agent skills
- Poisoned model artifacts
- Compromised AI infrastructure

OWASP's 2026 Agentic Applications work explicitly identifies risks including agent goal hijacking, tool misuse, identity and privilege abuse, agentic supply-chain vulnerabilities, unexpected code execution, memory poisoning, insecure inter-agent communication, cascading failures, human-agent trust exploitation, and rogue agents.

## AI as a Target

AI infrastructure itself is becoming a valuable target.

Threat intelligence reporting in 2026 describes targeting of:

- Model source code
- Model weights
- Prompts
- AI developer credentials
- AI coding configurations
- Cloud compute
- AI research

This means AI is simultaneously:

1. A tool for attackers.
2. A defensive technology.
3. A new attack surface.
4. A high-value target.

---

# 9. AI vs Human

A simple "winner" table is misleading. AI and humans have different strengths.

| Capability | Current assessment |
|---|---|
| Raw execution speed | AI advantage |
| Large-scale repetition | AI advantage |
| Parallelization | AI advantage |
| Pattern processing at scale | AI advantage |
| Deep contextual judgment | Human advantage |
| Ambiguous real-world decisions | Human advantage |
| Strategic objective selection | Human advantage |
| Novel reasoning | Mixed / task-dependent |
| Long-horizon reliability | Human advantage |
| Tool execution | AI advantage when tools are available |
| Accountability | Human |
| Adaptability to unfamiliar environments | Mixed |
| Consistency | AI can be higher, but failures can also be systematic |

The correct question is therefore not:

> "Is AI smarter than humans?"

A more useful cybersecurity question is:

> "Which parts of a cyber workflow can AI perform faster, cheaper, or at larger scale than humans, and where does human judgment remain necessary?"

---

# 10. AI Capability Assessment — 2026

| Capability | Status | Evidence strength |
|---|---|---|
| Coding assistance | Observed | Strong |
| Reasoning / planning | Observed | Strong but task-dependent |
| Tool use | Observed | Strong |
| Agentic workflows | Observed | Strong |
| Multi-agent collaboration | Observed | Moderate |
| Reconnaissance | Observed | Strong |
| Enumeration | Observed | Strong |
| Vulnerability discovery | Emerging | Moderate |
| Exploit generation | Emerging | Moderate |
| Reliable arbitrary exploitation | Emerging | Limited |
| Credential operations | Observed | Strong |
| Social engineering | Observed | Strong |
| Malware development assistance | Observed | Strong |
| Adaptive malware workflows | Observed | Moderate |
| Threat detection | Observed | Moderate–Strong |
| Threat hunting | Observed | Moderate |
| Malware analysis | Observed | Moderate–Strong |
| Incident response | Emerging | Moderate |
| Autonomous lateral movement | Emerging | Moderate |
| Autonomous collection | Emerging | Moderate |
| End-to-end autonomous cyber operations | Emerging | Limited–Moderate |
| Autonomous zero-day discovery in the wild | Speculative / insufficient evidence | Weak |

### Status Definitions

**Observed**  
Directly demonstrated or documented in a credible source or experiment.

**Emerging**  
Evidence exists, but the capability is not yet mature, general, or consistently reliable.

**Projected**  
A reasonable extrapolation from observed and emerging trends.

**Speculative**  
Possible, but current evidence is insufficient to support the claim.

---

# 11. Evidence Quality Framework

Not all evidence should receive the same weight.

## Tier 1 — Primary Evidence

Highest value:

- Original academic experiments
- Government research
- Original threat-intelligence reports
- Direct incident-response reporting
- Reproducible technical experiments

## Tier 2 — Expert Technical Research

- Security research organizations
- Major technical research teams
- Peer-reviewed surveys
- Technical industry reports

## Tier 3 — Secondary Reporting

- Reputable journalism
- Technical news
- Analyst commentary

## Tier 4 — Weak Evidence

- Marketing claims
- Unsourced posts
- Social-media claims
- Unverified demonstrations

## Research Rule

Whenever possible:

> **Cite the original report rather than an article describing the report.**

Also record:

- Model
- Model version
- Environment
- Tools
- Permissions
- Human involvement
- Success criteria
- Failure cases
- Date

---

# 12. Observed vs Emerging vs Projected vs Speculative

## Observed

AI agents can already:

- Use tools
- Execute multi-step workflows
- Write and debug code
- Perform reconnaissance
- Assist social engineering
- Support vulnerability research
- Automate parts of credential operations
- Support defensive analysis
- Operate for extended periods in some environments

## Emerging

- More reliable autonomous exploitation
- Long-horizon cyber operations
- Autonomous vulnerability discovery
- Multi-agent attack coordination
- Adaptive offensive workflows
- More autonomous incident response

## Projected

If current trends continue:

- Attack timelines may continue to compress.
- More cyber labor may be delegated to agents.
- The cost of large-scale operations may decrease.
- Defensive systems may increasingly use agents for continuous monitoring and response.
- Human roles may shift toward objective selection, authorization, validation, and oversight.

## Speculative

The current evidence is insufficient to confidently claim:

- Fully autonomous arbitrary cyberwarfare
- Universal zero-day discovery by AI
- AI independently choosing geopolitical targets
- Large-scale AI-vs-AI cyberwarfare without meaningful human direction

---

# 13. Human-in-the-Loop vs Human-on-the-Loop

This distinction is important for the 2036 research.

## Human-in-the-loop

The human approves individual or important actions.

```text
AI → proposes action → HUMAN → approves → action
```

## Human-on-the-loop

The AI performs actions while the human supervises the system.

```text
AI → action → action → action
          ↑
       HUMAN
     supervises
```

## Human-out-of-the-loop

The system performs actions without meaningful human supervision.

```text
Objective
   ↓
 AI
   ↓
Autonomous operation
   ↓
Outcome
```

Current evidence shows movement toward the second category in some workflows, but the most consequential decisions often remain under human control.

This distinction should remain explicit throughout the 2036 project.

---

# 14. Research Conclusions

## What AI Can Actually Do in 2026

AI is no longer limited to generating text or answering questions.

Current systems can combine:

- Reasoning
- Planning
- Coding
- Tool use
- Memory
- External-system interaction
- Multi-agent coordination

These capabilities are already being applied to cybersecurity workflows.

## What AI Does Particularly Well

AI has strong advantages in:

- Speed
- Repetition
- Parallelization
- Information processing
- Code generation
- Large-scale analysis
- Workflow automation

## What Still Requires Humans

Humans remain important for:

- Strategic objectives
- Target selection
- Authorization
- Ambiguous judgment
- Validation
- Risk acceptance
- Accountability
- High-consequence decisions

The boundary is not binary.

AI can perform some operational stages with high autonomy while still requiring humans to establish the overall objective.

## Biggest Technical Limitations

The most important limitations are:

1. Reliability
2. Long-horizon planning
3. Environment transfer
4. Tool-use errors
5. Context management
6. Evaluation quality
7. Authorization and identity
8. Human oversight

## Most Important Inflection Point

The most significant change in 2026 is the transition from:

> **AI as an assistant**

to:

> **AI as an agent that can observe, decide, act, evaluate, and continue.**

Cybersecurity makes this transition especially important because the consequences of incorrect actions can affect real systems.

## Evidence-Based Answer to the 2036 Research Question

**Question:**

> At what point does AI stop being a tool in cyberwarfare and become an active participant in cyber conflict?

The 2026 evidence suggests that there is no single boundary.

AI has already become an **active operational component** of some cyber workflows, particularly in reconnaissance, enumeration, credential operations, social engineering, coding, and parts of post-exploitation.

However, the evidence does not yet establish a generally capable, fully autonomous cyber operator that can independently select arbitrary targets, discover novel vulnerabilities, develop reliable exploits, conduct complete intrusions, and achieve strategic objectives without meaningful human direction.

Therefore, the 2026 inflection point is best understood as a **continuum of increasing agency**, not a single technological event.

This conclusion forms the baseline for the 2036 research.

---

# 15. Open Research Questions

The following questions should remain open for future experiments:

1. How reliably can agents operate over long time horizons?
2. How does performance change when tools fail?
3. How well do agents transfer from CTF environments to real enterprise environments?
4. How much autonomy can safely be granted to a security agent?
5. How should agent identity and authorization work?
6. Can agents reliably detect when their own reasoning is wrong?
7. How effective are current defenses against prompt injection?
8. Can autonomous agents discover genuinely novel vulnerabilities?
9. How should autonomous defensive actions be validated?
10. At what level of autonomy does human oversight become insufficient?
11. How will multi-agent systems change cyber operations?
12. What capabilities should be considered strategically dangerous by 2030–2036?

---

# Sources

## Government / Standards

1. NIST — AI Agent Standards Initiative, 2026.
2. NIST — CAISI Request for Information About Securing AI Agent Systems, 2026.
3. NIST — AI Agent Identity and Authorization Concept Paper, 2026.
4. NIST — Summary Analysis of Responses to the RFI Regarding Security Considerations for AI Agents, 2026.

## Security Research

5. Google Threat Intelligence Group — *AI Threat Tracker: From Prompting to Autonomy – The Evolution of Adversarial AI*, September 2026.
6. Anthropic — *Detecting and Countering Misuse of AI: September 2026*.
7. OWASP GenAI Security Project — *Top 10 for Agentic Applications 2026*.
8. OWASP GenAI Security Project — *Top 10 for LLM Applications 2026*.

## Academic / Technical Research

9. *AutoSec-Agent: A Fully Autonomous and Ethical Multi-Agent Framework for Scalable Penetration Testing Using Large Language Models*, 2026.
10. *A Survey of LLM-Driven Penetration Testing: Taxonomy, Co-Evolution, and Open Challenges*, 2026.
11. IEEE — *AI-Driven Penetration Testing: A Survey of Autonomous Agents, LLM-Based Approaches, and Future Directions*, 2026.
12. Cloud Security Alliance — research on automated exploit generation and LLM agents in offensive security, 2026.

## Industry / Threat Intelligence

13. Trend Micro — H1 2026 APT Activity Roundup.
14. Microsoft — Digital Defense Report.
15. Palo Alto Networks Unit 42 — 2026 AI-agent intrusion research.

---

# Research Notes

This document is a 2026 baseline, not a prediction.

Future updates should preserve previous findings and record:

- New evidence
- New model capabilities
- New real-world incidents
- Failed experiments
- Benchmark changes
- Changes in confidence
- Contradictory evidence

The file should be treated as a living research document through the end of 2026.
