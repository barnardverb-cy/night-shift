# NIGHT SHIFT — GAME DEVELOPMENT PLAN

## 1. Project Overview

**Game Name:** Night Shift  
**Game Type:** First-Person Maze Shooter  
**Theme:** Retro 90s FPS / Dark Office / Sci-Fi  
**Platform:** Web Browser (Desktop)  
**Development Approach:** AI-Assisted Development

### Game Description

Night Shift is a retro 90s-style first-person maze shooter where the player controls a security robot assigned to clear malfunctioning cleaning drones from a dark office after working hours.

The player must explore the office maze, locate and shoot eight malfunctioning cleaning drones, and survive their attacks before the battery runs out or time expires.

### Game Objective

Shut down all eight malfunctioning cleaning drones before the four-minute countdown reaches zero while keeping the player's battery above zero.

---

## 2. Technical Requirements

- Use only HTML, CSS, and vanilla JavaScript.
- All code must be contained in one file named `index.html`.
- Use HTML Canvas for rendering.
- Use JavaScript raycasting to create a first-person 3D perspective from a 2D grid map.
- Use the Web Audio API for sound effects and ambient audio.
- Do not use external libraries or frameworks.
- Do not use external images, audio files, or downloadable assets.
- The game must run by double-clicking `index.html`.
- No server, installation, or additional dependencies required.
- Ensure every development step produces a complete, playable version of the game.

### Project Structure

```text
Night-Shift/
└── index.html
```

---

# 3. Development Plan

## STEP 1 — FIRST PLAYABLE: BUILD THE 3D MAZE

### Objective

Create a working first-person environment with a functional maze, player movement, enemy drones, and shooting mechanics.

### Features

#### 1.1 Raycasting Engine
- Create a 2D grid-based office map.
- Render walls using JavaScript raycasting.
- Display walls with a retro 90s FPS visual style.
- Create a dark office atmosphere.
- Add basic floor and ceiling rendering.
- Use different shades and colors to create depth and distance effects.

#### 1.2 Player System
- Implement first-person player movement.
- WASD controls for movement.
- Mouse movement for turning.
- Use Pointer Lock API for mouse control.
- Click Start Game to activate pointer lock.
- Press ESC to release the mouse.
- Prevent the player from walking through walls.

#### 1.3 Drone System
- Create eight cleaning drones.
- Place drones in different locations throughout the maze.
- Make drones wander around the office.
- Make drones detect and chase the player.
- Render drones as simple retro-style enemies.
- Allow the player to shoot and eliminate drones.

#### 1.4 Shooting System
- Display a crosshair at the center of the screen.
- Use left-click to shoot.
- Shooting direction follows the center crosshair.
- Detect whether a drone is hit.
- Remove drones when successfully shot.
- Add basic shooting visual effects using Canvas.

### Acceptance Checks

1. Open `index.html` in a browser and click Start Game. The first-person office maze should appear.
2. Use WASD to move and the mouse to turn. The player should not be able to walk through walls.
3. Find a drone, aim at it using the center crosshair, and left-click. The drone should disappear when successfully hit.

### Restrictions for Step 1

Do not implement:
- Score system.
- Battery system.
- Countdown timer.
- Win or lose conditions.
- Result screens.
- Restart functionality.

**Expected Output:** A playable first-person maze prototype where the player can explore, encounter drones, and shoot them.

---

## STEP 2 — FULL GAME: IMPLEMENT GAMEPLAY SYSTEMS

### Objective

Transform the playable prototype into a complete game with player health, enemy behavior, winning and losing conditions, and restart functionality.

### Features

#### 2.1 Player Battery System
- Start each round with 100% battery.
- Every drone collision removes 10% battery.
- Display battery percentage on the HUD.
- Update the battery display whenever damage occurs.
- End the game when battery reaches 0%.

#### 2.2 Drone System Improvements
- Maintain eight drones in the office.
- Drones wander around the maze.
- Drones detect and chase the player.
- Drones attack when they collide with the player.
- Ensure drones cannot pass through walls.
- Track the number of eliminated drones.
- Display the remaining drone count on the HUD.

#### 2.3 Countdown Timer
- Set the round duration to four minutes.
- Display the countdown timer on the HUD.
- Update the timer continuously.
- End the round when the timer reaches zero.

#### 2.4 Winning Condition
- The player wins after eliminating all eight drones.
- Display a Victory screen.
- Show the player's final results.

#### 2.5 Losing Conditions
The player loses when either:
- Battery reaches 0%.
- The four-minute countdown expires.

Display a Game Over screen with the reason for losing.

#### 2.6 Result Screen
Display the following information:
- Victory or Game Over.
- Number of drones eliminated.
- Remaining battery percentage.
- Elapsed time.
- Restart button.

