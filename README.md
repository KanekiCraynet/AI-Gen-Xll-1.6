# Documentation: AI Gen XII EA.mq4

**Documentation: AI Gen XII EA.mq4**

**1. Overview**
The AI Gen XII EA is an Expert Advisor script written in MQL4 for MetaTrader 4. It leverages AI-based trading logic using GPT-4o and ATNet to enhance trading strategies. The EA includes automated trading features, risk management, and time filtering mechanisms.

**2. Input Parameters**
- `Risk`: Boolean flag for risk management.
- `automatic`: Boolean flag for enabling/disabling automated trading.
- `FixedLot`: Default fixed lot size (0.01).
- `PropFirm`: Boolean flag to tailor the strategy for prop firms.
- `Trailing`: Boolean flag for enabling trailing stop.
- `TrailingStart`: Distance in pips before trailing starts.
- `TrailingStop`: Distance in pips for trailing stop.
- `MagicNumber`: Unique identifier for EA trades.
- `Comment`: Label for trade identification.
- `GPTModel`: AI model used (GPT-4o).
- `Aggressivity`: Defines trading style (Low Aggressivity).
- `Function`: Role of the EA (Advisor only).
- `DisableAnimation`: Boolean flag to disable UI animations.

**3. Time Filtering**
- `StartHour`, `StartMinute`: Defines the beginning of trading hours.
- `EndHour`, `EndMinute`: Defines the end of trading hours.

**4. Core Variables**
- `MaxSpread`: Maximum allowed spread.
- `MaxTrailing`: Maximum allowed trailing stop.
- `RiskPercent`: Defines the percentage of capital to risk per trade.
- `Secs`, `Stop`, `MaxDistance`, `Delta`: Variables related to risk and execution.

**5. Initialization (init() function)**
- Resets global variables.
- Fetches market data such as leverage, lot step, max/min lot size, margin required, and stop levels.
- Adjusts parameters based on broker conditions.
- Prints warnings if the broker is unsuitable.
- Calculates spread, lot sizing, and initializes array storage.

**6. Execution (start() function)**
- Updates trade history and calculates recent profit/loss data.
- Uses moving averages to analyze spread variations.
- Dynamically adjusts trailing stop levels based on market conditions.
- Ensures compliance with broker-imposed limits (e.g., stop level constraints).

**7. Risk Management**
- Dynamically calculates trade lot sizes based on account balance and risk percentage.
- Prevents excessive lot sizes beyond broker-defined limits.
- Implements stop loss and trailing stop adjustments for active trades.

**8. Order Execution**
- Places buy/sell orders based on AI-generated signals.
- Ensures trade conditions meet defined criteria before execution.
- Incorporates logic to avoid high spread trades.

**9. Broker Suitability Check**
- Warns users if the broker's stop level or freeze level is too restrictive.
- Adjusts calculations to work within broker-defined constraints.

**10. Conclusion**
AI Gen XII EA is a sophisticated AI-driven Expert Advisor designed to optimize trading execution while managing risk efficiently. It integrates AI capabilities to enhance trade decision-making while adhering to market constraints. The EA is best suited for traders looking to leverage automated trading with AI assistance.
