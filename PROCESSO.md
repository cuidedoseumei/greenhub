# Processo de trabalho

Este documento define como o projeto avança. O objetivo é que **nenhum detalhe passe
sem verificação e teste**. Ele vale para hardware, firmware e software.

## Princípios

1. **Uma etapa por vez.** Não se inicia a etapa N+1 antes de a etapa N ser fechada.
2. **Pequeno e verificável.** Cada etapa tem um escopo pequeno o bastante para ser
   testada por completo.
3. **Tudo registrado.** Decisões, testes e resultados ficam no repositório, não só
   na conversa.
4. **Sem suposições silenciosas.** Se algo não foi verificado, é marcado como
   "não verificado" explicitamente.

## Ciclo de uma etapa

Cada etapa passa pelas fases abaixo, nesta ordem.

### 1. Definição

- Objetivo da etapa em uma frase.
- Lista do que entra e do que **não** entra no escopo.
- Critérios de aceite: condições objetivas que, quando todas satisfeitas, fecham a etapa.
- Registrada em `docs/01-roadmap.md`.

### 2. Decisões

- Toda escolha com alternativas relevantes (componente, protocolo, biblioteca,
  arquitetura) gera um registro em `docs/decisoes/NNNN-titulo.md`,
  usando o modelo `docs/decisoes/0000-modelo.md`.
- O registro inclui as alternativas consideradas e o motivo da escolha.

### 3. Execução

- Implementação do que foi definido, sem extrapolar o escopo.
- Mudanças pequenas e commits descritivos.
- Algo que surgir fora do escopo vai para a seção "Pendências" do roadmap, não é
  feito "de passagem".

### 4. Verificação e teste

- Cada critério de aceite tem pelo menos um teste correspondente.
- O plano de teste e o resultado ficam em `testes/etapa-NN-nome.md`.
- Para hardware: medições (tensão, corrente, temperatura), fotos quando útil, e
  condições do teste (ambiente, alimentação, duração).
- Para firmware e software: testes automatizados quando possível, e testes manuais
  descritos passo a passo com resultado esperado e resultado obtido.
- Um teste que falhou é registrado como falhou. A etapa só fecha quando todos
  passam ou quando a falha é aceita por decisão registrada.

### 5. Fechamento

- Atualizar a tabela de estado no `README.md`.
- Registrar a etapa no `CHANGELOG.md`.
- Revisar se alguma pendência nova precisa virar etapa futura.

## Convenções

- **Idioma:** documentação em português; nomes de arquivos, código, variáveis e
  mensagens de commit em inglês (para compatibilidade com ferramentas e bibliotecas).
- **Commits:** mensagem curta no imperativo, prefixada pela área:
  `docs:`, `hw:`, `fw:`, `sw:`, `test:`, `chore:`.
  Exemplo: `hw: add power supply schematic for stage 3`.
- **Unidades:** sempre explícitas (V, A, °C, %UR, lux, ppm).
- **Versões:** firmware e software usam versionamento semântico (`MAJOR.MINOR.PATCH`).

## Modelo de registro de teste

Ver `testes/0000-modelo.md`.
