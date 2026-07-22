# Changelog

Todas as mudanças notáveis neste repositório serão documentadas neste arquivo.

O formato é baseado em [Keep a Changelog](https://keepachangelog.com/pt-BR/1.1.0/),
e este projeto adere ao [Semantic Versioning](https://semver.org/lang/pt-BR/).

---

## [1.0.0] - 2026-07-21

### Adicionado

- **FASE 1 — Bootstrap do Workspace**
  - Estrutura de diretórios completa (23+ pastas)
  - `opencode.json` — configuração central do OpenCode
  - `AGENTS.md` — instrução global para todos os agents
  - `LICENSE` — MIT
  - `.gitignore` e `.gitattributes`
  - `CHANGELOG.md`
  - Sistema de ADRs em `docs/architecture/adr/`
  - ADR-0001: Arquitetura do Workspace Multi-Agent

- **FASE 2 — Agents (19 agents)**
  - 9 agents primários: workspace-architect, planner, architect, backend-engineer, frontend-engineer, qa-engineer, security-engineer, docs-engineer, git-engineer
  - 5 specialist agents: research, database-engineer, infra-engineer, reviewer, performance-engineer
  - 5 subagents: api-engineer, ui-engineer, a11y-engineer, test-engineer, data-engineer
  - Catálogo de agents em `agents/README.md`
  - Hierarquia de delegação documentada

- **FASE 3 — Skills + Documentação**
  - 12 skills customizadas: clean-code, architecture, testing, python, react, fastapi, typescript, git-workflow, security, documentation, performance, bmad-integration
  - 7 guias de documentação: instalação, uso, criar-agents, criar-skills, criar-workflows, configuração, evoluir-workspace
  - README.md profissional atualizado
  - Revisão e padronização completa da workspace
