# LLM Prompt Injection & Security Boundary Evaluator

<p align="center">
  <img src="https://img.shields.io/badge/Security-Defensive_Auditor-blue?style=flat" alt="Type">
  <img src="https://img.shields.io/badge/Status-Architectural_Showcase-success?style=flat" alt="Status">
  <img src="https://img.shields.io/badge/Python-3.10+-3776AB?style=flat&logo=python&logoColor=white" alt="Python">
</p>

> 🔒 **Technical Showcase & Architecture Specification**  
> *This repository provides public architectural documentation, system specifications, and implementation summaries. Full production source code, internal test suites, and proprietary algorithms are maintained in a secure private repository.*

---

## 📌 Executive Summary

**Category**: AI Security & LLM Governance  
**Tech Stack**: `Python 3.10+ · LLM Security · OWASP Top 10 for LLM · Adversarial Evaluation`  

Defensive testing suite evaluating Large Language Model application guardrails against direct, indirect, and jailbreak prompt injection attacks.

---

## 🎯 The Problem It Solves

LLM applications integrating untrusted user inputs or retrieved RAG documents are susceptible to prompt injection, causing models to ignore system instructions, exfiltrate data, or execute unauthorized tool calls.

---

## ⚙️ How the Engine Works

1. **Test Payload Ingestion**: Loads standardized prompt injection test suites covering:
   - Direct System Prompt Overrides (`Ignore all previous instructions...`)
   - Role-Play & Persona Jailbreaks
   - Delimiter / Formatting Escapes (Markdown, JSON, XML injection)
   - Indirect Injection payloads embedded inside simulated RAG context
2. **Boundary Testing Execution**: Feeds payloads through the target LLM application interface or guardrail layer.
3. **Output Sentiment & Compliance Scoring**: Analyzes model responses using heuristic pattern matching and safety classifiers to verify whether the model complied with the attack or preserved its system boundaries.
4. **Leakage Detection**: Validates whether hidden system prompt instructions or internal API tokens were exposed in the response.
5. **Vulnerability Scorecard**: Produces a standardized risk report with guardrail hardening recommendations.

---

## 🚀 Key Capabilities

- Evaluates LLM guardrails against direct and indirect prompt injection
- Tests system prompt boundary resilience and data exfiltration defenses
- Scores application robustness against OWASP LLM01: Prompt Injection
- Provides actionable prompt defense and input sanitization patterns

---

## 🏗️ System Data Flow & Architecture

```
+-----------------------------------+
|  Target Input / Configuration    |
|  (JSON Snapshots / Policies)      |
+-----------------+-----------------+
                  |
                  v
+-----------------------------------+
|  1. Schema Normalization Engine   |
|  Validates types & formats        |
+-----------------+-----------------+
                  |
                  v
+-----------------------------------+
|  2. Core Analytical Pipeline      |
|  Heuristic rule evaluation,       |
|  invariant checks & drift diffs   |
+-----------------+-----------------+
                  |
                  v
+-----------------------------------+
|  3. Risk Classification           |
|  Assigns severity: INFO / HIGH    |
+-----------------+-----------------+
                  |
                  v
+-----------------------------------+
|  4. Structured Findings & Report  |
|  Root cause, evidence &           |
|  actionable remediation steps     |
+-----------------------------------+
```

---

## 📄 Findings Output Structure

The engine generates structured, machine-parsable JSON reports adhering to this standard audit schema:

```json
{
  "results": [
    {
      "resource": "resource-identifier",
      "severity": "HIGH",
      "check": "CHECK_IDENTIFIER",
      "detail": "Descriptive analysis of the identified security posture issue.",
      "remediation": "Actionable step-by-step guidance to restore compliant state.",
      "evidence": {
        "observed_field": "value",
        "required_policy": "enforced_policy"
      }
    }
  ],
  "count": 1,
  "scope": "Comprehensive defensive security audit"
}
```

---

## 🔒 Source Code & Enterprise Inquiries

To protect proprietary intellectual property and client operational security:
* **Public Repository**: Contains comprehensive architecture specifications, schemas, and design overviews.
* **Private Repository**: Contains the complete production implementation, continuous integration pipelines, and full regression test suites.

For architectural questions or enterprise inquiries, connect via [LinkedIn](https://www.linkedin.com/in/karthikeyansubramaniam04/) or visit the [Portfolio Site](https://karthikeyansubramaniyam.github.io).
