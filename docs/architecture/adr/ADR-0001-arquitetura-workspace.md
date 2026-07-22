# ADR-0001: Arquitetura do Workspace Multi-Agent

**Status:** Aceito  
**Data:** 2026-07-21  
**Decisor:** GG + AI Workspace Architect

---

## Contexto

Este repositório (`agents-opencode`) precisa abrigar uma Software Factory
Multi-Agent baseada em OpenCode, com integração ao BMAD Method. As exigências
são:

1. Agents especializados com papéis claros (PM, Architect, Dev, QA, etc.)
2. Skills customizáveis que estendem as capacidades dos agents
3. Workflows documentados que orquestram a colaboração entre agents
4. Integração com o BMAD Method (46 skills + 46 comandos já instalados)
5. Convenções OpenCode (agents em `.opencode/agents/`, skills em
   `.opencode/skills/`, etc.)
6. Documentação viva: ADRs, guias, referências

## Decisão

Adotar uma arquitetura de **dupla camada** com separação entre **definição
runtime** (opencode) e **fonte humana** (documentação):

```
agents/            → documentação humana dos agents
.opencode/agents/  → definição runtime dos agents (.md com frontmatter)

skills/            → documentação humana das skills
.opencode/skills/  → definição runtime das skills (SKILL.md)

workflows/         → documentação de workflows (markdown puro)
```

### Princípios

1. **Convenção OpenCode primeiro** — seguir o schema do opencode para tudo
2. **Separação de interesses** — runtime vs documentação vs artefatos
3. **BMAD integration** — engine em `_bmad/`, output em `_bmad-output/`, skills
   auto-carregadas em `.agents/skills/`
4. **Docs-as-code** — ADRs, guias e referências versionados no Git
5. **Extensibilidade** — estrutura preparada para Fases 2 e 3

## Opções consideradas

### Opção A: Tudo no `.opencode/`

Colocar agents, skills, documentação e workflows todos dentro de `.opencode/`.

**Prós:**
- Seguia exatamente o schema do opencode
- Localização única e previsível

**Contras:**
- `.opencode/` é um diretório "mágico" — misturar documentação humana com
  config de runtime polui o conceito
- Workflows e ADRs não têm lugar natural no schema do opencode
- Dificulta navegação para humanos que não conhecem o opencode

### Opção B: Tudo no root

Colocar tudo no diretório raiz, sem separação clara.

**Prós:**
- Simples de navegar
- Sem subdiretórios profundos

**Contras:**
- Poluição visual no root
- Sem separação entre runtime e documentação
- Difícil de escalar com muitos agents e skills

### Opção C (decidida): Dupla camada

Separar definição runtime (`.opencode/`) de documentação humana (`agents/`,
`skills/`, `workflows/`, `docs/`).

**Prós:**
- Separação clara de responsabilidades
- Runtime segue o schema do opencode
- Documentação é versionável, auditável e navegable por humanos
- Escala bem com muitos agents e skills
- Compatível com o BMAD (que usa `.agents/skills/` e `_bmad/`)

**Contras:**
- Mais pastas para manter
- Requer disciplina para não misturar camadas

## Consequências

### Positivas
- Agents e skills têm dupla documentação: humana + runtime
- Workflows ficam como documentação viva, auditável
- ADRs registram decisões arquiteturais com contexto
- Estrutura preparada para as Fases 2 e 3
- Compatível com BMAD sem conflitos

### Negativas
- Mais complexidade inicial (23+ pastas criadas)
- Requer disciplina para manter a separação
- Alguns `.gitkeep` necessários para preservar estrutura no Git

### Neutras
- Pasta `_bmad-output/` é efêmera (artefatos regenerados)
- `.agents/skills/` é mantida pelo BMAD — não editar manualmente

## Notas adicionais

- A pasta `{output_folder}/` original era um bug do BMAD (chaves não
  expandidas). Foi renomeada para `_bmad-output/`.
- O BMAD v6.10.0 foi instalado com opencode como tool configurado.
- O default agent no `opencode.json` é `build` (temporário até a Fase 2).
