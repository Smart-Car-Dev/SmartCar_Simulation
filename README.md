# Smart Car Network Simulation System

This repository serves as the central core and simulation platform for the Smart Car project. The hardware circuit is designed using **Proteus**, while the firmware for the STM32 microcontrollers is developed in separate repositories and integrated into this workspace as **Git Submodules**.

---

## 🛠 Project Structure

- `SmartCar_Simulation.pdsprj`  
  Main Proteus hardware simulation file.

- `Hossein-SmartCar/`  
  Submodule containing firmware for the **Safety Node** (TPMS & Emergency Alerts).

- `Parinaz-SmartCar/`  
  Submodule containing firmware for the **Environment Node** (Temperature, Light Sensors, & PWM Lighting Control).

---

## 🚀 Setup and Cloning Instructions (Important)

Since this project relies on multiple Git Submodules, you must clone it recursively to ensure all sub-node firmwares are downloaded automatically.

### 1. Correct way to clone the project:
```bash
git clone --recursive <repository_link>