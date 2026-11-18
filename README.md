# Crowd-Filtered Residual Momentum

**Dennis Petushkov, Mitch Cahill, Krittrin Olarnrak — Data Driven Investing with AI and Python, Fall 2026**

## Question
Momentum buys recent winners. Do *hyped* winners (the ones a crowd is piling into) do worse than *quiet* winners, so that skipping them improves momentum?

## What we did
- **Strategy:** residual momentum (Blitz, Huij and Martens 2011), NYSE breakpoints, value-weighted, top decile minus bottom decile, rebalanced monthly, 1980–2000.
- **Hype ("crowd score"):** no social-media data exists for 1980–2000, so we measure hype from trading behavior: biggest single-day return, volatility, volume relative to company size, illiquidity, and last month's return. All are measured the month before we trade.
- **Test:** split winners into low / medium / high hype, and do the same for middle-of-the-pack stocks as a comparison group.
- **Trade:** drop the 30% most hyped winners; charge 25 bps per trade.

## What we found
- Hyped winners did **better** (about 30%/yr vs. 20% for quiet winners), while hyped ordinary stocks did slightly worse.
- Filtering out hyped winners **lowered** returns: 8.7% → 7.7% before costs, 4.4% → 3.2% after costs.
- Much of the effect comes from the late-1990s tech boom; in the 1980s hype made little difference to winners.

## Files
- `Crowd_Filtered_Momentum.ipynb` — all the code and results. Runs as-is in Google Colab; it loads the course data directly from the class GitHub.

## Next steps
- Follow hyped winners for 12 months to check whether they crash later.
- Test 2001–2024 (dot-com crash, WallStreetBets era) and Reddit data (2018+).
- Separate hype driven by real news (e.g. earnings) from pure hype.
