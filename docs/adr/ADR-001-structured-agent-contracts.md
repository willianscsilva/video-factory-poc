# ADR-001 - Contratos Estruturados Entre Agentes

Status: Aceita
Versão: v0.1.0

## Contexto

A POC Video Factory depende da passagem de informações entre agentes especializados. Se esses artefatos forem apenas texto livre, a revisão, validação, rastreabilidade e comparação entre versões se tornam mais difíceis.

## Decisão

Usar pacotes estruturados e versionados entre agentes, em vez de texto livre como interface principal.

Pacotes iniciais:

- `ResearchPackage`
- `ScriptPackage`
- `VisualPackage`
- `ThumbnailPackage`

Os contratos são documentados em [VFS-002](../architecture/VFS-002-data-contracts.md) e representados por JSON Schemas em `docs/schemas/`.

## Alternativas consideradas

- Texto livre entre agentes.
- Documento único acumulativo.
- Contratos estruturados por etapa.

## Consequências positivas

- Melhor rastreabilidade.
- Validação estrutural mínima.
- Separação clara de responsabilidades.
- Comparação mais simples entre versões.
- Menor ambiguidade entre etapas.

## Consequências negativas

- Maior custo inicial de documentação.
- Risco de contratos prematuros demais.
- Necessidade de manter schemas e especificações sincronizados.

## Riscos

- Contratos rígidos antes de aprendizado prático.
- Campos obrigatórios insuficientes para experimentos futuros.
- Uso dos schemas como substituto indevido para revisão editorial.

## Status

Aceita
