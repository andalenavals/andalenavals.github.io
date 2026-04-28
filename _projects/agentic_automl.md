---
layout: page
title: "Agentic AutoML"
description: An AI-first AutoML workflow package for coding agents, with stepwise workflow recommendations, execution, and a single exported notebook artifact.
img: assets/images/research/agentic_automl_thumbnail.png
importance: 3
category: industry
collection: research
author_profile: false
date: 2026-04-20
github: https://github.com/andalenavals/agentic-automl/
docs: https://andalenavals.github.io/agentic-automl/
---

**Agentic AutoML** is an AutoML package built for AI operators rather than click-through usage. The intended user is a coding agent such as Codex, Claude Code, or OpenClaw: the human provides the dataset location, target, task type, and success criteria, and the package takes over the fixed workflow from planning through execution and notebook export.

The project treats AutoML as an agent-centered operating workflow instead of a pile of disconnected knobs. Each step ships with operating guidance, capability knowledge, and explicit limits, so the system can recommend defaults, explain tradeoffs, revise policies through discussion, and then execute one coherent path.

## Links

- <a href="https://github.com/andalenavals/agentic-automl/" data-analytics-event="project_github_click" data-link-type="github" data-project="Agentic AutoML">GitHub repository</a>
- <a href="https://andalenavals.github.io/agentic-automl/" data-analytics-event="project_docs_click" data-link-type="docs" data-project="Agentic AutoML">Published documentation</a>

## What It Does

The package is built around a fixed canonical AutoML workflow for tabular CSV and Parquet problems in classification and regression. It can:

- profile a project brief from CLI or UI input
- recommend each workflow step with rationale
- execute the selected workflow end to end
- optionally run a compact hyperparameter competition
- export exactly one rerunnable workflow notebook

Feature pruning and feature-subset choices are handled inside preprocessing, so the workflow stays compact and the exported notebook reflects only the selected path.

## Interface and Output Model

The project supports both CLI planning/execution and a chat-style UI with workflow recommendations and visualizations. The final output is intentionally narrow: a single workflow-specific notebook that embeds the code needed for the chosen path and can rerun from the dataset location without importing `agentic_automl`.

That makes the package useful for AI-assisted operators who want a defensible, repeatable AutoML run rather than a black-box dashboard.

## Architecture

The repository separates workflow assets, execution logic, step guidance, documentation, and tests. A small Sphinx documentation site explains the workflow, action agents, and exported notebook model, while the codebase keeps the workflow engine shared across UI and CLI entry points.
