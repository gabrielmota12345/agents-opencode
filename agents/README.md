# Agents — Catálogo

## Agents Primários (invocáveis diretamente)

| Agent | Arquivo | Papel |
| --- | --- | --- |
| Workspace Architect | `.opencode/agents/workspace-architect.md` | Infraestrutura e arquitetura do workspace |
| Planner | `.opencode/agents/planner.md` | Planejamento de projetos, épicos, stories |
| Architect | `.opencode/agents/architect.md` | Arquitetura técnica de sistemas |
| Backend Engineer | `.opencode/agents/backend-engineer.md` | Implementação de backend/APIs |
| Frontend Engineer | `.opencode/agents/frontend-engineer.md` | Implementação de frontend/UI |
| QA Engineer | `.opencode/agents/qa-engineer.md` | Garantia de qualidade e testes |
| Security Engineer | `.opencode/agents/security-engineer.md` | Implementação de segurança |
| Docs Engineer | `.opencode/agents/docs-engineer.md` | Documentação técnica |
| Git Engineer | `.opencode/agents/git-engineer.md` | Git, CI/CD e releases |

## SubAgents (invocados por agents)

| Agent | Arquivo | Papel | Invocado por |
| --- | --- | --- | --- |
| Research | `.opencode/agents/research.md` | Pesquisa técnica e de mercado | Planner, Architect |
| Database Engineer | `.opencode/agents/database-engineer.md` | Banco de dados e queries | Architect, Backend |
| Infra Engineer | `.opencode/agents/infra-engineer.md` | Infraestrutura e DevOps | Architect, Git |
| Reviewer | `.opencode/agents/reviewer.md` | Revisão de código | Qualquer Engineer |
| Performance Engineer | `.opencode/agents/performance-engineer.md` | Performance e carga | QA, Backend |
| API Engineer | `.opencode/agents/api-engineer.md` | Implementação de APIs | Backend |
| UI Engineer | `.opencode/agents/ui-engineer.md` | Componentes UI | Frontend |
| A11y Engineer | `.opencode/agents/a11y-engineer.md` | Acessibilidade | Frontend, Reviewer |
| Test Engineer | `.opencode/agents/test-engineer.md` | Escrita de testes | QA, Engineers |
| Data Engineer | `.opencode/agents/data-engineer.md` | Pipelines de dados | Backend |

## Hierarquia de Delegação

```
User
├── workspace-architect (infraestrutura)
├── planner → research
├── architect → database-engineer, infra-engineer, security-engineer, research
├── backend-engineer → api-engineer, database-engineer, data-engineer, security-engineer
├── frontend-engineer → ui-engineer, a11y-engineer
├── qa-engineer → test-engineer, performance-engineer
├── security-engineer (autônomo)
├── docs-engineer (autônomo)
├── git-engineer → infra-engineer
└── reviewer (invocado por qualquer engineer)
```

## Regras de Delegação

1. Agents primários podem delegar para qualquer SubAgent
2. SubAgents NÃO delegam — executam tarefas diretamente
3. `research` é compartilhado por Planner e Architect
4. `reviewer` é compartilhado por todos os Engineers
5. Cada delegação deve ter contexto claro e objetivo definido
