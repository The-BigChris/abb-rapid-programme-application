# ABB RAPID Drawing Application - RobotStudio Simulation

## Project Overview

This project implements a modular ABB RAPID program developed in RobotStudio to simulate automated drawing of geometric shapes and text using a pen-based TCP on a planar work surface.

The system demonstrates structured robotic motion planning, proper coordinate system referencing, and controlled motion blending using zonedata and velocity parameters.

---

## Demonstration

## Simulation Video

Full simulation demonstration available in the `video/` folder.

---

## Features

- Modular RAPID procedures for:
  - Square
  - Circle
  - D-shape
  - SALFORD text
  - Custom name drawing
- FlexPendant user interface using `TPReadFK`
- Proper Tooldata configuration (TCP, mass, center of gravity)
- WorkObject referencing for sheet alignment
- Coordinated motion planning using:
  - `MoveJ`
  - `MoveL`
  - `MoveC`
- Zonedata blending (`fine`, `z10`, `z50`)
- Controlled velocity (`v100`) for drawing stability

---

## Motion Strategy

**MoveJ** was used for repositioning and safe approach movements where strict TCP path control was not required.

**MoveL** was used for all straight stroke segments to ensure linear and precise pen motion.

**MoveC** was implemented for circular and curved geometry to generate smooth arc trajectories.

---

## Coordinate System Design

- **Base Frame**: Global robot reference
- **Tool Frame (TCP)**: Defined at the pen tip for accurate drawing contact
- **WorkObject Frames**: Separate workobjects were defined for shapes and text to maintain spatial accuracy and modularity

---

## ZONEDATA Usage

- `fine` used for sharp corners and exact stopping points
- `z10` used for smooth curved transitions
- `z50` used for non-critical repositioning movements

---

## Technical Stack

- ABB RobotStudio
- RAPID Programming Language
- Virtual Controller
- Industrial Robot Model: ABB IRB 1200

---

## Lessons Learned

- Importance of accurate TCP calibration
- Differences between joint and linear motion paths
- Effect of zonedata blending on stroke smoothness
- Role of WorkObjects in task flexibility
- Structured modular programming improves scalability

---

## Repository Structure

```
abb-rapid-programme-application/
│
├── README.md
├── LICENSE
├── rapid/
│   └── RapidProgrammeCode.mod
├── screenshots/
├── video/
```

---

## Author

Developed as part of MSc Robotics & Automation practical work in ABB RobotStudio.
