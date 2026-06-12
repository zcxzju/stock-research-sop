# stock-research-sop

A Codex skill for turning stock or sector ideas into a structured research workflow.

中文说明：这是一个用于把股票、公司或赛道想法整理成结构化研究流程的 Codex skill。

It organizes equity research into four stages:

- monthly chokepoint screening
- quarterly financial review
- pre-buy red-team falsification
- holding-period milestone monitoring

Each full output ends with a compact Mermaid diagram that visualizes the screening, verification, red-team, and monitoring decision path.

## GitHub Pages

This repository includes a bilingual Chinese/English landing page at [docs/index.html](./docs/index.html).

After pushing the files to GitHub, enable it in:

```text
Settings -> Pages -> Build and deployment -> Source: Deploy from a branch -> main /docs
```

The page will be available at:

```text
https://zcxzju.github.io/stock-research-sop/
```

## Usage

```text
Use $stock-research-sop to turn a stock idea into a structured screening, review, red-team, and monitoring workflow.
```

## Files

- [SKILL.md](./SKILL.md): the skill instructions
- [agents/openai.yaml](./agents/openai.yaml): UI metadata
- [docs/index.html](./docs/index.html): bilingual GitHub Pages page

> Research organization only. Not investment advice.
