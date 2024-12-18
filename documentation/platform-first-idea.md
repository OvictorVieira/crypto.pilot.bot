# Plataforma de Bots Cripto de Alertas

## **Visão Geral da Plataforma**
A plataforma será destinada a usuários interessados em criar e configurar Bots para monitorar indicadores técnicos de criptomoedas. Os Bots poderão realizar notificações em tempo real através de Webhooks (para Telegram ou Discord), baseando-se em estratégias definidas pelo usuário. A monetização da plataforma será feita por meio de um sistema de créditos.

---

## **Funcionalidades Principais**

### **1. Criação e Configuração de Bots**
- Os usuários poderão:
  - Criar Bots com base em indicadores técnicos (e.g., RSI, MACD, cruzamento de médias móveis).
  - Configurar condições e parâmetros das estratégias dos Bots.
  - Definir um Webhook geral ou individual para cada Bot.
  - Iniciar, pausar e deletar Bots a qualquer momento.

### **2. Sistema de Créditos**
- Os Bots consomem créditos enquanto estão ativos.
- Créditos também serão necessários para executar Backtests.
- Pacotes de créditos disponíveis para compra:
  - **200**
  - **500**
  - **1000** (+100 bônus)
  - **2000** (+400 bônus)
  - **4000** (+1000 bônus)
  - **7500** (+2000 bônus)
  - **10000** (+3000 bônus)
- Créditos gratuitos serão disponibilizados para usuários beta testers para testes iniciais.

### **3. Notificações em Tempo Real**
- As notificações serão enviadas para Webhooks do Discord/Telegram quando os parâmetros definidos na estratégia forem atendidos.

### **4. Backtest**
- O Backtest permitirá aos usuários validar a eficácia de suas estratégias utilizando dados históricos.
- O consumo de créditos será proporcional à duração e complexidade do Backtest.

### **5. Copy Bot**
- Os usuários que criarem Bots com Backtest poderão optar por liberar esses Bots para Copy Bot.
- Outros usuários poderão copiar o Bot e utilizá-lo em suas estratégias.
- O criador original do Bot receberá uma porcentagem X dos créditos consumidos ("gás") por cada usuário que copiar e usar o Bot.

### **6. Pagamentos**
- Suporte a pagamentos com:
  - Criptomoedas, utilizando a plataforma [Depay](https://depay.com/).
  - Cartão de crédito/débito, boleto e PIX (integrando uma solução local).

---

## **Arquitetura Inicial**

### **1. Componentes da Plataforma**
- **Frontend**:
  - Interface amigável para configuração de Bots e compra de créditos.
- **Backend**:
  - Gerenciamento de usuários, Bots e créditos.
  - Execução das estratégias dos Bots.
  - Integração com APIs de preços (e.g., Binance WebSocket API).
  - Notificações via Webhook.
- **Banco de Dados**:
  - Tabelas para usuários, Bots, estratégias, créditos e logs.
- **Serviços Externos**:
  - APIs de preços de criptomoedas (e.g., Binance, CoinGecko).
  - Webhooks para notificações.

### **2. Fluxo de Operação dos Bots**
1. **Configuração do Bot**:
   - O usuário define token, estratégia e Webhook.
2. **Execução em Tempo Real**:
   - O serviço coleta preços e valida estratégias.
3. **Notificação**:
   - Caso a estratégia seja atendida, o Bot envia uma notificação via Webhook.

### **3. Consumo de Créditos**
- Bots ativos consomem créditos por hora.
- Backtests consomem créditos proporcionalmente à análise.
- Copy Bots consomem créditos, com parte desses créditos sendo repassados ao criador original.

---

## **Tecnologias Sugeridas**

### **Backend**
- **Node.js** com framework como NestJS ou AdonisJS.
- **Banco de Dados**: PostgreSQL para armazenamento persistente.
- **Cache**: Redis para armazenamento de preços em tempo real.
- **Filas**: Bull para execução assíncrona de tarefas como envio de notificações.

### **Frontend**
- **Framework**: Next.js para interface web.

### **Infraestrutura**
- **Plataforma de Hospedagem Inicial**: Heroku.
- **Escalabilidade Futura**: AWS, GCP ou Azure.

### **Integrações**
- APIs de Preços: Binance WebSocket API.
- Webhooks: Envio via HTTP POST para Discord e Telegram.
- Pagamentos: Depay para criptomoedas e uma API local para outros métodos.

---

## **Plano de Desenvolvimento**

### **Fase 1: Protótipo Inicial (MVP)**
1. Configuração básica de Bots (token, estratégia, Webhook).
2. Sistema de notificações via Webhook.
3. Consumo de créditos simples (por hora).
4. Pagamentos básicos com criptomoedas.

### **Fase 2: Beta Testing**
1. Convite para usuários beta testers.
2. Disponibilização de créditos gratuitos.
3. Coleta de feedback para ajustes.

### **Fase 3: Lançamento Oficial**
1. Implementação de Backtest.
2. Venda de créditos com pacotes.
3. Melhorias na interface do usuário.
4. Escalabilidade da infraestrutura.

---

## **Nome da Plataforma**
### **Crypto Copilot**
- **Significado**: Atua como um copiloto para ajudar o usuário a tomar decisões informadas, sem tomar decisões por conta própria.
- **Evolução Futura**: A plataforma poderá, eventualmente, incluir automação completa de compra/venda de ativos.

---

## **Referências**
- **3Commas** ([https://3commas.io](https://3commas.io)) como inspiração para funcionalidades e monetização.
- **Binance WebSocket API** ([https://binance-docs.github.io](https://binance-docs.github.io)) para coleta de preços em tempo real.
- **Depay** ([https://depay.com](https://depay.com)) para pagamentos com criptomoedas.

---

## **Próximos Passos**
1. Configurar repositório no GitHub para controle de versão.
2. Desenvolver MVP para testes iniciais.
3. Estruturar plano de marketing para aquisição de usuários beta testers.
4. Planejar migração para infraestrutura escalável conforme a demanda.

