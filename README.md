# RebalanceAI: AI-Powered Investment Portfolio Analyzer
### Group 2: Shreyas Sreenivas, Anagha Veena Sanjeev, Harshitha Chandrashekar

An intelligent investment co-pilot combining quantitative finance, AI sentiment analysis, and real-time economic data to deliver institutional-quality portfolio recommendations.

---

## Overview

RebalanceAI leverages LangChain's ReAct agent architecture to orchestrate multiple data sources and provide comprehensive investment insights. The system combines:

- Technical indicators (RSI, MACD, Bollinger Bands)
- Fundamental metrics (P/E, growth, margins, ROE)
- Multi-source sentiment analysis (NewsAPI + Reddit)
- Real-time economic data (Federal Reserve FRED API)
- Risk-aware portfolio optimization

---

## Quick Start

### Installation
```bash
pip install yfinance pandas numpy matplotlib plotly langchain langchain-openai gradio scikit-learn praw google-generativeai langchain-google-genai
```

### Required API Keys

Configure these keys in Google Colab Secrets or `.env` file:
```
OPENAI_API_KEY          # OpenAI GPT-4o-mini
NEWSAPI_KEY             # Financial news sentiment
REDDIT_CLIENT_ID        # Reddit social sentiment
REDDIT_CLIENT_SECRET    # Reddit API authentication
REDDIT_USER_AGENT       # Reddit API user agent
GOOGLE_API_KEY          # Google Gemini (optional)
FRED_API_KEY            # Federal Reserve economic data
```

### Get API Keys

- **OpenAI**: https://platform.openai.com
- **NewsAPI**: https://newsapi.org (100 requests/day free)
- **Reddit**: https://www.reddit.com/prefs/apps
- **FRED**: https://fred.stlouisfed.org/docs/api/api_key.html (free)
- **Google**: https://ai.google.dev (optional)

### Launch
```python
# Run all notebook cells, then:
demo.launch(share=True)
```

---

## System Architecture

### Core Components

**1. ReAct Agent**
- Autonomous reasoning and tool orchestration
- GPT-4o-mini powered decision-making
- Multi-step analysis workflows
- Conversation memory for context

**2. Tools**
- Market Data Gatherer (Yahoo Finance)
- Sentiment Analyzer (NewsAPI + Reddit)
- Economic Calendar (FRED API)
- Portfolio Allocator (Multi-factor optimization)
- Stock Comparator (Head-to-head analysis)

**3. Global Cache System**
- Intelligent data caching for performance
- Shared state across tools
- Optimized API usage

**4. Gradio Interface**
- Professional dark-themed UI
- Interactive visualizations
- Real-time progress tracking
- Multi-tab feature organization

---

## Methodology

### Multi-Factor Scoring System

Each stock is evaluated across four pillars, with scores normalized to 0-1 scale:

**Technical Analysis**
- RSI (Relative Strength Index): Momentum indicator
- MACD: Trend following signal
- Bollinger Bands: Volatility context
- Moving Averages: Price trend analysis
- Volume Ratio: Liquidity assessment

**Fundamental Analysis**
- P/E Ratio: Valuation metric
- Revenue Growth: Top-line expansion
- Profit Margins: Operational efficiency
- Return on Equity: Capital efficiency
- Debt-to-Equity: Financial health

**Sentiment Analysis**
- News Sentiment: Professional media (70% weight)
- Reddit Sentiment: Retail investor mood (30% weight)
- Confidence Scoring: Based on data volume and consistency
- 7-day rolling window for current market psychology

**Economic Risk Assessment**
- Federal Funds Rate: Monetary policy stance
- Unemployment Rate: Labor market health
- CPI Inflation: Price stability
- GDP Growth: Economic expansion
- Sector-Specific Sensitivity: Industry impact analysis

---

## Risk Profile Weighting

Portfolio allocation varies by investor risk tolerance:

