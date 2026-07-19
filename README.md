# Smart Car Network Simulation System

This repository serves as the central core and distributed simulation platform for the Smart Car project. To prevent high CPU load and ensure real-time simulation execution, the hardware architecture is split across multiple interconnected **Proteus** environments communicating via virtual serial interfaces (**COMPIM**). The firmware for each STM32 microcontroller node is developed in separate repositories and integrated into this workspace as **Git Submodules**.

---

## 🛠 Project Structure & Submodules

### 💻 Hardware & Simulation
* **`SmartCar_Simulation.pdsprj`**  
  The main standalone Proteus hardware simulation file.
* **`SmartCar_Compim_Communication/`**  
  Directory containing the optimized, multi-file Proteus simulation layout where separate nodes communicate seamlessly via **COMPIM** serial port modules.

### 🔌 Firmware Nodes (STM32 Submodules)
* **`Salar-SmartCar/`**  
  Firmware for the **Display & Master Node**. Acts as the central system coordinator, handles menu state machines, and manages the character LCD display interface.
* **`Hossein-SmartCar/`**  
  Firmware for the **Safety Node** (Responsible for TPMS monitoring, obstacle flags, and emergency alert transmissions).
* **`Parinaz-SmartCar/`**  
  Firmware for the **Environment Node** (Manages ambient temperature, light sensors, and PWM-based lighting automation).
* **`Mahdi-SmartCar/`**  
  Firmware for the **Status Node** (Tracks critical vehicle telemetry including current speed and battery state of charge).
* **`Sobhan-SmartCar/`**  
  Firmware for the **AI Node** (Implements real-time computer vision/obstacle avoidance workflows, utilizing `TinyML`).

### 📊 External Interfaces
* **`SmartCar-Dashboard/`**  
  Frontend web application and telemetric dashboard for remote monitoring of the smart vehicle's data.

---

## 🔄 Distributed Simulation Setup (COMPIM)

To run the simulation smoothly without encountering the *"Simulation is not running in real time"* error:
1. Install a Virtual Serial Port Driver (e.g., **VSPD** or **com0com**).
2. Create virtual COM port pairs (e.g., `COM1 ↔ COM2`, `COM3 ↔ COM4`, etc.).
3. Open the distributed schematics inside the `SmartCar_Compim_Communication/` folder.
4. Configure the **COMPIM** blocks in each Proteus instance to point to the respective virtual cross-over COM ports matching your baud rate settings.
5. Run the instances simultaneously to observe the fully integrated system behavior.

---

## 🚀 Setup and Cloning Instructions (Important)

Since this project relies on multiple Git Submodules, you must clone it recursively to ensure all sub-node firmwares are downloaded automatically.

### 1. Correct way to clone the project:
```bash
git clone --recursive <repository_link>