# Video Factory POC

Status: Em definição
Versão: v0.1.0

## Visão geral

Video Factory POC é uma prova de conceito para validar uma linha de produção de vídeos apoiada por agentes de IA especializados. O projeto começa com quatro agentes conceituais: Pesquisa, Roteiro, Direção Visual e Thumbnail.

## Objetivo da POC

Validar se uma cadeia de agentes com contratos de dados explícitos consegue produzir artefatos rastreáveis, revisáveis e comparáveis para a criação de vídeos.

## Primeiro experimento

Tema inicial: terras raras no Brasil.

Proposta editorial inicial: "As tecnologias e recursos que moldam o futuro".

## Escopo atual

- Definir a arquitetura conceitual da POC.
- Documentar responsabilidades dos agentes.
- Definir contratos mínimos entre agentes.
- Criar JSON Schemas iniciais marcados como `v0.1.0`.
- Registrar a primeira decisão arquitetural em ADR.

## Fora de escopo

- Implementar agentes executáveis.
- Integrar LLMs, APIs, banco de dados ou orquestração real.
- Escolher modelos de IA, provedores, linguagens, frameworks ou infraestrutura.
- Produzir pesquisa, roteiro, direção visual ou thumbnail finais.
- Escrever prompts finais dos agentes.

## Estrutura da documentação

- [VFS-000 - Princípios Fundamentais](docs/architecture/VFS-000-foundational-principles.md)
- [VFS-001 - Visão Geral](docs/architecture/VFS-001-overview.md)
- [VFS-002 - Contratos de Dados](docs/architecture/VFS-002-data-contracts.md)
- [VFS-003 - Agente de Pesquisa](docs/agents/VFS-003-research-agent.md)
- [VFS-004 - Agente de Roteiro](docs/agents/VFS-004-script-agent.md)
- [VFS-005 - Agente de Direção Visual](docs/agents/VFS-005-visual-direction-agent.md)
- [VFS-006 - Agente de Thumbnail](docs/agents/VFS-006-thumbnail-agent.md)
- [VFS-007 - Orquestrador](docs/architecture/VFS-007-orchestrator.md)
- [VFS-008 - Avaliação de Qualidade](docs/architecture/VFS-008-quality-evaluation.md)
- [ADR-001 - Contratos Estruturados Entre Agentes](docs/adr/ADR-001-structured-agent-contracts.md)
- [Exemplo: terras raras no Brasil](examples/rare-earths-brazil/README.md)

## Fluxo simplificado do pipeline

```text
Tema
  ↓
Pesquisa
  ↓
ResearchPackage
  ↓
Roteiro
  ↓
ScriptPackage
  ├── Direção Visual → VisualPackage
  └── Thumbnail → ThumbnailPackage
```

## Status do projeto

Status: documentação inicial da POC.

Não há implementação executável nesta etapa.

## Princípios de engenharia

- Arquitetura modular.
- Contratos de dados explícitos.
- Componentes desacoplados.
- Documentação versionada.
- Decisões rastreáveis.
- Critérios de qualidade mensuráveis.
- Ausência de informações inventadas.
- Evolução orientada por dados e experimentação.
