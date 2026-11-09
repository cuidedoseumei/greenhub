# 0001 — Estrutura do repositório e processo por etapas

**Data:** 2026-11-09
**Etapa:** 0
**Situação:** proposta (aguarda aprovação do responsável)

## Contexto

O projeto reúne hardware, firmware e software, e será conduzido etapa por etapa com
verificação e teste de cada uma. É preciso decidir, antes de qualquer trabalho técnico,
como o repositório é organizado e como o progresso é registrado.

## Alternativas consideradas

### Alternativa A — Repositório único (monorepo) com pastas por área
- Prós: histórico único, fácil cruzar decisões de hardware com software, uma só
  fonte de verdade para documentação e testes.
- Contras: ferramentas de build de firmware e de software convivem no mesmo lugar.

### Alternativa B — Repositórios separados (hardware, firmware, software)
- Prós: cada área com suas próprias ferramentas e releases.
- Contras: documentação e decisões ficam espalhadas; mais difícil garantir que uma
  etapa foi verificada de ponta a ponta.

### Alternativa C — Apenas documentação em wiki, código em repositório
- Contras: decisões e testes fora do controle de versão do código.

## Decisão

Alternativa A: repositório único, com pastas `docs/`, `hardware/`, `firmware/`,
`software/` e `testes/`, e com o processo descrito em `PROCESSO.md`.

Decisões ficam em `docs/decisoes/` (um arquivo por decisão, numerado), e registros de
teste em `testes/` (um arquivo por etapa ou por item testado).

## Consequências

- Toda etapa deixa rastro no mesmo lugar: decisão, implementação, teste, changelog.
- Se o projeto crescer muito, firmware ou software podem ser extraídos depois sem
  perder o histórico de decisões.

## Verificação

Ao fechar a Etapa 2, revisar se a estrutura atendeu bem. Se decisões ou testes
estiverem sendo registrados fora do repositório, esta decisão deve ser revista.
