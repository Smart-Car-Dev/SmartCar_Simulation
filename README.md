# Smart Car Network Simulation System

This repository serves as the central core and simulation platform for the Smart Car project. The hardware circuit is designed using **Proteus**, while the firmware for the STM32 microcontroller is developed in a separate repository and integrated into this workspace as a **Git Submodule**.

---

## 🛠 Project Structure

- `SmartCar_Simulation.pdsprj`  
  Main Proteus hardware simulation file.

- `Hossein-SmartCar/`  
  Submodule containing firmware for the safety system and TPMS.

---

## 🚀 Setup and Cloning Instructions (Important)

Since this project includes Git Submodules, you must clone it recursively to obtain the full project with all dependencies.

### Correct way to clone:

```bash
git clone --recursive <repository_link>