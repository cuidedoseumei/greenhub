# Teste — Etapa 01 — E42 mantém configuração após queda de energia?

**Data:** (preencher)
**Responsável:** (preencher)
**Resultado geral:** (aprovado | reprovado)

## Objetivo

Verificar se o controlador GrowHub E42 volta ao mesmo estado (velocidade fixa do
exaustor) depois de perder e recuperar a alimentação, sem intervenção. Define se a
opção de integração I2 (ligar/desligar o conjunto exaustor + E42 pela alimentação) é
viável. Cobre a pendência 3 do roadmap e dá suporte a RF-05.

## Condições do teste

- Local e temperatura ambiente:
- Tensão de rede medida ou nominal: 220 V (nominal)
- Modelo exato do controlador (etiqueta): E42 / E42A / E42A+ → (preencher)
- Versão do app Vivosun, se usado:
- Duração: cerca de 10 minutos

## Procedimento

1. No E42, colocar o exaustor em modo manual com velocidade fixa (sugestão: nível 5 de 10).
   Anotar a velocidade e o que a tela mostra.
2. Esperar 1 minuto e confirmar que o exaustor está girando nessa velocidade.
3. Retirar o plugue do exaustor da tomada (o E42 deve apagar junto, pois é alimentado
   pelo exaustor). Anotar se o E42 apagou.
4. Esperar 1 minuto.
5. Religar o plugue. Cronometrar quanto tempo o exaustor leva para voltar a girar.
6. Anotar: voltou sozinho? na mesma velocidade? no mesmo modo (manual)? a tela pediu
   alguma confirmação ou reconfiguração?
7. Repetir os passos 3 a 6 com 10 minutos desligado.
8. Repetir uma vez com o E42 em modo automático (por temperatura) em vez de manual,
   e anotar se o modo automático é mantido.

## Resultados

| # | Verificação | Esperado | Obtido | Situação |
|---|-------------|----------|--------|----------|
| 1 | E42 apaga ao desligar o exaustor da tomada | sim (alimentado pelo exaustor) | | |
| 2 | Exaustor volta a girar sozinho após religar (1 min) | sim, em até 30 s | | |
| 3 | Mesma velocidade de antes (1 min) | sim | | |
| 4 | Mesmo modo (manual) de antes (1 min) | sim | | |
| 5 | Exaustor volta a girar sozinho após religar (10 min) | sim | | |
| 6 | Mesma velocidade e modo (10 min) | sim | | |
| 7 | Modo automático mantido após queda | sim | | |

## Evidências

Fotos da tela do E42 antes e depois, em `testes/evidencias/etapa-01/`.

## Observações e problemas encontrados

## Pendências geradas
