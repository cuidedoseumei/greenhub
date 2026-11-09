# Equipamentos existentes

Levantamento dos equipamentos que já existem no ambiente de teste e do que precisa ser
verificado fisicamente antes da Etapa 2. **Nada aqui foi verificado ainda.**

## Luz — Master Plants 240 W, ajuste manual de intensidade

| Item | Valor | Como verificar | Situação |
|------|-------|----------------|----------|
| Tensão de entrada | ? | Etiqueta do driver (fonte) | não verificado |
| Corrente de entrada | ? | Etiqueta do driver | não verificado |
| Modelo do driver | ? | Etiqueta do driver (ex.: Mean Well HLG/XLG, Sosen, Inventronics) | não verificado |
| Tipo de dimerização | ? | Etiqueta ou manual: "0–10 V", "PWM", "resistência", ou apenas potenciômetro interno | não verificado |
| Conector do dimmer | ? | Foto do cabo/conector do botão de ajuste | não verificado |

**O que isso define**
- Tensão e corrente: dimensionamento do dispositivo de acionamento certificado (RNF-02).
- Tipo de dimerização: se for 0–10 V ou PWM, RF-15 (intensidade automática) é viável com
  módulo pronto. Se for só potenciômetro, RF-15 exige abrir o equipamento e sai da versão 1.

**Pedido:** foto nítida da etiqueta do driver e do botão de ajuste com seu cabo.

## Exaustor — Vivosun com controlador E42

O que foi levantado em fontes públicas (não verificado no equipamento):

- O E42 é um controlador Wi-Fi 2,4 GHz com sensor de temperatura e umidade e app
  próprio da Vivosun. Não há API pública documentada.
- Existem variantes E42, E42A e E42A+, com acessórios não compatíveis entre si.

| Item | Valor | Como verificar | Situação |
|------|-------|----------------|----------|
| Modelo exato do controlador | E42 / E42A / E42A+ ? | Etiqueta atrás do controlador | não verificado |
| Modelo do exaustor | ? | Etiqueta no corpo do exaustor | não verificado |
| Tensão e corrente do exaustor | ? | Etiqueta | não verificado |
| Como o controlador se liga ao exaustor | cabo proprietário? | Foto do conector | não verificado |
| O exaustor funciona sem o controlador? | ? | Teste: ligar o exaustor na tomada sem o E42 | não verificado |

**Opções de integração (decisão na Etapa 2)**

| Opção | Descrição | Prós | Contras |
|-------|-----------|------|---------|
| I1 | Manter o E42 controlando o exaustor; nosso sistema só monitora o ambiente. | zero risco | não atende RF-05 |
| I2 | Deixar o E42 em modo manual (velocidade fixa) e ligar/desligar a alimentação do conjunto por dispositivo certificado. | atende RF-05 com o que já existe | sem controle de velocidade; verificar se o E42 mantém configuração após queda de energia |
| I3 | Substituir o E42 por controle direto da velocidade pela entrada do exaustor (0–10 V ou PWM). | controle fino | depende de conector proprietário; pode ser inviável sem abrir equipamento |
| I4 | Nosso sistema controla exaustor próprio (novo), e o Vivosun fica como está. | independência total | custo de um exaustor novo |

**Pedido:** fotos das etiquetas do controlador e do exaustor, e do conector entre eles.

## Rede elétrica do local

| Item | Valor | Situação |
|------|-------|----------|
| Tensão de rede (127 V / 220 V) | ? | não verificado |
| Há tomadas suficientes perto da tenda? | ? | não verificado |
| Rede Wi-Fi 2,4 GHz alcança o local do cultivo? | ? | não verificado |
