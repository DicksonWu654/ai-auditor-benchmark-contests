# Findings

| Finding ID | Severity | Title | Description |
|---|---|---|---|
| 1 | High | Inconsistent Price Conversion Logic Leads to Incorrect Oracle Prices | `OracleHelper.getPricesD18()` divides redemption demand by `priceD18` even though the code comments and later calculations treat `priceD18` as a multiplier, which misprices the base asset and all derived asset prices. |
| 2 | High | Off-chain price calculation can result in an infinite loop | The keeper-side iterative price calculation in `OracleHelper` can oscillate between two values because performance fees are applied conditionally, so the `while (true)` loop may never converge and the price update flow can stall. |
