---
layout: page
title: "Chatbot Performance Evaluator"
description: A Python framework for benchmarking FAQ-style chatbots with deterministic metrics, LLM-as-judge review, and Streamlit result inspection.
img: assets/images/research/chatbot_evaluator_thumbnail.png
importance: 1
category: industry
collection: research
author_profile: false
date: 2026-04-01
github: https://github.com/andalenavals/chatbot_performance_evaluator/
demo: https://andalenavals-chatbot-performance-evaluator.hf.space
---

The **Chatbot Performance Evaluator** is a modular framework for systematically benchmarking, validating, and monitoring chatbot behavior. It was designed around a practical industry problem: once a chatbot is exposed to users, the difficult part is no longer only building the assistant, but proving that it continues to answer correctly, safely, and consistently as prompts, models, policies, and domain knowledge evolve.

The project turns chatbot quality checks into a repeatable engineering workflow. Given an FAQ-style evaluation dataset, it can run multiple chatbot variants over the same questions, persist row-level outputs, compute aggregate summaries, and make the results inspectable through both machine-readable reports and a Streamlit app.

## Links

- [GitHub repository](https://github.com/andalenavals/chatbot_performance_evaluator/)
- [Live Streamlit demo](https://andalenavals-chatbot-performance-evaluator.hf.space)
- [Documentation overview](https://andalenavals.github.io/chatbot_performance_evaluator/overview.html)
- [Metrics documentation](https://andalenavals.github.io/chatbot_performance_evaluator/metrics.html)

## What It Evaluates

The framework supports two complementary chatbot strategies:

- **Full-context prompting**, where a chat model receives a reusable prompt plus a domain-knowledge file and answers from that context.
- **Strict semantic match**, where the system treats the FAQ as a controlled answer bank and returns the answer attached to the most similar known question.

Because both strategies implement the same text-in/text-out contract, they can be evaluated with the same pipeline. This makes it possible to compare prompt changes, model changes, retrieval-like matching, and full LLM generation under one shared benchmark.

## Evaluation Pipeline

The project loads FAQ datasets from CSV files with questions and expected answers, runs one or more configured bots, and writes detailed outputs for each bot-question pair. Those outputs include:

- the bot name,
- the original question,
- the expected answer,
- the generated answer,
- deterministic metric scores,
- LLM-judge score details,
- latency,
- and bot metadata for debugging.

This row-level design is important because it supports both executive summaries and technical debugging. A product owner can compare aggregate performance across chatbot variants, while an engineer can inspect exactly which questions regressed and why.

## Metrics

The framework combines transparent deterministic metrics with model-based qualitative review:

- **Exact match** checks whether the normalized generated answer equals the expected answer.
- **Keyword recall** measures how much expected-answer vocabulary appears in the generated answer.
- **Answer length** provides a simple communication and truncation signal.
- **Politeness** tracks lightweight tone markers.
- **Latency** records operational response time.
- **LLM-as-a-judge metrics** score richer properties such as relevance, faithfulness, safety, and robustness.

The LLM judge prompts are configurable and return structured JSON with a numeric score and a rationale. This keeps qualitative evaluation auditable while still capturing dimensions that are hard to express with a single deterministic formula.

## Configuration-Driven Design

Bots, models, and judges are configured with small JSON files. The current setup includes:

- OpenAI-compatible chat clients,
- local Ollama-backed models such as DeepSeek and Qwen,
- full-context bot configurations,
- semantic-match bot configurations,
- judge prompts for safety/robustness,
- judge prompts for relevance/faithfulness,
- and fallback behavior when OpenAI credentials are not available.

This makes the project useful for teams that need to compare providers, run local experiments, or test prompt changes without rewriting the evaluation code.

## Outputs and Inspection

The framework writes detailed CSV and JSONL outputs, plus aggregate summaries by bot. A Streamlit app provides an interactive inspection layer for reviewing the benchmark results, comparing chatbot variants, and finding weak spots in the evaluation dataset.

It also includes a Sphinx documentation site with installation, demo, testing, deployment, API, and metric-reference pages. The documentation is published at [andalenavals.github.io/chatbot_performance_evaluator](https://andalenavals.github.io/chatbot_performance_evaluator/overview.html).

## Why It Matters

For customer-support assistants, HR bots, internal policy assistants, and other high-frequency chatbot workflows, quality cannot depend on occasional manual checks. This project treats FAQ evaluation as a living regression suite: teams can add real user intents, edge cases, multilingual variants, adversarial prompts, and safety-sensitive questions over time.

The result is a practical validation loop for answering questions such as:

- Did the new prompt improve factual accuracy?
- Did a model change reduce latency without hurting safety?
- Which bot strategy is better for a tightly governed FAQ workflow?
- Are refusal and safety behaviors still robust on adversarial inputs?

In short, the project provides the scaffolding needed to move chatbot evaluation from ad hoc demos toward repeatable product-quality measurement.
