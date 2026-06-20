# DeepSeek Prompt - Balloon Shop Phase 2

You are implementing **Phase 2 only** of the Balloon Shop task.

## Role
You are a careful Roblox Luau implementation agent. Make the smallest correct change for balloon purchase and inventory, and nothing else.

## Read First
- `docs/ARCHITECTURE.md`
- `docs/STATE.md`
- `docs/TASK.md`
- `docs/contracts/API_RULES.md`
- `docs/contracts/DATA_SCHEMA.md`
- `docs/contracts/REMOTES.md`
- `docs/contracts/UI_STRUCTURE.md`
- `docs/systems/ECONOMY.md`
- `docs/systems/BALLOON.md`
- `docs/systems/UI.md`

## Task
- Connect the existing `BuyButton` in `ShopGui` to the purchase flow.
- Use the existing `Shop_BuyBalloon` RemoteFunction contract.
- Validate the purchase on the server.
- Deduct coins through `EconomyService`.
- Add exactly one balloon to `PlayerData.Balloons`.
- Use `BalloonConfig` for balloon metadata and price.

## Rules
- Phase 2 only.
- Do not change shop open/close behavior.
- Do not change balloon selection behavior.
- Do not change roulette rarity logic.
- Do not change pet systems.
- Do not add new remotes.
- Do not modify data schema unless you find a real blocker.
- Keep all server-critical logic on the server.

## Expected Output
- Implement the purchase path from UI to server and back.
- Report exactly how affordability and validation are handled.
- Report how balloon inventory is updated.
- If you need a schema change or another contract change, stop and explain why.

## Response Format
1. Files changed.
2. Purchase flow summary.
3. Inventory update summary.
4. Any blockers or follow-up for Phase 3.

## Stop Condition
If the task would require roulette changes, rarity changes, or UI redesign, stop and report that this is outside Phase 2.
