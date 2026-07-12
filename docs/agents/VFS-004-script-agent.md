# VFS-004 - Agente de Roteiro

Status: Em definição
Versão: v0.1.0

## Objetivo

Transformar um `ResearchPackage` em um `ScriptPackage` narrativo, preservando precisão factual e rastreabilidade.

## Responsabilidades

- Definir estrutura narrativa.
- Organizar cenas ou blocos.
- Criar hook, desenvolvimento, conclusão e CTA quando aplicável.
- Preservar fatos, números e contexto do pacote de pesquisa.
- Sinalizar necessidade de pesquisa adicional quando houver lacunas.

## Entrada

- `ResearchPackage` conforme [VFS-002](../architecture/VFS-002-data-contracts.md).

## Saída

- `ScriptPackage` conforme [script-package.schema.json](../schemas/script-package.schema.json).

## Estrutura narrativa

Status: TBD

A estrutura inicial deve conter pelo menos hook, blocos de desenvolvimento e conclusão.

## Cenas ou blocos

Cada bloco deve conter objetivo narrativo, texto ou descrição inicial e referências às evidências usadas quando aplicável.

## Duração alvo

Status: TBD

O pacote deve registrar uma duração alvo, mesmo que experimental.

## Hook

O hook deve criar interesse sem distorcer fatos ou prometer algo que o conteúdo não entrega.

## Desenvolvimento

O desenvolvimento deve explicar o tema de forma progressiva, mantendo relação clara com o `ResearchPackage`.

## Conclusão

A conclusão deve fechar a tese narrativa sem introduzir fatos novos sem referência.

## CTA

CTA é opcional e deve ser coerente com o contexto editorial.

## Restrições

- Não realizar pesquisa independente sem registrar a necessidade.
- Não alterar fatos ou números.
- Não criar clickbait enganoso.
- Preservar rastreabilidade das afirmações.
- Escrever para retenção sem sacrificar precisão.

## Critérios de qualidade

- Narrativa compreensível.
- Precisão factual preservada.
- Blocos conectados ao pacote de pesquisa.
- Hook honesto.
- Conclusão coerente com o desenvolvimento.

## Critérios de falha

- Distorção factual.
- Afirmações novas sem rastreabilidade.
- Clickbait enganoso.
- Perda da relação com o `ResearchPackage`.

## Questões em aberto

- Status: TBD - Duração alvo do primeiro formato.
- Status: TBD - Granularidade ideal entre cena e bloco.
