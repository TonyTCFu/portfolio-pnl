# AGENTS.md — portfolio-pnl

Public GitHub Pages dashboard: the user's US-stock portfolio P&L.
Repo: TonyTCFu/portfolio-pnl → https://tonytcfu.github.io/portfolio-pnl/

## Structure
- `index.html` — the whole dashboard (static snapshot + browser live-quote refresh)
- `AGENTS.md`, `MEMORY.md` — this repo's own operating notes

## Data pipeline
- Source of truth: `~/workspace/goals/portfolio-pnl-dashboard/hidden_files/portfolio_data.json`
  (transcribed from brokerage 资金流水/持仓 screenshots, cross-verified per symbol).
- Rebuild: user sends new screenshots → update `build_data.py` transcription →
  verify (every symbol's buy total == broker cost×qty) → regenerate `index.html` → push.
- Quote refresh is browser-direct (CNBC bulk primary, TradingView per-symbol fallback);
  no quote.json push pipeline, no 15-min server snapshots.

## Conventions
- Page language: Traditional Chinese (user's 2026-10-09 rule: new deliverables in 繁體).
- Honest quote labels: 靜態快照 (2026-10-16 close) vs 即時 (source + ET time).
- Never invent holdings data; holdings only change from new user screenshots.
- This page contains personal dollar amounts — public link by explicit user request.
