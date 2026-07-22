# Workflows

Workflows multi-agent documentados em markdown.

## Estrutura

| Pasta | Descrição |
| --- | --- |
| `discovery/` | Ideação → Brief → PRD |
| `planning/` | PRD → Arquitetura → Épicos/Stories |
| `implementation/` | Story → Dev → Review → Testes |
| `review/` | Code Review, QA, Revisão Adversarial |

## Formato

Cada workflow é um arquivo `.md` que documenta:

- **Trigger**: quando este workflow é ativado
- **Agentes envolvidos**: quais agents participam
- **Inputs**: artefatos de entrada necessários
- **Steps**: sequência de passos executados
- **Outputs**: artefatos gerados
