# Agents — Catálogo

## Agents Primários (invocáveis diretamente)

| Agent | Arquivo | Papel |
| --- | --- | --- |
| Workspace Architect | `.opencode/agents/workspace-architect.md` | Infraestrutura e arquitetura do workspace |
| Planner | `.opencode/agents/planner.md` | Planejamento de projetos, épicos, stories |
| Solution Architect | `.opencode/agents/architect.md` | Arquitetura técnica e trade-offs |
| Product Manager | `.opencode/agents/product-manager.md` | Valor de negócio e critérios de aceite |
| Backend Engineer | `.opencode/agents/backend-engineer.md` | Implementação de backend/APIs |
| Frontend Engineer | `.opencode/agents/frontend-engineer.md` | Implementação de frontend/UI |
| QA Engineer | `.opencode/agents/qa-engineer.md` | Garantia de qualidade e testes |
| Security Engineer | `.opencode/agents/security-engineer.md` | Segurança e compliance |
| Documentation Engineer | `.opencode/agents/docs-engineer.md` | Documentação técnica |
| Git Engineer | `.opencode/agents/git-engineer.md` | Git, CI/CD e releases |
| AI Engineer | `.opencode/agents/ai-engineer.md` | IA, prompts, RAG, fine-tuning |
| Workflow Orchestrator | `.opencode/agents/workflow-orchestrator.md` | Orquestração de workflows |

## Specialist Agents (invocados por agents)

| Agent | Arquivo | Papel | Invocado por |
| --- | --- | --- | --- |
| Research Engineer | `.opencode/agents/research.md` | Pesquisa técnica e de mercado | Planner, Architect |
| Database Engineer | `.opencode/agents/database-engineer.md` | Banco de dados e queries | Architect, Backend |
| DevOps Engineer | `.opencode/agents/infra-engineer.md` | Infraestrutura e DevOps | Architect, Git |
| Code Reviewer | `.opencode/agents/reviewer.md` | Revisão de código | Qualquer Engineer |
| Performance Engineer | `.opencode/agents/performance-engineer.md` | Performance e carga | QA, Backend |
| Refactoring Engineer | `.opencode/agents/refactoring-engineer.md` | Refatoração segura | Qualquer Engineer |
| Release Manager | `.opencode/agents/release-manager.md` | Gestão de releases | Git Engineer |
| Session Reporter | `.opencode/agents/session-reporter.md` | Relatórios de sessão | Qualquer Agent |

## SubAgents (invocados por agents específicos)

| Agent | Arquivo | Papel | Invocado por |
| --- | --- | --- | --- |
| API Engineer | `.opencode/agents/api-engineer.md` | Implementação de APIs | Backend |
| UI Engineer | `.opencode/agents/ui-engineer.md` | Componentes UI | Frontend |
| A11y Engineer | `.opencode/agents/a11y-engineer.md` | Acessibilidade | Frontend |
| Test Engineer | `.opencode/agents/test-engineer.md` | Escrita de testes | QA |
| Data Engineer | `.opencode/agents/data-engineer.md` | Pipelines de dados | Backend |

## Hierarquia de Delegação

```
User
├── workspace-architect (infraestrutura)
├── planner → research-engineer
├── solution-architect → database-engineer, devops-engineer, security-engineer, research-engineer
├── product-manager (valida valor de negócio)
├── backend-engineer → api-engineer, database-engineer, data-engineer, security-engineer
├── frontend-engineer → ui-engineer, a11y-engineer
├── qa-engineer → test-engineer, performance-engineer
├── security-engineer (autônomo)
├── documentation-engineer (autônomo)
├── git-engineer → devops-engineer, release-manager
├── ai-engineer (autônomo)
├── code-reviewer (invocado por qualquer engineer)
├── refactoring-engineer (invocado por qualquer engineer)
├── session-reporter (invocado por qualquer agent)
└── workflow-orchestrator (coordena todos)
```

## Regras de Delegação

1. Agents primários podem delegar para qualquer SubAgent
2. SubAgents NÃO delegam — executam tarefas diretamente
3. `research-engineer` é compartilhado por Planner e Solution Architect
4. `code-reviewer` é compartilhado por todos os Engineers
5. `workflow-orchestrator` coordena todos os Agents
6. Cada delegação deve ter contexto claro e objetivo definido
