# Commodity SEPA+VCP Screener

Automated daily screener for commodities using Minervini's SEPA trend template, VCP scoring, stage classification and the shared rule-based decision engine. Sibling of the [ASX](https://github.com/KidLearning99/asx-sepa-vcp-screener), [US](https://github.com/KidLearning99/us-sepa-vcp-screener), [India](https://github.com/KidLearning99/india-sepa-vcp-screener) and [crypto](https://github.com/KidLearning99/crypto-sepa-vcp-screener) screeners.

- **Universe (one list, filter by type):**
  - **Futures:** 27 Yahoo continuous front-month contracts across energy, precious and industrial metals, grains, softs and livestock.
  - **ETFs:** 36 commodity ETFs (US-listed, plus gold and oil ETFs on the ASX).
  - **Producer stocks:** 60 miners, oil & gas, fertiliser and ag companies listed in the US and on the ASX, with revenue/EPS, results dates and analyst data like the share screeners.
  - The list lives in `UNIVERSE` at the top of `screener.py`. Every item is listed on the dashboard, whatever its score.
- **Benchmark:** DBC (Invesco DB Commodity Index Tracking Fund) for relative strength, beta and the market filter.
- **Futures caveats:** continuous contracts are not back-adjusted for rolls, so a roll can show as a price jump (most visible in natural gas and livestock), and volume is the front month only. Futures are always treated as liquid.
- **Prices:** USD, except ASX listings in AUD. Futures are in each contract's quote units (for example, cents per bushel for grains).
- **Data:** Yahoo Finance via `yfinance`.
- **Schedule:** GitHub Actions after the US close, Mon-Fri. Output is deployed to the `gh-pages` branch.

`decision.py` is shared with the other screeners; commodity wording is set at the top of `screener.py`.

Educational and research use only. Not financial advice.
