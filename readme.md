# Awesome Agentic Trading [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> LLMs and autonomous agents that analyze markets and trade them — and the infrastructure gap between intelligence and reliable execution.
>
> Multi-agent frameworks now simulate entire trading firms. LLMs generate signals and execute orders. But the layer between agent intent and order execution — partial fills, reconnection, position reconciliation, risk guardrails — is mostly unbuilt. This list maps what exists and where the gaps are.

## Contents

- [Multi-Agent Trading Frameworks](#multi-agent-trading-frameworks)
- [Single-Agent Trading Bots](#single-agent-trading-bots)
- [Execution Infrastructure](#execution-infrastructure)
- [Exchange Connectivity & APIs](#exchange-connectivity--apis)
- [Risk Management](#risk-management)
- [Financial LLMs & Models](#financial-llms--models)
- [Data & Market Intelligence](#data--market-intelligence)
- [Backtesting & Evaluation](#backtesting--evaluation)
- [Agent Protocols & Communication](#agent-protocols--communication)
- [Research Papers](#research-papers)
- [Related Awesome Lists](#related-awesome-lists)

## Multi-Agent Trading Frameworks

Multiple LLM agents working together on trades. Analyst teams, risk managers, portfolio managers.

- [ai-hedge-fund](https://github.com/virattt/ai-hedge-fund) ![Stars](https://img.shields.io/github/stars/virattt/ai-hedge-fund?style=flat-square) - Simulates a hedge fund where AI agents roleplay as Buffett, Ackman, and Cathie Wood. Educational, built on LangChain.
- [TradingAgents](https://github.com/TauricResearch/TradingAgents) ![Stars](https://img.shields.io/github/stars/TauricResearch/TradingAgents?style=flat-square) - Mirrors a real trading firm: fundamental analysts, sentiment analysts, bull/bear researchers, risk team. Built on LangGraph.
- [AgenticTrading](https://github.com/Open-Finance-Lab/AgenticTrading) ![Stars](https://img.shields.io/github/stars/Open-Finance-Lab/AgenticTrading?style=flat-square) - Columbia's FinAgent framework. 9 agent types, MCP/A2A protocols, DAG execution with strict data leakage prevention.
- [AI-Trader](https://github.com/HKUDS/AI-Trader) ![Stars](https://img.shields.io/github/stars/HKUDS/AI-Trader?style=flat-square) - Agent marketplace where OpenClaw-compatible agents publish signals, debate strategies, and copy-trade. Supports Polymarket paper trading.
- [FinRobot](https://github.com/AI4Finance-Foundation/FinRobot) ![Stars](https://img.shields.io/github/stars/AI4Finance-Foundation/FinRobot?style=flat-square) - AI agents for market forecasting, document analysis, and trading strategies. Open source.
- [AutoHedge](https://github.com/The-Swarm-Corporation/AutoHedge) ![Stars](https://img.shields.io/github/stars/The-Swarm-Corporation/AutoHedge?style=flat-square) - Swarm intelligence approach to a hedge fund. Risk management first, currently on Solana.
- [AIBrokers](https://github.com/AI-Brokers/AIBrokers) ![Stars](https://img.shields.io/github/stars/AI-Brokers/AIBrokers?style=flat-square) - Crypto hedge fund framework. Trader, quant, sentiment, and fundamental agents with configurable risk per trade. *(Inactive)*
- [agentic-trading](https://github.com/kweinmeister/agentic-trading) ![Stars](https://img.shields.io/github/stars/kweinmeister/agentic-trading?style=flat-square) - Google ADK + A2A demo. AlphaBot runs an SMA strategy, RiskGuard enforces risk rules, they talk via A2A.
- [LLM-TradeBot](https://github.com/EthanAlgoX/LLM-TradeBot) ![Stars](https://img.shields.io/github/stars/EthanAlgoX/LLM-TradeBot?style=flat-square) - Crypto bot where agents argue before deciding. DataSync, Quant, Decision, and Risk agents in both LLM and rule-based variants.
- [Stockagent](https://github.com/MingyuJ666/Stockagent) ![Stars](https://img.shields.io/github/stars/MingyuJ666/Stockagent?style=flat-square) - Stock trading simulation where LLM agents respond to real market conditions. Designed to avoid test set leakage.

## Single-Agent Trading Bots

LLM-powered bots with a single agent doing the work.

- [dexter](https://github.com/virattt/dexter) ![Stars](https://img.shields.io/github/stars/virattt/dexter?style=flat-square) - Autonomous financial research agent that plans tasks, executes them, and checks its own work. Like Claude Code but for finance.
- [FinMem-LLM-StockTrading](https://github.com/pipiku915/FinMem-LLM-StockTrading) ![Stars](https://img.shields.io/github/stars/pipiku915/FinMem-LLM-StockTrading?style=flat-square) - Trading agent with layered memory (working, episodic, semantic) modeled after how human traders think. *(Inactive)*
- [ai-agents-for-trading](https://github.com/MrFadiAi/ai-agents-for-trading) ![Stars](https://img.shields.io/github/stars/MrFadiAi/ai-agents-for-trading?style=flat-square) - Trading and risk agents for crypto. Focused on what actually works in execution. *(Inactive)*
- [ai-trading-agent](https://github.com/Gajesh2007/ai-trading-agent) ![Stars](https://img.shields.io/github/stars/Gajesh2007/ai-trading-agent?style=flat-square) - LLM agent on Hyperliquid using OpenRouter + TAAPI indicators. Live dashboards with real money and TEE deployment via EigenCloud.
- [finagents](https://github.com/weirdapps/finagents) ![Stars](https://img.shields.io/github/stars/weirdapps/finagents?style=flat-square) - Simulates an investment committee where AI agents debate as Buffett, Cathie Wood, etc. Educational.

## Execution Infrastructure

What sits between agent intent and order execution. Connectivity, state management, order lifecycle.

> **Thinnest category here.** Most agent frameworks stop at signal generation. The execution layer (partial fills, reconnection, order state reconciliation) is mostly unbuilt. Know a repo that handles this? Open a PR.

- [freqtrade](https://github.com/freqtrade/freqtrade) ![Stars](https://img.shields.io/github/stars/freqtrade/freqtrade?style=flat-square) - The most battle-tested crypto trading bot. Real order management, dry-run mode, exchange integration, and FreqAI for ML.
- [nautilus_trader](https://github.com/nautechsystems/nautilus_trader) ![Stars](https://img.shields.io/github/stars/nautechsystems/nautilus_trader?style=flat-square) - Algo trading platform in Rust/Python with low latency, proper order management, and multi-venue support. Probably the most serious infra on this list.
- [hummingbot](https://github.com/hummingbot/hummingbot) ![Stars](https://img.shields.io/github/stars/hummingbot/hummingbot?style=flat-square) - Multi-exchange, WebSocket-based market-making bot that handles real order lifecycle. Good execution layer to hook agents into.
- [FinRL-Trading](https://github.com/AI4Finance-Foundation/FinRL-Trading) ![Stars](https://img.shields.io/github/stars/AI4Finance-Foundation/FinRL-Trading?style=flat-square) - FinRL's live trading extension with Alpaca integration, execution engine, and risk management. Bridges backtesting to production.

## Exchange Connectivity & APIs

The plumbing agents depend on. Nobody thinks about exchange connectivity until it breaks.

- [ccxt](https://github.com/ccxt/ccxt) ![Stars](https://img.shields.io/github/stars/ccxt/ccxt?style=flat-square) - Unified API for 100+ crypto exchanges in JS/TS/Python/C#/PHP/Go. Every agentic trading project probably depends on this.
- [ib_insync](https://github.com/erdewit/ib_insync) ![Stars](https://img.shields.io/github/stars/erdewit/ib_insync?style=flat-square) - Python wrapper for Interactive Brokers with sync and async support. If your agent trades TradFi, you'll probably end up here. *(Archived)*
- [cryptofeed](https://github.com/bmoscon/cryptofeed) ![Stars](https://img.shields.io/github/stars/bmoscon/cryptofeed?style=flat-square) - Asyncio WebSocket feed handler for crypto exchanges. Order books, trades, liquidations.

## Risk Management

Guardrails, circuit breakers, position limits. What keeps an agent from blowing up an account.

> **Also thin.** Exchange risk engines assume humans are trading. Agent behavior is non-deterministic and the risk tooling hasn't caught up. Know a repo? Open a PR.

- [systemr-python](https://github.com/System-R-AI/systemr-python) ![Stars](https://img.shields.io/github/stars/System-R-AI/systemr-python?style=flat-square) - Python SDK for a risk API. Kelly sizing, drawdown analysis, Monte Carlo, and regime detection via REST + MCP.
- [Riskfolio-Lib](https://github.com/dcajasn/Riskfolio-Lib) ![Stars](https://img.shields.io/github/stars/dcajasn/Riskfolio-Lib?style=flat-square) - Portfolio optimization and risk management. Not agent-specific, but any agent managing a portfolio needs something like this.
- [PyPortfolioOpt](https://github.com/PyPortfolio/PyPortfolioOpt) ![Stars](https://img.shields.io/github/stars/PyPortfolio/PyPortfolioOpt?style=flat-square) - Efficient frontier, Black-Litterman, HRP. Useful as the allocation layer when an agent needs to think about risk.

## Financial LLMs & Models

LLMs fine-tuned for finance and the models behind trading agents.

- [FinGPT](https://github.com/AI4Finance-Foundation/FinGPT) ![Stars](https://img.shields.io/github/stars/AI4Finance-Foundation/FinGPT?style=flat-square) - Open source financial LLM for sentiment, forecasting, and NER. The community alternative to BloombergGPT.
- [FinRL](https://github.com/AI4Finance-Foundation/FinRL) ![Stars](https://img.shields.io/github/stars/AI4Finance-Foundation/FinRL?style=flat-square) - Deep RL for stock, crypto, and portfolio trading. Most RL trading papers since 2020 reference it.
- [Qlib](https://github.com/microsoft/qlib) ![Stars](https://img.shields.io/github/stars/microsoft/qlib?style=flat-square) - Microsoft's quant platform. Alpha research, model training, portfolio construction.
- [Trading-R1](https://github.com/TauricResearch/Trading-R1) ![Stars](https://img.shields.io/github/stars/TauricResearch/Trading-R1?style=flat-square) - Reasoning-first trading model from the TradingAgents team. SFT + reinforcement learning with a three-stage curriculum trained on 100k financial reasoning samples.
- [Awesome-finance-skills](https://github.com/RKiding/Awesome-finance-skills) ![Stars](https://img.shields.io/github/stars/RKiding/Awesome-finance-skills?style=flat-square) - Drop-in skills for AI agents: news feeds, stock data, sentiment, time-series prediction. Works with Claude Code, OpenCode, etc.

## Data & Market Intelligence

Data feeds, market data APIs, and tools that structure financial data for agents.

- [orderflow](https://github.com/tiagosiebler/orderflow) ![Stars](https://img.shields.io/github/stars/tiagosiebler/orderflow?style=flat-square) - Builds Footprint Candles from WebSocket trade data in TypeScript/NestJS/TimescaleDB. Supports Binance, Bybit, OKX, and others. *(Inactive)*

### MCP Servers

> MCP (Model Context Protocol) servers that give agents structured access to financial data. The read side of the agent-data interface.

- [parsec-mcp](https://github.com/parsecular/parsec-mcp) ![Stars](https://img.shields.io/github/stars/parsecular/parsec-mcp?style=flat-square) - MCP server for prediction markets. Trade across Polymarket, Kalshi, and others through one interface.
- [edgartools](https://github.com/dgunning/edgartools) ![Stars](https://img.shields.io/github/stars/dgunning/edgartools?style=flat-square) - SEC EDGAR fundamentals, 13F holdings, and insider transactions. Includes an MCP server for AI workflows.
- [alpaca-mcp-server](https://github.com/alpacahq/alpaca-mcp-server) ![Stars](https://img.shields.io/github/stars/alpacahq/alpaca-mcp-server?style=flat-square) - Alpaca's official MCP server for stocks, ETFs, crypto, and options via natural language. V2 rewrite with FastMCP.
- [KDB-X MCP Server](https://github.com/KXSystems/kdb-x-mcp-server) ![Stars](https://img.shields.io/github/stars/KXSystems/kdb-x-mcp-server?style=flat-square) - KX Systems' MCP server for querying time-series and vector data in KDB-X. Natural language to SQL over high-frequency market data.
- [financial-datasets MCP](https://github.com/financial-datasets/mcp-server) ![Stars](https://img.shields.io/github/stars/financial-datasets/mcp-server?style=flat-square) - MCP server for income statements, balance sheets, cash flows, stock prices, and market news.
- [yahoo-finance-mcp](https://github.com/Alex2Yang97/yahoo-finance-mcp) ![Stars](https://img.shields.io/github/stars/Alex2Yang97/yahoo-finance-mcp?style=flat-square) - Yahoo Finance data via MCP. Historical prices, fundamentals, options, news.
- [Financial Modeling Prep MCP](https://github.com/imbenrabi/Financial-Modeling-Prep-MCP-Server) ![Stars](https://img.shields.io/github/stars/imbenrabi/Financial-Modeling-Prep-MCP-Server?style=flat-square) - Comprehensive financial data MCP with dynamic toolset management. Covers fundamentals, technicals, crypto, forex, ETFs, and SEC filings.
- [EODHD MCP Server](https://github.com/EodHistoricalData/EODHD-MCP-Server) ![Stars](https://img.shields.io/github/stars/EodHistoricalData/EODHD-MCP-Server?style=flat-square) - Provides 75 read-only tools covering historical prices, fundamentals, and technical indicators with 100+ embedded documentation resources.
- [finance-trading-ai-agents-mcp](https://github.com/aitrados/finance-trading-ai-agents-mcp) ![Stars](https://img.shields.io/github/stars/aitrados/finance-trading-ai-agents-mcp?style=flat-square) - Full financial MCP server with departmental architecture. Includes broker integration for order placement.
- [mcp_massive](https://github.com/massive-com/mcp_massive) ![Stars](https://img.shields.io/github/stars/massive-com/mcp_massive?style=flat-square) - Massive.com financial data via MCP. Four composable tools (search, docs, call, query) with in-memory DataFrames and SQL.
- [OKX Agent Trade Kit](https://github.com/okx/agent-trade-kit) ![Stars](https://img.shields.io/github/stars/okx/agent-trade-kit?style=flat-square) - OKX's official exchange-native MCP toolkit — covers spot, perpetuals, options, and grid bots; API credentials are stored locally and never passed to the LLM.

## Backtesting & Evaluation

Testing agents before they touch real money.

- [live-trade-bench](https://github.com/ulab-uiuc/live-trade-bench) ![Stars](https://img.shields.io/github/stars/ulab-uiuc/live-trade-bench?style=flat-square) - Runs multiple LLM agents against real markets simultaneously. No backtest overfitting because there is no backtest.
- [jesse](https://github.com/jesse-ai/jesse) ![Stars](https://img.shields.io/github/stars/jesse-ai/jesse?style=flat-square) - Crypto backtesting framework with a clean strategy API. JesseGPT helps write strategies.
- [TensorTrade](https://github.com/tensortrade-org/tensortrade) ![Stars](https://img.shields.io/github/stars/tensortrade-org/tensortrade?style=flat-square) - RL trading environments. Modular: swap out data sources, reward functions, action spaces.

## Agent Protocols & Communication

How agents find each other, talk, and work together.

- [Model Context Protocol (MCP)](https://modelcontextprotocol.io/) - Anthropic's standard for connecting agents to tools and data. Showing up in finance (edgartools, systemr, etc.).
- [A2A](https://github.com/a2aproject/A2A) ![Stars](https://img.shields.io/github/stars/a2aproject/A2A?style=flat-square) - Agent-to-Agent protocol for peer-to-peer coordination between agents. Used in Columbia's FinAgent.
- [Google Agent Development Kit (ADK)](https://github.com/google/adk-python) ![Stars](https://img.shields.io/github/stars/google/adk-python?style=flat-square) - Google's framework for building AI agents. Used in agentic-trading demo with A2A protocol.
- [LangGraph](https://github.com/langchain-ai/langgraph) ![Stars](https://img.shields.io/github/stars/langchain-ai/langgraph?style=flat-square) - Stateful multi-agent apps. Powers TradingAgents and a lot of the projects on this list.
- [CrewAI](https://github.com/crewAIInc/crewAI) ![Stars](https://img.shields.io/github/stars/crewAIInc/crewAI?style=flat-square) - Role-based agent orchestration. Give agents roles and let them collaborate.

## Research Papers

Academic work on LLM agents in trading.

- [TradingAgents: Multi-Agents LLM Financial Trading Framework](https://arxiv.org/abs/2412.20138) - Structured multi-agent communication beats single-agent on returns, Sharpe, and drawdown. *arXiv 2024*
- [FinAgent: A Multimodal Foundation Agent for Financial Trading](https://arxiv.org/abs/2402.18485) - Multimodal agent with tool use, layered memory, and reflection. *KDD 2024*
- [FinMem: LLM Trading Agent with Layered Memory](https://arxiv.org/abs/2311.13743) - Working memory, episodic memory, semantic memory. Modeled after how traders think. *ICLR Workshop*
- [CryptoTrade: Reflective LLM-based Agent for Crypto Trading](https://arxiv.org/abs/2407.09546) - Agent that reflects on past trades. Zero-shot crypto trading. *EMNLP 2024*
- [LiveTradeBench: Seeking Real-world Alpha with LLMs](https://arxiv.org/abs/2511.03628) - Live evaluation, not backtesting. Runs agents against real markets. *arXiv 2025*
- [A Survey of Financial AI](https://arxiv.org/abs/2411.12747) - Survey of AI in finance. Covers agent-based approaches. *arXiv 2024*
- [Large Language Model Agent in Financial Trading: A Survey](https://arxiv.org/abs/2408.06361) - Comprehensive survey of LLM trading agent architectures, data inputs, and backtesting performance. *arXiv 2024, updated 2026*
- [LLM Agents Do Not Replicate Human Market Traders](https://arxiv.org/abs/2502.15800) - Experimental finance study. LLM agents behave erratically in endogenous markets, failing to produce human-like trading dynamics. *arXiv 2025*
- [Trading-R1: Financial Trading with LLM Reasoning via RL](https://arxiv.org/abs/2509.11420) - Reasoning LLM for trading using SFT + RL curriculum. Structured thesis generation with volatility-adjusted rewards. *arXiv 2025*
- [TradeTrap: Are LLM-based Trading Agents Truly Reliable?](https://arxiv.org/abs/2512.02261) - Red-teaming framework that stress-tests trading agents across data poisoning, prompt injection, and state manipulation. *arXiv 2025*
- [AI Agents in Financial Markets: Architecture, Applications, and Systemic Implications](https://arxiv.org/abs/2603.13942) - Proposes a four-layer architecture for agentic finance (data perception, reasoning, strategy, execution) and a market model linking agent autonomy and heterogeneity to systemic risk outcomes. *arXiv 2026*
- [Be Water: An Evolutionary Proof for Trend-Following](https://arxiv.org/abs/2603.29593) - 10,000-agent simulation finds trend-following dominates mean-reversion evolutionarily; builds an LLM-driven system to operationalize the winning strategy for real investors. *arXiv 2026*

## Related Awesome Lists

- [awesome-ai-in-finance](https://github.com/georgezouq/awesome-ai-in-finance) ![Stars](https://img.shields.io/github/stars/georgezouq/awesome-ai-in-finance?style=flat-square) - The OG list. ML, DL, RL, data, tools for finance.
- [awesome-systematic-trading](https://github.com/wangzhe3224/awesome-systematic-trading) ![Stars](https://img.shields.io/github/stars/wangzhe3224/awesome-systematic-trading?style=flat-square) - Quant trading libraries across all languages.
- [awesome-quant](https://github.com/wilsonfreitas/awesome-quant) ![Stars](https://img.shields.io/github/stars/wilsonfreitas/awesome-quant?style=flat-square) - Libraries and resources for quants.
- [awesome-ai-agents](https://github.com/slavakurilyak/awesome-ai-agents) ![Stars](https://img.shields.io/github/stars/slavakurilyak/awesome-ai-agents?style=flat-square) - General AI agent resources.
- [Awesome-AI-in-Finance](https://github.com/ihobbang250/Awesome-AI-in-Finance) ![Stars](https://img.shields.io/github/stars/ihobbang250/Awesome-AI-in-Finance?style=flat-square) - Academic papers on AI + finance. *(Inactive)*
- [awesome-deep-trading](https://github.com/cbailes/awesome-deep-trading) ![Stars](https://img.shields.io/github/stars/cbailes/awesome-deep-trading?style=flat-square) - RL and deep learning for trading. *(Inactive)*
- [awesome-algorithmic-trading](https://github.com/joelowj/awesome-algorithmic-trading) ![Stars](https://img.shields.io/github/stars/joelowj/awesome-algorithmic-trading?style=flat-square) - Algo trading tutorials and communities. *(Inactive)*
- [awesome-agent-payments-protocol](https://github.com/tsubasakong/awesome-agent-payments-protocol) ![Stars](https://img.shields.io/github/stars/tsubasakong/awesome-agent-payments-protocol?style=flat-square) - Agentic commerce standards: AP2, A2A, x402, ACP.

---

### The Gap This List Reveals

Look at the categories above. Multi-Agent Trading Frameworks is crowded. Execution Infrastructure and Risk Management are almost empty.

That's the gap. Everyone is building the brain. Almost nobody is building the nervous system.

An LLM can analyze a market, generate a signal, and decide to buy. But it has no idea that the WebSocket just dropped, that its last order was partially filled, or that the exchange is about to go into maintenance.

MCP servers for reading financial data are multiplying fast (see above). MCP servers for executing trades with risk guardrails? Count them on one hand. The governed middleware layer between agent decision and exchange execution does not exist as a category yet.

The layer between agent intent and order execution — handling partial fills, reconnection, position reconciliation, risk guardrails — is mostly left to each team to build from scratch.

## Contributing

Contributions welcome! Read the [contributing guidelines](contributing.md) first.
