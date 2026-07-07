# V38.1 Price-Neutral Lock Patch Test Report

Changes made:
- Money, odds, payout, EV, and expensive-price warnings no longer add or remove Master Judge confirmations.
- Odds/price no longer changes the Master Judge score based on cheap vs expensive price.
- A neutral score baseline preserves the previous score scale without rewarding cheap odds or punishing expensive odds.
- Export still includes payout information, but `tooExpensive` is always false and `priceWarning` is display-only.
- Current call should lock based on prediction quality only.

Verification:
- node --check app.js: passed
- node --check lib/decision-engine.mjs: passed
- npm test: 18 passed / 0 failed
