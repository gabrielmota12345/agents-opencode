# Agents — Catálogo

## Agents Primários (invocáveis diretamente)

| Agent | Arquivo | Papel |
| --- | --- | --- |
| Workspace Architect | `.opencode/agents/workspace-architect.md` | Infraestrutura e arquitetura do workspace |
| Planner | `.opencode/agents/planner.md` | Planejamento de projetos, épicos, stories |
| Solution Architect | `.opencode/agents/architect.md` | Arquitetura técnica e trade-offs |
| Product Manager | `.opencode/agents/product-manager.md` | Valor de negócio e critérios de aceite |
| Backend Engineer | `.opencode/agents/backend-engineer.md` | Lógica de negócio e integrações |
| Frontend Engineer | `.opencode/agents/frontend-engineer.md` | Estado, rotas, integração com API |
| API Engineer | `.opencode/agents/api-engineer.md` | Contratos, versionamento, OpenAPI |
| UI Engineer | `.opencode/agents/ui-engineer.md` | Componentes UI reutilizáveis |
| A11y Engineer | `.opencode/agents/a11y-engineer.md` | Acessibilidade e WCAG |
| Test Engineer | `.opencode/agents/test-engineer.md` | Escrita de testes (unit/integration/E2E) |
| Data Engineer | `.opencode/agents/data-engineer.md` | Pipelines ETL e qualidade de dados |
| QA Engineer | `.opencode/agents/qa-engineer.md` | Critérios de gate e priorização de bugs |
| Security Engineer | `.opencode/agents/security-engineer.md` | Segurança e compliance |
| Documentation Engineer | `.opencode/agents/docs-engineer.md` | Documentação técnica |
| Git Engineer | `.opencode/agents/git-engineer.md` | Git, CI/CD e releases |
| AI Engineer | `.opencode/agents/ai-engineer.md` | IA, prompts, RAG, fine-tuning |
| Workflow Orchestrator | `.opencode/agents/workflow-orchestrator.md` | Orquestração de workflows |

## Specialist Agents

| Agent | Arquivo | Papel | Invocado por |
| --- | --- | --- | --- |
| Research Engineer | `.opencode/agents/research.md` | Pesquisa técnica e de mercado | Planner, Architect |
| Database Engineer | `.opencode/agents/database-engineer.md` | Schema, migrations, queries | Architect, Backend |
| DevOps Engineer | `.opencode/agents/infra-engineer.md` | Infraestrutura e DevOps | Architect, Git |
| Code Reviewer | `.opencode/agents/reviewer.md` | Revisão de código | Qualquer Engineer |
| Performance Engineer | `.opencode/agents/performance-engineer.md` | Performance e carga | QA, Backend |
| Refactoring Engineer | `.opencode/agents/refactoring-engineer.md` | Refatoração segura | Qualquer Engineer |
| Release Manager | `.opencode/agents/release-manager.md` | Gestão de releases | Git Engineer |
| Session Reporter | `.opencode/agents/session-reporter.md` | Relatórios de sessão | Qualquer Agent |

## Hierarquia de Delegação

```
User
├── workspace-architect (infraestrutura + CHANGELOG workspace)
├── planner → research-engineer (tarefa 3+ domínios = epic paralelo)
├── solution-architect → database-engineer, devops-engineer, security-engineer, research-engineer (ADR obrigatório)
├── product-manager (fecha loop pós-entrega)
├── backend-engineer → database-engineer, security-engineer (foca em lógica de negócio)
├── frontend-engineer → state-engineer (foca em estado e integração)
├── api-engineer (contratos, versionamento, OpenAPI)
├── ui-engineer (componentes reutilizáveis)
├── a11y-engineer (gate obrigatório)
├── test-engineer (pirâmide de teste, flaky = bug)
├── data-engineer (ETL, qualidade de dado em trânsito)
├── qa-engineer (critério de gate, priorização de bug)
├── security-engineer (escala de severidade)
├── documentation-engineer (auditoria periódica)
├── git-engineer → devops-engineer, release-manager (changelog automático)
├── ai-engineer (custo por chamada formal)
├── code-reviewer (SLA de revisão)
├── refactoring-engineer (gatilho automático)
├── performance-engineer (baseline salvo)
├── release-manager (checklist fechado)
├── session-reporter (linka ADRs)
└── workflow-orchestrator (hierarquia de conflito)
```

## Regras de Delegação

1. Agents primários podem delegar para specialist agents
2. Specialist agents NÃO delegam — executam tarefas diretamente
3. `research-engineer` é compartilhado por Planner e Solution Architect
4. `code-reviewer` é compartilhado por todos os Engineers
5. `workflow-orchestrator` coordena todos os Agents
6. Cada delegação deve ter contexto claro e objetivo definido
7. Security tem prioridade sobre Performance em caso de empate
