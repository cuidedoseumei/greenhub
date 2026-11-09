# 0002 — Hardware modular, sem solda e sem fiação em tensão de rede

**Data:** 2026-11-09
**Etapa:** 1
**Situação:** proposta (aguarda aprovação do responsável)

## Contexto

O responsável pelo projeto não tem experiência com eletrônica nem solda (resposta 5 do
levantamento). O sistema vai acionar cargas em tensão de rede (luz de 240 W, exaustor e,
no futuro, umidificador e aquecedor). Fiação de rede feita por quem não tem experiência
é risco de choque e incêndio. É preciso decidir, antes da escolha de componentes, qual
abordagem de montagem o projeto adota.

## Alternativas consideradas

### Alternativa A — Placa dedicada (PCB própria) com relés e fonte integrados
- Prós: produto final mais compacto e barato em escala.
- Contras: exige projeto de PCB, solda, testes de isolamento e, para venda, certificação.
  Inviável para a versão 1 com a equipe atual.

### Alternativa B — Módulos prontos com conectores, e cargas de rede acionadas por dispositivos certificados
- Controlador: placa de desenvolvimento com conectores padronizados (sem solda).
- Sensores: módulos com cabo e conector.
- Cargas de rede: tomadas ou relés inteligentes certificados, controlados pela rede local
  pelo nosso software.
- Prós: montagem sem solda, sem contato com tensão de rede, cada peça substituível,
  segurança delegada a dispositivos já certificados.
- Contras: custo unitário maior; aparência menos "produto"; dependência de protocolos
  dos dispositivos de acionamento (deve-se escolher dispositivos com controle local, sem
  depender de nuvem do fabricante).

### Alternativa C — Controlador comercial pronto (ex.: Vivosun, AC Infinity, TrolMaster)
- Prós: zero montagem.
- Contras: não é o produto que queremos construir; sem acesso aos dados e às regras;
  multiambiente limitado ao ecossistema do fabricante.

## Decisão

Alternativa B. Na versão 1:

1. Nenhum passo de montagem exige solda (RNF-01).
2. Nenhuma carga em tensão de rede é ligada a relé montado pelo usuário. O acionamento
   é feito por dispositivo certificado, dimensionado com folga (RNF-02).
3. Os dispositivos de acionamento devem aceitar controle pela rede local sem internet
   (RNF-05). A escolha do modelo é da Etapa 2.
4. Sensores e controlador usam módulos com conector; o padrão de conector é escolhido
   na Etapa 2.

## Consequências

- A Etapa 2 escolhe os componentes dentro dessa restrição.
- Fica para uma versão futura, com equipe habilitada, a integração em placa própria.
- A luz Master Plants, se o driver tiver entrada de dimerização 0–10 V, poderá ter a
  intensidade controlada por módulo pronto de 0–10 V; isso é RF-15 (desejável) e não
  altera esta decisão.

## Verificação

Na Etapa 4 (acionamento), o registro de teste deve confirmar que o procedimento de
montagem foi executado sem ferramenta de solda e sem abrir nenhum equipamento de rede.
