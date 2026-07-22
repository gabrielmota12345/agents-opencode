# Instrução Global — AGENTS.md

> Este arquivo é lido automaticamente por **todos** os agents do opencode.
> Ele define convenções, regras e contexto que valem para qualquer sessão.

---

## 🎯 Propósito do workspace

Esta é uma **Software Factory Multi-Agent**. Cada agent tem um papel definido
dentro de um ciclo de desenvolvimento completo: descoberta → planejamento →
implementação → revisão → entrega.

---

## 📁 Convenções de diretórios

| Caminho | O que contém | Quando usar |
| --- | --- | --- |
| `.opencode/agents/` | Definição dos agents (runtime) | Definir agents do opencode |
| `.opencode/skills/` | Skills próprias do projeto | Criar skills customizadas |
| `.opencode/commands/` | Comandos do opencode | Criar comandos `/meu-comando` |
| `.opencode/plugins/` | Plugins locais | Integrar plugins custom |
| `.agents/skills/` | Skills BMAD (external) | NÃO editar — auto-carregadas |
| `_bmad/` | Engine BMAD | NÃO editar — instalado pelo BMAD |
| `_bmad-output/` | Artefatos BMAD gerados | Leitura e escrita durante workflows |
| `agents/` | Fonte humana dos agents | Documentar e descrever agents |
| `workflows/` | Definições de workflows | Documentar processos multi-agent |
| `skills/` | Fonte humana das skills | Documentar e descrever skills |
| `docs/` | Documentação do workspace | Guides, ADRs, referências |
| `examples/` | Exemplos de uso | Demonstrar padrões e templates |
| `scripts/` | Scripts utilitários | Automatizar tarefas do repo |
| `tests/` | Testes do workspace | Testar configs e estruturas |

---

## 🤖 Convenções de Agents

### Definição

- Agents são definidos em `.opencode/agents/<nome>.md`
- A fonte humana (descrição detalhada, decisões de design) fica em
  `agents/<categoria>/<nome>.md`
- Cada agent deve ter um **papel único** — não duplicar responsabilidades

### Categorias de agents

| Categoria | Pasta | Descrição |
| --- | --- | --- |
| Core | `agents/core/` | PM, Architect, Dev, QA — papéis centrais |
| Specialist | `agents/specialist/` | UX, Tech Writer, Researcher — domínio específico |
| Orchestration | `agents/orchestration/` | Roteadores e orquestradores de workflow |

### Formato do arquivo `.opencode/agents/<nome>.md`

```markdown
---
description: Descrição curta do que o agent faz.
mode: subagent | primary | all
model: anthropic/claude-sonnet-4-6
---

Você é um [papel]. Sua responsabilidade é [escopo].
...
```

### Regras

1. **Nunca inventar nomes** — seguir o padrão kebab-case (`code-reviewer`, não
   `codeReviewer`)
2. **Um agent = um arquivo** — não empilhar múltiplos agents no mesmo `.md`
3. **Prompt claro** — o body do `.md` é o prompt; ser específico e acionável
4. **Sem chaves no body** — o YAML frontmatter só aceita campos conhecidos

---

## 📝 Convenções de Skills

### Localização

- Skills do projeto: `.opencode/skills/<nome>/SKILL.md`
- Documentação de skills: `skills/<categoria>/<nome>.md`

### Formato do `SKILL.md`

```markdown
---
name: minha-skill
description: Uma frase descrevendo o que a skill faz E quando ativá-la.
---

# Minha Skill

( corpo da skill em markdown )
```

### Regras

1. O `name` deve ser kebab-case e correspond ao nome da pasta
2. A `description` deve incluir palavras-gatilho e "Use when..." / "Use ONLY
   when..."
3. Cada skill fica em sua própria pasta com possíveis assets/referências

---

## 🔄 Convenções de Workflows

- Formato: **markdown puro** (auditable, simples)
- Localização: `workflows/<fase>/<workflow>.md`
- Cada workflow documenta: trigger, agentes envolvidos, inputs, steps, outputs
- Workflows são **documentação viva** — não executáveis diretamente

---

## 🌐 Idioma

- **Todo o conteúdo** é escrito em **Português-BR (PT-BR)**
- Inglês técnico é permitido para: nomes de ferramentas, comandos, IDs,
  e termos consagrados (agent, workflow, skill, etc.)

---

## ⚡ Regras gerais

1. **Não alterar `_bmad/`** — é o engine; qualquer mudança deve ser feita via
   `npx bmad-method install` ou update
2. **Artefatos em `_bmad-output/`** são efêmeros — podem ser regenerados
3. **ADRs** devem ser registrados em `docs/architecture/adr/` para qualquer
   decisão significativa de arquitetura
4. **Antes de criar um novo agent/skill**, verificar se já existe um equivalente
   nas skills BMAD (`.agents/skills/`)
5. **Seguir o schema do opencode** — config em `opencode.json` deve seguir
   `https://opencode.ai/config.json`
