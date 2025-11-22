# 🗡️ Project 1 – Melee + Break Stuff Mini Demo (UE5)

This project showcases a **lightweight melee test setup** in **Unreal Engine 5.5.4**, focused on clean animation blending, upper-body attack layering, and simple breakable props.
It’s a fast, practical sandbox to experiment with melee hits, weapon collision, and real-time destruction — without building a full combat system.

---

## 🖼️ Preview

![Melee Demo Preview](Media/MeleeDemo.gif)

---

## 🧱 Features

- **Two imported attack animations** retargeted to the SK_Mannequin
- **Anim Montages** created for both attacks
- **Upper-body attack layer** using:
  - Cached Pose (Attacks)
  - Layered Blend Per Bone (from `spine_01` upward)
  - DefaultSlot for montage playback
- **Weapon mesh** attached to `hand_r` with proper transforms
- **Capsule Collision** added to weapon to detect hit overlaps
- **Left/Right Mouse Inputs** triggering the attack montages
- **Breakable props** generated using Geometry Collections
  - Fracture Mode setup
  - Uniform fracture pattern
  - Clean visual (bone colors disabled)
- **Automatic cleanup** of debris using **Remove on Sleep**
- Fully modular, Blueprint-only — ideal for prototyping melee interactions

---

## 🚀 Result

Press Play and start swinging — your character performs clean, upper-body attack animations while the weapon interacts with destructible props in the world.
Objects fracture on impact, chunks disappear after settling, and the whole system stays responsive, modular, and easy to expand.

---

# 🎭 Project 2 – Custom Headshake Animation (UE5)

This project demonstrates how to **create a full custom animation from scratch** inside **Unreal Engine 5.5.4** using Control Rig, Sequencer, and Animation Blueprints.
You’ll build a clean headshake animation, bake it into an Animation Sequence, trigger it through gameplay, and blend it seamlessly into the Third Person character’s movement system.

---

## 🖼️ Preview

![Headshake Animation Preview](Media/HeadshakeDemo.gif)

---

## 🧱 Features

- **Control Rig–driven custom animation** created directly in the Level Sequence
- **MM_Idle duplicated into MM_Headshake** as the editable base pose
- **Sequencer keyframe animation** for smooth head rotation:
  - Base key at frame 0
  - Up rotation
  - Down rotation
  - Return to neutral
- **Baked Animation Sequence** exported from Level Sequence
- **AnimMontage** generated for the new animation
- **Third Person Character** input trigger:
  - Keyboard input `1`
  - Play Anim Montage at custom play rate
- **Full Animation Blueprint integration** using:
  - Cached Pose (Headshake)
  - Layered Blend Per Bone targeting `neck_01`
  - DefaultSlot for montage playback
- **Clean additive blending** that works during movement, jumping, and locomotion

---

## 🚀 Result

Press **1** in-game to trigger a polished custom headshake animation.
The animation blends smoothly into your existing movement system, allowing expressive character gestures without disrupting locomotion.

---
