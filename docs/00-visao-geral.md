# Visão geral

## Objetivo

Construir um sistema de hardware e software que monitore e controle o ambiente de um
cultivo de plantas indoor, de forma confiável e verificável, permitindo ao cultivador
acompanhar as condições e automatizar rotinas.

## O que o sistema deve cobrir (visão inicial, a refinar na Etapa 1)

### Monitoramento (leitura de sensores)
- Temperatura e umidade do ar.
- Umidade do solo / substrato.
- Luminosidade.
- Possíveis extensões: CO₂, pH e condutividade elétrica (EC) de solução nutritiva,
  temperatura da água, nível de reservatório.

### Controle (atuadores)
- Iluminação (liga/desliga e, possivelmente, intensidade).
- Ventilação / exaustão.
- Irrigação (bomba ou válvula).
- Possíveis extensões: aquecedor, umidificador, desumidificador.

### Software
- Registro histórico das leituras.
- Visualização (painel) local e/ou remota.
- Regras de automação (horários, limites, ciclos de fotoperíodo).
- Alertas quando algo sai do esperado.

## Premissas iniciais

Estas premissas ainda **não foram validadas** e serão confirmadas ou revistas na Etapa 1.

- Um único ambiente de cultivo (uma tenda ou estante) na primeira versão.
- Operação em rede local; acesso remoto é extensão futura.
- O cultivador tem acesso físico ao equipamento para manutenção.
- Alimentação pela rede elétrica, sem bateria na primeira versão.

## Fora de escopo (por enquanto)

- Múltiplos ambientes gerenciados pelo mesmo controlador.
- Aplicativo móvel nativo.
- Integração com plataformas de terceiros.

## Perguntas em aberto

As respostas definem a Etapa 1 e serão registradas em `02-requisitos.md`.

1. Qual o tamanho e tipo do espaço de cultivo (tenda, armário, estante, sala)?
2. Quais plantas e qual método (solo, hidroponia, coco)?
3. Quais grandezas são essenciais e quais são desejáveis?
4. Quais atuadores já existem (lâmpadas, exaustor, bomba) e qual sua alimentação
   (127 V / 220 V, 12 V, 24 V)?
5. Nível de experiência com eletrônica e solda: isso define se o hardware será com
   módulos prontos ou placa dedicada.
6. Onde o software vai rodar (no próprio controlador, em um computador local, em nuvem)?
7. Orçamento aproximado para a primeira versão.
