# Tilt Sensor-Based Suitcase Lift Alarm System

A compact, low-cost, microcontroller-free anti-theft alarm system designed to detect unauthorised luggage movement using a tilt sensor, transistor-based switching circuit, and audible and visual indicators. The project includes circuit simulation using NI Multisim and custom single-layer PCB design.

## Overview

The security of personal luggage is an important concern in public places, where unauthorised lifting or movement can go unnoticed. Conventional mechanical locks restrict access but do not provide immediate alerts when luggage is moved.

The Tilt Sensor-Based Suitcase Lift Alarm System addresses this problem by detecting changes in suitcase orientation and activating an audible and visual warning. The system uses an SW-520D tilt sensor as the primary sensing element and a BC547 NPN transistor as the switching device to control a piezoelectric buzzer and LED indicator.

Unlike microcontroller-based security systems, this design relies on discrete electronic components and a transistor-based switching circuit, keeping the implementation simple and cost-effective.

The project covers circuit design, simulation, sensor calibration, PCB layout, and hardware validation.

## Problem Statement

Personal luggage can be vulnerable to unauthorised lifting or movement in crowded environments such as railway stations, airports, waiting areas, and public transport. Mechanical locks alone cannot alert the owner when a suitcase is moved.

The objective is to develop a compact, economical electronic alarm that detects unauthorised tilting or lifting and generates an immediate local warning without requiring a microcontroller or software-based control.

## Proposed Solution

A tilt-sensor-based alarm circuit that detects changes in luggage orientation and activates a piezoelectric buzzer and LED through a BC547 transistor switching stage. The circuit is simulated in NI Multisim and complemented by a custom single-layer PCB layout featuring organised component placement, 45° trace routing, and a copper ground pour.

The design aims to provide a portable, low-cost luggage security solution using basic electronic components.

## Key Features

- **Tilt-Based Movement Detection:** Uses an SW-520D tilt sensor to detect changes in orientation.
- **Microcontroller-Free Operation:** Implements hardware-based sensing and transistor switching without programmable controllers.
- **Audible Alert:** A piezoelectric buzzer provides a warning when the alarm is triggered.
- **Visual Indication:** An LED provides a visual indication of alarm activation.
- **Transistor-Based Switching:** Uses a BC547 NPN transistor to control the output devices.
- **Circuit Simulation:** Enables circuit-level verification and troubleshooting using NI Multisim.
- **Custom PCB Design:** Includes component placement, trace routing, grounding, and board layout.
- **Portable Power Supply:** Designed to operate from a 9 V battery.
- **Sensitivity Calibration:** Allows adjustment of the tilt sensor module's sensitivity, where supported by the module.

## Project Preview

### Circuit Schematic

<img width="631" height="333" alt="DOC-20260612-WA0012 pdf (1)" src="https://github.com/user-attachments/assets/420d04e4-eb64-45ab-a0c1-9935fbf0d7c9" />


*Figure 1: Circuit schematic of the tilt sensor-based alarm system.*

### NI Multisim Simulation

![NI Multisim simulation](images/multisim-simulation.png)

*Figure 2: Circuit simulation and verification in NI Multisim.*

### PCB Layout

<img width="1066" height="656" alt="WhatsApp Image 2026-09-20 at 7 52 04 PM (1)" src="https://github.com/user-attachments/assets/786c9d2a-e89c-4e8f-a25d-0d5c25be88c6" />

*Figure 3: Custom single-layer PCB layout.*

### PCB 3D View

<img width="1200" height="795" alt="WhatsApp Image 2026-09-20 at 7 52 04 PM" src="https://github.com/user-attachments/assets/20a3ccc3-f631-42fa-a0c1-64fa9c2c2ce3" />

*Figure 4: Three-dimensional PCB view.*


## Technology Stack

| Component | Technology / Tool |
|---|---|
| Sensing | SW-520D tilt sensor |
| Switching | BC547 NPN transistor |
| Audible output | Piezoelectric buzzer |
| Visual output | LED indicator |
| Passive components | Resistors |
| Power supply | 9 V battery |
| Circuit simulation | NI Multisim |
| PCB design | PCB design software used for the project |
| PCB implementation | Single-layer PCB layout |
| Design techniques | Component placement, track routing, copper ground pour |
| Version control | Git and GitHub |

## System Architecture

The system follows a hardware-based sensing and switching architecture.

```text
          9 V Battery Supply
                  |
                  v
           Power Switch
                  |
                  v
         SW-520D Tilt Sensor
                  |
                  v
       Transistor Biasing Network
           (R1 and R2)
                  |
                  v
          BC547 Transistor
           Switching Stage
                  |
             +----+----+
             |         |
             v         v
       Piezo Buzzer   LED
        Audio Alert   Visual Alert
```

The tilt sensor responds to changes in orientation. Its output controls the transistor's switching state through the biasing network, enabling the buzzer and LED to provide an alert when the triggering condition is met.

The exact switching behaviour depends on the sensor module's contact arrangement and the implemented circuit connections.

