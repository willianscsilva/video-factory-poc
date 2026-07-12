# VFS-006 - Agente de Thumbnail

Status: Em definição
Versão: v0.1.0

## Objetivo

Produzir um `ThumbnailPackage` com conceito, composição e variações para thumbnail, mantendo coerência com o roteiro.

## Responsabilidades

- Definir uma ideia principal.
- Propor hierarquia visual.
- Sugerir texto curto.
- Descrever composição e contraste.
- Considerar legibilidade em telas pequenas.
- Propor variações controladas.

## Entradas

- `ScriptPackage` conforme [VFS-002](../architecture/VFS-002-data-contracts.md).
- Restrições editoriais disponíveis, quando existirem.

## Saída

- `ThumbnailPackage` conforme [thumbnail-package.schema.json](../schemas/thumbnail-package.schema.json).

## Conceito principal

A thumbnail deve comunicar uma ideia principal, sem tentar resumir todo o vídeo.

## Hierarquia visual

Status: TBD

A hierarquia deve priorizar o elemento principal, texto curto e contraste.

## Texto curto

O texto deve ser mínimo, legível e coerente com o conteúdo.

## Composição

A composição deve indicar foco visual, disposição dos elementos e relação com o tema.

## Contraste

O contraste deve favorecer leitura rápida e diferenciação dos elementos principais.

## Legibilidade em telas pequenas

A proposta deve considerar leitura em miniatura e evitar excesso de detalhes.

## Variações

Variações devem testar alternativas sem mudar a promessa central do vídeo.

## Restrições

- Uma ideia principal.
- Pouco texto.
- Sem promessa enganosa.
- Coerência com o conteúdo do vídeo.
- Priorizar legibilidade e curiosidade.
- Não gerar imagem final nesta etapa.

## Critérios de qualidade

- Clareza imediata.
- Curiosidade sem engano.
- Texto curto e legível.
- Relação direta com o `ScriptPackage`.
- Variações comparáveis.

## Critérios de falha

- Clickbait enganoso.
- Excesso de texto.
- Conceito desconectado do vídeo.
- Baixa legibilidade em tamanho reduzido.

## Questões em aberto

- Status: TBD - Número inicial de variações.
- Status: TBD - Critérios objetivos de legibilidade.
