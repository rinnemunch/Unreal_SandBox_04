# 🗡️ Project 1 – Melee + Break Stuff Mini Demo (UE5)

This project showcases a lightweight melee test setup in Unreal Engine 5.5.4, focused on clean animation blending, upper-body attack layering, and simple breakable props. It’s a fast, practical sandbox to experiment with melee hits, weapon collision, and real-time destruction — without building a full combat system.

---

## 🖼️ Preview

![Melee Demo](Media/3.gif)

---

## 🧱 Features

- **Imported Animations**

  - Two attack animations retargeted to SK_Mannequin
  - Clean retargeting for Third Person compatibility

- **Animation Blueprint Setup**

  - **Anim Montages** created for both attacks
  - **Cached Pose (Attacks)** for clean reuse
  - **Layered Blend Per Bone** (from spine_01 upward)
  - **DefaultSlot** for montage playback

- **Weapon Setup**

  - Weapon mesh attached to **hand_r**
  - Corrected transforms for natural positioning
  - Capsule Collision added to detect strike overlaps

- **Input Mapping**

  - Left Mouse → Attack 1
  - Right Mouse → Attack 2

- **Breakable Props**
  - Geometry Collections created for destructible objects
  - Fracture Mode configured with uniform fracture pattern
  - Bone colors disabled for clean visuals
  - **Remove on Sleep** used for automatic debris cleanup

---

## 🚀 Result

Press **Play**, swing the weapon, and objects break instantly on hit.
Animations blend smoothly, collisions feel responsive, and the destruction loop is fully Blueprint-driven and modular.

---

# 🎭 Project 2 – Custom Headshake Animation (UE5)

This project demonstrates how to create a fully custom animation inside Unreal Engine 5.5.4 using Control Rig, Sequencer, and Animation Blueprints. You’ll animate a clean headshake gesture, bake it into an Animation Sequence, and blend it into gameplay without disrupting locomotion.

---

## 🖼️ Preview

![Headshake Demo](Media/2.gif)

---

## 🧱 Features

- **Control Rig Workflow**

  - MM_Idle duplicated into **MM_Headshake**
  - Keyframed head rotation sequence in Sequencer
  - Smooth neutral → up → down → neutral animation pass

- **Bake & Export**

  - Animation baked from Sequencer to an **Animation Sequence**
  - Clean curves with proper looping behavior

- **Montage Setup**

  - AnimMontage generated for MM_Headshake
  - Adjustable play rate for timing control

- **Gameplay Integration**

  - Keyboard **1** mapped to trigger montage
  - Plays on DefaultSlot for simple insertion

- **Animation Blueprint Layering**
  - **Cached Pose (Headshake)**
  - **Layered Blend Per Bone** targeting **neck_01**
  - Blends cleanly into walk/run/jump movement

---

## 🚀 Result

Press **1** to fire the headshake animation.
It layers perfectly onto movement using upper-body blending, giving you expressive character gestures with zero interruption to locomotion.

---

# 🌐 Project 3 – Level Switching with Open Level by Name (UE5)

This project demonstrates a clean, Blueprint-only level switching system using overlap triggers to instantly move between the Third Person and First Person template maps. Ideal for rapid prototyping or building multi-map hubs.

---

## 🖼️ Preview

![Level Switch Demo](Media/1.gif)

---

## 🧱 Features

- **BP_ToFirstPerson Trigger Actor**

  - Simple Plane mesh for visibility
  - Box Collision for overlap detection
  - Opens **FirstPersonMap** on player overlap

- **First Person Content Pack**

  - Added directly into the Third Person project
  - Ensures both maps are available for loading

- **Blueprint Logic**

  - **Open Level (by Name)** for instant switching
  - Exact match of map name to prevent load errors

- **BP_ToThirdPerson Trigger**

  - Duplicate of the first trigger
  - Sends player back to **ThirdPersonMap**

- **Two-Way Travel**
  - Zero UI
  - Zero delays
  - No GameMode changes
  - Simple, fast level cycling using overlaps

---

## 🚀 Result

Walk onto the trigger plane to swap maps instantly.
Walk onto the return trigger to go back.
A clean two-way teleport system for tests, prototypes, or hub transitions.

---

# ⚡ Project 4 – Skyrim-Inspired Sprint & Stamina System (UE5)

This project builds a **Skyrim-style sprint/stamina system** inside Unreal Engine 5.5.4. Sprinting drains stamina, plays armor-clank audio, boosts FOV, and triggers tired breathing when exhausted. Stamina regenerates when resting, and a UI bar visualizes the entire cycle.

---

## 🖼️ Preview

![Sprint System Demo](Media/4.gif)

---

## 🧱 Features

- **Character Setup**

  - Third Person template character used as base
  - Mesh swapped to **SKM_MidPoly** (Juggernaut)
  - Mesh transform adjusted for correct orientation

- **Audio Components**

  - **Armor** loop for running
  - **Tired** breathing for exhaustion
  - Both set to **Auto Activate = False**

- **Core Variables**

  - **isSprinting** (bool)
  - **Stamina** = 100
  - **MaxStamina** = 100

- **StartRunning Function**

  - Max Walk Speed set to **600**
  - Armor audio **Fade In (0.5s)**
  - Camera FOV set to **80**
  - isSprinting = true

- **StopRunning Function**

  - Walk speed restored to **150**
  - Camera FOV returned to **90**
  - Armor audio **Fade Out (0.5s)**
  - isSprinting = false

- **Stamina Regeneration**

  - **Regen** event created
  - Adds +1 stamina per tick using **Clamp**
  - Stops regenerating when stamina = max
  - Only runs when **not sprinting**

- **Stamina Drain**

  - **Drain** event created
  - Subtracts –1 stamina per tick
  - Loop continues only while **isSprinting = true**
  - When stamina hits **0**:
    - Auto-calls **StopRunning**
    - Tired breathing **Fade In (0.5s)** plays instantly

- **UI Stamina Bar**

  - `WBP_UI` created with Progress Bar
  - Bound to **Stamina / MaxStamina**
  - Positioned with bottom-left anchor
  - Updates automatically during play

- **Event Graph Integration**
  - Begin Play → calls **Regen**
  - Begin Play → creates & adds UI to viewport
  - Left Shift (Pressed) → **StartRunning**
  - Left Shift (Released) → **StopRunning**
  - StartRunning → calls **Drain**
  - StopRunning → calls **Regen**

---

## 🚀 Result

Hold **Left Shift** to sprint with speed boost, armor sounds, and FOV tightening.
Stamina drains dynamically, the character becomes exhausted when empty, breathing kicks in, and regeneration restarts when resting.
The UI bar tracks everything in real time — a clean, immersive Skyrim-inspired stamina loop.

---