### Conservative Profile
- **Stock Count**: 8 positions
- **Factor Weights**: 50% Fundamental, 30% Technical, 20% Sentiment
- **Economic Sensitivity**: 80% (high risk aversion)
- **Max Position**: 15% per stock
- **Best For**: Capital preservation with steady growth

### Moderate Profile
- **Stock Count**: 6 positions
- **Factor Weights**: 40% Fundamental, 35% Technical, 25% Sentiment
- **Economic Sensitivity**: 60% (balanced consideration)
- **Max Position**: 20% per stock
- **Best For**: Balanced growth and income

### Aggressive Profile
- **Stock Count**: 4 positions
- **Factor Weights**: 30% Fundamental, 35% Technical, 35% Sentiment
- **Economic Sensitivity**: 40% (accepts volatility)
- **Max Position**: 25% per stock
- **Best For**: Maximum growth potential

---

## Allocation Formula
```
Base Score = (Fundamental × Wf) + (Technical × Wt) + (Sentiment × Ws)

Economic Adjustment:
  If Economic Risk > 0.5:
      Adjustment = max(0.70, 1.0 - (Risk × Sensitivity × 0.3))
  Elif Economic Risk > 0.3:
      Adjustment = max(0.85, 1.0 - (Risk × Sensitivity × 0.2))
  Else:
      Adjustment = 1.0

Final Score = Base Score × Economic Adjustment
Position Weight = Final Score / Sum(All Final Scores)
```

---

## Features

### Portfolio Allocation
- AI-optimized asset allocation across 20 S&P 500 stocks
- Economic risk-adjusted position sizing
- Interactive 4-panel visualization dashboard
- Sector diversification analysis
- Expected Sharpe ratio and volatility metrics

### AI Investment Advisor
- Natural language investment queries
- ReAct agent with transparent reasoning
- Multi-tool orchestration
- Comprehensive analysis combining all data sources
- Specific buy/hold/sell recommendations

### Stock Comparison
- Head-to-head analysis across 20+ metrics
- Winner determination for each category
- Investor profile-specific recommendations
- Risk-reward positioning matrix
- Business model and sector analysis

### Economic Calendar
- Real-time FRED economic data integration
- Current Fed policy and interest rate environment
- Key economic indicators (unemployment, CPI, GDP)
- Sector-specific impact assessment
- Risk adjustment recommendations

### Multi-LLM Comparison
- OpenAI GPT-4o-mini vs Google Gemini benchmarking
- Response time and quality metrics
- Cost efficiency analysis
- Investment analysis performance testing
- Production deployment recommendations

---

## Usage Examples

### Example 1: Portfolio Allocation
<img width="1404" height="125" alt="image" src="https://github.com/user-attachments/assets/edabecf3-7848-4d77-9ca9-11916f325581" />
<img width="758" height="1053" alt="image" src="https://github.com/user-attachments/assets/4bebd312-be6e-4ff1-a0dc-a854fcbcfa12" />


### Example 2: AI Advisor Query
```
Query: "Should I invest in Apple considering current economic conditions and sentiment?"

```
<img width="1921" height="1117" alt="image" src="https://github.com/user-attachments/assets/7da50743-58a7-4a38-9c5c-22d5685b4423" />


### Example 3: Stock Comparison
```
Input: AAPL,MSFT,GOOGL
```
<img width="791" height="1008" alt="image" src="https://github.com/user-attachments/assets/f6cd1b81-282c-477f-8ca0-4a907ef89d73" />
<img width="823" height="513" alt="image" src="https://github.com/user-attachments/assets/b27b6e60-5831-4b92-b5a4-ce18258a47da" />

### Example 4: Economic Calendar
<img width="1198" height="316" alt="image" src="https://github.com/user-attachments/assets/3023f86d-5356-49a3-bee3-186771ef469f" />

### Example 5: Multi-model Comparison
<img width="1436" height="1068" alt="image" src="https://github.com/user-attachments/assets/ffd22ce5-f203-4925-a8c8-0db6e71b46ff" />

