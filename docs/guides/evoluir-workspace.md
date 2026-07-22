# Como Evoluir a Workspace

## Adicionar Novo Agent

1. Criar arquivo em `.opencode/agents/<nome>.md`
2. Definir frontmatter (description, mode, model, permission)
3. Escrever system prompt completo
4. Documentar em `agents/README.md`
5. Criar documentação em `agents/<categoria>/<nome>.md`

## Adicionar Nova Skill

1. Criar pasta em `.opencode/skills/<nome>/`
2. Criar `SKILL.md` com frontmatter
3. Documentar em `skills/README.md`
4. Criar documentação em `skills/<categoria>/<nome>.md`

## Adicionar Novo Workflow

1. Criar arquivo em `workflows/<fase>/<nome>.md`
2. Documentar trigger, agentes, steps, outputs
3. Incluir exemplo prático
4. Atualizar `workflows/README.md`

## Adicionar Novo Comando

1. Criar arquivo em `.opencode/commands/<nome>.md`
2. Definir frontmatter (description, agent, model)
3. Escrever template com `$ARGUMENTS`

## Adicionar Nova Referência

No `opencode.json`:

```json
{
  "references": {
    "minha-ref": {
      "path": "docs/minha-ref",
      "description": "Descrição da referência"
    }
  }
}
```

## Adicionar Plugin

1. Criar arquivo `.opencode/plugin/<nome>.ts`
2. Exportar função Plugin
3. Ou adicionar no `opencode.json`:

```json
{
  "plugin": ["meu-plugin"]
}
```

## Atualizar Config

1. Editar `opencode.json`
2. Seguir schema: `https://opencode.ai/config.json`
3. Reiniciar OpenCode

## Manter Compatibilidade

- Agents novos não devem sobrepor existentes
- Skills novas devem ter trigger keywords únicas
- Workflows devem referenciar agents existentes
- Documentação deve ser atualizada
- CHANGELOG deve ser atualizado

## Versionamento

- **Major**: breaking changes na arquitetura
- **Minor**: novos agents, skills, workflows
- **Patch**: correções e ajustes
