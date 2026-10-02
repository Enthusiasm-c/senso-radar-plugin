# Senso Radar

Senso Radar connects Claude to Senso, a restaurant analytics service. Every day Senso checks the
restaurant's POS data (iiko / Syrve today, read-only) against the restaurant's own norms and shows
findings with the receipts behind them: voids after the kitchen ticket, discounts and comps,
cash shift discrepancies, refunds, stop-list losses.

## Use it

Connect the Senso connector from the plugin's **Connectors** tab and sign in with the same POS account
you use in the Senso app (or open the demo restaurant). Then ask in plain words:

- "How did yesterday go?" — `senso-morning-review`: summary card, top signals, what to check first.
- "Break down the kitchen deletions" — `senso-investigate-finding`: who, when, which receipts.
- "Compare this week with last week" / "Month review" — `senso-period-review`.
- "Check the cash" / "Who stands out among staff?" / "Stop-list losses" — `senso-control-checks`.

All figures come from Senso; Claude does not recalculate them. A finding is a signal to check, not proof
of wrongdoing. Senso is a control tool, not accounting.

## Data

The connector at `https://api.senso.rest/mcp` (OAuth) returns the restaurant's sales, findings and
receipts to Claude. Senso never writes to the POS. Owner decisions on findings ("normal", "snooze",
"hide") are stored in Senso only. Privacy: https://api.senso.rest/privacy

## License

MIT — see LICENSE.
