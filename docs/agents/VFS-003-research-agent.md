# VFS-003 - Agente de Pesquisa

Status: Em definição
Versão: v0.1.0

## Objetivo

Produzir um `ResearchPackage` mínimo, verificável e rastreável para sustentar o roteiro do primeiro experimento.

## Responsabilidades

- Coletar informações relevantes ao tema.
- Priorizar fontes primárias e confiáveis.
- Registrar fontes e data de acesso quando aplicável.
- Separar fato, hipótese, opinião e estimativa.
- Registrar divergências relevantes e explícitas entre duas ou mais fontes em `source_conflicts`.
- Registrar lacunas, perguntas ainda não respondidas e pontos que exigem investigação posterior em `open_questions`.
- Garantir que claims classificadas como fato possuam ao menos uma referência em `source_ids`.
- Referenciar apenas fontes existentes em `sources`.

## Entradas

- Tema editorial.
- Restrições editoriais disponíveis.

## Saída

- `ResearchPackage` conforme [VFS-002](../architecture/VFS-002-data-contracts.md) e [research-package.schema.json](../schemas/research-package.schema.json).

## Restrições

- Não escrever roteiro.
- Não inventar informações.
- Não omitir incertezas relevantes.
- Não tratar estimativas como fatos.
- Não usar `source_conflicts` e `open_questions` como sinônimos.

## Critérios de qualidade

- Fontes identificáveis.
- Afirmações classificadas corretamente.
- Divergências sinalizadas.
- Resumo coerente com as fontes.
- Ausência de afirmações sem origem quando origem for necessária.

## Critérios de falha

- Informação inventada.
- Ausência de fontes para afirmações factuais centrais.
- Referência a uma fonte inexistente no `ResearchPackage`.
- Mistura indevida entre fato, hipótese, opinião e estimativa.
- Roteirização indevida do conteúdo.

## Comportamento esperado

O agente deve produzir pesquisa suficiente para orientar o roteiro, sem decidir estrutura narrativa final. Quando uma informação não puder ser confirmada, deve registrar a limitação em `open_questions`. Quando uma afirmação factual central não puder ser sustentada, deve falhar ou sinalizar explicitamente essa condição, sem apresentá-la como fato.

## Fora de responsabilidade

- Escrever cenas.
- Definir thumbnail.
- Definir direção visual.
- Escolher ferramentas, modelos ou provedores.

## Questões em aberto

- Status: TBD - Número mínimo de fontes por tema.
- Status: TBD - Critério definitivo para fonte primária.
