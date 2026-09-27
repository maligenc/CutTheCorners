# Cut The Corners — MoSCoW

<!--
How to use:
- Must   = without it, the game is not shippable. If one Must is missing, you don't publish.
- Should = important, but the game still works without it.
- Could  = nice to have. Only if time is left.
- Won't  = consciously out of scope for THIS release (not "never").
- One item = one testable sentence. "Combat feels good" is not testable; "Player can block a sword hit" is.
- Tick [x] when done. Don't delete items; move them and log the change below.
-->

**Release target:** WebGL build on itch.io
**Time budget:** 12 weeks, 2026-09-28 → 2026-12-20 (3–5 h/week)
**Scope frozen on:** 2026-10-18 (end of week 3, after the feel prototype). After this date, new ideas go to Could/Won't or the next project.

---

## Must Have

**Build & release**
- [ ] Game is built for WebGL and published on itch.io

**Player**
- [ ] Player (pill shape) moves with Rigidbody2D physics: run and jump
- [ ] Player has 3 HP; every hit deals 1 damage unless a weapon says otherwise
- [ ] Player can pick up and drop a weapon
- [ ] Player aims with the mouse cursor

**Weapons**
- [ ] Sword: swings toward the cursor (left click)
- [ ] Sword: parries an attack (right click)
- [ ] Spear: poke (left click)
- [ ] Spear: throw (right click); a thrown spear kills instantly
- [ ] Thrown spear sticks into walls and the player can stand on it
- [ ] Stuck spear can be picked up again
- [ ] Every weapon breaks after 3 uses
- [ ] Weapons spawn at random points on the map during the match

**Enemies**
- [ ] AI enemies (rectangles) walk to a weapon, pick it up and attack the player
- [ ] Match has at least 3 enemies

**Arena & match flow**
- [ ] 1 arena with platforms at different heights
- [ ] Match starts with everyone empty-handed
- [ ] Last one standing wins; if the player dies, the match is lost

**Feel**
- [ ] Characters feel heavy and wobbly (weight + inertia), while weapon animations are quick (pillar 1 + 2)

**UI**
- [ ] Main menu (Start)
- [ ] HUD shows player HP
- [ ] Win screen and Lose screen, both with Replay

## Should Have

- [ ] Shield: blocks every attack; breaks after taking 3 hits or instantly from a thrown spear
- [ ] Sword + shield can be held together
- [ ] Dash
- [ ] Crates spawn randomly (less often than weapons) and can be broken
- [ ] Pistol: dropped only from crates; ranged; deals 2 damage; breaks after 3 shots
- [ ] Bullets have mass and a slightly wonky trajectory
- [ ] Game feel: hit-stop, screen shake and knockback on hits
- [ ] Idle / run / jump / attack animations (Animator state machine)
- [ ] Sound effects for hits, swings, throws and breaks
- [ ] Pause screen

## Could Have

- [ ] Ropes: climbable
- [ ] Ladders: climbable
- [ ] Difficulty selection (number of enemies)
- [ ] Color selection for the player
- [ ] 2nd and 3rd arenas + level selection
- [ ] Moving camera for bigger arenas
- [ ] Music
- [ ] Gamepad support
- [ ] **Mobile lite version** (reduced controls, for showing in interviews); a separate small project after the WebGL release

## Won't Have (this release)

| Item | Why not now |
|---|---|
| Local / online multiplayer | Player vs AI is the concept; networking is a different project |
| Meta progression (unlocks, upgrades) | Each match is standalone by design |
| AI 2D pathfinding across ropes/ladders | AI is already the most expensive system; enemies stay on walkable platforms |
| Save system / settings menu | Not needed for a short-session arena game |

---

## Scope Change Log

| Date | Change | Reason |
|---|---|---|
| 2026-09-27 | First draft of MoSCoW | 12-week budget; full GDD doesn't fit, so Must is sized to 1 arena + 2 weapons + basic AI |
