# TASK — Balloon Shop MVP

## Goal
Implement balloon shop for MVP.

The shop opens from `HudGui.RightSide.ShopButton`.
The player can buy balloon types with coins.
Each balloon type changes pet roulette rarity distribution:
- lower rarities stay available
- higher rarities become much less likely
- each step above the base balloon is about 10x rarer than the previous tier

After purchase, the balloon is only added to inventory.
Do not auto-equip it.

## Allowed Context
Read only docs.

Use these files as the source of truth:
- `docs/ARCHITECTURE.md`
- `docs/STATE.md`
- `docs/contracts/REMOTES.md`
- `docs/contracts/DATA_SCHEMA.md`
- `docs/contracts/API_RULES.md`
- `docs/systems/UI.md`
- `docs/systems/ECONOMY.md`
- `docs/systems/BALLOON.md`
- `docs/systems/ROULETTE.md`

Do not read `src`.
Do not invent unrelated systems.

## Scope
Implement only the MVP shop flow for balloon purchase and roulette rarity influence.

In scope:
- open shop from HUD button
- show balloon catalog
- buy balloon with coins
- store bought balloon in inventory with count `1`
- reflect balloon ownership in UI
- make roulette pet rarity weighting depend on current equipped balloon

Out of scope:
- auto-equip after purchase
- monetization / gamepasses / devproducts
- new gameplay systems
- schema changes unless strictly required
- new remotes unless strictly required and documented

## Expected Behavior
- Shop opens via `HudGui.RightSide.ShopButton`.
- Player sees available balloon types.
- Player can buy one balloon only if they have enough coins.
- Bought balloon is added to `Balloons` inventory with value `1`.
- Existing ownership blocks duplicate purchase if that is already the current design in docs.
- Roulette result generation uses the equipped balloon to bias rarity distribution.
- Common pets must always remain possible.
- Higher balloon tiers should make their own rare pets much less likely, not impossible.

## Rules
- Keep server authority for purchases and rewards.
- Client is UI only.
- Use existing remote contracts unless a new one is absolutely required.
- If a new remote or schema field is needed, stop and explain why.
- Keep changes minimal.
- Do not add `task.wait` hacks.

## Verification
Before finishing, report:
1. What files were changed.
2. How shop opening works.
3. How purchase validation works.
4. How roulette rarity weighting was applied.
5. How to test the flow in Studio.

## Notes
- If the docs are ambiguous, ask before implementing.
- Prefer small changes to existing modules over adding new systems.
