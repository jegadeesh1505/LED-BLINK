
# LED-BLINK
# 💡 Experiment 01 – Interfacing a Digital Output (LED) with ARM Development Board

### 🎯 **Aim**
To interface a digital output (LED) to an ARM development board and write a blink code.

---

### ⚙️ **Components Required**
- STM32CubeIDE  
- NUCLEO ARM Development Board  

---

### 🧠 **Theory**

**ARM (Advanced RISC Machine)** is a 32-bit processor architecture developed by ARM Holdings. It is widely used in embedded systems and SoC (System-on-Chip) products. Many semiconductor companies like Samsung, Atmel, and Texas Instruments license ARM architecture to design their own SoCs.
### 🧩 **What is an ARM7 Processor?**
The **ARM7 processor** is commonly used in embedded system applications. It provides a balance between the classic ARM architecture and the newer Cortex series, offering an excellent platform for both hardware and software development.
### 🔍 **LPC2148 Microcontroller**
The **LPC2148**, developed by NXP Semiconductors (Philips), is a 16/32-bit ARM7-based microcontroller featuring a wide range of peripherals.
#### **Key Features**
- 16/32-bit ARM7TDMI-S core in LQFP64 package  
- On-chip **Flash memory**: 32 KB – 512 KB  
- On-chip **SRAM**: 8 KB – 40 KB  
- **ISP/IAP** via on-chip bootloader  
- **Embedded ICE-RT** and **Real Monitor** for real-time debugging  
- **USB 2.0** full-speed device controller with 2 KB endpoint RAM  
- **10-bit ADC** (6 or 14 channels, 2.44 μs conversion time)  
- **10-bit DAC** for analog output  
- **Timers:** Two 32-bit timers, watchdog, and PWM unit  
- **RTC** with 32 kHz clock input  
- **UARTs (2x), I²C (2x)** up to 400 kbit/s  
- **5V-tolerant GPIOs**, 21 external interrupt pins  
- **Max CPU Clock:** 60 MHz using on-chip PLL (lock time 100 µs)  
- **Crystal Frequency:** 1 MHz – 25 MHz  
- **Power modes:** Idle and Power-down with peripheral clock scaling  

---

### 🧭 **Procedure**

1. Open **STM32CubeIDE**.
 
  <img width="720" height="500" alt="Screenshot (25)" src="https://github.com/user-attachments/assets/87aa9be0-2406-4ca5-b5d1-f36a20f9f76b" />

2. Click **File → New STM32 Project**.
 
   <img width="720" height="500" alt="Screenshot (26)" src="https://github.com/user-attachments/assets/e89b4a11-bb5e-46c5-844b-2b61be7efd68" />
   <img width="720" height="500" alt="Screenshot (27)" src="https://github.com/user-attachments/assets/4f24f543-cbe5-4b8e-81ec-89ba57561b8b" />

3. Select the **target microcontroller** or board and click **Next**.

   <img width="720" height="500" alt="Screenshot (28)" src="https://github.com/user-attachments/assets/0ff62990-806f-4084-817d-fde959eb7b4c" />

4. Name the project.

   <img width="720" height="500" alt="Screenshot (29)" src="https://github.com/user-attachments/assets/2d85fc55-8d85-4fca-9516-cb95214defc0" />

5. The corresponding `.ioc` file will be generated automatically.

<img width="720" height="500" alt="Screenshot (30)" src="https://github.com/user-attachments/assets/4a3f9c80-d2f1-4e5b-9701-3c3d63624c9a" />

6. Configure the pins as **GPIO (Input/Output)**, **USART**, etc. as needed.

   <img width="720" height="500" alt="Screenshot (31)" src="https://github.com/user-attachments/assets/094c91e0-edf1-4d50-8003-09f39baf1cf5" />

7. Save the configuration (`Ctrl + S`) – the base C program will be generated automatically

   <img width="720" height="500" alt="image" src="https://github.com/user-attachments/assets/0e97cc0c-8278-437c-bbdc-5caafd0b7eaf" />
 
8. Edit the generated main program as required.
 
   <img width="720" height="500" alt="Screenshot (32)" src="https://github.com/user-attachments/assets/06a60700-25b8-42eb-b6fa-62496b777f45" />
<img width="720" height="500" alt="Screenshot (34)" src="https://github.com/user-attachments/assets/b8a10ad1-ddd4-4100-9a5c-270063dbf820" />


9. Click **Project → Build All**.
 
    <img width="720" height="500" alt="Screenshot (35)" src="https://github.com/user-attachments/assets/9e15744b-1401-4aa1-b369-831047de9728" />

10. Link the **HEX file** using the post-build process.
 
    <img width="720" height="500" alt="image" src="https://github.com/user-attachments/assets/9b123942-04e2-46d1-80ca-82339800e839" />

11. Click **Debug** and connect the **STM Nucleo Board**.
  
  <img width="720" height="500" alt="image" src="https://github.com/user-attachments/assets/a176542a-f6ba-4e7d-ae72-7f6fbb5ffd00" />

12. Click **Run** to execute the program.
    
---

### 💻 **Program**


```c
#include "main.h"

void SystemClock_Config(void);
static void MX_GPIO_Init(void);

int main(void)
{
    HAL_Init();
    SystemClock_Config();
    MX_GPIO_Init();

    while (1)
    {
        HAL_GPIO_WritePin(GPIOA, GPIO_PIN_5, GPIO_PIN_RESET);
        HAL_Delay(1000);
        HAL_GPIO_WritePin(GPIOA, GPIO_PIN_5, GPIO_PIN_SET);
        HAL_Delay(1000);
    }
}
```
---
### OUTPUT
CASE 1: LED ON 

![WhatsApp Image 2025-10-29 at 20 09 49_92cacc29](https://github.com/user-attachments/assets/060dff43-1636-4b77-9753-e163b8531683)

CASE 2: LED OFF

![WhatsApp Image 2025-10-29 at 20 09 49_27929b72](https://github.com/user-attachments/assets/78e2b94d-ba7f-4181-96a3-00568d00c53e)

---
### RESULT
Interfacing a digital output with ARM microcontroller is executed and the results are verified.

