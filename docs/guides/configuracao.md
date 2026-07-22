# Como Alterar Modelos e Permissões

## Alterar Modelo de um Agent

### No arquivo do agent (`.opencode/agents/<nome>.md`)

Adicionar `model` no frontmatter:

```yaml
---
description: "..."
mode: subagent
model: anthropic/claude-sonnet-4-6
---
```

### No `opencode.json`

```json
{
  "agent": {
    "meu-agent": {
      "model": "anthropic/claude-sonnet-4-6"
    }
  }
}
```

### Modelos disponíveis

| Modelo | ID |
|---|---|
| Claude Sonnet 4 | `anthropic/claude-sonnet-4-6` |
| Claude Haiku | `anthropic/claude-haiku-3` |
| GPT-4o | `openai/gpt-4o` |
| Gemini | `google/gemini-2.5-pro` |

## Alterar Permissões

### No arquivo do agent

```yaml
---
permission:
  edit: allow
  read: allow
  bash: { "git *": "allow", "*": "ask" }
---
```

### No `opencode.json`

```json
{
  "permission": {
    "edit": "allow",
    "read": "allow",
    "bash": { "git *": "allow", "*": "ask" }
  }
}
```

### Ações disponíveis

| Ação | Descrição |
|---|---|
| `allow` | Permite sempre |
| `ask` | Pergunta ao usuário |
| `deny` | Nunca permite |

### Chaves de permissão

| Chave | Descrição |
|---|---|
| `edit` | Criar/modificar arquivos |
| `read` | Ler arquivos |
| `bash` | Executar comandos |
| `glob` | Buscar arquivos |
| `grep` | Buscar conteúdo |
| `websearch` | Buscar na web |
| `webfetch` | Buscar URLs |

## Configurar Provider

No `opencode.json`:

```json
{
  "provider": {
    "anthropic": {
      "options": {
        "apiKey": "sua-chave-aqui"
      }
    }
  }
}
```

## Desabilitar Provider

```json
{
  "disabled_providers": ["openai"]
}
```

## Após Alterações

**Reiniciar o OpenCode** para que as mudanças tenham efeito.
