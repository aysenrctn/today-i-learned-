# 🤖 Real-Time IoT Vending System with FreeRTOS

Today, I developed a synchronized hardware simulation for a secure product delivery system using **FreeRTOS** on Arduino (Wokwi platform).

### 🚀 Technical Implementation
* **Task Management:** Implemented three concurrent tasks: 
    1. **Keypad Task:** Handles user input for the delivery code.
    2. **Validation Task:** Processes the code and checks "payment/approval" status.
    3. **Actuator Task:** Controls a Servo motor to physically dispense the product upon success.
* **Inter-Task Communication:** Used **Queues** to safely pass the entered codes between tasks without blocking the system.
* **Real-Time Reliability:** Leveraged RTOS primitives to ensure the system remains responsive even during mechanical movements.

### 💡 Insight
Using an RTOS in embedded systems transforms a linear "loop" into a robust, multi-threaded application. This approach is essential for production-grade IoT devices where timing and reliability are non-negotiable.
