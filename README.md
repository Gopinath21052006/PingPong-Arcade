# Retro Ping Pong Arcade

A 1980s-style retro arcade table tennis game built 100% in **Unreal Engine 5.8** using **Pure Blueprints** (Content-Only). No C++ compiler or Visual Studio required!

![Platform](https://img.shields.io/badge/Platform-Windows-blue) ![Engine](https://img.shields.io/badge/Unreal_Engine-5.8-black) ![Type](https://img.shields.io/badge/Architecture-Pure_Blueprint-orange) ![License](https://img.shields.io/badge/License-MIT-green)

---

## 🎮 About the Game

Experience classic Pong reimagined with authentic vector-glow aesthetics, smooth arcade paddle mechanics, tournament match flow, and dynamic HUD rendering.

Play solo against a responsive AI opponent or challenge a friend in head-to-head local 2-player multiplayer.

---

## ✨ Features

* **Home / Mode Select Screen**: Choose between **1 Player vs Computer** or **2 Players Local** right from the start menu.
* **Animated Round Countdown**: "GET READY!" with color-coded **3... 2... 1... GO!** numbers before the ball launches.
* **Target 7 Tournament Scoring**: First player to score **7 points** wins the match (`WinningScore = 7`).
* **Scoreboard Top Plate**:
  * Clean, formatted score values with centered spacing.
  * Active mode badge (`1P vs CPU` or `2-PLAYER`).
  * Centered `TARGET: 7` indicator.
* **Post-Match Game Over Screen**:
  * Winner celebration announcement banner.
  * `[SPACE]` **Play Again**: Instant rematch in the same mode.
  * `[H]` **Home**: Return to the mode select screen.
* **Authentic Retro Aesthetic**:
  * Letterboxed 16:9 court maintaining aspect ratio on any resolution.
  * Neon stadium boundary lines and center divider.
  * Electric cyan P1 paddle, coral/amber P2/CPU paddle, and glowing golden ball.
* **100% Pure Blueprint (Content-Only)**:
  * Zero C++ compiler, Visual Studio, or LiveCoding setup required.
  * Opens and runs directly out of the box in Unreal Engine 5.8.

---

## 🕹️ Controls

| Key | Mode / Screen | Action |
| :--- | :--- | :--- |
| **`1`** or **NumPad `1`** | Home Menu | Start **1 Player vs Computer** |
| **`2`** or **NumPad `2`** | Home Menu | Start **2 Players Local** |
| **`W`** / **`S`** | In-Game | Player 1: **W = Move Up**, **S = Move Down** |
| **`Up`** / **`Down`** | In-Game | Player 2: **Up Arrow = Move Up**, **Down Arrow = Move Down** |
| **`P`** | In-Game | **Pause / Resume** match |
| **`SPACE`** or **`Enter`** | Game Over | **Play Again** (Instant Rematch) |
| **`H`** | In-Game / Game Over | **Return to Home Menu** |
| **`ESC`** | Any | **Quit Game** |

---

## 🚀 Quick Start Guide

### Prerequisites
* Windows 10/11 x64
* [Unreal Engine 5.8](https://www.unrealengine.com) installed via the Epic Games Launcher.

### Running the Game
1. Double-click **`PingPong.uproject`** to launch Unreal Editor 5.8.
2. In the editor, open `/Game/Maps/PingPongMap` (if not already opened).
3. Click the **Play** button (or press `Alt + P`) to play in editor, or select **Standalone Game**.
4. Press **`1`** for Single Player vs CPU or **`2`** for 2-Player Local!

---

## 📦 Git Guide

### 1. How to Clone & Pull this Repository

#### Clone the Project to a New Machine
```bash
git clone <YOUR_REPOSITORY_URL>
cd "pingpong-master 5.8"
```

#### Pull Latest Updates from Git
To fetch and merge the latest commits from the remote repository:
```bash
git pull origin main
```
*(If your default branch is `master`, use `git pull origin master`)*

---

### 2. How to Push this Project to GitHub / Remote Git

If you are setting up a new GitHub repository for this project:

1. **Initialize Git** *(already configured in this folder)*:
   ```bash
   git init
   ```

2. **Stage and Commit all project files**:
   ```bash
   git add .
   git commit -m "feat: complete pure blueprint arcade ping pong with mode select and 3-2-1 countdown"
   ```

3. **Rename default branch to `main`**:
   ```bash
   git branch -M main
   ```

4. **Connect to your GitHub / GitLab repository**:
   ```bash
   git remote add origin https://github.com/<your-username>/<your-repo-name>.git
   ```

5. **Push to GitHub**:
   ```bash
   git push -u origin main
   ```

> [!NOTE]
> The included `.gitignore` automatically excludes Unreal Engine cache folders (`Intermediate/`, `Saved/`, `DerivedDataCache/`), keeping the repository lightweight and fast to sync (~3 MB total).

---

## 🏛️ Project Architecture

```
PingPong/
├── Config/
│   ├── DefaultEngine.ini       # Project settings & default map configuration
│   └── DefaultInput.ini        # Input mappings (Select1P, Select2P, HomeMenu, W/S, Up/Down)
├── Content/
│   ├── Blueprints/
│   │   ├── BP_PingPongGameMode         # State machine, ball physics, AI tracking, win checks
│   │   ├── BP_PingPongHUD              # 2D canvas rendering (arena, HUD, overlays, countdown)
│   │   └── BP_PingPongPlayerController # Keyboard input event routing
│   └── Maps/
│       └── PingPongMap.umap            # Main game level
├── diagrams/                           # Architectural overview & mechanics diagrams
└── PingPong.uproject                   # Unreal Engine 5.8 descriptor (Content-Only)
```

### State Machine (`ArcadeState`)
* **State `4` — Home Menu**: Mode select screen on startup (`[1] vs CPU` or `[2] 2-Player`).
* **State `0` — Countdown**: 3-2-1 countdown before ball serve.
* **State `1` — Active Play**: Ball in motion, paddle movement active.
* **State `2` — Paused**: Game frozen with resume prompt (`[P]` to resume, `[H]` to return Home).
* **State `3` — Game Over**: Winner announced when first player reaches 7 points (`[SPACE]` rematch, `[H]` home).

---

## 📄 License

This project is licensed under the **MIT License** — free to use, modify, and distribute.
