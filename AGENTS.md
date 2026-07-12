# Orientações para agentes e ferramentas

Status: Em vigor
Versão: v0.1.0

Este repositório contém a documentação inicial da POC Video Factory. Qualquer agente ou ferramenta que trabalhe neste projeto deve preservar rastreabilidade, compatibilidade documental e escopo controlado.

## Regras gerais

- Leia as especificações em `docs/` antes de alterar qualquer artefato.
- Não altere contratos sem atualizar a documentação correspondente.
- Não invente decisões arquiteturais, técnicas ou editoriais.
- Quando uma decisão estiver em aberto, registre `Status: TBD` ou adicione a questão em `Questões em aberto`.
- Mantenha compatibilidade entre JSON Schemas e documentos.
- Prefira mudanças pequenas, rastreáveis e revisáveis.
- Adicione ou atualize exemplos quando um contrato for alterado.
- Registre decisões arquiteturais relevantes em `docs/adr/`.
- Mantenha todos os documentos em português.
- Não implemente funcionalidades fora do escopo solicitado.
- Não escreva prompts finais de agentes nesta etapa documental.

## Contratos e documentação

- Os schemas ficam em `docs/schemas/`.
- As especificações de arquitetura ficam em `docs/architecture/`.
- As especificações de agentes ficam em `docs/agents/`.
- Mudanças em campos obrigatórios devem atualizar a especificação de contratos: [VFS-002](docs/architecture/VFS-002-data-contracts.md).
- Mudanças arquiteturais relevantes devem ter ADR associado.

## Fora de escopo atual

- Código de produção.
- Orquestração executável.
- Integração com LLMs, APIs ou bancos de dados.
- Escolha de modelos, provedores, frameworks, linguagens ou infraestrutura.
