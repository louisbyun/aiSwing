# aiSwing™

**aiSwing™ Crypto** is an end-to-end automated swing crypto trading platform engineered from scratch for real-market execution — not demos or backtests.
aiSwing™ was designed, implemented, and is actively operated by a systems engineer with hands-on experience in:

- Production-grade backend development using **Python (Flask)**  
- Data modeling and persistence with **PostgreSQL / SQLAlchemy**
- Containerized deployment using **Docker**
- Scheduled and stateful automation via **APScheduler**
- Exchange-level execution and reconciliation via **Coinbase & Upbit APIs**
- Structured logging, diagnostics, and runtime observability
- Risk-aware automation design inspired by real manufacturing systems

The platform is developed and maintained in a live environment with real capital, real executions, and continuous iteration based on production data.


This system is built around one core philosophy:

> **Discipline beats prediction. Systems beat emotion.**

---

## 🚀 Overview

aiSwing™ is a production-grade automated trading system designed to operate under real market conditions using live capital.

The system executes real trades through direct integration with the **Coinbase Exchange API**, enabling programmatic order placement, execution tracking, and post-trade reconciliation.

It focuses on:
- Risk-first execution
- Staged entries instead of all-in trades
- Capital preservation during drawdowns
- Consistent, repeatable behavior over market cycles
![aiSwing™ Crypto](/aiSwing-arch.png)

This is a continuously running and actively maintained system.

---

## 🧠 Core Trading Philosophy

aiSwing™ does **not** try to predict tops or bottoms.

Instead, it emphasizes:

- **RSI-based staged buying**  
  Gradual position building as markets enter oversold conditions

- **Slope-adjusted risk control**  
  Entry size dynamically reduced during strong downtrends

- **Market state awareness**  
  Defensive behavior in downstream markets, aggressive only when conditions improve

- **Capital-first design**  
  Maximum investment ratio enforced at all times (cash is always reserved)

---

## ⚙️ Key Features

### 📉 Entry Logic
- 5-level RSI staged buying
- Dynamic position sizing
- Downtrend acceleration & deceleration detection
- Cascade-drop protection

### 📈 Exit Logic
- Tier-based take-profit execution
- Partial vs full exit rules based on position size
- Dust prevention and minimum execution thresholds

### 🛡️ Risk Management
- Hard cap on total capital usage
- Minimum order protection
- Trade throttling during extreme volatility
- No revenge trading, no overtrading
![My Strategy](/mystrategy.png)

---

## 🏗️ System Architecture

- **Backend**: Python (Flask)
- **Database**: PostgreSQL / SQLAlchemy ORM
- **Frontend**: Jinja2 templates, Bootstrap 5, Vue.js
- **Execution**: Exchange API–driven (Coinbase / Upbit)
- **Runtime**: Dockerized environment
- **Scheduling**: APScheduler
- **Monitoring**: Structured logs, performance metrics, ROI tracking
- **Notifications**: Telegram / Email alerts

> Designed with production stability and observability in mind.

---

## 📊 Performance Tracking

The system tracks:
- Realized vs unrealized profit
- Daily / weekly / monthly ROI
- Trade-level execution history
- Strategy-specific contribution metrics
![Performance Dashboard](/dashboard.png)

All metrics are derived from **actual executed trades**, not simulations.

---

## 🔍 What This Project Is (and Isn’t)

### ✅ This project **is**
- A real, operating automated trading system
- Built and maintained by a systems engineer
- Designed for long-term survivability
- Iteratively improved based on live data

### ❌ This project **is not**
- A signal service
- A prediction engine
- A “get rich quick” bot
- Financial advice

---

## ⚠️ Disclaimer

This project is for **educational and engineering demonstration purposes only**.

It reflects personal experimentation with automated trading systems using real capital.  
Nothing in this repository constitutes financial or investment advice.

---

## 👤 Author

Built and operated by an engineer with experience in:
- Systems engineering
- Automation & RPA
- Data-driven diagnostics
- Production-grade software systems

---

## 📌 Status

🟢 **Active development**  
🟢 **Live trading with real capital**  
🟢 **Continuous iteration & risk tuning**

## 🏗️ System Architecture

```text
                    ┌──────────────────────────┐
                    │        Web Dashboard     │
                    │   (Performance / ROI)    │
                    └────────────┬─────────────┘
                                 │
                                 ▼
┌───────────────────┐    ┌──────────────────────────┐
│   Scheduler       │───▶│     Trading Engine      │
│  (APScheduler)    │    │  - RSI Staged Buy        │
│                   │    │  - Slope Adjustment      │
│                   │    │  - Market State Filter   │
└─────────┬─────────┘    └────────────┬─────────────┘
          │                           │
          ▼                           ▼
┌───────────────────┐    ┌──────────────────────────┐
│ Market Data Layer │    │   Risk & Capital Manager │
│ - OHLCV / RSI     │    │  - Max Invest Ratio      │
│ - Indicators      │    │  - Position Sizing       │
└─────────┬─────────┘    └────────────┬─────────────┘
          │                           │
          ▼                           ▼
┌────────────────────────────────────────────────────┐
│                Exchange API Layer                  │
│           (Coinbase / Upbit Execution)             │
└─────────┬───────────────────────────────┬─────────┘
          │                               │
          ▼                               ▼
┌──────────────────────┐      ┌──────────────────────┐
│     Trade Logger     │      │   Notification Bot   │
│  - Orders / Fills    │      │ Telegram / Email     │
└─────────┬────────────┘      └──────────────────────┘
          │
          ▼
┌────────────────────────────────────────────────────┐
│                 PostgreSQL Database                │
│  Trades | Positions | Cash | ROI | Metrics         │
└────────────────────────────────────────────────────┘


---

"A system that survives long enough eventually wins.”
