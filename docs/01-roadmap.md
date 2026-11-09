# Roadmap por etapas

As etapas abaixo são uma **proposta inicial**. Elas serão ajustadas conforme as
respostas da Etapa 1. Cada etapa só é fechada seguindo o ciclo de `PROCESSO.md`.

Situações possíveis: `não iniciada`, `em andamento`, `em teste`, `fechada`.

---

## Etapa 0 — Fundação do repositório e processo

**Situação:** em andamento

**Objetivo:** ter um repositório organizado e um processo de trabalho claro antes de
qualquer decisão técnica.

**Escopo**
- Estrutura de pastas.
- Documento de processo.
- Modelos de registro de decisão e de teste.
- Roadmap inicial.

**Critérios de aceite**
- [x] Estrutura de pastas criada e descrita no `README.md`.
- [x] `PROCESSO.md` escrito.
- [x] Modelos de decisão e de teste disponíveis.
- [ ] Repositório publicado em um remoto (GitHub ou equivalente).
- [ ] Revisado e aprovado pelo responsável do projeto.

---

## Etapa 1 — Requisitos e escopo

**Situação:** não iniciada

**Objetivo:** responder as perguntas em aberto de `00-visao-geral.md` e transformá-las
em requisitos numerados em `02-requisitos.md`.

**Escopo**
- Levantamento do ambiente de cultivo real.
- Lista de grandezas a medir, com faixa e precisão desejadas.
- Lista de atuadores, com tensão e corrente de cada um.
- Definição do que é essencial na versão 1 e do que fica para depois.

**Critérios de aceite**
- [ ] Todas as perguntas em aberto respondidas.
- [ ] Requisitos numerados (RF-xx funcionais, RNF-xx não funcionais) em `02-requisitos.md`.
- [ ] Cada requisito marcado como `essencial` ou `desejável`.

---

## Etapa 2 — Arquitetura e escolha de componentes

**Situação:** não iniciada

**Objetivo:** definir a arquitetura geral (controlador, sensores, atuadores, software)
e escolher os componentes principais, com registro de decisão para cada escolha.

**Escopo**
- Diagrama de blocos do sistema.
- Escolha do microcontrolador / computador de placa única.
- Escolha de cada sensor e de cada módulo de acionamento.
- Escolha da pilha de software (linguagens, banco de dados, interface).
- Lista de materiais (BOM) preliminar com custo estimado.

**Critérios de aceite**
- [ ] Diagrama de blocos em `hardware/`.
- [ ] Um registro de decisão para cada componente principal.
- [ ] BOM preliminar em `hardware/bom.md`.
- [ ] Orçamento estimado dentro do definido na Etapa 1.

---

## Etapa 3 — Bancada: leitura de sensores

**Situação:** não iniciada

**Objetivo:** ler cada sensor individualmente no controlador escolhido e validar as
leituras contra uma referência.

**Critérios de aceite**
- [ ] Cada sensor lido com sucesso e comparado a um instrumento de referência.
- [ ] Erro de leitura dentro da precisão definida nos requisitos.
- [ ] Registro de teste por sensor em `testes/`.

---

## Etapa 4 — Bancada: acionamento de atuadores

**Situação:** não iniciada

**Objetivo:** acionar cada atuador de forma segura a partir do controlador.

**Critérios de aceite**
- [ ] Cada atuador liga e desliga sob comando.
- [ ] Corrente e aquecimento medidos nos módulos de acionamento.
- [ ] Verificação de segurança para cargas em tensão de rede (isolamento, fusível).

---

## Etapa 5 — Firmware integrado

**Situação:** não iniciada

**Objetivo:** firmware que lê todos os sensores, aciona atuadores e expõe os dados
por uma interface definida na Etapa 2.

**Critérios de aceite**
- [ ] Leituras periódicas de todos os sensores.
- [ ] Comandos de atuação recebidos e executados.
- [ ] Comportamento seguro em falha (sensor desconectado, perda de rede).
- [ ] Teste contínuo de pelo menos 24 h sem travamento.

---

## Etapa 6 — Software: coleta e armazenamento

**Situação:** não iniciada

**Objetivo:** receber os dados do controlador, armazenar o histórico e permitir consulta.

---

## Etapa 7 — Software: painel e automação

**Situação:** não iniciada

**Objetivo:** painel de visualização e regras de automação (fotoperíodo, limites,
irrigação por horário ou por umidade do solo).

---

## Etapa 8 — Montagem final e operação assistida

**Situação:** não iniciada

**Objetivo:** montar o sistema no ambiente real e operar por um período definido
com acompanhamento, registrando problemas.

---

## Pendências

Itens que surgiram fora do escopo da etapa atual e precisam ser avaliados.

| # | Descrição | Origem | Destino proposto |
|---|-----------|--------|------------------|
| 1 | Definir licença do projeto | Etapa 0 | decisão `0002` |
| 2 | Publicar repositório no GitHub (token da sessão inválido) | Etapa 0 | Etapa 0 |
