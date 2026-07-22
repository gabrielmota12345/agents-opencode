# Guia de Instalação

## Pré-requisitos

- [Node.js](https://nodejs.org/) 20+
- [Git](https://git-scm.com/)
- [uv](https://docs.astral.sh/uv/) (recomendado para scripts Python)

## Instalação

### 1. Clonar o repositório

```powershell
git clone git@github.com:gabrielmota12345/agents-opencode.git
cd agents-opencode
```

### 2. Instalar BMAD (já pré-instalado)

O BMAD já vem instalado neste workspace. Se precisar reinstalar:

```powershell
npx bmad-method install
```

### 3. Configurar uv (recomendado)

```powershell
powershell -c "irm https://astral.sh/uv/install.ps1 | iex"
```

### 4. Iniciar OpenCode

```powershell
opencode
```

## Verificação

Após iniciar, teste com:

```
/bmad-help
```

Se a resposta retornar, tudo está funcionando.

## Estrutura esperada

```
agents-opencode/
├── .opencode/agents/      # 19 agents
├── .opencode/skills/      # 12 skills
├── .opencode/commands/    # 46 comandos BMAD
├── .agents/skills/        # 46 skills BMAD
├── _bmad/                 # Engine BMAD
├── _bmad-output/          # Artefatos gerados
├── agents/                # Documentação dos agents
├── workflows/             # Workflows documentados
├── skills/                # Documentação das skills
├── docs/                  # Documentação do workspace
├── examples/              # Exemplos de uso
├── opencode.json          # Configuração
├── AGENTS.md              # Instrução global
└── README.md              # Este arquivo
```
