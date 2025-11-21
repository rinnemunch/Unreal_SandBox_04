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
