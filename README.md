# RuleTrek# RuleTrek: Benchmarking Agentic Rule Reasoning in Complex Scenarios

[![arXiv](https://img.shields.io/badge/arXiv-2610.19698-b31b1b.svg)](https://arxiv.org/abs/2610.19698)
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-Papers-yellow)](https://huggingface.co/papers/2610.19698)

**RuleTrek** is a multi-domain benchmark for evaluating LLM agents' ability to perform **rule reasoning in complex scenarios**.

📄 **Paper:** [RuleTrek: Benchmarking Agentic Rule Reasoning in Complex Scenarios](https://arxiv.org/abs/2610.19698)

## Overview

Identifying and correctly applying domain-specific rules is essential for LLM agents to solve complex real-world tasks.

However, existing rule-reasoning benchmarks typically represent scenarios using only a few factual statements, simplifying the identification and application of relevant rules.

**RuleTrek** addresses this limitation by introducing **complex, multi-file scenarios** in which agents must:

- **Integrate distributed information** across multiple heterogeneous files.
- **Identify applicable rules** and their dependencies from original rule documents.
- **Correctly apply rules** to derive answers in complex scenarios.
- **Interact with realistic workspaces**, using tools to explore files and solve tasks.

RuleTrek contains **240 instances across six domains**: Taxation, PostgreSQL, Cybersecurity, Software Policy, Procurement, and Game Rules.

## Benchmark Construction

RuleTrek employs a **rule-grounded scenario construction pipeline** consisting of three stages:

1. **Domain Rule Graph Extraction:** Extract structured rule graphs from real-world rule repositories to capture domain-specific rules and their dependencies.
2. **Rule-Specific Sub-Scenario Construction:** Generate sub-scenarios grounded in individual rules, ensuring that each sub-scenario requires the application of its corresponding rule.
3. **Dependency-Aware Composition:** Incrementally compose sub-scenarios according to rule dependencies, while verifying consistency and rule-based solvability.

This pipeline enables the construction of complex, multi-file scenarios grounded in real-world rules.

## Evaluation Tasks

RuleTrek systematically evaluates three core capabilities in interactive workspaces:

| Task | Description |
|------|-------------|
| **Rule Identification (RI)** | Identify applicable rules and their dependencies from original rule documents. |
| **Rule Deduction (RD)** | Integrate distributed scenario information and correctly apply provided rules to derive answers. |
| **End-to-End Rule Reasoning (E2E)** | Jointly identify and apply rules from original documents to solve complex tasks. |

## Benchmark Statistics

RuleTrek contains **240 evaluation instances** across six domains.

| Domain | Instances |
|--------|-----------|
| Taxation | 48 |
| Game Rules | 45 |
| Procurement | 42 |
| Cybersecurity | 38 |
| Software Policy | 37 |
| PostgreSQL | 30 |
| **Total** | **240** |

## Main Results

Experiments on **11 frontier LLMs** reveal substantial limitations in agentic rule reasoning over complex scenarios.

- **Rule Identification:** The highest average score is only **62.47%**.
- **Rule Deduction:** Even with verified rules provided, the highest average score reaches only **60.43%**.
- **End-to-End Rule Reasoning:** Scores range from **26.97% to 55.29%**.

These findings demonstrate that current LLM agents struggle with both identifying applicable rules and correctly applying them to complex scenarios with distributed information.

## Code and Data

The benchmark dataset, evaluation code, and usage instructions will be released in this repository.

