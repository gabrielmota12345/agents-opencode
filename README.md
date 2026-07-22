# agents-opencode

> Software Factory Multi-Agent baseada em [OpenCode](https://opencode.ai) com
> integração nativa ao [BMAD Method](https://bmadcode.com).

---

## Visão Geral

Uma workspace profissional para desenvolvimento de software dirigido por IA,
com 19 agents especializados, 12 skills customizadas, 46 skills BMAD e
workflows documentados para o ciclo completo de desenvolvimento.

## Arquitetura

```
agents-opencode/
├── .opencode/
│   ├── agents/          19 agents (9 primários + 10 specialist/subagents)
│   ├── skills/          12 skills customizadas
│   ├── commands/        46 comandos BMAD
│   └── plugins/         plugins locais
├── .agents/skills/      46 skills BMAD (auto-carregadas)
├── _bmad/               Engine BMAD v6.10.0
├── _bmad-output/        Artefatos gerados em runtime
├── agents/              Documentação dos agents
├── workflows/           Workflows multi-agent documentados
├── skills/              Documentação das skills
├── docs/                Documentação completa
│   ├── architecture/    ADRs e decisões arquiteturais
│   └── guides/          Guias de uso
├── examples/            Exemplos de uso
├── scripts/             Scripts utilitários
├── tests/               Testes do workspace
├── opencode.json        Configuração central
├── AGENTS.md            Instrução global para todos os agents
└── README.md            Este arquivo
```

## Agents

### Primários (invocáveis diretamente)

| Agent | Descrição |
|---|---|
| `/workspace-architect` | Infraestrutura e arquitetura do workspace |
| `/planner` | Planejamento de projetos, épicos, stories |
| `/architect` | Arquitetura técnica de sistemas |
| `/backend-engineer` | Implementação de backend e APIs |
| `/frontend-engineer` | Implementação de frontend e UI |
| `/qa-engineer` | Garantia de qualidade e testes |
| `/security-engineer` | Segurança e compliance |
| `/docs-engineer` | Documentação técnica |
| `/git-engineer` | Git, CI/CD e releases |

### Specialist e SubAgents

| Agent | Invocado por |
|---|---|
| `research` | Planner, Architect |
| `database-engineer` | Architect, Backend |
| `infra-engineer` | Architect, Git |
| `reviewer` | Qualquer Engineer |
| `performance-engineer` | QA, Backend |
| `api-engineer` | Backend |
| `ui-engineer` | Frontend |
| `a11y-engineer` | Frontend |
| `test-engineer` | QA |
| `data-engineer` | Backend |

## Skills

| Skill | Descrição |
|---|---|
| `/clean-code` | Princípios Clean Code, SOLID, DRY, KISS |
| `/architecture` | Padrões arquiteturais, ADRs |
| `/testing` | Estratégias de teste, pirâmide, TDD |
| `/python` | Convenções Python, PEP 8, type hints |
| `/react` | Componentes React, hooks, state management |
| `/fastapi` | FastAPI, routing, dependency injection |
| `/typescript` | TypeScript strict, types, generics |
| `/git-workflow` | Conventional commits, branches, PR flow |
| `/security` | OWASP, auth, encryption, secrets |
| `/documentation` | Padrões de documentação, ADRs |
| `/performance` | Cache, profiling, métricas, otimização |
| `/bmad-integration` | Integração com BMAD Method |

## Instalação

### Pré-requisitos

- [Node.js](https://nodejs.org/) 20+
- [Git](https://git-scm.com/)
- [uv](https://docs.astral.sh/uv/) (recomendado)

### Passos

```powershell
git clone git@github.com:gabrielmota12345/agents-opencode.git
cd agents-opencode
opencode
```

BMAD já vem pré-instalado. Para reinstalar:

```powershell
npx bmad-method install
```

### Verificação

```
/bmad-help
```

## Uso

### Criando uma feature

```
/planner Preciso de um sistema de autenticação JWT
```

```
/architect Projete a arquitetura de auth com refresh tokens
```

```
/backend-engineer Implemente os endpoints de login
```

```
/qa-engineer Crie testes para o fluxo de autenticação
```

```
/reviewer Revise o código de autenticação
```

### Workflows disponíveis

| Workflow | Fase | Descrição |
|---|---|---|
| `workflows/discovery/` | Descoberta | Ideação → Brief → PRD |
| `workflows/planning/` | Planejamento | PRD → Arquitetura → Stories |
| `workflows/implementation/` | Implementação | Story → Dev → Review → Tests |
| `workflows/review/` | Revisão | Code Review, QA, Adversarial |

## Documentação

| Documento | Descrição |
|---|---|
| [Instalação](docs/guides/instalacao.md) | Como instalar e configurar |
| [Uso](docs/guides/uso.md) | Como usar agents e skills |
| [Criar Agents](docs/guides/criar-agents.md) | Como criar novos agents |
| [Criar Skills](docs/guides/criar-skills.md) | Como criar novas skills |
| [Criar Workflows](docs/guides/criar-workflows.md) | Como criar novos workflows |
| [Configuração](docs/guides/configuracao.md) | Como alterar modelos e permissões |
| [Evoluir Workspace](docs/guides/evoluir-workspace.md) | Como expandir a workspace |
| [ADRs](docs/architecture/adr/) | Decisões arquiteturais |

## Roadmap

| Fase | Escopo | Status |
|---|---|---|
| 1 | Bootstrap do Workspace | Concluída |
| 2 | Criação dos Agents (19) | Concluída |
| 3 | Skills + Documentação + Finalização | Concluída |

### Futuro

- [ ] Plugins customizados
- [ ] MCP servers
- [ ] Mais workflows automatizados
- [ ] Dashboard de agents
- [ ] Testes E2E do workspace

## Contribuição

1. Fork o repositório
2. Criar branch: `git checkout -b feat/nome-da-feature`
3. Seguir convenções em `AGENTS.md`
4. Criar ADR se necessário
5. Abrir PR com descrição clara

### Guias de Contribuição

- [Como criar Agents](docs/guides/criar-agents.md)
- [Como criar Skills](docs/guides/criar-skills.md)
- [Como criar Workflows](docs/guides/criar-workflows.md)

## Licença

Distribuído sob a licença MIT. Veja [LICENSE](LICENSE).

## Links

- OpenCode: <https://opencode.ai>
- BMAD Method: <https://bmadcode.com>
- Repositório: <https://github.com/gabrielmota12345/agents-opencode>
