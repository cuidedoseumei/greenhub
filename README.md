# indoor-grow

Sistema de hardware + software para gerenciamento de cultivo de plantas indoor.

O projeto é desenvolvido **etapa por etapa**. Nenhuma etapa é considerada concluída
sem verificação e teste documentados. O processo está descrito em
[`PROCESSO.md`](PROCESSO.md).

## Estado atual

| Etapa | Nome | Situação |
|-------|------|----------|
| 0 | Fundação do repositório e processo de trabalho | em andamento |
| 1 | Requisitos e escopo (o que o sistema deve fazer) | não iniciada |
| 2 | Arquitetura e escolha de componentes | não iniciada |
| 3+ | Ver [`docs/01-roadmap.md`](docs/01-roadmap.md) | não iniciada |

## Estrutura do repositório

```
.
├── README.md          # este arquivo: visão geral e estado atual
├── PROCESSO.md        # como cada etapa é conduzida, verificada e fechada
├── CHANGELOG.md       # histórico de mudanças por etapa
├── docs/
│   ├── 00-visao-geral.md   # objetivo, escopo e premissas do projeto
│   ├── 01-roadmap.md       # etapas planejadas com critérios de aceite
│   ├── 02-requisitos.md    # requisitos funcionais e não funcionais
│   └── decisoes/           # registros de decisão (ADR), um arquivo por decisão
├── hardware/          # esquemáticos, lista de materiais (BOM), PCB, mecânica
├── firmware/          # código embarcado do controlador
├── software/          # backend, interface e integrações
└── testes/            # planos e registros de teste de cada etapa
```

## Como navegar

1. Leia [`docs/00-visao-geral.md`](docs/00-visao-geral.md) para entender o objetivo.
2. Veja [`docs/01-roadmap.md`](docs/01-roadmap.md) para saber em que etapa estamos.
3. Toda decisão relevante tem um registro em [`docs/decisoes/`](docs/decisoes/).
4. Toda etapa fechada tem um registro de teste em [`testes/`](testes/).

## Licença

Ainda não definida. Ver decisão pendente em `docs/decisoes/`.
