
# Stock Trading Simulator Using Deep Reinforcement Learning

This repository contains a project for a **stock trading bot** developed using **deep reinforcement learning** techniques. The aim of this project is to build an automated trading system that optimizes trading strategies and adapts dynamically to market conditions, minimizing risk while maximizing profit.

## Overview

In financial markets, consistently profitable trading strategies are challenging to implement due to the dynamic and complex nature of stock price fluctuations. This project leverages reinforcement learning (RL) techniques to enable a trading bot to learn optimal **buy**, **sell**, and **hold** actions based on historical market data and technical indicators.

### Key Features
- **Technical Indicators**: Utilizes RSI, MACD, ADX, and CCI to represent the trading environment for the RL model.
- **Adaptive Strategies**: Automatically adapts to changing market conditions.
- **Risk Management**: Integrates transaction cost management and nonnegative balance constraints.
- **Ensemble Approach**: Combines multiple RL agents to select the best-performing strategy.
- **Backtesting**: Evaluates performance through in-sample and out-of-sample testing.

## Reinforcement Learning Algorithms
The following RL algorithms are implemented to optimize the trading policy:
- **Advantage Actor-Critic (A2C)**
- **Deep Deterministic Policy Gradient (DDPG)**
- **Proximal Policy Optimization (PPO)**
- **Soft Actor-Critic (SAC)**
- **Twin Delayed Deep Deterministic Policy Gradient (TD3)**

### Ensemble Strategy
An ensemble of PPO, A2C, and DDPG is used to select the top-performing agent based on the **Sharpe ratio** over rolling validation periods. This approach ensures a robust trading strategy that adjusts according to market volatility.

## Methodology
1. **Environment Setup**: A stock trading environment is created using **OpenAI Gym** to simulate realistic trading scenarios, incorporating technical indicators and price history.
2. **MDP Framework**: The problem is formulated as a **Markov Decision Process (MDP)**, with:
   - **State**: Stock prices, shares held, and balance.
   - **Action**: Buy, hold, or sell decisions.
   - **Reward**: Net portfolio change based on action taken.
3. **Agent Training**: Agents interact with the environment, aiming to maximize portfolio value using the above algorithms.
4. **Performance Evaluation**: Backtesting is conducted on historical data, and results are compared using metrics like the Sharpe ratio.

## Results
The findings demonstrate that the **TD3** and **A2C** agents performed the best, achieving higher Sharpe ratios and consistent growth in net worth during testing phases. The ensemble strategy provided balanced returns, albeit slightly lower than individual top-performing agents.

## Getting Started

### Prerequisites
- Python 3.9.8 or higher
- Libraries:  `numpy`, `pandas`, `matplotlib`, `gym`, `stable-baselines3`, 'yfinance'

### Installation
Clone this repository:
```bash
git clone https://github.com/Jayasuryan0821/Stock-trading-simulator.git
cd Stock-trading-simulator
```

Install required libraries:
```bash
pip install -r requirements.txt
```

### Running the Model
To train and evaluate the trading bot:
1. Download historical data for training and testing.
2. Adjust configurations in `RL_trading_bot.ipynb` as needed.
3. Run the notebook or Python scripts to start training the agent.

## Future Work
1. **Enhanced Risk Management**: Incorporate stop-loss and volatility-adjusted reward functions.
2. **Hybrid Models**: Combine RL agents with LSTM-based trend forecasting.
3. **Meta-Learning Framework**: Dynamic weighting of ensemble strategies based on market conditions.

