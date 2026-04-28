---
layout: page
title: "Agentic Trading Bots"
description: A commodity decision-support dashboard combining LME price data, curated news, FinBERT sentiment features, and PPO trading-bot decision overlays.
img: assets/images/research/agentic_trading_bots_thumbnail.png
importance: 2
category: industry
collection: research
author_profile: false
date: 2026-04-15
github: https://github.com/andalenavals/agentic-trading-bots/
demo: https://andalenavals.github.io/agentic-trading-bots/
docs: https://andalenavals.github.io/agentic-trading-bots/docs/
---

The **Agentic Trading Bots** project is a local-first commodity decision-support dashboard for exploring market signals and trained trading-bot behavior. It combines LME copper, nickel, and aluminium price data with curated commodity news, generated sentiment features, and saved PPO agent decisions.

The project is designed as a compact MVP that still keeps the data pipeline, analytics layer, interface, and reinforcement-learning modules separate. Raw CSV snapshots live in the repository, while sentiment-enriched datasets, training files, and agent outputs can be regenerated from repeatable commands.

## Links

- <a href="https://andalenavals.github.io/agentic-trading-bots/" data-analytics-event="project_demo_click" data-link-type="demo" data-project="Agentic Trading Bots">Interactive demo</a>
- <a href="https://github.com/andalenavals/agentic-trading-bots/" data-analytics-event="project_github_click" data-link-type="github" data-project="Agentic Trading Bots">GitHub repository</a>
- <a href="https://andalenavals.github.io/agentic-trading-bots/docs/" data-analytics-event="project_docs_click" data-link-type="docs" data-project="Agentic Trading Bots">Sphinx documentation</a>

## What It Shows

The dashboard has two complementary layers:

- **Market and news context**, with commodity cards, price charts, sentiment summaries, normalized relative-performance comparisons, and market-event feeds.
- **Trading bots gym**, with PPO hold, buy, and sell decisions overlaid on price time series using marker size and opacity to communicate model confidence.

The chart interaction is built for inspection rather than prediction theater. Selecting a point in the price series opens the linked news context for that date and commodity, making it easier to connect market movement, event summaries, and sentiment scores.

## Agentic Layer

The agent modules are configuration-driven. Single-asset PPO trains one policy per commodity, while the multi-asset agent uses a shared policy across aluminium, copper, and nickel. Both emit per-step actions and diagnostics that the dashboard can discover dynamically from generated output files.

The browser demo does not retrain agents. Instead, it visualizes saved PPO evaluation outputs, including the selected action, greedy action, hold/buy/sell probabilities, confidence, entropy, reward, net worth, and position when available.

## Architecture

The repository separates responsibilities across a small set of layers:

- Python preprocessing creates derived market, news, sentiment, and training datasets from raw CSV files.
- TypeScript data loaders and analytics helpers parse local files and compute dashboard-ready signals.
- React/Next.js components render commodity cards, charts, event feeds, and the trading bots gym.
- Sphinx documentation is deployed next to the interactive demo.

This modular shape keeps the first useful slice easy to run locally while leaving room for future additions such as forecasting services, policy simulation, or richer agent evaluation.
