# BMS Project – Design Assumptions

## 1. Hardware Assumptions
- The system uses an ESP32 microcontroller.
- Four battery cells are monitored independently.
- Voltage inputs are connected to ESP32 ADC pins.
- A relay is used for battery protection control.
- A buzzer provides audible fault alerts.
- A 16x2 I2C LCD displays battery information.
- Relay feedback is monitored through a separate ESP32 input.

## 2. Voltage Measurement Assumptions
- ADC resolution is assumed to be 12-bit (0–4095).
- ESP32 ADC reference voltage is treated as approximately 3.3 V for simulation calculations.
- A voltage scaling factor is used to estimate cell voltage.
- Battery voltage thresholds are defined in the source code.
- Simulation readings represent the modeled battery inputs and not calibrated laboratory measurements.

## 3. Software Assumptions
- The firmware is developed using Arduino C++.
- Wokwi is used for circuit simulation and functional testing.
- Blynk IoT is used for cloud telemetry and dashboard visualization.
- The system uses non-blocking timing for periodic monitoring.
- Wi-Fi connectivity is provided through the Wokwi simulation environment.

## 4. Fault Handling Assumptions
- Zero or very low readings can indicate a disconnected sensor.
- ADC readings that remain unchanged under suitable test conditions may indicate a frozen ADC.
- Relay feedback is used to identify differences between commanded and observed relay states.
- System modes include NORMAL, DEGRADED, FAILSAFE and SHUTDOWN.

## 5. Limitations
- Wokwi simulation does not replace physical battery testing.
- Actual ADC accuracy depends on hardware calibration and input circuitry.
- Battery temperature monitoring and real-world electrical protection require additional hardware validation.
- Cloud dashboard operation depends on network availability.

## Conclusion
These assumptions define the operating conditions and limitations considered during the design and simulation of the ESP32-based Battery Management System.
