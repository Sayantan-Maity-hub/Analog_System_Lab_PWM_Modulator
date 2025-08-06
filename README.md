# BS Analog Systems Lab — Experiment 2
## Single-Ended to Differential Converter & PWM Modulator

### **Overview**
This project implements a **single-ended to differential converter** followed by a **PWM modulator**.  
The experiment demonstrates how an analog sine wave can be converted into complementary PWM signals using a triangular carrier wave.

---

### **Specifications**
- **Supply Voltage (VDD):** 5 V
- **Carrier Frequency (Ramp):** ~5 kHz
- **Input Signal:** 312.5 Hz sine wave, 1 V peak-to-peak, centered at 2.5 V
- **Output:** Complementary PWM signals (VPWM_P & VPWM_N)

---

### **Circuit Diagram**
![Circuit Schematic](https://github.com/Sayantan-Maity-hub/Analog_System_Lab_PWM_Modulator/blob/main/circuit_diagram.png)

---

### **Theory**
1. **Single-Ended to Differential Conversion**  
   - \(V_{in+}\) = input sine wave  
   - \(V_{in-}\) = inverted copy of sine wave (180° out of phase)  
   - Both signals are centered at mid-supply (2.5 V).

2. **PWM Modulation**  
   - Each signal is compared with a triangular carrier wave from Experiment 1.
   - Comparator outputs switch high when \(V_{in}\) > ramp, and low otherwise.
   - VPWM_P follows \(V_{in+}\), VPWM_N follows \(V_{in-}\) (complementary).

3. **Duty Cycle Relationship**  
   - When sine wave is high → VPWM_P pulses are wide, VPWM_N pulses are narrow.
   - When sine wave is low → VPWM_P pulses are narrow, VPWM_N pulses are wide.

---

### **Simulation Results**
![PWM Waveforms](https://github.com/Sayantan-Maity-hub/Analog_System_Lab_PWM_Modulator/blob/main/LTspice_output.png)  
- Top: \(V_{in+}\), ramp, and VPWM_P  
- Bottom: \(V_{in-}\), ramp, and VPWM_N  
- Complementary PWM is observed.

---

### **Measurement Steps**
1. **Set VDD = VIN = 5 V**.
2. Apply 312.5 Hz sine wave (same peak-to-peak as triangular wave).
3. Verify \(V_{in+}\) and \(V_{in-}\) are equal amplitude and 180° out of phase.
4. Observe VPWM_P and VPWM_N duty cycles.
5. Confirm VPWM_N duty = \(1-D\) of VPWM_P duty.
6. (Optional) Pass PWM outputs through RC filter (fc ≈ 1–2 kHz) to recover sine wave.

---

### **Author**
**Sayantan Maity**  
BS Electronics System, IIT Madras  
[LinkedIn](https://www.linkedin.com/in/sayantan-maity-b30534373/) | [GitHub](https://github.com/Sayantan-Maity-hub)
