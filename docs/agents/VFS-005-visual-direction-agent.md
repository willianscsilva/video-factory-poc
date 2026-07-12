# VFS-005 - Agente de Direção Visual

Status: Em definição
Versão: v0.1.0

## Objetivo

Transformar um `ScriptPackage` em um `VisualPackage` com orientação visual por cena ou bloco.

## Responsabilidades

- Descrever intenção visual por cena.
- Sugerir enquadramento, movimento e elementos em tela.
- Registrar texto em tela quando aplicável.
- Indicar transições e estilo visual.
- Manter consistência com o roteiro.

## Entrada

- `ScriptPackage` conforme [VFS-002](../architecture/VFS-002-data-contracts.md).

## Saída

- `VisualPackage` conforme [visual-package.schema.json](../schemas/visual-package.schema.json).

## Descrição visual por cena

Cada cena ou bloco deve ter uma descrição visual correspondente quando houver material suficiente no roteiro.

## Enquadramento

Status: TBD

O enquadramento deve ser descrito em linguagem conceitual, sem depender de ferramenta específica.

## Movimento

Status: TBD

Movimentos podem ser descritos quando contribuírem para clareza ou retenção.

## Elementos em tela

Elementos em tela devem ser coerentes com o conteúdo e não introduzir informações factuais não sustentadas.

## Texto em tela

Texto em tela deve ser curto, legível e consistente com o roteiro.

## Transições

Transições devem apoiar continuidade narrativa. Regras definitivas estão em aberto.

## Estilo visual

Status: TBD

O estilo visual inicial deve ser descrito sem escolher ferramentas, modelos ou sistemas de geração.

## Consistência

O pacote deve manter coerência entre cenas, tom editorial e conteúdo factual.

## Restrições

- Não gerar imagens ou vídeos nesta especificação.
- Não escolher ferramentas, modelos ou provedores.
- Não criar elementos visuais que contradigam o roteiro.
- Não inventar fatos visuais apresentados como realidade.

## Critérios de qualidade

- Coerência com o `ScriptPackage`.
- Clareza visual por cena.
- Legibilidade de textos em tela.
- Consistência de estilo.
- Ausência de afirmações visuais enganosas.

## Critérios de falha

- Geração efetiva de imagens ou vídeos nesta etapa.
- Contradição com roteiro ou pesquisa.
- Direção visual vaga demais para revisão.
- Introdução de informação factual sem suporte.

## Questões em aberto

- Status: TBD - Vocabulário visual padrão.
- Status: TBD - Nível de detalhe esperado por cena.
