# 🛡️ OSS Maintainer Copilot

<div align="center">

[![GitHub Action](https://img.shields.io/badge/GitHub-Action-blue?logo=github)](https://github.com/features/actions)
[![Python](https://img.shields.io/badge/Python-3.11+-brightgreen.svg)](https://www.python.org/)
[![License](https://img.shields.io/badge/License-MIT-purple.svg)](https://opensource.org/licenses/MIT)
[![OpenAI Grant Target](https://img.shields.io/badge/Target-OSS%20Maintainer%20Automation-orange.svg)]()

[**中文**](#-中文说明) | [**English**](#-english-documentation)

*AI-Powered GitHub Action for Open-Source Maintainers: Automated PR Reviews, Issue Triaging, and Release Workflows.*  
*专为开源维护者打造的 AI GitHub Action：全自动 PR 代码审查、Issue 分流与发布管理。*

</div>

---

## 🎯 The Problem This Solves (解决的痛点)

Open-source maintainers face a massive burden of daily operations. Reviewing Pull Requests, categorizing endless issues, and maintaining release logs are the major bottlenecks in the OSS ecosystem. **OSS Maintainer Copilot** is built to automate these workflows using LLMs, explicitly targeting the real-world scenarios outlined by the OpenAI Open Source Grant.

开源项目的维护者每天都被繁琐的工单（Issue）和代码审查（PR）淹没。**OSS Maintainer Copilot** 利用 AI 自动化处理这些痛点，完美契合“日常编码、问题分流、代码审查、维护者工作流等真实 OSS 场景”。

## ✨ Core Features (核心功能)

1.  🔍 **Automated PR Code Review (智能代码审查)**
    *   Automatically fetch PR diffs and provide inline line-by-line feedback.
    *   Identify potential security vulnerabilities and performance bottlenecks before merging.
2.  🏷️ **Smart Issue Triaging (自动工单分流)**
    *   Automatically read newly opened issues, assign proper labels (`bug`, `enhancement`, `documentation`), and detect duplicates.
3.  🚀 **Release Notes Generation (自动化发布日志)**
    *   Summarize merged PRs and closed issues to generate professional changelogs and release notes automatically.

## 🛠️ Usage (如何使用)

To use this action in your repository, create a workflow file `.github/workflows/ai-maintainer.yml`:

```yaml
name: AI Maintainer Automation

on:
  pull_request:
    types: [opened, synchronize]
  issues:
    types: [opened]

jobs:
  ai_review_and_triage:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout Code
        uses: actions/checkout@v4
      
      - name: Run OSS Maintainer Copilot
        uses: qwbwj3/oss-maintainer-copilot@v1
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          llm_api_key: ${{ secrets.OPENAI_API_KEY }}
          mode: 'pr_review' # or 'issue_triage'
```

## 🔐 Security & Reliability (安全与可靠性)

*   **Stateless Execution**: Runs entirely within GitHub Actions runners. No code is stored externally.
*   **Security Focused**: Emphasizes identifying security flaws in incoming PRs to protect repository integrity.
*   **Opt-in Automation**: Maintainers have full control over which repositories enable the bot.

---
*Built for the Open Source Ecosystem.*