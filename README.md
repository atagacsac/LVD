## 🧠 LLM Vulnerability Database Schema

This project introduces a database for documenting vulnerabilities in **Large Language Models (LLMs)**, with a focus on their application in **Multi-Agent Systems (MAS)**. This database aims to address that gap by organizing and presenting known LLM vulnerabilities to support threat analysis and enhance security research in this emerging field.

### 📋 Schema Fields of LVDS

| **Field Name**                      | **Description**                                                                                                                                  | **Example**                                            |
| ----------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------ |
| `Identifier`                        | A unique numerical ID for each record or attack procedure.                                                                                       | `1`                                                    |
| `Attack Procedure`                  | High-level name of the attack method.                                                                                                | `Simple Adaptive`                                      |
| `Description`                       | Detailed textual explanation of the attack method.                                                                                               | *See description text from entry*                      |
| `LLM Version`                       | Specific large language model and its version that is targeted.                                                                                  | `GPT-4o`, `Llama-2-Chat-7B`                            |
| `Vulnerability Category (OWASP 10)` | The type of vulnerability based on the OWASP LLM Top 10                         | `Prompt Injection`                                     |
| `Tactic (MITRE ATLAS)`              | MITRE ATLAS tactic being leveraged by the attacker, describing the high-level goals.                                                  | `Execution`, `Privilege Escalation`, `Defense Evasion` |
| `Technique (MITRE ATLAS)`           | Specific technique used, based on MITRE ATLAS mappings.                                                                                          | `LLM Jailbreak`                                        |
| `Agentic Framework`                 | Indicates if the attack exploits or depends on an agentic/multi-agent system (MAS) framework.                                                    | `Yes` / `No`                                           |
| `Tool Type`                         | Specifies how the permission LLM has to interact with the tools.| `No Tool / LLM Core`, `API Interaction`                |
| `Tool Configuration/Permissions`    | Indicates tool permissions (e.g., read/write) relevant to the LLM’s interaction.                                                                 | `NA`, `Read/Write`                                     |
| `Impact (CIA Triad)`                | States which component(s) of the CIA triad (Confidentiality, Integrity, Availability) are impacted.                                              | `CI` (Confidentiality & Integrity)                     |
| `Attack Success Rate (ASR)`         | The success rate of the attack (based on source if available).                                                                          | `~95%`                                                 |
| `Severity`                          | Overall severity of the attack                                            | A numeric score(To be added once Beni is done with the calculation)                   |
| `Source`                            | Academic or technical source providing or describing the attack procedure.                                                                       | `https://arxiv.org/pdf/2404.02151`                     |

---

### 🧰 Field Highlights

- **LLM Version** – Indicates which large language model is being targeted, helping contextualize vulnerability across different architectures.
- **Vulnerability Category (OWASP 10)** – Classifies each attack using the OWASP LLM Top 10, aiding in standard risk assessment.
- **Tactic & Technique (MITRE ATLAS)** – Maps each attack to standardized framework, for threat modeling.
- **Agentic Framework** – Flags whether the attack relies on agent-based or autonomous systems, a growing concern in LLM deployment.
- **Impact (CIA Triad)** – Clarifies what’s at risk Confidentiality, Integrity, or Availability.
- **Severity & ASR** – Together, these fields offer a quick read on how damaging and successful an attack is.

### Tool Categorization and Descriptions

| **Tool Category**           | **Description**                                                   |
|----------------------------|-------------------------------------------------------------------|
| Code Execution             | Tools that can execute code in some environment.                 |
| API Interaction (External) | Tools that interact with external third-party APIs.              |
| API Interaction (Internal) | Tools that interact with internal company APIs or microservices. |
| Human Interaction          | Tools that explicitly require human confirmation or input before proceeding. |
| Computational/Analytical   | Tools for performing calculations or complex analysis.           |
| Sensor/Actuator            | Tools that interact with the physical world.                     |
| No Tool/LLM Core           | No tool, the LLM's core processing, prompting, or its direct output handling. |

