# 🎮 Echo Protocol

[![Unreal Engine](https://img.shields.io/badge/Unreal%20Engine-5.x-blue?logo=unrealengine)](https://www.unrealengine.com/)
[![Language](https://img.shields.io/badge/Language-C%2B%2B%20%2F%20Blueprints-orange?logo=c%2B%2B)](https://isocpp.org/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](#license)

**Echo Protocol** is an action-adventure gameplay framework and game prototype built in **Unreal Engine 5** using a hybrid of high-performance **C++** and **Blueprints**.

The project showcases three distinct gameplay paradigms—**Combat**, **Platforming**, and **Side-Scrolling**—sharing a clean, modular architecture with AI powered by Unreal's **StateTree** and **Environment Query System (EQS)**.

---

## 🌟 Gameplay Variants & Features

### ⚔️ 1. Combat Variant (Third-Person Melee)
- **Combo Attack System:** Multi-stage melee combos with timed hit-windows and animation notifies.
- **Charged Attacks:** Press-and-hold mechanic that powers up a heavy attack release.
- **Dynamic Hit Tracing:** Sphere collision sweeps (`AnimNotify_DoAttackTrace`) for precise attack detection.
- **Damage & Reaction:** Health system, ragdoll impulse response, hazard floor detection (e.g., lava), and destructible props.
- **Intelligent Enemy AI:**
  - Built with Unreal's **StateTree** and **EQS (Environment Query System)**.
  - Enemy AI anticipates incoming attacks (`NotifyDanger`), manages aggro, and engages using tactically evaluated positions.
- **Checkpoints & Respawning:** Seamless checkpoint volume system that handles player respawns and resets.

### 🏃 2. Platforming Variant (3D Movement)
- **Enhanced Locomotion:** Smooth third-person movement with walking, sprinting, and crouch toggling.
- **Dash Ability:** Fast aerial/ground dash mechanic controlled through animation notifies (`AnimNotify_EndDash`).
- **Precision Platforming:** Tuned jump curves and responsive camera boom control.

### 🕹️ 3. Side-Scrolling Variant (2.5D Action)
- **Dynamic Camera System:** Specialized `SideScrollingCameraManager` for fixed-depth framing.
- **Advanced Jumps:** Double jump, wall jumping with momentum lockout, and **coyote time** (for forgiving edge-jumps).
- **Soft Platforms (One-Way):** Drop-through platform system (`DropAction`) for smooth vertical navigation.
- **Interactive Stage Elements:**
  - Jump pads with impulse boosts.
  - Moving platforms with synchronized pawn attachment.
  - Pickups and collectible triggers.
  - Interactive switches and triggers (`SideScrollingInteractable`).
- **Side-Scrolling AI:** NPC and enemy behaviors integrated using StateTree.

---

## 📁 Project Structure

```text
EchoProtocol/
├── Config/                     # Engine, Input, Game, and Editor configurations
├── Content/                    # Maps, Blueprints, Materials, Audio, and Animations
│   ├── Characters/             # Character skeletal meshes and animation assets
│   ├── Variant_Combat/         # Combat levels, Blueprints, and UI widgets
│   ├── Variant_Platforming/    # 3D platforming assets and levels
│   └── Variant_SideScrolling/  # 2.5D side-scrolling maps and interactive actors
├── Source/
│   └── EchoProtocol/           # Main C++ source module
│       ├── Variant_Combat/     # Combat characters, controllers, AI, UI, and anim notifies
│       ├── Variant_Platforming/# Platforming movement and abilities
│       ├── Variant_SideScrolling/# 2.5D characters, camera manager, interactables, and AI
│       ├── EchoProtocolCharacter.* # Base third-person character class
│       └── EchoProtocolGameMode.*  # Base game mode class
└── EchoProtocol.uproject       # Unreal Engine project descriptor
```

---

## ⌨️ Controls & Input

The project uses Unreal Engine's **Enhanced Input System** (`InputMappingContext` & `InputAction`):

### Third-Person Combat & Platforming
| Action | Keyboard / Mouse | Gamepad |
| :--- | :--- | :--- |
| **Move** | `W` / `A` / `S` / `D` | Left Stick |
| **Look** | Mouse Move | Right Stick |
| **Jump** | `Spacebar` | `Face Button Bottom` (A / ✕) |
| **Sprint** | `Left Shift` | `Left Thumbstick Click` (L3) |
| **Crouch** | `Left Ctrl` / `C` | `Right Thumbstick Click` (R3) |
| **Combo Attack** | `Left Mouse Button` | `Face Button West` (X / ▢) |
| **Charged Attack** | `Right Mouse Button` (Hold & Release) | `Right Trigger` (RT / R2) |
| **Toggle Camera Side** | `V` / Middle Mouse | `D-Pad Down` |

### Side-Scrolling
| Action | Keyboard / Mouse | Gamepad |
| :--- | :--- | :--- |
| **Move Left / Right** | `A` / `D` (or `Left` / `Right`) | Left Stick (X-axis) |
| **Jump / Multi-Jump** | `Spacebar` | `Face Button Bottom` (A / ✕) |
| **Drop Through Platform** | `S` (Down) + `Spacebar` | Left Stick Down + Jump |
| **Interact** | `E` | `Face Button West` (X / ▢) |

---

## 🚀 Getting Started

### Prerequisites
1. **Unreal Engine 5** installed (UE 5.x / 5.8).
2. **Visual Studio 2022** (with *Game Development with C++* workload and *Unreal Engine Installer* component) or **JetBrains Rider**.
3. **Git** for version control.

### Installation & Launch

1. **Clone the repository:**
   ```bash
   git clone https://github.com/NitishKumarKushwah/EchoProtocol.git
   cd EchoProtocol
   ```

2. **Generate Visual Studio Project Files:**
   - Right-click `EchoProtocol.uproject` and select **Generate Visual Studio project files**.

3. **Build the Project:**
   - Open `EchoProtocol.sln` in Visual Studio 2022.
   - Set build configuration to `Development Editor` and `Win64`.
   - Build the solution (`Ctrl + Shift + B`).

4. **Launch the Unreal Editor:**
   - Double-click `EchoProtocol.uproject` or hit `F5` in Visual Studio to debug and run.

5. **Play the Levels:**
   - In the Content Browser, navigate to `Content/` and choose your preferred variant level:
     - `Variant_Combat` for Melee Combat & AI arena
     - `Variant_Platforming` for 3D platforming
     - `Variant_SideScrolling` for 2.5D action & platform challenges
   - Press **Play (PIE)** to test in-editor!

---

## 🛠️ Built With

- **Unreal Engine 5** - Game Engine
- **C++20** - Core gameplay mechanics, collision traces, and camera managers
- **StateTree** & **GameplayStateTree** - Next-generation decision-making AI
- **Enhanced Input** - Input action mapping and cross-platform controller support
- **UMG (Unreal Motion Graphics)** - Floating health bars and HUD elements

---

## 👤 Author

**Nitish Kumar Kushwah**
- GitHub: [@NitishKumarKushwah](https://github.com/NitishKumarKushwah)