## Working Principle

### 1. Normal / Armed Condition

When the suitcase remains in its intended orientation, the tilt sensor maintains its normal electrical state. The transistor switching stage keeps the alarm outputs inactive under the configured circuit conditions.

### 2. Tilt or Lift Detection

When the suitcase is tilted beyond the sensor's effective detection threshold, the internal conductive ball changes position, altering the sensor's electrical state.

### 3. Transistor Switching

The sensor output and associated resistor network control the base drive of the BC547 transistor. The transistor switches between cutoff and conduction according to the applied base current and circuit configuration.

### 4. Audible and Visual Alert

When the switching stage activates the output devices, the piezoelectric buzzer produces an audible warning, and the LED illuminates to indicate detected movement.

### 5. Return to Normal Position

The alarm responds to the sensor's restored state according to the circuit configuration. In the implemented non-latching design, the alert may stop when the suitcase returns to its normal orientation.

**Note:** The SW-520D is a ball-type tilt switch, and its effective triggering angle depends on the particular sensor, mounting orientation, and movement direction. The actual threshold should be established through testing rather than assumed to be a fixed angle.

## Circuit Design and Simulation

The circuit was designed around the SW-520D tilt sensor and BC547 transistor switching stage.

NI Multisim was used to model and examine the circuit connections before physical implementation. Simulation and circuit inspection supported troubleshooting of the switching stage and output connections.

The main circuit elements include:

- SW-520D tilt sensor for movement detection.
- BC547 NPN transistor for switching control.
- R1 and R2 for transistor biasing, according to the circuit design.
- LED and its current-limiting resistor for visual indication.
- Piezoelectric buzzer for audible indication.
- Power switch and battery connections.

The simulation stage helped establish the intended circuit behaviour and identify connection issues before proceeding to hardware validation.

## PCB Design and Layout

The circuit was translated into a custom single-layer PCB layout to improve component organisation and facilitate practical implementation.

### Component Placement

- **Tilt sensor:** Positioned near the centre of the PCB and aligned with the intended horizontal reference plane to support consistent orientation-based detection.
- **Biasing resistors:** R1 and R2 were positioned close to the BC547 base connection to minimise the length of the high-impedance base trace.
- **Output components:** The LED, buzzer, and power switch were arranged near accessible board edges where practical.
- **Battery connector:** A two-pin screw terminal was positioned at the board perimeter for the 9 V supply connection.

### PCB Routing

- **45° trace routing:** Used instead of sharp 90° corners to support clean, manufacturable routing.
- **Copper ground pour:** Incorporated on the available ground region to provide a common return path and reduce ground-path impedance.
- **Compact routing:** Component placement and trace routing were arranged to keep connections clear and minimise unnecessary trace lengths.
- **Connector accessibility:** Power connections were positioned to simplify external wiring.

The PCB layout was developed with practical assembly, accessibility, and circuit reliability in mind.

## Bill of Materials (BOM)

| No. | Component | Designator | Quantity |
|---|---|---|---|
| 1 | SW-520D tilt sensor | TS1 | 1 |
| 2 | BC547 NPN transistor | Q1 | 1 |
| 3 | Biasing resistors | R1, R2 | 2 |
| 4 | LED current-limiting resistor | R3 | 1 |
| 5 | LED | LED1 | 1 |
| 6 | Piezoelectric buzzer | PZ1 | 1 |
| 7 | SPST slide switch | SW1 | 1 |
| 8 | Two-pin screw terminal | J1 | 1 |
| 9 | 9 V battery and connector | — | 1 set |

## Application Workflow

1. **Circuit Design:** Develop the schematic using the tilt sensor, transistor, resistors, buzzer, LED, and power supply.
2. **Simulation:** Model the circuit in NI Multisim and inspect the expected switching behaviour.
3. **Component Verification:** Check transistor pin configuration, sensor connections, resistor values, and output polarity.
4. **PCB Layout:** Arrange the components and complete the single-layer routing, grounding, and connector placement.
5. **Hardware Assembly:** Assemble the components on the prototype or fabricated PCB.
6. **Sensor Calibration:** Adjust the sensor module's sensitivity, if applicable, and verify its mounting orientation.
7. **Functional Testing:** Test the circuit in stationary, tilted, and restored orientations.
8. **Validation:** Observe the buzzer and LED response under different operating conditions and troubleshoot any false triggering.

## Testing and Results

The prototype was evaluated under different operating conditions to assess its response to suitcase movement.

| Test Condition | Expected / Observed Behaviour |
|---|---|
| Suitcase stationary | Alarm remains inactive under normal conditions. |
| Suitcase tilted beyond the effective threshold | Sensor state changes and the alarm activates. |
| Suitcase held in a triggering orientation | Alarm behaviour follows the sensor state and switching circuit. |
| Suitcase returned to normal orientation | Alarm returns to its normal state in the non-latching configuration. |
| Incorrect sensor orientation | Detection performance may change. |
| Excessive sensitivity | Unwanted triggering may occur and require recalibration. |

