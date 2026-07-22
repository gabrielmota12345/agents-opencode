# Como Criar Novos Agents

## Visão Geral

Agents são definidos em `.opencode/agents/<nome>.md` com frontmatter YAML e um system prompt em markdown.

## Estrutura do Arquivo

```markdown
---
description: "Descrição curta do que o agent faz."
mode: primary | subagent | all
model: anthropic/claude-sonnet-4-6
permission:
  edit: allow
  read: allow
  bash: allow
---

# Nome do Agent

Você é o **Nome**, o agente de [domínio] desta Software Factory.

## Papel
[Descrição do papel]

## Responsabilidades
1. [Responsabilidade 1]
2. [Responsabilidade 2]

## Limites
- **NÃO** [limite 1]
- **NÃO** [limite 2]

## Contexto
[Contexto de operação]

## Permissões
[Permissões detalhadas]

## Ferramentas
[Ferramentas disponíveis]

## Melhores Práticas
1. [Prática 1]
2. [Prática 2]

## Regras
1. [Regra 1]
2. [Regra 2]

## SubAgents Disponíveis
- `nome-do-subagent` — descrição

## Integração com AGENTS.md
Segue convenções de `AGENTS.md`.
```

## Passos

### 1. Definir o papel
- Qual problema o agent resolve?
- Quem o invoca?
- Quais são seus limites?

### 2. Criar o arquivo
```powershell
New-Item -ItemType File -Path ".opencode/agents/meu-agent.md" -Force
```

### 3. Escrever o frontmatter
- `description`: uma frase clara e acionável
- `mode`: `primary` (invocável pelo user) ou `subagent` (invocado por agents)
- `permission`: permissões mínimas necessárias

### 4. Escrever o system prompt
- Papel claro e específico
- Responsabilidades numeradas
- Limites explícitos
- Contexto operacional
- Regras e melhores práticas

### 5. Documentar
- Adicionar ao `agents/README.md`
- Criar documentação em `agents/<categoria>/<nome>.md`

## Regras

- **Um agent = um papel único** — não sobrepor responsabilidades
- **Kebab-case** para nomes de arquivo
- **SubAgents não delegam** — executam tarefas diretamente
- **Permissões mínimas** — dar apenas o necessário
- **Sempre documentar** no `agents/README.md`

## Exemplo Rápido

```markdown
---
description: "Traduz documentação técnica para PT-BR."
mode: subagent
---

# Translator

Você é o **Translator**, responsável por traduzir documentação técnica.

## Responsabilidades
1. Traduzir READMEs e guias para PT-BR
2. Manter termos técnicos em inglês
3. Garantir qualidade da tradução

## Regras
- Termos técnicos permanecem em inglês
- Tradução natural, não literal
```
