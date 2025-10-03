# STM32 LED Button with Debouncing

This project uses an *STM32F103C8T6* microcontroller to control an LED using a push button.  
Debouncing is implemented using a *counter-based software method* to avoid false triggers caused by mechanical noise.

---

## 📂 Project Contents
- *STM32_Project/* → STM32CubeIDE project files (Core, Drivers, .ioc, etc.)
- *Proteus_Sim/* → Proteus simulation project files (.pdsprj)
- *Hex_Output/* → Compiled .hex file for use in Proteus
- *README.md* → Project description

---

## ⚙ How It Works
- The push button is connected to *PA0* (configured as input with Pull-up).
- The LED is connected to *PC13* (configured as output).
- The program samples the button state every 1 ms.
- A *counter* validates if the button state is stable for a threshold (e.g., 5 ms).
- When a valid press is confirmed, the LED toggles ON ↔ OFF.
- The LED stays in that state until the next valid press.

---

## 🖥 Simulation
1. Open the Proteus project file in Proteus_Sim/.
2. Load the .hex file from Hex_Output/ into the STM32 (use STM32F103C6 in Proteus).
3. Run the simulation.
4. Press the button → LED toggles.

---

## 📝 Notes
- Debouncing prevents multiple false toggles due to button bouncing.
- This implementation uses a *counter method*, which is more efficient than a fixed delay since the CPU does not remain blocked.

---

## 🔗 Resources
- [STM32F1 HAL and LL drivers documentation](https://www.st.com/resource/en/user_manual/dm00154093-description-of-stm32f1-hal-and-lowlayer-drivers-stmicroelectronics.pdf)
- [Proteus Software](https://www.labcenter.com/)