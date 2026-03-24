# Awesome Agentic Trading [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> LLMs and autonomous agents that analyze markets and trade them.

Multi-agent frameworks now simulate entire trading firms. LLMs generate signals and execute orders. But there's a gap between how smart these agents are and whether they actually work reliably. This list covers agent frameworks, execution infra, and the unglamorous stuff in between.

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

- [ai-hedge-fund](https://github.com/virattt/ai-hedge-fund) - Simulates a hedge fund where AI agents roleplay as Buffett, Ackman, and Cathie Wood. LangChain. Educational only.
- [TradingAgents](https://github.com/TauricResearch/TradingAgents) - Mirrors a real trading firm: fundamental analysts, sentiment analysts, bull/bear researchers, risk team. Built on LangGraph.
- [AgenticTrading](https://github.com/Open-Finance-Lab/AgenticTrading) - Columbia's FinAgent framework. 9 agent types, MCP/A2A protocols, DAG execution. Strict about data leakage prevention.
- [FinRobot](https://github.com/AI4Finance-Foundation/FinRobot) - AI agents for market forecasting, document analysis, and trading strategies. Open source.
- [AutoHedge](https://github.com/The-Swarm-Corporation/AutoHedge) - Swarm intelligence approach to a hedge fund. Risk management first, currently on Solana.
- [AIBrokers](https://github.com/AI-Brokers/AIBrokers) - Crypto hedge fund framework. Trader, quant, sentiment, and fundamental agents with configurable risk per trade.
- [agentic-trading](https://github.com/kweinmeister/agentic-trading) - Google ADK + A2A demo. AlphaBot runs an SMA strategy, RiskGuard enforces risk rules, they talk via A2A.
- [LLM-TradeBot](https://github.com/EthanAlgoX/LLM-TradeBot) - Crypto bot where agents argue before deciding. DataSync, Quant, Decision, and Risk agents in both LLM and rule-based variants.
- [Stockagent](https://github.com/MingyuJ666/Stockagent) - Stock trading simulation where LLM agents respond to real market conditions. Designed to avoid test set leakage.

## Single-Agent Trading Bots

LLM-powered bots with a single agent doing the work.

- [dexter](https://github.com/virattt/dexter) - Autonomous financial research agent. Plans its own tasks, runs them, checks its own work. Like Claude Code but for finance.
- [FinMem-LLM-StockTrading](https://github.com/pipiku915/FinMem-LLM-StockTrading) - Trading agent with layered memory (working, episodic, semantic) modeled after how human traders think. ICLR Workshop.
- [ai-agents-for-trading](https://github.com/MrFadiAi/ai-agents-for-trading) - Trading and risk agents for crypto. Built by a quant, focused on what actually works in execution.
- [finagents](https://github.com/weirdapps/finagents) - Simulates an investment committee where AI agents debate as Buffett, Cathie Wood, etc. Educational.

## Execution Infrastructure

What sits between agent intent and order execution. Connectivity, state management, order lifecycle.

> **Thinnest category here.** Most agent frameworks stop at signal generation. The execution layer (partial fills, reconnection, order state reconciliation) is mostly unbuilt. Know a repo that handles this? Open a PR.

- [freqtrade](https://github.com/freqtrade/freqtrade) - The most battle-tested crypto trading bot out there. Real order management, dry-run mode, stop losses, exchange integration. FreqAI adds ML support.
- [nautilus_trader](https://github.com/nautechsystems/nautilus_trader) - Algo trading platform in Rust/Python. Low latency, proper order management, multi-venue. Probably the most serious infra on this list.
- [hummingbot](https://github.com/hummingbot/hummingbot) - Market-making bot. Multi-exchange, WebSocket-based, handles real order lifecycle. Good execution layer to hook agents into.
- [FinRL-Trading](https://github.com/AI4Finance-Foundation/FinRL-Trading) - FinRL's live trading extension. Alpaca integration, execution engine, risk management. Bridges backtesting to production.

## Exchange Connectivity & APIs

The plumbing agents depend on. Nobody thinks about exchange connectivity until it breaks.

- [ccxt](https://github.com/ccxt/ccxt) - The standard. Unified API for 100+ crypto exchanges. JS/TS/Python/C#/PHP/Go. Every agentic trading project probably depends on this.
- [ib_insync](https://github.com/erdewit/ib_insync) - Python wrapper for Interactive Brokers. Sync and async. If your agent trades TradFi, you'll probably end up here. *(Archived)*
- [cryptofeed](https://github.com/bmoscon/cryptofeed) - WebSocket feed handler for crypto exchanges. Asyncio. Order books, trades, liquidations.

## Risk Management

Guardrails, circuit breakers, position limits. What keeps an agent from blowing up an account.

> **Also thin.** Exchange risk engines assume humans are trading. Agent behavior is non-deterministic and the risk tooling hasn't caught up. Know a repo? Open a PR.

- [systemr-python](https://github.com/System-R-AI/systemr-python) - Python SDK for a risk API. Kelly sizing, drawdown analysis, Monte Carlo, regime detection. REST + MCP.
- [Riskfolio-Lib](https://github.com/dcajasn/Riskfolio-Lib) - Portfolio optimization and risk management. Not agent-specific, but any agent managing a portfolio needs something like this.
- [PyPortfolioOpt](https://github.com/robertmartin8/PyPortfolioOpt) - Efficient frontier, Black-Litterman, HRP. Useful as the allocation layer when an agent needs to think about risk.

## Financial LLMs & Models

LLMs fine-tuned for finance and the models behind trading agents.

- [FinGPT](https://github.com/AI4Finance-Foundation/FinGPT) - Open source financial LLM. Sentiment, forecasting, NER. The community alternative to BloombergGPT.
- [FinRL](https://github.com/AI4Finance-Foundation/FinRL) - Deep RL for trading. Stock, crypto, portfolio allocation. Been around since 2020 and most RL trading papers reference it.
- [Qlib](https://github.com/microsoft/qlib) - Microsoft's quant platform. Alpha research, model training, portfolio construction.
- [Awesome-finance-skills](https://github.com/RKiding/Awesome-finance-skills) - Drop-in skills for AI agents: news feeds, stock data, sentiment, time-series prediction. Works with Claude Code, OpenCode, etc.

## Data & Market Intelligence

Data feeds, market data APIs, and tools that structure financial data for agents.

- [parsec-mcp](https://github.com/parsecular/parsec-mcp) - MCP server for prediction markets. Trade across Polymarket, Kalshi, and others through one interface.
- [edgartools](https://github.com/dgunning/edgartools) - SEC EDGAR data. Fundamentals, 13F holdings, insider transactions. Has an MCP server for AI workflows.
- [orderflow](https://github.com/tiagosiebler/orderflow) - Builds Footprint Candles from WebSocket trade data. TypeScript/NestJS/TimescaleDB. Supports Binance, Bybit, OKX, and others.

## Backtesting & Evaluation

Testing agents before they touch real money.

- [live-trade-bench](https://github.com/ulab-uiuc/live-trade-bench) - Runs multiple LLM agents against real markets simultaneously. No backtest overfitting because there is no backtest.
- [jesse](https://github.com/jesse-ai/jesse) - Crypto backtesting framework. Clean strategy API. JesseGPT helps write strategies.
- [TensorTrade](https://github.com/tensortrade-org/tensortrade) - RL trading environments. Modular: swap out data sources, reward functions, action spaces.

## Agent Protocols & Communication

How agents find each other, talk, and work together.

- [Model Context Protocol (MCP)](https://modelcontextprotocol.io/) - Anthropic's standard for connecting agents to tools and data. Showing up in finance (edgartools, systemr, etc.).
- [A2A](https://github.com/a2aproject/A2A) - Agent-to-Agent protocol. Peer-to-peer coordination between agents. Used in Columbia's FinAgent.
- [LangGraph](https://github.com/langchain-ai/langgraph) - Stateful multi-agent apps. Powers TradingAgents and a lot of the projects on this list.
- [CrewAI](https://github.com/crewAIInc/crewAI) - Role-based agent orchestration. Give agents roles and let them collaborate.

## Research Papers

Academic work on LLM agents in trading.

- [TradingAgents: Multi-Agents LLM Financial Trading Framework](https://arxiv.org/abs/2412.20138) - Structured multi-agent communication beats single-agent on returns, Sharpe, and drawdown. *arXiv 2024*
- [FinAgent: A Multimodal Foundation Agent for Financial Trading](https://arxiv.org/abs/2402.18485) - Multimodal agent with tool use, layered memory, and reflection. *KDD 2024*
- [FinMem: LLM Trading Agent with Layered Memory](https://arxiv.org/abs/2311.13743) - Working memory, episodic memory, semantic memory. Modeled after how traders think. *ICLR Workshop*
- [CryptoTrade: Reflective LLM-based Agent for Crypto Trading](https://arxiv.org/abs/2407.09546) - Agent that reflects on past trades. Zero-shot crypto trading. *EMNLP 2024*
- [LiveTradeBench: Seeking Real-world Alpha with LLMs](https://arxiv.org/abs/2511.03628) - Live evaluation, not backtesting. Runs agents against real markets. *arXiv 2025*
- [A Survey of Financial AI](https://arxiv.org/abs/2411.12747) - Survey of AI in finance. Covers agent-based approaches. *arXiv 2024*

## Related Awesome Lists

- [awesome-ai-in-finance](https://github.com/georgezouq/awesome-ai-in-finance) - The OG list. ML, DL, RL, data, tools for finance.
- [awesome-systematic-trading](https://github.com/wangzhe3224/awesome-systematic-trading) - Quant trading libraries across all languages.
- [awesome-quant](https://github.com/wilsonfreitas/awesome-quant) - Libraries and resources for quants.
- [awesome-ai-agents](https://github.com/slavakurilyak/awesome-ai-agents) - General AI agent resources.
- [Awesome-AI-in-Finance](https://github.com/ihobbang250/Awesome-AI-in-Finance) - Academic papers on AI + finance.
- [awesome-deep-trading](https://github.com/cbailes/awesome-deep-trading) - RL and deep learning for trading.
- [awesome-algorithmic-trading](https://github.com/joelowj/awesome-algorithmic-trading) - Algo trading tutorials and communities.
- [awesome-agent-payments-protocol](https://github.com/tsubasakong/awesome-agent-payments-protocol) - Agentic commerce standards: AP2, A2A, x402, ACP.

---

### The Gap This List Reveals

Look at the categories above. Multi-Agent Trading Frameworks is crowded. Execution Infrastructure and Risk Management are almost empty.

That's the gap. Everyone is building the brain. Almost nobody is building the nervous system.

An LLM can analyze a market, generate a signal, and decide to buy. But it has no idea that the WebSocket just dropped, that its last order was partially filled, or that the exchange is about to go into maintenance.

The layer between agent intent and order execution — handling partial fills, reconnection, position reconciliation, risk guardrails — is mostly left to each team to build from scratch.

## Contributing

Contributions welcome! Read the [contributing guidelines](contributing.md) first.
