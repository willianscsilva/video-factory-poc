# VFS-001 - Visão Geral

Status: Em definição
Versão: v0.1.0

## Problema

Produzir vídeos com apoio de agentes pode gerar artefatos difíceis de revisar quando pesquisa, roteiro, direção visual e thumbnail são tratados como texto livre sem contratos claros.

## Objetivo

Definir uma arquitetura conceitual mínima para uma linha de produção de vídeos baseada em agentes especializados e pacotes estruturados.

## Escopo da POC

- Quatro agentes conceituais: Pesquisa, Roteiro, Direção Visual e Thumbnail.
- Pacotes de dados versionados entre etapas.
- Documentação das responsabilidades e critérios de qualidade.
- Primeiro experimento futuro sobre terras raras no Brasil.

## Não objetivos

- Implementar agentes executáveis.
- Escolher modelos, provedores, linguagens, frameworks, bancos de dados ou infraestrutura.
- Criar prompts finais.
- Produzir artefatos editoriais finais nesta etapa.

## Arquitetura conceitual

O pipeline é composto por etapas desacopladas. Cada etapa consome um artefato de entrada, aplica sua responsabilidade específica e produz um pacote estruturado.

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

## Pipeline

1. Um tema editorial inicia o processo.
2. O Agente de Pesquisa produz um `ResearchPackage`.
3. O Agente de Roteiro transforma o `ResearchPackage` em `ScriptPackage`.
4. Os agentes de Direção Visual e Thumbnail podem consumir o `ScriptPackage` em paralelo.
5. Os resultados são `VisualPackage` e `ThumbnailPackage`.

## Responsabilidades dos agentes

- Pesquisa: coletar, organizar e classificar informações com fontes.
- Roteiro: criar estrutura narrativa preservando rastreabilidade factual.
- Direção Visual: especificar linguagem visual por cena ou bloco.
- Thumbnail: propor composição de thumbnail coerente com o conteúdo.

## Artefatos trocados entre agentes

- `ResearchPackage`: definido em [VFS-002](VFS-002-data-contracts.md) e [research-package.schema.json](../schemas/research-package.schema.json).
- `ScriptPackage`: definido em [VFS-002](VFS-002-data-contracts.md) e [script-package.schema.json](../schemas/script-package.schema.json).
- `VisualPackage`: definido em [VFS-002](VFS-002-data-contracts.md) e [visual-package.schema.json](../schemas/visual-package.schema.json).
- `ThumbnailPackage`: definido em [VFS-002](VFS-002-data-contracts.md) e [thumbnail-package.schema.json](../schemas/thumbnail-package.schema.json).

## Princípios arquiteturais

- Separação de responsabilidades.
- Contratos explícitos.
- Versionamento dos artefatos.
- Rastreabilidade de fontes e decisões.
- Evolução incremental.
- Validação humana quando a automação não for suficiente.

Validação automática ou um agente validador é uma possibilidade futura, ainda não obrigatória na primeira implementação.

## Riscos iniciais

- Perda de rastreabilidade entre pesquisa e roteiro.
- Confusão entre fato, hipótese, opinião e estimativa.
- Contratos excessivamente rígidos antes de validação prática.
- Produção de conteúdo persuasivo sem precisão factual.

## Questões em aberto

- Status: TBD - Critérios definitivos de aprovação por etapa.
- Status: TBD - Formato final de armazenamento dos pacotes.
- Status: TBD - Forma de execução e orquestração.
- Status: TBD - Estratégia de validação automática.
