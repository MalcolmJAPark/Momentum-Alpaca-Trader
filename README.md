# Momentum-Alpaca-Trader
A high-frequency momentum research &amp; live paper-trading framework built around the Alpaca Markets API.

| Section | What you’ll find |
|---------|------------------|
| [Key Features](#key-features) ||
| [Quick Start](#quick-start) | One-command setup with Docker |
| [Architecture](#architecture) | Layered, test-driven design |
| [Usage](#usage) | Scraping, back-testing, live paper trading |
| [Roadmap](#roadmap) | Where the project is heading |
| [Contributing](#contributing) | How to get involved |
| [License](#license) | MIT |

---

## Key Features

* **Ultra-fast data pipeline** – async Python + websockets + DuckDB/PostgreSQL for sub-second writes.  
* **Modular strategy engine** – plug-and-play momentum factors (e.g., intraday ROC, VWAP drift).  
* **Vectorized back-tester** – pandas-compatible but 10-20× faster via NumPy & numba.  
* **Walk-forward optimizer** – minimizes forecast error (MSE, directional accuracy, Sharpe).  
* **Risk & execution layer** – position sizing, max-drawdown guard, Alpaca paper endpoint.  
* **CI/CD & Docker** – GitHub Actions: unit tests → lint → build image → deploy to Codespaces.  
* **Clean code** – type-hinted, PEP-621 pyproject, 90 %+ coverage, conventional commits.

---

## Quick Start

```bash
# 1. clone & configure
git clone https://github.com/MalcolmJAPark/momentum-alpaca-trader.git
cd momentum-alpaca-trader
cp .env.example .env   # add your Alpaca API keys here

# 2. run everything (scraper + back-test + live paper trade) in Docker
docker compose up --build
