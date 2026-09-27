# Cut The Corners — Game Design Document

<!--
Living document. Short bullets > long paragraphs.
If a section has nothing yet, write "TBD" — don't delete the heading.
Scope decisions live in MoSCoW.md; this file describes WHAT the game is.
-->

**Version:** 0.1 — 2026-09-27
**Author:** Mehmet Ali Genç

---

## 1. Overview

- **Working title:** Cut The Corners
- **Genre:** 2D Arena Fighter
- **Platform:**
  - **Main:** WebGL (itch.io)
  - **Mobile (lite):** a reduced version with a simplified control scheme, a playable sample to show from my pocket in job interviews.
- **Players:** Single player vs AI. One against all.
- **Characters:** The player is a pill (capsule) shape; enemies are rectangles.
- **Session length:** 2–5 min per match. Not a rule; will be tuned during development.
- **Elevator pitch (1–2 sentences):** Wonky, cute, simple shapes fight each other with weapons. Characters and weapons have mass, and the animations sell their weight, torque and wobbly movement.

## 2. Design Pillars

1. **Heavy, wonky bodies:** Characters have weight and inertia; every movement and animation supports this.
2. **Sharp weapons:** Weapon animations feel quick and responsive.
   *Deliberate contrast with pillar 1: clumsy body, sharp blade. Open to change if it doesn't feel right in playtests.*
3. **The arena is a weapon:** Interactable objects let the player use the terrain in the fight.

## 3. Core Loop

- **Moment-to-moment:** Attack, retreat, search for a weapon, look for an opening to attack.
- **Match:** Everyone starts empty-handed. Weapons appear randomly on the map; everyone (player and AI) runs for them. The fight begins. Last one standing wins.
- **Meta:** None for now; each match is standalone.

## 4. Player

- **Movement:** Run, jump, dash, climb.
- **Health / damage:** Every character has 3 HP. Every hit deals 1 damage unless a weapon says otherwise (see Weapons table). Values may change during development.
- **Actions:** Attack, block (shield) / parry (sword), pick up, throw (spear is thrown aggressively; other weapons are just dropped), break (crates), climb.
- **Hand slots (what can be held at once):**

| Loadout | Allowed |
|---|---|
| Sword + Shield | ✅ |
| Sword alone | ✅ |
| Shield alone | ✅ |
| Pistol alone | ✅ (no shield) |
| Spear alone | ✅ (two-handed; nothing else) |

## 5. Weapons & Combat

| Weapon | How it attacks | Special property | How it breaks |
|---|---|---|---|
| Sword | Swings toward the mouse cursor | Right click: parry | After 3 hits |
| Spear | Left click: poke. Right click: throw | Thrown spear kills instantly. It sticks into most surfaces and becomes part of the terrain (if it doesn't break on impact); can be picked up again | After 3 hits |
| Pistol | Shoots bullets (fast but wonky; bullets have mass) | Ranged. Deals 2 damage. Only obtained by breaking a crate | After 3 shots |
| Shield | Doesn't attack | Blocks every attack | After taking 3 hits; breaks instantly if hit by a thrown spear |

- **Blocking:** Shield blocks; sword parries. No other weapon can defend.
- **Weapon durability / breaking:** Every weapon lasts 3 uses (see "How it breaks" column).
- **Weapon pickup / spawning:** Weapons spawn randomly on the map. Crates also spawn randomly, but less often than weapons; breaking a crate drops a pistol.
- **Interaction with the arena:** Climbing ropes, jumping on a spear stuck in a wall, maybe climbing ladders.

## 6. Opponents

- AI enemies (rectangles). They also run for weapons and pick them up.
- Difficulty is set by the number of enemies.

## 7. Arena / Levels

- **Layout:** TBD
- **Number of arenas:** 1–3
- **Hazards / interactive elements:** TBD (see "Interaction with the arena" above)

## 8. Win / Lose & Progression

- **Win condition:** Be the last shape standing.
- **Lose condition:** Get killed by the rectangles.
- **Progression / difficulty curve:** Controlled by the number of enemies.

## 9. Controls

*Not decided yet. Known so far: aiming with the mouse, left/right click for weapon actions (see Weapons table). The mobile lite version will have its own reduced scheme.*

| Action | Keyboard + Mouse | Gamepad | Mobile (lite) |
|---|---|---|---|
| Move | TBD | | |
| Jump | TBD | | |
| Aim | Mouse cursor | | |
| Attack | Left click | | |
| Parry / Throw | Right click | | |
| Pick up | TBD | | |
| Drop | TBD | | |

## 10. Art & Audio Direction

- **Visual style:** Sprite pack is ready: black-and-white sprites, colored characters.
- **Camera:** Static; may follow the action on bigger maps (if any).
- **Audio / music:** TBD

## 11. UI / Screens

- Main menu
- Pause screen
- Win screen
- Lose screen
- Level selection (if there are multiple arenas)
- Color selection
- Difficulty selection (if any)

## 12. Technical Notes

- **Engine:** Unity 6000.5.2f1
- **Key systems:**
  - Physics-based character controller (Rigidbody2D: forces, mass, inertia)
  - Animation system (Animator state machine + procedural wobble)
  - Equipment / hand-slot system (pick up, drop, throw, loadout rules)
  - Weapon system (shared durability, per-weapon behavior)
  - Spawn system (random weapons and crates)
  - Enemy AI (find weapon → approach → attack / block / retreat)
  - Input System with separate action maps (desktop, mobile)
- **Learning goals for this project:**
  - **Enemy AI:** state machines, decision-making (which weapon to go for, when to attack or retreat), basic 2D pathfinding across platforms, ropes and ladders.
  - **Rigidbody2D physics:** moving with forces instead of `transform.Translate`, mass/drag/gravity, torque, tuning "weight" and "wonkiness".
  - **Joints:** HingeJoint2D / other 2D joints for weapons attached to bodies, rope climbing and a physics-driven wobble.
  - **Animation:** Animator state machines (idle / run / jump / attack), blending physics with animation, squash & stretch for feel.
  - **Complex collisions:** layers and the collision matrix, trigger vs collision, continuous collision detection for fast objects (bullets, thrown spear), attaching a spear to a surface on impact.
  - **Game feel:** hit-stop, screen shake, knockback. Making a hit *feel* like a hit.
  - **New Input System:** mouse aiming, multiple control schemes (desktop + mobile touch).
  - **Mobile build:** touch controls, performance, screen sizes.

## 13. References & Inspirations

*To review (then note what exactly to take from each):*

- Stick Fight: The Game
- TowerFall
- Duck Game

## 14. Open Questions

- Most decisions will be made during development.
- Do AI enemies also fight each other, or do they all target the player?
- Controls: pick up / drop / throw keys; mobile scheme.
- Arena layout and interactive elements.
