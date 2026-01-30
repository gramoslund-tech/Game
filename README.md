# Game
Fnaf game consept

# 🕹️ The Glitch: Mobile Horror Framework

A high-tension, survival-horror game engine built in C# for Unity, optimized for mobile performance. 

## 🚀 Key Features

* **Adaptive Mobile Controls:** Smooth 1:1 swipe-to-look logic designed for touchscreens.
* **Dynamic Power Management:** Real-time battery drain system influenced by environmental interactions (doors, lights, UI).
* **Night 4 "Hardware Hack":** A unique mechanic where enemy interference inverts player input logic, forcing a fight against muscle memory.
* **Night 5 Free-Roam:** A logic switch from stationary survival to a scavenger-hunt mission with active AI stalking.

## 📁 Project Structure



- **Scripts/**: Contains `GlitchGameManager.cs` (The core brain of the game).
- **UI/**: Handles the power meter, hack overlays, and mobile button mapping.
- **Prefabs/**: Ready-to-use door and fuse objects with pre-configured hitboxes.

## 🛠️ Installation & Usage

1. **Clone the Repo:** Download the `GlitchGameManager.cs` file.
2. **Import to Unity:** Drag the script into your Unity project `Scripts` folder.
3. **Setup Scene:** - Create an Empty GameObject and name it `GameManager`.
    - Attach the `GlitchGameManager` script.
    - Drag your Door models and UI Text elements into the corresponding slots in the **Inspector**.
4. **Build Settings:** Set Platform to **Android** or **iOS** for optimal touch performance.

## 🧠 Mechanics Logic (Night 4 Hack)

The inversion code utilizes a simple boolean check to swap door targets:
```csharp
if (isHacked) {
    // Invert: Left button closes Right door
    if (side == "Left") ToggleDoor("Right");
    else ToggleDoor("Left");
}
