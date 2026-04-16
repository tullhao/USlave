USlave 🔧 Just another U1 + ACE Pro Custom Project

A custom **Snapmaker U1 + ACE Pro** setup based on **SnapACE / MultiAce** ideas, adapted and tuned for my own real machine and maybe yours too?

---

## 🎯 Goal

The goal of this project is **not** to make ACE more aggressive or more “automatic” like other similar Projects.

The goal is:

- ✅ Have the Ace Pro as Load/Unload/dryer Slave
- ✅ reloads when filament is still partly inside the tube
- ✅ Print out of the dry/heaterbox
- ✅ stabilize chained unload behavior
- ✅ add practical service / recovery macros
- ✅ replace the weak stock U1 side motors handling over the filament transport job to the ACE...
- ✅ deterministic control over hidden automation
- ✅ ACE in Idle during prints and non load/unload jobs
- ✅ Feeding / retracting Idle unused Toolheads to prepare/unwind filament.

---

## ⚙️ Current Test performed

- ⚠️ set longer tubes as in reality -> when runoutsensor is reached, retracts 10cm
- ⚠️ Load all Filaments from the Menu at once ( Tuned the timings and implemented guards )
- ⚠️ Unload all, Tuned timings for the Ace to be ready when needed
- ⚠️ Reload with Filament partially in the tube without timeout from U1 ( retry logic in cfg )
- ⚠️ Retract/Feed while Toolhead ready, no movement as expected and Console Output
- ⚠️ Retract/Feed unused Slots while machine is Printing

- RFID is not tested by my, Apparenty only ACE RFID is supported. different as if you use the side mounted readers of the U1


## ✅ What currently works well

- **load / unload** performed by the ACE
-  **half-in-tube reload** same as Stock
- stable **chained unload timing**
- protected **manual feed / retract macros**
- configurable **retry / delay values**
- useful **service/heating and testing macros**
- practical tuning workflow through extended config values

---

## 🧪 What is still being refined

Eliminating a bug that if a filament was discovered to been retracted 10cm due to long feed_length in console, the first load job might not start. but 1 of 10 times this bug appeared for me.

The next challenge is simple:

- ⚠️ refine and tune extra ACE movement to slim down all the timings. Maybe no retry logics or guards are necessary if the correct values were found in the scripts... But my limited knowledge and AI got me so far :)


So the project is already usable for me and I have tested it now for multiple days and refined the issues I encountered and could solve, but it is still under active refinement. 
Your help is very welcome for the coding part as I have only used basic programming knowledge and a not so intelligent AI to implement most of the changes. 

There are other Projects out there way more refined than mine (SnapAce,MultiAce etc)
USlave serves exactly what I need and not more. Shout out the other U1/ACE Projects!!

---

## 🧠 Design Philosophy

This project follows a few simple rules:

- ✅ keep flows that already works
- ✅ avoid unnecessary motor activity during extruder moves on multicolor Prints
- ✅ avoid “smart but random” behavior ( SnapACE does the job perfectly by helping the U1, but in my cases I didn't need the extra Ace Assist )
- ✅ make failures easier to understand ( Ace in Idle while printing )
- ✅ make service and recovery easier ( Makro buttons with safety )
- ✅ tune from real-world testing, not theory alone

---



## 🧩 Influences

This project is based on a **SnapACE / MultiAce style direction**.

It also includes practical lessons and ideas inspired by **MultiACE discussions**, but adapted to this specific setup and testing process.

So this is **not** a direct port of another project.

It is a custom build shaped by:

- SnapACE ideas
- USlave Project
- MultiACE inspiration
- real machine testing

---

## 🚧 Current Status

This project is in a **working but still evolving** state.

### Stable enough for:
- daily testing
- real loading / unloading
- retry tuning
- macro-based service actions
- Load/Unload TPU ( confirm manualaction in Remotescreen/Touchscreen and let ACE do the Unload ;)
- TPU reload after unload, filament in the tume ( no fresh load )

### Still under active work:

- deciding whether **per-slot tube lengths** are truly worth keeping
- further cleanup before calling it fully “done”

---

## 📌 Notes

This project is tuned for **my own machine and filament path geometry**.

That means:

- it may not be a universal drop-in solution
- some values are intentionally tuned from testing
- behavior should always be validated on the real machine
- All values are well described in the ace.cfg
- Follow SnapAce Installation path, replace same files. don't forget to also edit printer.cfg and include these lines
  [include ace.cfg]
  [save_variables]
  filename: ~/printer_data/config/variables.cfg


---

## 💬 Summary

In short:

**less noise, less randomness, more deterministic control.**

This project was made with help of AI to stick together my Ideas. Use it at your own risk!!
