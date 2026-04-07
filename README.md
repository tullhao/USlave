# USlave – ACE Pro as a Controlled Filament Transport for Snapmaker U1

USlave is a fork / derivative work of SnapACE that transforms the ACE Pro into a controlled, deterministic filament transport system for the Snapmaker U1.

Instead of acting as a constantly assisting feeder, the ACE becomes a **precise, on-demand “slave” motor** used only when required.

---

## 🚀 Key Idea

> The ACE should not “help” all the time — it should only move when explicitly needed.

USlave focuses on:

* predictable behavior
* reduced noise
* controlled filament movement
* improved usability for difficult filament paths

---

## 🔧 Features

* ACE-only filament transport (no reliance on side feed motor)
* Automatic preload on real insertion (empty → occupied detection)
* Safe interaction with toolhead sensors
* No blind long pushes (sensor-based stop behavior)
* Per-toolhead PTFE calibration
* Reduced motor activity (no constant assist noise)
* Manual service macros for feed/retract
* Compatible with stock U1 load/unload workflow

---

## 🧠 Design Philosophy

* No automation without a confirmed state
* No blind movements
* No loops
* Deterministic behavior over “smart guessing”

---

## ⚙️ Configuration

All distances are defined in **centimeters (cm)** by default.

```ini
length_unit: cm

load_length: 150
unload_length: 150

load_length_slots: 150,150,150,150
unload_length_slots: 150,150,150,150
```

* Global values apply to all toolheads
* Per-slot values override when needed

---

## 🔁 Workflow

### Normal operation

1. Insert filament into ACE
2. USlave detects real insertion
3. Auto-preload runs
4. Use "Load Filament" on U1
5. Final short move completes loading

---

## 🛠️ Manual Macros

Used only for:

* recovery
* calibration
* maintenance

Not required for normal use.

---

## 🔒 Safety

* Toolhead sensor stops movement
* No full load after manual interference
* No preload loops
* No uncontrolled pushing

---

## ⚡ Differences to SnapACE

SnapACE:

* active assist system
* shared feed length
* deeper integration (extruder/kinematics)

USlave:

* passive, controlled slave behavior
* per-toolhead calibration
* reduced motor activity
* simpler, more predictable flow

---

## 📦 Installation

See: `USLAVE_INSTALL.md`

---

## 🧪 Testing

See: `USLAVE_TEST_PROTOCOL.md`

---

## 🙏 Credits

Based on ideas and groundwork from SnapACE.

---

## 📢 Status

Work in progress – designed for real-world testing and iterative improvement.
