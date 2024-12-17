# Crypto Alert Bot Platform

## **Platform Overview**
The platform will be designed for users interested in creating and configuring Bots to monitor cryptocurrency technical indicators. Bots will send real-time notifications via Webhooks (to Telegram or Discord), based on strategies defined by the user. The platform will be monetized through a credit-based system.

---

## **Core Features**

### **1. Bot Creation and Configuration**
- Users will be able to:
  - Create Bots based on technical indicators (e.g., RSI, MACD, moving average crossovers).
  - Configure conditions and parameters for Bot strategies.
  - Set up a general Webhook or individual Webhooks for each Bot.
  - Start, pause, and delete Bots at any time.

### **2. Credit System**
- Bots consume credits while active.
- Credits will also be required to execute Backtests.
- Available credit packages for purchase:
  - **200**
  - **500**
  - **1000** (+100 bonus)
  - **2000** (+400 bonus)
  - **4000** (+1000 bonus)
  - **7500** (+2000 bonus)
  - **10000** (+3000 bonus)
- Free credits will be provided to beta testers for initial testing.

### **3. Real-Time Notifications**
- Notifications will be sent to Discord/Telegram Webhooks when strategy parameters are met.

### **4. Backtest**
- Backtesting will allow users to validate the effectiveness of their strategies using historical data.
- Credit consumption will be proportional to the duration and complexity of the Backtest.

### **5. Payments**
- Support for payments via:
  - Cryptocurrencies using the [Depay](https://depay.com/) platform.
  - Credit card, debit card, boleto, and PIX (integrating a local payment solution).

---

## **Initial Architecture**

### **1. Platform Components**
- **Frontend**:
  - User-friendly interface for Bot configuration and credit purchases.
- **Backend**:
  - User, Bot, and credit management.
  - Bot strategy execution.
  - Integration with price APIs (e.g., Binance WebSocket API).
  - Notifications via Webhooks.
- **Database**:
  - Tables for users, Bots, strategies, credits, and logs.
- **External Services**:
  - Cryptocurrency price APIs (e.g., Binance, CoinGecko).
  - Webhooks for notifications.

### **2. Bot Execution Workflow**
1. **Bot Configuration**:
   - Users define token, strategy, and Webhook.
2. **Real-Time Execution**:
   - The service fetches prices and validates strategies.
3. **Notification**:
   - When the strategy conditions are met, the Bot sends a notification via Webhook.

### **3. Credit Consumption**
- Active Bots will consume credits hourly.
- Backtests will consume credits proportional to the analysis duration.

---

## **Suggested Technologies**

### **Backend**
- **Node.js** with frameworks like NestJS or AdonisJS.
- **Database**: PostgreSQL for persistent storage.
- **Cache**: Redis for real-time price storage.
- **Queues**: Bull for asynchronous task execution, such as sending notifications.

### **Frontend**
- **Framework**: Next.js for the web interface.

### **Infrastructure**
- **Initial Hosting Platform**: Heroku.
- **Future Scalability**: AWS, GCP, or Azure.

### **Integrations**
- Price APIs: Binance WebSocket API.
- Webhooks: Notifications via HTTP POST to Discord and Telegram.
- Payments: Depay for cryptocurrency payments and a local API for other methods.

---

## **Development Plan**

### **Phase 1: Initial Prototype (MVP)**
1. Basic Bot configuration (token, strategy, Webhook).
2. Real-time notifications via Webhook.
3. Simple credit consumption (hourly).
4. Basic cryptocurrency payments.

### **Phase 2: Beta Testing**
1. Invite beta testers.
2. Provide free credits for testing.
3. Collect feedback for adjustments.

### **Phase 3: Official Launch**
1. Implement Backtesting.
2. Launch credit packages for purchase.
3. Improve user interface.
4. Scale infrastructure for increased demand.

---

## **Platform Name**
### **Crypto Copilot**
- **Meaning**: Acts as a copilot to help users make informed decisions without making decisions on their behalf.
- **Future Evolution**: The platform may eventually include full automation for buying/selling assets.

---

## **References**
- **3Commas** ([https://3commas.io](https://3commas.io)) for inspiration on features and monetization.
- **Binance WebSocket API** ([https://binance-docs.github.io](https://binance-docs.github.io)) for real-time price data.
- **Depay** ([https://depay.com](https://depay.com)) for cryptocurrency payments.

---

## **Next Steps**
1. Set up a GitHub repository for version control.
2. Develop the MVP for initial testing.
3. Plan marketing to acquire beta testers.
4. Prepare for infrastructure scaling based on demand.
