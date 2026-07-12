# VFS-007 - Orquestrador

Status: Em definição
Versão: v0.1.0

## Propósito

Documentar o comportamento conceitual do orquestrador da POC sem escolher tecnologia de implementação.

## Ordem de execução

1. Receber tema.
2. Executar Pesquisa.
3. Validar presença mínima de `ResearchPackage`.
4. Executar Roteiro.
5. Validar presença mínima de `ScriptPackage`.
6. Executar Direção Visual e Thumbnail.

## Dependências

- Pesquisa depende do tema.
- Roteiro depende de `ResearchPackage`.
- Direção Visual depende de `ScriptPackage`.
- Thumbnail depende de `ScriptPackage`.

## Paralelismo

Direção Visual e Thumbnail podem ser executados em paralelo porque ambos dependem do `ScriptPackage` e não dependem um do outro.

## Estados do pipeline

Status: TBD

Estados conceituais iniciais:

- `pending`
- `running`
- `completed`
- `failed`
- `interrupted`

## Falhas

Falhas devem preservar entrada, saída parcial quando existir, mensagem de erro e etapa afetada.

## Retry

Status: TBD

Retries podem ser considerados para falhas transitórias, mas critérios definitivos não foram definidos.

## Interrupção

Interrupções devem permitir identificar a última etapa concluída e os pacotes válidos já produzidos.

## Versionamento dos pacotes

Cada pacote deve declarar `schema_version` e referência ao pacote anterior quando aplicável.

## Observabilidade futura

Status: TBD

Observabilidade futura pode incluir logs, métricas por etapa, tempos de execução, taxa de falha e comparação entre versões. Nenhuma tecnologia está definida.

## Questões em aberto

- Status: TBD - Formato de persistência dos estados.
- Status: TBD - Política de retry.
- Status: TBD - Critérios de validação automática.
- Status: TBD - Nível mínimo de observabilidade da primeira implementação.
