---
layout: page
title: "Agentic Job Search"
description: A CLI automation tool for multi-source job collection, link verification, profile-based ranking, and optional curated email delivery.
img: assets/images/research/agentic_job_search_thumbnail.png
importance: 4
category: industry
collection: research
author_profile: false
date: 2026-04-22
github: https://github.com/andalenavals/agentic-job-search/
docs: https://andalenavals.github.io/agentic-job-search/
---

**Agentic Job Search** is a CLI automation project for collecting job postings across multiple public sources, checking which links resolve to likely official application pages, ranking jobs against a candidate profile, and optionally sending curated email digests.

The project combines two complementary workflows: a standard search mode for likely official links and a debug-verification mode that fetches live pages, records redirect and reachability behavior, extracts richer job text, and produces detailed reports plus links-only action summaries.

## Links

- <a href="https://github.com/andalenavals/agentic-job-search/" data-analytics-event="project_github_click" data-link-type="github" data-project="Agentic Job Search">GitHub repository</a>
- <a href="https://andalenavals.github.io/agentic-job-search/" data-analytics-event="project_docs_click" data-link-type="docs" data-project="Agentic Job Search">Project documentation</a>

## What It Does

The package can:

- search multiple public job sources from one command
- filter down to links that look like official application targets
- verify link quality source by source in debug mode
- extract job descriptions from source data or resolved pages
- rank verified jobs with semantic matching and optional local Ollama scoring
- produce Markdown or CSV output, detailed reports, action-only reports, and optional email digests

This turns a repetitive, noisy workflow into something auditable and easier to operationalize.

## Operating Model

The tool is especially strong when used with a candidate profile. In that mode it can score job matches, sort reports by fit or freshness, and keep the email/report output aligned with the same ranked selection logic.

Helper scripts layer on top of the core CLI for recurring digests, including newest-first and top-match email flows, while preserving useful local artifacts even when SMTP delivery is skipped or fails.

## Source Coverage

The project already supports a broad mix of public job boards and company-board integrations, including Greenhouse, Lever, Ashby, Personio, SmartRecruiters, and Workday, plus a wider source catalog for public boards and remote-search flows.
