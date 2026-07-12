# VFS-002 - Contratos de Dados

Status: Em definição
Versão: v0.1.0

## Propósito

Os contratos de dados definem como os agentes trocam informações de forma rastreável, versionada e revisável. Eles reduzem ambiguidade entre etapas e permitem comparar versões futuras dos artefatos.

## Conceito de Package

Um Package representa um artefato estruturado produzido por um agente da Video Factory.

Todo Package deve:

- possuir um schema próprio;
- possuir uma versão;
- possuir um identificador único;
- registrar sua origem;
- poder ser persistido;
- poder ser auditado;
- servir como entrada para outros agentes;
- representar um contrato estável entre etapas.

Package é um conceito arquitetural e não está associado a uma tecnologia específica.

## Princípio arquitetural

Os Packages representam o principal mecanismo de comunicação da Video Factory.

Agentes são responsáveis por transformar um Package em outro. Essa visão preserva o desacoplamento entre etapas e torna os artefatos produzidos mais fáceis de auditar, comparar e evoluir.

## Contratos como interface

Agentes não conhecem as implementações uns dos outros. Eles conhecem apenas os contratos dos Packages que consomem e produzem.

Os contratos são a interface oficial da Video Factory. Isso permite desacoplar a implementação interna de cada agente do consumo feito pelas etapas seguintes.

## Imutabilidade

Packages são imutáveis.

Depois de gerado, um Package não deve ser alterado. Caso alguma informação precise ser modificada, um novo Package deve ser produzido. O Package original permanece preservado para auditoria e rastreabilidade.

## Lineage

Cada Package deve conhecer explicitamente sua origem.

Exemplo conceitual:

```text
Tema
  ↓
ResearchPackage
  ↓
ScriptPackage
  ↓
VisualPackage
```

Essa cadeia permite rastrear completamente a produção de um vídeo, desde o tema inicial até os artefatos finais. A forma de implementação da linhagem ainda não está definida.

Status: TBD

## Metadados comuns

Todos os Packages compartilham um conjunto mínimo de metadados. Nesta versão, os campos já refletidos nos schemas incluem `schema_version`, `package_id`, `created_at` e uma origem ou referência ao pacote anterior.

Conceitualmente, os metadados comuns também devem incluir:

- `agent_name`;
- `agent_version`.

Esses campos ainda não fazem parte dos JSON Schemas em `v0.1.0`.

## Versionamento

Todos os pacotes devem conter `schema_version`. A versão inicial dos schemas é `v0.1.0`.

Mudanças compatíveis devem preservar campos existentes quando possível. Mudanças incompatíveis devem ser documentadas nesta especificação e, quando relevantes, em ADR.

## Compatibilidade

Nesta fase, os schemas evitam `additionalProperties: false` para permitir evolução inicial sem rigidez excessiva. Campos novos devem ser documentados antes de se tornarem obrigatórios.

## Campos obrigatórios e opcionais

Campos obrigatórios representam o mínimo necessário para rastrear e consumir um pacote. Campos opcionais podem evoluir conforme os experimentos gerem evidências de necessidade.

`package_id` deve identificar globalmente um Package de forma única. A convenção técnica para geração e formato desse identificador permanece em aberto.

Status: TBD

## Tratamento de erros

Status: TBD

Erros devem ser registrados sem apagar o contexto de entrada. Critérios definitivos de erro, retry e interrupção estão descritos conceitualmente em [VFS-007](VFS-007-orchestrator.md).

## Rastreabilidade de fontes

Afirmações factuais devem preservar referência de origem quando aplicável. O `ResearchPackage` deve conter fontes. Pacotes posteriores devem manter referências ao pacote anterior e, quando necessário, às evidências usadas.

## Fato, hipótese, opinião e estimativa

O pipeline deve distinguir:

- Fato: afirmação sustentada por fonte verificável.
- Hipótese: explicação plausível ainda não comprovada no contexto do pacote.
- Opinião: julgamento atribuído a uma pessoa, instituição ou ao próprio tratamento editorial, quando permitido.
- Estimativa: valor aproximado ou inferido, acompanhado de fonte, método ou ressalva quando disponível.

## Relação entre documentação e JSON Schema

A documentação define intenção, semântica e restrições editoriais. Os JSON Schemas definem a estrutura mínima validável.

Schemas iniciais:

- [research-package.schema.json](../schemas/research-package.schema.json)
- [script-package.schema.json](../schemas/script-package.schema.json)
- [visual-package.schema.json](../schemas/visual-package.schema.json)
- [thumbnail-package.schema.json](../schemas/thumbnail-package.schema.json)

## ResearchPackage

Entrada: tema.

Saída do Agente de Pesquisa, contendo resumo, fontes e afirmações classificadas. Campos mínimos: `schema_version`, `package_id`, `created_at`, `input_origin`, `topic`, `summary`, `sources`, `claims`.

`sources` representa as evidências utilizadas durante a pesquisa. Uma fonte pode conter metadados como autor, título, URL, data, data de acesso e tipo da fonte. Esses metadados são conceituais nesta versão e não se tornam todos obrigatórios em `v0.1.0`.

`claims` representa as afirmações produzidas pelo Agente de Pesquisa. Uma Claim pode conter texto, classificação, fonte ou fontes, observações e, futuramente, confiança como campo opcional. A classificação deve seguir a distinção entre fato, hipótese, opinião e estimativa.

## ScriptPackage

Entrada: `ResearchPackage`.

Saída do Agente de Roteiro, contendo estrutura narrativa, cenas ou blocos e referências ao pacote de pesquisa. Campos mínimos: `schema_version`, `package_id`, `created_at`, `research_package_id`, `title_working`, `target_duration`, `hook`, `blocks`.

## VisualPackage

Entrada: `ScriptPackage`.

Saída do Agente de Direção Visual, contendo proposta visual por cena ou bloco. Campos mínimos: `schema_version`, `package_id`, `created_at`, `script_package_id`, `visual_style`, `scenes`.

## ThumbnailPackage

Entrada: `ScriptPackage`.

Saída do Agente de Thumbnail, contendo conceito principal, composição e variações. Campos mínimos: `schema_version`, `package_id`, `created_at`, `script_package_id`, `main_concept`, `short_text`, `composition`, `variations`.

## Questões em aberto

- Status: TBD - Convenção definitiva para `package_id`, que deve ser globalmente único.
- Status: TBD - Formato definitivo de datas e fusos além de `date-time` nos schemas.
- Status: TBD - Regras de compatibilidade entre versões maiores.
