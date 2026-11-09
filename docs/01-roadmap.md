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

**Situação:** em andamento

**Objetivo:** responder as perguntas em aberto de `00-visao-geral.md` e transformá-las
em requisitos numerados em `02-requisitos.md`.

**Escopo**
- Levantamento do ambiente de cultivo real.
- Lista de grandezas a medir, com faixa e precisão desejadas.
- Lista de atuadores, com tensão e corrente de cada um.
- Definição do que é essencial na versão 1 e do que fica para depois.

**Critérios de aceite**
- [x] Perguntas 1 a 5 respondidas e registradas em `00-visao-geral.md`.
- [ ] Perguntas 6 (onde o software roda) e 7 (orçamento) respondidas, ou proposta da
      decisão `0003` aceita.
- [x] Requisitos numerados (RF-xx funcionais, RNF-xx não funcionais) em `02-requisitos.md`.
- [x] Cada requisito marcado como `essencial` ou `desejável`.
- [ ] Requisitos revisados e marcados como `aprovado` pelo responsável.
- [ ] Decisões `0002` e `0003` aceitas.
- [ ] Checklist de `hardware/equipamentos-existentes.md` preenchido com fotos das etiquetas.

---

## Etapa 2 — Arquitetura e escolha de componentes

**Situação:** não iniciada

**Objetivo:** definir a arquitetura "hub + nós" (decisão `0003`) e escolher os
componentes principais dentro da restrição de montagem sem solda (decisão `0002`),
com registro de decisão para cada escolha.

**Escopo**
- Diagrama de blocos: hub, nós por ambiente, sensores, dispositivos de acionamento.
- Escolha do controlador do nó e do padrão de conector dos módulos.
- Escolha do sensor de temperatura e umidade.
- Escolha do dispositivo certificado de acionamento de cargas de rede, com controle local.
- Escolha do hub (hardware) e da pilha de software (linguagens, banco de dados, painel).
- Protocolo de comunicação nó ↔ hub.
- Definição da integração com o exaustor Vivosun (opções I1 a I4 em
  `hardware/equipamentos-existentes.md`).
- Lista de materiais (BOM) preliminar com custo estimado para 2 ambientes.

**Critérios de aceite**
- [ ] Diagrama de blocos em `hardware/`.
- [ ] Um registro de decisão para cada componente principal e para o protocolo nó ↔ hub.
- [ ] BOM preliminar em `hardware/bom.md`, com fornecedor no Brasil quando possível.
- [ ] Orçamento estimado dentro do definido na Etapa 1.
- [ ] Nenhum item da BOM exige solda ou fiação de rede pelo usuário.

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
| 1 | Definir licença do projeto | Etapa 0 | decisão futura |
| 2 | Publicar repositório no GitHub (token da sessão inválido) | Etapa 0 | Etapa 0 |
| 3 | Verificar se o E42 mantém configuração após queda de energia (define viabilidade da opção I2) | Etapa 1 | Etapa 2 |
| 4 | Verificar tipo de dimerização do driver da luz (define RF-15) | Etapa 1 | Etapa 2 |
| 5 | Produto para terceiros exigirá certificação e documentação de instalação; avaliar quando a versão 1 estiver validada | Etapa 1 | versão futura |
