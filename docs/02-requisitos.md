# Requisitos

**Situação:** proposta inicial (Etapa 1), aguardando aprovação do responsável.

Cada requisito recebe um identificador único e nunca é renumerado. Se um requisito for
removido, ele é marcado como `cancelado` com o motivo, e o número não é reaproveitado.

Prioridade: `essencial` (obrigatório na versão 1) ou `desejável` (pode ficar para depois).

Valores numéricos (faixas, precisões, prazos) são **propostas** e podem ser ajustados
antes da aprovação.

## Requisitos funcionais (RF)

| ID | Descrição | Prioridade | Situação | Verificado em |
|----|-----------|------------|----------|---------------|
| RF-01 | Medir a temperatura do ar de cada ambiente, faixa de 10 a 45 °C, erro máximo ±0,5 °C. | essencial | proposto | — |
| RF-02 | Medir a umidade relativa do ar de cada ambiente, faixa de 20 a 95 %UR, erro máximo ±3 %UR. | essencial | proposto | — |
| RF-03 | Calcular e exibir o VPD de cada ambiente a partir de RF-01 e RF-02, com compensação configurável de temperatura de folha. | essencial | proposto | — |
| RF-04 | Gerenciar vários ambientes simultaneamente, cada um com seus próprios sensores, atuadores, alvos e histórico, a partir de um único painel. | essencial | proposto | — |
| RF-05 | Controlar a exaustão de cada ambiente por limites de temperatura e umidade (liga acima de um limite, desliga abaixo, com histerese configurável). | essencial | proposto | — |
| RF-06 | Controlar a iluminação de cada ambiente por fotoperíodo (horário de ligar e desligar configurável por ambiente). | essencial | proposto | — |
| RF-07 | Permitir acionamento manual de qualquer atuador pelo painel, com indicação clara de que o modo manual está ativo e retorno automático ao modo automático após tempo configurável. | essencial | proposto | — |
| RF-08 | Registrar o histórico de leituras de cada sensor, com intervalo configurável (padrão 60 s) e retenção mínima de 12 meses. | essencial | proposto | — |
| RF-09 | Registrar cada acionamento de atuador com data, hora, ambiente, estado e motivo (regra que disparou ou comando manual). | essencial | proposto | — |
| RF-10 | Exibir no painel, por ambiente, as leituras atuais, o estado dos atuadores e gráficos do histórico com período selecionável. | essencial | proposto | — |
| RF-11 | Gerar alerta quando temperatura ou umidade ficarem fora da faixa alvo por mais de um tempo configurável, ou quando um sensor ficar sem comunicação. | essencial | proposto | — |
| RF-12 | Permitir perfis de alvo por fase de cultivo (ex.: vegetativo, floração) aplicáveis a um ambiente. | desejável | proposto | — |
| RF-13 | Controlar umidificador e desumidificador por limites de umidade. | desejável | proposto | — |
| RF-14 | Controlar aquecedor por limite de temperatura. | desejável | proposto | — |
| RF-15 | Ajustar automaticamente a intensidade da luz (sinal 0–10 V ou PWM), quando o driver permitir. | desejável | proposto | — |
| RF-16 | Medir temperatura de folha (sensor infravermelho) para VPD mais preciso. | desejável | proposto | — |
| RF-17 | Medir concentração de CO₂. | desejável | proposto | — |
| RF-18 | Exportar o histórico de um ambiente e período em CSV. | desejável | proposto | — |
| RF-19 | Enviar alertas para fora do painel (notificação por aplicativo de mensagens ou e-mail). | desejável | proposto | — |

## Requisitos não funcionais (RNF)

| ID | Descrição | Prioridade | Situação | Verificado em |
|----|-----------|------------|----------|---------------|
| RNF-01 | Nenhuma etapa de montagem exige solda nem fiação em tensão de rede pelo usuário. Toda conexão é por módulo pronto e conector. | essencial | proposto | — |
| RNF-02 | Cargas em tensão de rede são acionadas somente por dispositivos certificados para esse fim, com corrente nominal de pelo menos 1,5× a corrente da carga. | essencial | proposto | — |
| RNF-03 | Em caso de perda de rede ou do servidor central, o controle local de cada ambiente continua operando com as últimas regras recebidas (fotoperíodo e limites). | essencial | proposto | — |
| RNF-04 | O sistema opera 30 dias contínuos sem reinício manual. | essencial | proposto | — |
| RNF-05 | Funciona integralmente em rede local, sem acesso à internet. Internet é opcional (acesso remoto, notificações). | essencial | proposto | — |
| RNF-06 | O relógio usado para fotoperíodo tem erro inferior a 1 minuto por mês e sobrevive a queda de energia. | essencial | proposto | — |
| RNF-07 | A versão 1 suporta de 1 a 8 ambientes; a arquitetura não impõe esse limite. | essencial | proposto | — |
| RNF-08 | Adicionar um ambiente novo não exige reprogramar os existentes. | essencial | proposto | — |
| RNF-09 | Um sensor pode ser substituído por outro do mesmo modelo sem reprogramação. | desejável | proposto | — |
| RNF-10 | Documentação de montagem e configuração escrita para usuário sem experiência em eletrônica. | desejável | proposto | — |
| RNF-11 | O painel é acessível por navegador em computador e celular. | essencial | proposto | — |
| RNF-12 | Todo componente ligado à rede elétrica é bivolt (100–240 V, 50/60 Hz). Os testes da versão 1 são feitos em 220 V. | essencial | proposto | — |
| RNF-13 | O custo total dos componentes novos da versão 1 (hub, nós para 2 ambientes, sensores, dispositivos de acionamento) não ultrapassa R$ 2.000. | essencial | proposto | — |

## Situações possíveis

- `proposto`: escrito, ainda não aprovado.
- `aprovado`: aceito como requisito do projeto.
- `atendido`: implementado e verificado (coluna "Verificado em" aponta o registro de teste).
- `cancelado`: removido, com motivo registrado abaixo.

## Requisitos cancelados

*(nenhum)*
