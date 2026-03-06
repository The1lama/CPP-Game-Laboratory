# Battleships Buggy Lab — Answers

## Team
- Team name: Team Beast
- Partner A: Rasmus Eriksson
- Partner B: Anton Baksa
- Partner C: Linnèa Ljung

---

## 1) Requirement → Code Map (spec verification)

Fill this table by reading `games/battleships/specification.md` and mapping requirements to code.

Requirement (from specification.md) | Pass/Fail/Unsure | Code location (file + class/function) | Notes (what it does)
---|---|---|---
Example: Turns alternate after each valid shot |  | `battleships_buggy/src/core/Game.cpp` → `Game::AdvanceTurn` | flips current player index
Example: Tracking board records shots |  | `battleships_buggy/src/core/Game.cpp` → `Game::ShootAtOpponent` | updates `Player::tracking`

Add rows for all major requirements you verify.

---

## 2) Spec verification summary

Write Pass/Fail/Unsure for each area and explain *how you verified it* (test steps or observation).

- Setup phase: Pass
- Placement rules: Fail
- Input commands: Pass
- Shot resolution: Unsure
- Tracking board: Fail
- Win condition: Fail

---

## 3) Bugs found (at least 6 total)

You must list at least:
- 3 functional bugs (incorrect behavior vs spec)
- 3 robustness issues (bad input handling, silent failures, crashes, etc.)

### Bug 1
- Symptom: Only one player has setup phase. Game ends after first round, because the player two has no ships. 
- Steps to reproduce (exact inputs): Place player one ships on board and press enter.
- Expected (spec): Player two can place ships on the board.
- Actual: Bug desc.
- Suspected root cause (file/function): Setup is considerd finnished as soon as player one is done, player two is not looked at.
- Fix approach: Check both players placed ships when determening if SetupPhase is done. 

### Bug 2
- Symptom: The last ship part when placed can overlap with another ship
- Steps to reproduce (exact inputs): Place a ship on board. Place another ship on board one cell closer and ship length. 
- Expected (spec): Geting an Overlap error message
- Actual: Could place the ship, and override the first ships cell
- Suspected root cause (file/function): Something in the CanPlaceShip function
- Fix approach: Removed old piece of code that did nothing usefull

### Bug 3
- Symptom: Ships could overlap
- Steps to reproduce (exact inputs):
- Expected (spec):
- Actual:
- Suspected root cause (file/function):
- Fix approach:

### Bug 4
- Symptom:
- Steps to reproduce (exact inputs):
- Expected (spec):
- Actual:
- Suspected root cause (file/function):
- Fix approach:

### Bug 5
- Symptom:
- Steps to reproduce (exact inputs):
- Expected (spec):
- Actual:
- Suspected root cause (file/function):
- Fix approach:

### Bug 6
- Symptom:
- Steps to reproduce (exact inputs):
- Expected (spec):
- Actual:
- Suspected root cause (file/function):
- Fix approach:

(Add more if you find more.)

---

## 4) Code smells found (at least 5)

A “smell” is not necessarily a bug, but a design/implementation choice that increases risk or cost.

### Smell 1
- What (where in code):
- Why risky:
- Better approach (short plan):

### Smell 2
- What (where in code):
- Why risky:
- Better approach (short plan):

### Smell 3
- What (where in code):
- Why risky:
- Better approach (short plan):

### Smell 4
- What (where in code):
- Why risky:
- Better approach (short plan):

### Smell 5
- What (where in code):
- Why risky:
- Better approach (short plan):

---

## 5) Good patterns found (at least 4)

Find at least 4 things the code does reasonably well.

### Good thing 1
- Where:
- Why good:
- How to reuse:

### Good thing 2
- Where:
- Why good:
- How to reuse:

### Good thing 3
- Where:
- Why good:
- How to reuse:

### Good thing 4
- Where:
- Why good:
- How to reuse:

---

## 6) Team bug-fix PR (pair programming)

- Branch name:
- PR link:
- Bugs fixed (list):
- Tests added/updated:
- How you verified the fixes:
- What you learned:

---

## 7) Team feature PR (pair programming)

- Feature implemented (from spec’s “Explicit Missing Features”):
- Branch name:
- PR link:

Mini-spec (write BEFORE coding):
- Behavior:
- Edge cases:
- How to verify (test or manual steps):

Verification performed:
- Tests/manual steps used:
- Result:

---

## 8) Individual feature PRs

### Partner A
- Feature:
- Branch:
- PR link:

Mini-spec:
- Behavior:
- Edge cases:
- How to verify:

Verification performed:
- Tests/manual steps used:
- Result:

### Partner B
- Feature:
- Branch:
- PR link:

Mini-spec:
- Behavior:
- Edge cases:
- How to verify:

Verification performed:
- Tests/manual steps used:
- Result:

---

## 9) Manual test script (if needed)

If you could not write tests for some behavior, write a reproducible manual test script.

Example format:
1) Start game
2) Place ships for both players with valid placements
3) Player 1 shoots A1 → expect: Miss/Hit/Sunk
4) Player 1 shoots A1 again → expect: AlreadyTried and turn should NOT change