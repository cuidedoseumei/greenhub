# Visão geral

## Objetivo

Construir um **produto** de hardware + software que monitore e controle o ambiente de
cultivos indoor, de forma confiável e verificável. O sistema deve atender desde uma
tenda pequena (0,60 m × 0,60 m) até salas e galpões, e deve gerenciar **mais de um
ambiente simultaneamente**.

O foco é em medição, parametrização e resultado: o cultivador define os alvos, o
sistema mantém o ambiente dentro deles e registra o que aconteceu.

## Respostas do levantamento (Etapa 1, 2026-11-09)

| # | Pergunta | Resposta |
|---|----------|----------|
| 1 | Tamanho e tipo do espaço | Produto para tendas de cultivo de cannabis, de 0,60 m × 0,60 m até salas e galpões. Deve controlar mais de um ambiente ao mesmo tempo. |
| 2 | Plantas e método | Não é determinante. Foco em medições, parametrização e resultados. |
| 3 | Grandezas essenciais | Temperatura e umidade do ar. As demais são desejáveis. |
| 4 | Atuadores existentes | Luz Master Plants Quantum Bar 240 W PRO-MASTER (bivolt, dimmer integrado de tipo não informado). Exaustor Vivosun AeroZesh T6 150 mm (110–240 V, 35 W, motor EC/PWM) com controlador GrowHub E42. Detalhes em `hardware/equipamentos-existentes.md`. |
| 5 | Experiência com eletrônica | Nenhuma. O projeto precisa ser modular: módulos prontos, sem solda. |
| 6 | Onde o software roda | Hub local + nós por ambiente. Decisão `0003` aceita. |
| 7 | Orçamento | R$ 2.000 para a versão 1. |
| 8 | Rede elétrica | Testes em 220 V. O produto deve ser bivolt (127 V / 220 V). |

## Escopo da versão 1

### Monitoramento
- Temperatura e umidade relativa do ar, por ambiente (**essencial**).
- Déficit de pressão de vapor (VPD) calculado a partir de temperatura e umidade (**essencial**, só software).
- Extensões desejáveis: temperatura de folha, CO₂, umidade de substrato, luminosidade,
  pH / EC de solução.

### Controle
- Exaustão por limites de temperatura e umidade (**essencial**).
- Iluminação por fotoperíodo (**essencial**).
- Extensões desejáveis: umidificador, desumidificador, aquecedor, intensidade da luz.

### Software
- Vários ambientes, cada um com seus sensores, atuadores e alvos.
- Histórico de leituras e de acionamentos.
- Painel com leituras atuais, gráficos e alertas.

## Premissas revisadas

| Premissa | Situação |
|----------|----------|
| O sistema gerencia de 1 a vários ambientes a partir de um único ponto de controle. | confirmada pela resposta 1 |
| O usuário final não faz solda nem fiação em tensão de rede. Toda montagem é por conectores e módulos prontos. | confirmada pela resposta 5 |
| Cargas em tensão de rede (luz, exaustor, umidificador) são acionadas por dispositivos certificados, nunca por relé "nu" montado pelo usuário. | derivada da resposta 5; ver decisão `0002` |
| Operação em rede local sem depender de internet; acesso remoto é camada opcional. | confirmada; decisão `0003` aceita |
| Alimentação pela rede elétrica, bivolt, sem bateria. | confirmada |
| Orçamento da versão 1: R$ 2.000, incluindo hub, nós para 2 ambientes, sensores e dispositivos de acionamento. Os equipamentos já existentes (luz e exaustor) não entram nesse valor. | confirmada; detalhamento na BOM da Etapa 2 |
| Versão 1 é um protótipo funcional no ambiente do responsável; certificação e embalagem de produto ficam para depois. | proposta, a confirmar |

## Fora de escopo da versão 1

- Aplicativo móvel nativo (painel web responsivo cobre o uso pelo celular).
- Certificação do produto (INMETRO/Anatel) para venda.
- Controle de irrigação e de solução nutritiva.
- Integração com o app da Vivosun ou de outros fabricantes.

## Perguntas em aberto

1. **Quantos ambientes** a versão 1 deve controlar de fato no teste. Premissa adotada:
   2, para validar o multiambiente sem multiplicar custo. Confirmar.
2. **Tipo do dimmer** da luz e **modelo exato** do controlador Vivosun. Checklist e fotos
   pedidas em `hardware/equipamentos-existentes.md`.
3. A versão 1 é para uso próprio ou já será instalada em cultivo de terceiros?
