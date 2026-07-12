# VFS-008 - Avaliação de Qualidade

Status: Em definição
Versão: v0.1.0

## Propósito

Definir uma estratégia inicial de avaliação de qualidade por agente, com checks objetivos, checks subjetivos e registro de falhas.

## Dimensões de qualidade

- Precisão factual.
- Rastreabilidade.
- Clareza.
- Coerência com o pacote de entrada.
- Aderência ao escopo do agente.
- Utilidade para a próxima etapa.

## Checks objetivos

- Presença dos campos obrigatórios do schema.
- `schema_version` preenchida.
- `package_id` preenchido.
- Referência ao pacote anterior quando aplicável.
- Presença de fontes no `ResearchPackage`.
- Ausência de artefatos fora do escopo declarado.

## Checks subjetivos

- Qualidade narrativa do roteiro.
- Clareza da direção visual.
- Força e honestidade do conceito de thumbnail.
- Adequação editorial ao tema.
- Suficiência da pesquisa para o objetivo do experimento.

## Score opcional

Status: TBD

Um score pode ser usado no futuro, mas pesos definitivos não estão definidos.

## Critérios mínimos para aprovação

- Schema mínimo válido.
- Ausência de informações inventadas identificáveis.
- Rastreabilidade preservada.
- Escopo do agente respeitado.
- Questões críticas registradas quando existirem.

## Revisão humana

Revisão humana é necessária nesta fase para avaliar julgamento editorial, suficiência de fontes, coerência narrativa e adequação visual.

## Registro de falhas

Falhas devem ser registradas com etapa, pacote afetado, descrição, severidade e recomendação de correção quando possível.

## Comparação entre versões

Versões futuras dos pacotes devem permitir comparar mudanças de conteúdo, qualidade, falhas e decisões tomadas.

## Métricas futuras da POC

Status: TBD

Possíveis métricas futuras:

- Tempo por etapa.
- Taxa de retrabalho.
- Número de falhas por pacote.
- Grau de rastreabilidade preservada.
- Avaliação humana por dimensão.

## Estratégia por agente

- Pesquisa: avaliar fontes, classificação de afirmações e divergências.
- Roteiro: avaliar precisão, retenção e rastreabilidade.
- Direção Visual: avaliar clareza, consistência e aderência ao roteiro.
- Thumbnail: avaliar legibilidade, honestidade e coerência com o vídeo.

## Questões em aberto

- Status: TBD - Pesos de avaliação.
- Status: TBD - Escala de score.
- Status: TBD - Métricas mínimas para declarar sucesso da POC.
