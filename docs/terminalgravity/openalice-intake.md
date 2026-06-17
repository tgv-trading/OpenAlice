# OpenAlice intake for Terminal Gravity

Source: https://github.com/TraderAlice/OpenAlice

Initial posture:
- Treat as read-only architecture/reference until licensing and security review are complete.
- Do not copy AGPL code into Terminal Gravity production repos without an explicit licensing decision.
- Preserve Terminal Gravity broker/execution safety law: broker-confirmed fills are truth; submitted/pending rows are not performance truth.

High-value areas to inspect:
- `services/uta/` broker carrier and guard pipeline.
- `packages/ibkr/` TypeScript IBKR TWS API port.
- `src/workspaces/` native agent CLI workspace substrate.
- `safe/` threat model and findings.
- `ui/` trading/account/workspace surfaces.

Terminal Gravity mapping candidates:
- UTA service boundary -> Risk Gate / execution service boundary.
- Trading-as-Git lifecycle -> Execution Journal / Evidence Ledger UX pattern.
- Workspace substrate -> Hermes/Codex worker surface ideas.
- IBKR market data channel notes -> broker freshness/readiness monitor improvements.

Next required external step:
- Create GitHub fork under `tgv-trading` once `gh` auth is repaired for this runtime.
