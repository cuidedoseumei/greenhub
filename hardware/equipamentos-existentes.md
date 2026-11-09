# Equipamentos existentes

Levantamento dos equipamentos que já existem no ambiente de teste. Os dados abaixo vêm
das **páginas dos fabricantes e da loja** (lidas em 2026-11-09) e ainda **não foram
conferidos na etiqueta do equipamento físico**. A coluna "Situação" diz de onde veio
cada valor.

Legenda: `fabricante` = página oficial ou loja; `verificado` = conferido no equipamento;
`não informado` = nenhuma fonte diz.

## Rede elétrica do local

| Item | Valor | Situação |
|------|-------|----------|
| Tensão de rede dos testes | 220 V | informado pelo responsável |
| Produto deve ser bivolt (127 V / 220 V) | sim | requisito RNF-12 |
| Tomadas suficientes perto da tenda | ? | não verificado |
| Wi-Fi 2,4 GHz alcança o local do cultivo | ? | não verificado |

## Luz — Master Plants Quantum Bar 240 W PRO-MASTER

Fonte: https://masterplantsloja.com.br/products/led-quantum-bar-240w-pro-master

| Item | Valor | Situação |
|------|-------|----------|
| Potência nominal | 240 W | fabricante |
| Tensão de entrada | "Bivolt" (faixa não informada) | fabricante |
| Corrente estimada | ≈ 1,1 A em 220 V; ≈ 1,9 A em 127 V (cálculo a partir de 240 W, sem fator de potência) | estimativa |
| Driver | "Master Plants Integrado"; marca e modelo não informados | fabricante |
| Dimmer | "Sim", "dimmer integrado". Tipo (potenciômetro, 0–10 V, PWM) e localização não informados | fabricante |
| Expansão em série | sim, com cabo incluso | fabricante |
| Chips | 896 (864 full spectrum + 32 deep red), 3000 K + 5000 K + 660 nm | fabricante |
| Eficácia / PPF | 2,9 µmol/J / 696 µmol/s | fabricante |
| Dimensões / peso | 56 × 52 × 4 cm / 2,35 kg | fabricante |
| Cabo AC | 170 cm; tipo de plugue não informado | fabricante |
| Garantia | 5 anos | fabricante |
| Preço de referência | R$ 975,87 (promocional) | loja, 2026-11-09 |

**O que isso define**
- Para a versão 1, a luz é tratada como carga liga/desliga (RF-06). Um dispositivo de
  acionamento certificado de 10 A tem folga maior que 1,5× em 127 V e em 220 V (RNF-02).
- RF-15 (intensidade automática) depende de saber o tipo do dimmer. Se for um
  potenciômetro no painel, exige abrir o equipamento e sai da versão 1.
- "Expansão em série" sugere que o dimmer de um painel pode comandar os outros; isso
  é um indício de sinal de controle externo (0–10 V ou PWM), mas **não é confirmação**.

**Pendente (responsável):** foto da etiqueta do driver e do botão de dimmer com seu
cabo/conector, e do conector do "cabo de expansão em série". Alternativa: perguntar ao
fabricante (sac@masterplants.com.br) qual é o protocolo de dimerização.

## Exaustor — Vivosun AeroZesh T6 (150 mm) com controlador GrowHub E42

Fontes: página oficial do AeroZesh T6 e manual do GrowHub E42A+ em vivosun.com. O anúncio
do Mercado Livre não pôde ser lido automaticamente (acesso bloqueado). O manual oficial
trata do **E42A+**; o kit comprado diz "E42". Confirmar o modelo exato na etiqueta.

### Exaustor AeroZesh T6 (modelo VSV-AZT6)

| Item | Valor | Situação |
|------|-------|----------|
| Tensão de entrada | 110–240 V, 50/60 Hz | fabricante |
| Potência | 35 W | fabricante |
| Corrente | não informada (≈ 0,16 A em 220 V; ≈ 0,3 A em 127 V) | estimativa |
| Motor | EC, controlado por PWM, 10 velocidades, 3000 RPM | fabricante |
| Vazão máxima | 408 CFM (≈ 693 m³/h) | fabricante |
| Ruído | 32 dBA (ficha) / 28 dB (descrição); valores divergem | fabricante |
| Proteção | IP44 | fabricante |
| Cabo de força | 2 m | fabricante |
| Cabo até o controlador | 3 m | fabricante |
| Funciona sem controlador? | não informado em nenhuma fonte | não informado |
| Garantia | 2 anos | fabricante |

### Controlador GrowHub E42 (dados do manual do E42A+)

| Item | Valor | Situação |
|------|-------|----------|
| Alimentação | 12 V, 3 W; "draws power directly from these devices" (alimentado pelo exaustor pelo cabo de controle) | fabricante |
| Conexão com o exaustor | portas "Type-C" A/B; FAQ cita "control cable (RJ45 or Type-C)"; conector físico exato não detalhado | fabricante |
| Sensores | sensor interno + sonda externa de temperatura e umidade (3 m, plugue 2,5 mm) | fabricante |
| Faixa de operação | 0–60 °C, 35–85 %UR | fabricante |
| Wi-Fi | só 2,4 GHz; app Vivosun via nuvem; controle básico offline no aparelho | fabricante |
| Automação própria | modo automático por temperatura, umidade e VPD | fabricante |
| API pública | não existe documentação | não informado |

**O que isso define**
- O exaustor é carga pequena (35 W). Qualquer dispositivo de acionamento certificado serve.
- O controlador E42 é **alimentado pelo exaustor**. Se a alimentação do exaustor for
  cortada (opção I2), o E42 desliga junto. Por isso a pendência 3 do roadmap (o E42
  mantém a configuração após queda de energia?) é decisiva.
- O motor é EC com PWM e 10 velocidades. Controle direto da velocidade (opção I3) é
  tecnicamente possível, mas o conector e o protocolo são proprietários e não documentados.
  Fica fora da versão 1 por violar a decisão `0002` (exigiria abrir ou adaptar equipamento).

**Opções de integração (decisão na Etapa 2)**

| Opção | Descrição | Prós | Contras | Avaliação preliminar |
|-------|-----------|------|---------|----------------------|
| I1 | E42 continua controlando o exaustor; nosso sistema só monitora. | zero risco | não atende RF-05 | só como fallback |
| I2 | E42 em velocidade fixa; nosso sistema liga/desliga a alimentação do conjunto por dispositivo certificado. | atende RF-05 com o que existe | sem controle de velocidade; E42 desliga junto; depende da pendência 3 | **candidata para a versão 1** |
| I3 | Nosso nó controla a velocidade pela entrada PWM do exaustor. | controle fino | conector e protocolo proprietários, não documentados; fere `0002` | fora da versão 1 |
| I4 | Exaustor novo com entrada de controle documentada, Vivosun fica como está. | independência total | custo adicional; aperta o orçamento de R$ 2.000 | avaliar na BOM |

**Pendente (responsável):**
1. Foto da etiqueta atrás do controlador (modelo exato: E42, E42A ou E42A+).
2. Foto da etiqueta do exaustor e do conector entre exaustor e controlador.
3. Teste seguro: com o E42 configurado em velocidade fixa, tirar o exaustor da tomada
   por 1 minuto, religar e observar se ele volta na mesma velocidade sem intervenção.
   Registrar o resultado em `testes/etapa-01-e42-queda-de-energia.md`.
