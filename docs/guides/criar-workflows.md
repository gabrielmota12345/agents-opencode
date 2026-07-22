# Como Criar Novos Workflows

## Visão Geral

Workflows são documentados em markdown em `workflows/<fase>/<workflow>.md`. Eles descrevem processos multi-agent: triggers, agentes envolvidos, inputs, steps e outputs.

## Estrutura do Arquivo

```markdown
# Workflow: [Nome]

## Trigger
[Quando este workflow é ativado]

## Agentes Envolvidos
- **Agent 1**: [papel]
- **Agent 2**: [papel]

## Inputs
- [Input 1]: [descrição]
- [Input 2]: [descrição]

## Steps

### 1. [Nome do Step]
**Agent:** [qual agent executa]
**Ação:** [o que fazer]
**Output:** [o que gerar]

### 2. [Nome do Step]
...

## Outputs
- [Output 1]: [descrição]
- [Output 2]: [descrição]

## Exemplo
[Exemplo de execução completa]
```

## Passos

### 1. Identificar o fluxo
- Qual problema o workflow resolve?
- Quais agents participam?
- Qual a sequência de steps?

### 2. Criar arquivo
```powershell
New-Item -ItemType File -Path "workflows/discovery/meu-workflow.md" -Force
```

### 3. Documentar
- Trigger claro e específico
- Cada step com agent responsável
- Inputs e outputs documentados
- Exemplo prático

## Fases de Workflows

| Fase | Pasta | Exemplos |
|---|---|---|
| Discovery | `workflows/discovery/` | Ideação, Brief, PRD |
| Planning | `workflows/planning/` | Arquitetura, Épicos, Stories |
| Implementation | `workflows/implementation/` | Dev, Review, Test |
| Review | `workflows/review/` | Code Review, QA, Adversarial |

## Regras

- **Um workflow = um fluxo completo** — não fragmentar
- **Documentar em PT-BR**
- **Incluir exemplo prático**
- **Referenciar agents por nome**
- **Outputs claros e acionáveis**

## Exemplo: Workflow de Feature

```markdown
# Workflow: Nova Feature

## Trigger
Solicitação de nova funcionalidade pelo usuário

## Agentes Envolvidos
- **Planner**: planeja a feature
- **Architect**: projeta arquitetura
- **Backend Engineer**: implementa backend
- **Frontend Engineer**: implementa frontend
- **QA Engineer**: testa
- **Reviewer**: revisa

## Steps

### 1. Planejamento
**Agent:** Planner
**Ação:** Analisar requisitos, criar épicos e stories
**Output:** `_bmad-output/planning-artifacts/`

### 2. Arquitetura
**Agent:** Architect
**Ação:** Projetar design técnico
**Output:** `_bmad-output/planning-artifacts/`

### 3. Implementação
**Agent:** Backend + Frontend Engineers
**Ação:** Implementar código
**Output:** Código fonte no projeto

### 4. Testes
**Agent:** QA Engineer
**Ação:** Escrever e executar testes
**Output:** `tests/`

### 5. Revisão
**Agent:** Reviewer
**Ação:** Revisar código
**Output:** Relatório de revisão
```