#### 2.7 Restart System
When the player clicks Restart:
- Reset the player's position.
- Restore battery to 100%.
- Reset the countdown to four minutes.
- Respawn all eight drones.
- Reset eliminated drone count.
- Reset enemy positions and behaviors.
- Reset all gameplay variables.
- Start a completely new round.

### Acceptance Checks

1. Start a game and allow a drone to collide with the player. The battery should decrease by 10%.
2. Eliminate all eight drones to trigger the Victory screen. Also test the losing conditions by allowing the battery to reach zero or the timer to expire.
3. Click Restart. The game should reset to eight drones, 100% battery, and four minutes on the timer.

**Expected Output:** A complete and playable game with functional gameplay systems, win/lose conditions, result screens, and restart functionality.

---

## STEP 3 — READY TO SHARE: POLISH AND FINALIZE

### Objective

Improve the presentation and overall experience so the game is ready to share and play on desktop browsers.

### Features

#### 3.1 Browser Information
- Set the browser tab title to Night Shift.
- Add appropriate HTML metadata.
- Ensure the game loads correctly by opening `index.html`.

#### 3.2 Start Screen
- Create a retro-style title screen.
- Display the game name: NIGHT SHIFT.
- Add a Start Game button.
- Include a short description of the mission.

#### 3.3 Controls Guide
Display the following controls on the screen:

- WASD — Move.
- Mouse — Look / Turn.
- Left Click — Shoot.
- ESC — Release Mouse.

#### 3.4 Visual Improvements
- Improve the retro 90s FPS aesthetic.
- Refine the HUD layout.
- Improve shooting effects.
- Improve enemy hit feedback.
- Ensure consistent visual styling across all screens.

#### 3.5 Sound Effects
Use the Web Audio API to generate:
- Shooting sounds.
- Drone hit sounds.
- Drone shutdown sounds.
- Player damage sounds.
- Victory and defeat sounds.
- Basic ambient office sounds.

No external audio files should be used.

#### 3.6 Credits
Display the following credits line:

Developed with AI assistance | Night Shift

#### 3.7 Mobile Warning
- Detect phone-sized screens.
- Display a friendly message when the game is viewed on a small screen.

Message:

"Best on a computer! This game is designed for keyboard and mouse."

The desktop game should remain the primary supported experience.

### Acceptance Checks

1. Open the game and verify that the browser tab displays Night Shift and the start screen displays the game title and controls.
2. Play a round and verify that the HUD, shooting effects, and generated sound effects work correctly.
3. Resize the browser to a phone-sized screen. The mobile warning should appear.

**Expected Output:** A polished, complete, desktop-ready version of Night Shift.

---

# 4. Features Reserved for Future Updates

The following features are intentionally excluded from Version 1:

- Multiple office floors.
- Battery or health pickups.
- Minimap.
- Saved high scores.
- Additional drone types.
- Additional weapons.
- More office environments.
- Difficulty selection.

These features may be considered for future versions after the initial game is complete.

---

# 5. Final Version 1 Requirements Checklist

The final game must satisfy the following requirements:

- [ ] Runs by double-clicking `index.html`.
- [ ] Uses only HTML, CSS, and vanilla JavaScript.
- [ ] Uses HTML Canvas for graphics.
- [ ] Uses raycasting for first-person rendering.
- [ ] Has a walkable maze with solid walls.
- [ ] Supports WASD movement.
- [ ] Supports mouse turning using Pointer Lock.
- [ ] Has eight malfunctioning cleaning drones.
- [ ] Drones wander and chase the player.
- [ ] Player can shoot drones using left-click.
- [ ] Has a center-screen crosshair.
- [ ] Has a 100% starting battery.
- [ ] Drone collisions remove 10% battery.
- [ ] Has a four-minute countdown timer.
- [ ] Displays remaining drones.
- [ ] Has a victory screen.
- [ ] Has a game-over screen.
- [ ] Has a functional restart button.
- [ ] Restart resets all gameplay variables.
- [ ] Has a proper start screen.
- [ ] Displays the controls guide.
- [ ] Has generated sound effects using Web Audio API.
- [ ] Has a credits line.
- [ ] Displays a mobile warning on small screens.
- [ ] Contains no external dependencies or assets.

---

# 6. Development Rules

1. Follow the three development steps in order.
2. Do not start the next step until the current step passes all acceptance checks.
3. Always provide the complete updated `index.html` file when implementing a step.
4. Do not provide partial code snippets that require manually combining multiple versions.
5. Preserve all previously working features when implementing the next step.
6. Keep the code beginner-friendly, organized, and commented.
7. Avoid unnecessary complexity and premature optimization.
8. Explain exactly how to test each development step in a browser.
9. Fix bugs before adding new features.
10. Keep everything inside one `index.html` file.

---

**PROJECT END GOAL**

Create NIGHT SHIFT, a complete retro-style first-person maze shooter that runs directly in a desktop browser using a single HTML file, with no installations, external dependencies, or additional assets.