# Skills — Catálogo

## Skills do Workspace

| Skill | Pasta | Descrição |
|---|---|---|
| clean-code | `.opencode/skills/clean-code/` | Princípios Clean Code, SOLID, DRY, KISS |
| architecture | `.opencode/skills/architecture/` | Padrões arquiteturais, ADRs, decisões |
| testing | `.opencode/skills/testing/` | Estratégias de teste, pirâmide, TDD |
| python | `.opencode/skills/python/` | Convenções Python, PEP 8, type hints |
| react | `.opencode/skills/react/` | Componentes React, hooks, state management |
| fastapi | `.opencode/skills/fastapi/` | FastAPI, routing, dependency injection |
| typescript | `.opencode/skills/typescript/` | TypeScript strict, types, generics |
| git-workflow | `.opencode/skills/git-workflow/` | Conventional commits, branches, PR flow |
| security | `.opencode/skills/security/` | OWASP, auth, encryption, secrets |
| documentation | `.opencode/skills/documentation/` | Padrões de documentação, ADRs, READMEs |
| performance | `.opencode/skills/performance/` | Cache, profiling, métricas, otimização |
| bmad-integration | `.opencode/skills/bmad-integration/` | Integração com BMAD Method |

## Como usar

1. As skills são carregadas automaticamente pelo OpenCode
2. Invocar via `/nome-da-skill` no terminal
3. Ou deixar o agent detectar automaticamente pelo contexto

## Como criar nova skill

1. Criar pasta em `.opencode/skills/<nome>/`
2. Criar `SKILL.md` com frontmatter obrigatório
3. Adicionar `name` e `description` no frontmatter
4. Documentar no `skills/README.md`
