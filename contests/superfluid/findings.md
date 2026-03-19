# Official High and Medium Findings

| Finding ID | Severity | Title | Description |
| --- | --- | --- | --- |
| H-1 | High | `FluidLocker::_getUnlockingPercentage()` incorrectly divides one of the components of the formula by `S`, leading to always having `80%` penalty | The formula divides `Math.sqrt(unlockPeriod * _SCALER)` by `SCALER`, so any non-zero unlock period still leaves the user with only a 20% unlock and an 80% penalty. |
| H-2 | High | `FluidLocker::_getUnlockingPercentage()` uses 540 instead of `540 days` leading to stuck funds as the unlocking percentage will be bigger than `100%` and underflow | Using `540` instead of `540 days` makes the computed unlocking percentage exceed 100%, which causes the unlock flow calculation to underflow and prevents normal unlocking. |
| H-3 | High | `Fontaine` never stops the flows to the tax and recipient, so the buffer component of the flows will be lost | `Fontaine::initialize()` starts the recipient and tax flows but never stops them, so the Superfluid buffer reserve is never reclaimed and value is lost. |
| M-1 | Medium | An attacker may DoS user Fluid balance increases by frontrunning `FluidLocker::claim()` calls and calling `EP_PROGRAM_MANAGER::batchUpdateUserUnits()` directly | An attacker can spend the claim signature first, making the user's claim revert and preventing the user from increasing their Fluid balance before a tax distribution. |
| M-2 | Medium | `FluidLocker::_getUnlockingPercentage()` divides before multiplying, suffering a significant precision error | The calculation loses precision by dividing before multiplying, which rounds unlock outcomes down and shifts value by about 1 BPS in common cases. |
| M-3 | Medium | A malicious user may unlock instantly all the funds from the `FluidLocker` when no one is staking in the Tax pool | If the tax pool has no stakers, the instant-unlock path can be repeated to withdraw all funds without paying tax. |
