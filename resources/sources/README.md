# Research Sources — Index

This is the main source list for the AI agent permissions and least-privilege project. Each numbered title opens its own source record in this folder. Each record includes a link to the original publication or project.

These are collected references for review; inclusion does not mean a source has been fully read or selected for the final bibliography. The individual files are reference records, not copies of the original papers.

| Source | Brief description |
| --- | --- |
| [01. Progent: Programmable Privilege Control for LLM Agents](01-progent.md) | Enforces policies on agent tool use to allow necessary actions and block unnecessary ones. |
| [02. Do Coding Agents Understand Least-Privilege Authorization? — AuthBench](02-authbench.md) | Tests whether models can identify the file-level read, write, and execute permissions needed for terminal tasks. |
| [03. FORTIS: Benchmarking Over-Privilege in Agent Skills](03-fortis.md) | Examines whether models select broader skills or tools than tasks require, including ordinary, non-adversarial requests. |
| [04. AgentGuardian: Learning Access Control Policies to Govern AI Agent Behavior](04-agentguardian.md) | Learns legitimate behaviour from execution logs and uses it to govern subsequent tool calls. |
| [05. Towards Automating Data Access Permissions in AI Agents](05-automated-data-permissions.md) | Studies users’ permission preferences and tests a system for predicting which data-sharing requests they would allow. |
| [06. Taming Various Privilege Escalation in LLM-Based Agent Systems](06-mandatory-access-control.md) | Proposes mandatory access controls to prevent agents from exceeding the authority required for a user’s task. |
| [07. Ajar: Measuring Open Privilege in Agent Defenses](07-ajar.md) | Measures unnecessary authority remaining after a defence is applied, alongside security and task performance. |
| [08. Defeating Prompt Injections by Design — CaMeL](08-camel.md) | Uses a protective execution layer and capability-based controls to constrain agent behaviour and sensitive-data flows. |
| [09. IsolateGPT: An Execution Isolation Architecture for LLM-Based Agentic Systems](09-isolategpt.md) | Tests whether separating application execution can prevent data theft and unwanted system changes while preserving functionality. |
| [10. CaMeLs Can Use Computers Too](10-camel-computer-use.md) | Research implementation extending CaMeL-style security to computer-use agents and operating-system boundaries. |
| [11. AgentDojo](11-agentdojo.md) | Runs realistic assistant tasks with prompt-injection attacks, measuring task completion and attacker success. |
| [12. InjecAgent](12-injecagent.md) | Tests whether malicious instructions in external content cause tool-using agents to steal data or perform harmful actions. |
| [13. Agent Security Bench — ASB](13-agent-security-bench.md) | Compares attacks and defences across multiple agent scenarios, tools, and security metrics. |
| [14. Identifying the Risks of LM Agents with an LM-Emulated Sandbox — ToolEmu](14-toolemu.md) | Simulates tool execution to identify risky behaviour, including privacy leaks and damaging actions. |
| [15. Agent-SafetyBench](15-agent-safetybench.md) | Evaluates agent safety across diverse interactive environments and categorises common failure modes. |
| [16. AgentHarm](16-agentharm.md) | Measures whether agents carry out explicitly harmful, multi-step requests using tools. |
| [17. Not What You’ve Signed Up For](17-indirect-prompt-injection.md) | Demonstrates how instructions hidden in retrieved content can redirect applications, manipulate tool use, and expose information. |
| [18. Design Patterns for Securing LLM Agents against Prompt Injections](18-security-design-patterns.md) | Examines architectural defences and their trade-offs between useful functionality and security. |
| [19. AgentBench: Evaluating LLMs as Agents](19-agentbench.md) | Compares models across interactive tasks, including operating-system tasks, and analyses reasons for failure. |
| [20. τ-bench: Tool-Agent-User Interaction](20-tau-bench.md) | Tests tool use and policy compliance, with repeated trials to measure consistency. |
| [21. AI Agents That Matter](21-ai-agents-that-matter.md) | Explains problems with agent evaluation and argues for measuring cost, reproducibility, and robustness alongside success. |
| [22. OSWorld](22-osworld.md) | Provides real computer tasks with repeatable starting conditions and checks of the resulting environment state. |
| [23. ReAct: Synergizing Reasoning and Acting in Language Models](23-react.md) | Explains an approach where models alternate between planning actions, using tools, and observing results. |
| [24. OWASP: Excessive Agency](24-owasp-excessive-agency.md) | Explains risks caused by excessive agent functionality, permissions, and autonomy. |
| [25. The Protection of Information in Computer Systems — Saltzer and Schroeder](25-saltzer-schroeder.md) | Foundational security paper covering least privilege, protection mechanisms, and controlled access to information. |
| [26. Role-Based Access Control Models — Sandhu and colleagues](26-role-based-access-control.md) | Establishes the theory behind assigning permissions through roles. |
| [27. NIST SP 800-162: Attribute Based Access Control](27-nist-attribute-based-access-control.md) | Explains access decisions based on the requester, resource, operation, and context. |