The prototype demonstrated the intended detection and alert functionality during testing. Sensor orientation, sensitivity adjustment, and transistor interfacing were important factors in achieving consistent operation.


## Applications

- Personal suitcase and travel bag security.
- Luggage monitoring in waiting areas and public transport.
- Storage boxes and portable equipment cases.
- Small cabinets and containers where movement-triggered alerts are useful.
- Educational demonstrations of sensors, transistor switching, and PCB design.

## Current Limitations

- **Orientation-based detection:** The sensor responds to changes in orientation and may not detect every form of unauthorised movement.
- **Directional sensitivity:** Detection depends on the mounting orientation and direction of movement.
- **Mechanical vibration:** Shocks or vibrations may cause unwanted triggering.
- **Local alert only:** The current design provides audible and visual alerts but does not remotely notify the owner.
- **No alarm memory:** In the non-latching configuration, the alarm may stop when the sensor returns to its normal state.
- **Power dependency:** Operation depends on the condition and voltage of the battery.
- **No quantified security guarantee:** The prototype demonstrates movement-triggered alert functionality, not resistance to all theft scenarios.

## Future Improvements

- **Alarm latching:** Add a CD4013 flip-flop or an appropriate latch circuit to retain the alarm state until manual reset.
- **Entry and exit delay:** Introduce an NE555 timer-based delay circuit to provide time for arming and disarming.
- **Vibration detection:** Integrate a piezoelectric vibration sensor or another suitable shock sensor for additional tamper detection.
- **Siren generation:** Use a dual-NE555 circuit to generate a modulated siren tone.
- **Low-battery indication:** Add a comparator-based battery monitoring circuit.
- **Tamper protection:** Include a microswitch to detect opening of the alarm enclosure.
- **Improved power management:** Evaluate lower-power components and a suitable rechargeable supply.
- **Additional sensor inputs:** Combine tilt detection with a magnetic reed switch using appropriate logic circuitry.

These improvements could expand the functionality while retaining a microcontroller-free design.

## Repository Structure

```text
tilt-sensor-suitcase-alarm/
├── README.md
├── LICENSE
├── .gitignore
├── images/
│   ├── circuit-schematic.png
│   ├── multisim-simulation.png
│   ├── pcb-layout.png
│   ├── pcb-3d-view.png
│   └── hardware-prototype.png
└── design-files/
    ├── multisim/
    ├── pcb/
    ├── gerber/
    └── bom.csv
```

The structure is illustrative. Include only files and folders that exist in the final repository.

## Getting Started

### Prerequisites

To inspect or reproduce the project, you may need:

- NI Multisim or a compatible circuit-simulation environment.
- The PCB design software used to create the layout.
- The circuit schematic and native design files.
- The electronic components listed in the bill of materials.
- A suitable 9 V supply and appropriate assembly tools for hardware testing.

### 1. Clone the Repository

```bash
git clone <YOUR_REPOSITORY_URL>
cd tilt-sensor-suitcase-alarm
```

### 2. Explore the Circuit Design

Open the schematic or Multisim project from the `design-files/multisim/` directory, if provided.

Review the sensor connections, transistor biasing network, LED current-limiting resistor, buzzer connection, and power supply before running the simulation.

### 3. Explore the PCB Layout

Open the native PCB project from `design-files/pcb/`, if provided.

Inspect component placement, routing, the copper ground pour, and the battery connector.

### 4. Fabricate and Assemble

If fabrication files are available, review the Gerber outputs and board dimensions before submitting them to a PCB manufacturer.

Assemble the components according to the final schematic and verify polarity, transistor pinout, and power connections before applying power.

### 5. Test the System

Power the circuit and test the sensor in its intended mounting orientation. Gradually tilt the assembly and observe the buzzer and LED response.

Verify normal operation, triggering behaviour, and recovery after returning the sensor to its normal position.

**Safety:** Verify the circuit's supply requirements and check for shorts before powering the PCB. Do not connect the battery until assembly and polarity checks are complete.

## Learning Outcomes

This project provided practical experience in:

- Tilt-sensor interfacing and orientation-based detection.
- NPN transistor biasing and switching.
- Resistor selection and LED current limiting.
- Circuit design and simulation using NI Multisim.
- PCB component placement and single-layer routing.
- Ground-plane design and connector placement.
- Hardware troubleshooting and sensitivity calibration.
- Translating a circuit concept into a practical electronic prototype.

## Conclusion

The Tilt Sensor-Based Suitcase Lift Alarm System demonstrates a simple approach to luggage movement detection using a tilt sensor, a BC547 transistor switching stage, and audible and visual indicators.

Combining circuit simulation with custom single-layer PCB design provided a practical opportunity to explore analogue electronics, sensor interfacing, hardware debugging, and PCB implementation. Its simple architecture and low component count make it a useful educational prototype for exploring microcontroller-free security systems.

## Acknowledgements

Developed collaboratively as an electronics project focused on circuit design, simulation, sensor interfacing, and PCB development.
