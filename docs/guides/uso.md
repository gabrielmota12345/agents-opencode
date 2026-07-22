# Guia de Uso

## Agents Disponíveis

### Invocação Direta (agents primários)

No OpenCode, invocando um agent:

```
/workspace-architect [descrição da tarefa]
/planner [descrição da tarefa]
/architect [descrição da tarefa]
/backend-engineer [descrição da tarefa]
/frontend-engineer [descrição da tarefa]
/qa-engineer [descrição da tarefa]
/security-engineer [descrição da tarefa]
/docs-engineer [descrição da tarefa]
/git-engineer [descrição da tarefa]
```

### Delegação Automática

Os agents primários delegam automaticamente para SubAgents quando necessário:

- **Planner** → research (para pesquisa)
- **Architect** → database-engineer, infra-engineer, security-engineer
- **Backend** → api-engineer, database-engineer, data-engineer
- **Frontend** → ui-engineer, a11y-engineer
- **QA** → test-engineer, performance-engineer

### Skills Disponíveis

```
/clean-code       - Princípios de código limpo
/architecture     - Padrões arquiteturais
/testing          - Estratégias de teste
/python           - Convenções Python
/react            - Convenções React
/fastapi          - Convenções FastAPI
/typescript       - Convenções TypeScript
/git-workflow     - Boas práticas Git
/security         - Segurança
/documentation    - Padrões de documentação
/performance      - Otimização de performance
/bmad-integration - Integração com BMAD
```

### Comandos BMAD

```
/bmad-help                    - Ajuda do BMAD
/bmad-forge-idea              - Forjar ideia
/bmad-create-prd              - Criar PRD
/bmad-create-architecture     - Criar arquitetura
/bmad-create-epics-and-stories - Criar épicos/stories
/bmad-dev-story               - Desenvolver story
/bmad-code-review             - Revisão de código
/bmad-qa-generate-e2e-tests   - Gerar testes E2E
```

## Exemplo de Uso

### Criando uma nova feature

1. **Planner** planeja a feature:
   ```
   /planner Preciso de um sistema de autenticação JWT para minha API
   ```

2. **Architect** projeta a arquitetura:
   ```
   /architect Projete a arquitetura de autenticação com JWT e refresh tokens
   ```

3. **Backend Engineer** implementa:
   ```
   /backend-engineer Implemente os endpoints de login e refresh token
   ```

4. **QA Engineer** testa:
   ```
   /qa-engineer Crie testes para o fluxo de autenticação
   ```

5. **Reviewer** revisa:
   ```
   /reviewer Revise o código de autenticação
   ```

## Workflows

Workflows estão documentados em `workflows/`:
- `workflows/discovery/` — Ideação → Brief → PRD
- `workflows/planning/` — PRD → Arquitetura → Stories
- `workflows/implementation/` — Story → Dev → Review → Tests
- `workflows/review/` — Code Review, QA, Adversarial