---

## Innovation Highlights

### 1. Economic Calendar Integration
First AI portfolio system to dynamically adjust allocations based on real-time FRED economic data:
- Live Federal Reserve policy monitoring
- Current economic indicators (unemployment, inflation, GDP)
- Sector-specific sensitivity scoring
- Risk-adjusted position sizing

### 2. Multi-LLM Architecture
Provider-agnostic design supporting multiple AI models:
- OpenAI GPT-4o-mini (primary): Fast, cost-effective
- Google Gemini 2.5 Flash (secondary): Detailed analysis
- Easy integration of new models
- Comparative benchmarking system

### 3. Four-Pillar Analysis
Unique combination of data sources:
- Technical: Real-time market data
- Fundamental: Company financials
- Sentiment: News + social media
- Economic: FRED current conditions

### 4. Transparent Reasoning
Full visibility into AI decision-making:
- ReAct agent shows reasoning steps
- Component scores for each stock
- Economic adjustment calculations
- Data source attribution

### 5. Pipeline Operators
Modern LangChain implementation:
- Elegant data flow composition
- Tool dependency management
- Error resilience
- Performance monitoring

---

## Technical Stack

**Core Technologies:**
- Python 3.8+
- LangChain (Agent framework)
- OpenAI GPT-4o-mini (Primary LLM)
- Google Gemini 2.5 Flash (Secondary LLM)

**Data Sources:**
- Yahoo Finance (Market data)
- NewsAPI (Financial news)
- Reddit API (Social sentiment)
- FRED API (Economic data)

**Libraries:**
- yfinance (Market data)
- pandas/numpy (Data processing)
- plotly (Visualizations)
- gradio (Web interface)
- praw (Reddit integration)
- scikit-learn (Optimization)

---

## Stock Universe

Top 20 S&P 500 stocks across diverse sectors:

**Technology**: AAPL, MSFT, GOOGL, NVDA, META
**Financials**: JPM, V, MA, BRK-B
**Healthcare**: JNJ, UNH, LLY, ABBV
**Consumer**: WMT, PG, HD, TSLA, AMZN
**Energy**: XOM, CVX

---

## Sample Outputs

### Portfolio Summary Statistics
```
Expected Sharpe Ratio: 0.92
Portfolio Volatility: 35.8%
Portfolio Beta: 1.31
Sector Diversification: 3 sectors
Economic Conditions: Integrated via FRED
Position Count: 8 stocks
Max Position Size: 15%
```

### Stock Analysis Metrics
```
NVDA Analysis:
- Price: $183.22
- Annual Return: 41.03%
- Volatility: 49.58%
- Sharpe Ratio: 0.787
- P/E: 44.5, Growth: 55.6%
- Sentiment: +0.29 (bullish)
- Technical Score: -0.50/3.0
- Fundamental Score: 1.50/4.0
```
<img width="1905" height="930" alt="image" src="https://github.com/user-attachments/assets/029716d0-6d3b-4f2d-9e7f-c77add7bec1a" />

---

## Future Roadmap

**Short Term:**
- Backtesting framework
- Additional technical indicators
- Enhanced visualizations
- Performance optimization

**Medium Term:**
- Full S&P 500 coverage
- International markets
- Options analysis
- Real-time alerts

**Long Term:**
- Live trading integration
- Tax-loss harvesting
- Portfolio rebalancing automation
- Mobile app development

---

## Disclaimer

**IMPORTANT: Educational and Research Use Only**

This software is designed exclusively for educational purposes and does NOT constitute financial advice.

**Critical Reminders:**
- Past performance does not guarantee future results
- All investments involve risk of loss
- Consult qualified financial advisors before investing
- Market conditions change rapidly
- System relies on third-party data sources
- No guarantees of accuracy or profitability

**Use at your own risk. Developers assume no liability for investment decisions.**

---

Built with LangChain, OpenAI, and Python | Educational Use Only | Not Financial Advice

Last Updated: October 2025
