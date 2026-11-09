# 0003 — Onde o software roda

**Data:** 2026-11-09
**Etapa:** 1
**Situação:** proposta (pergunta 6 do levantamento não foi respondida; esta é a recomendação)

## Contexto

O sistema precisa controlar vários ambientes (RF-04), continuar funcionando sem internet
(RNF-05) e manter o controle local mesmo se o servidor cair (RNF-03). É preciso decidir
onde roda cada parte do software.

## Alternativas consideradas

### Alternativa A — Tudo no controlador de cada ambiente
- Cada ambiente tem um controlador com painel web próprio.
- Prós: simples, sem servidor.
- Contras: não há visão unificada de vários ambientes; histórico limitado pela memória
  do controlador; cada ambiente configurado separadamente.

### Alternativa B — Nós por ambiente + servidor central local (hub)
- Cada ambiente tem um **nó**: controlador pequeno que lê os sensores, aplica as regras
  recebidas e aciona os atuadores daquele ambiente.
- Um **hub** local (computador pequeno na mesma rede) recebe os dados de todos os nós,
  guarda o histórico, roda o painel e distribui as regras.
- Se o hub cair, cada nó continua com as últimas regras (RNF-03).
- Prós: visão unificada, histórico longo, escala de 1 a muitos ambientes, funciona sem
  internet.
- Contras: um equipamento a mais (o hub); dois softwares para manter (firmware do nó e
  software do hub).

### Alternativa C — Nós por ambiente + servidor em nuvem
- Igual à B, mas o servidor fica na internet.
- Prós: acesso remoto nativo; um só servidor para todos os clientes do produto.
- Contras: depende de internet para configurar e ver dados (fere RNF-05); custo mensal;
  responsabilidade por dados de terceiros desde a versão 1.

## Decisão

Alternativa B para a versão 1. Acesso remoto e nuvem entram como camada opcional em
versão futura, sem alterar o funcionamento local.

## Consequências

- A arquitetura da Etapa 2 é "hub + nós".
- O firmware do nó precisa guardar as regras localmente e ter relógio confiável (RNF-06).
- O protocolo entre nó e hub é uma decisão da Etapa 2.
- O hub pode ser um computador de placa única ou um mini PC; escolha na Etapa 2.

## Verificação

Teste da Etapa 5: desligar o hub por 24 h e confirmar que fotoperíodo e limites de
exaustão continuam sendo respeitados pelo nó.
