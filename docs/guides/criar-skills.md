# Como Criar Novas Skills

## Visão Geral

Skills são definidas em `.opencode/skills/<nome>/SKILL.md` com frontmatter YAML e instruções em markdown.

## Estrutura do Arquivo

```markdown
---
name: nome-da-skill
description: "Use when [quando ativada]. Trigger keywords: [palavras-gatilho]."
---

# Nome da Skill

## Seção 1
[Instruções]

## Seção 2
[Exemplos]

## Checklist
- [ ] Item 1
- [ ] Item 2
```

## Passos

### 1. Criar diretório
```powershell
New-Item -ItemType Directory -Path ".opencode/skills/minha-skill" -Force
```

### 2. Criar SKILL.md
```powershell
New-Item -ItemType File -Path ".opencode/skills/minha-skill/SKILL.md" -Force
```

### 3. Escrever frontmatter
- `name`: kebab-case, deve corresponder ao nome da pasta
- `description`: "Use when..." ou "Use ONLY when..." com palavras-gatilho

### 4. Escrever corpo da skill
- Instruções claras e acionáveis
- Exemplos práticos
- Checklist quando aplicável
- Referências para outros recursos

### 5. Documentar
- Adicionar ao `skills/README.md`
- Criar documentação em `skills/<categoria>/<nome>.md`

## Regras

- **Uma skill = uma responsabilidade** — não misturar concerns
- **Kebab-case** para nome e pasta
- **Description é crucial** — sem ela a skill não é surfada
- **Palavras-gatilho** na description para detecção automática
- **Corpo em markdown** — instruções, não código executável

## Template Básico

```markdown
---
name: minha-skill
description: "Use when [contexto]. Trigger keywords: [palavras]."
---

# Minha Skill

## O que faz
[Descrição]

## Quando usar
- [Caso 1]
- [Caso 2]

## Como usar
1. [Passo 1]
2. [Passo 2]

## Exemplos
```[exemplo]```

## Checklist
- [ ] Item 1
- [ ] Item 2
```
