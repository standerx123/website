# RustDog
A Rust embedded four-legged robot inspired by the STEM Dog project, controlled via a mobile app.

## Info
- **Author:** Andrei Babiciu
- **GitHub Project Link:** [link_to_github](https://github.com/)

## Description
RustDog is a four-legged walking robot built using Rust on embedded hardware. It is inspired by the open-source STEM Dog project and is controlled wirelessly through a dedicated mobile application. The robot uses servo motors to simulate natural dog-like movement, coordinated by a Raspberry Pi Pico W running Rust firmware.

## Motivation
I chose this project because I wanted to explore the world of embedded systems programming using Rust, a modern language known for its memory safety and performance. Robotics has always fascinated me, and the STEM Dog project provided a perfect mechanical blueprint to build upon. Adding a mobile app layer made the project even more interesting, combining embedded firmware, wireless communication, and mobile development into one complete system.

## Architecture

The main components of the system are:

- **Raspberry Pi Pico W** — the central microcontroller that runs the Rust firmware, controls the servos via PWM, and handles wireless communication over WiFi
- **PCA9685 PWM Driver** — receives I2C commands from the Pico W and generates PWM signals for all 8 servo motors
- **Servo Motors (x8)** — two per leg (hip and knee joints), responsible for the physical movement of the robot
- **Mobile App** — connects to the robot over WiFi and sends movement commands (walk, turn, sit, stop)
- **LiPo Battery Pack** — powers the entire system

How they connect:

```
[ Mobile App ]
      |
    WiFi
      |
[ Raspberry Pi Pico W ]  ← Rust firmware (embassy-rp)
      |
     I2C
      |
[ PCA9685 PWM Driver ]
      |
     PWM
      |
[ 8x SG90 Servo Motors ]
  FL   FR   BL   BR
(hip+knee per leg)
```

## Log

### Week 5 - 11 May
Set up the Rust embedded development environment. Configured the Raspberry Pi Pico W toolchain using `probe-rs` and `embassy-rp`. Successfully flashed a basic blink program to verify the hardware setup.

### Week 12 - 18 May
Implemented I2C communication with the PCA9685 PWM driver. Connected all 8 SG90 servo motors and wrote the basic leg movement sequences in Rust (stand, sit, single step). Tested and calibrated servo angles.

### Week 19 - 25 May
Integrated WiFi communication using the `cyw43` driver on the Pico W. Built the mobile app interface for sending movement commands. Tested the full walking sequence with real-time control from the app.

## Hardware
The robot uses a Raspberry Pi Pico W as the main microcontroller running Rust firmware. Eight SG90 micro servo motors control the four legs (two servos per leg — hip and knee). A PCA9685 16-channel PWM driver board controls all servos over I2C. The frame is 3D printed based on the open-source STEM Dog design. A 7.4V LiPo battery powers the servos, with a voltage regulator providing 3.3V to the Pico W.

### Schematics

Place your KiCAD or similar schematics here in SVG format.

### Bill of Materials

| Device | Usage | Price |
|--------|-------|-------|
| [Raspberry Pi Pico W](https://www.raspberrypi.com/documentation/microcontrollers/raspberry-pi-pico.html) | The microcontroller | [35 RON](https://www.optimusdigital.ro/en/raspberry-pi-boards/12394-raspberry-pi-pico-w.html) |
| SG90 Micro Servo x8 | Leg joints — hip and knee per leg | 96 RON (8 x 12 RON) |
| [PCA9685 PWM Driver Board](https://www.adafruit.com/product/815) | Controls all 8 servos over I2C | 25 RON |
| LiPo Battery 7.4V 2000mAh | Powers servos and microcontroller | 45 RON |
| 3D Printed Frame | Robot body and leg structure (STEM Dog design) | ~30 RON filament |
| Jumper Wires & Connectors | Internal wiring | 10 RON |

## Software

| Library | Description | Usage |
|---------|-------------|-------|
| [embassy-rp](https://github.com/embassy-rs/embassy) | Async embedded framework for RP2040 | Main firmware runtime on the Pico W |
| [cyw43](https://github.com/embassy-rs/embassy/tree/main/cyw43) | WiFi driver for the Pico W | Wireless communication with the mobile app |
| [embedded-hal](https://github.com/rust-embedded/embedded-hal) | Hardware abstraction layer for embedded Rust | Portable I2C and PWM interfaces |
| [pwm-pca9685](https://github.com/eldruin/pwm-pca9685) | Driver for the PCA9685 PWM controller | Controlling all 8 servo motors |
| [defmt](https://github.com/knurling-rs/defmt) | Logging framework for embedded Rust | Debug output over RTT during development |

## Links

1. [STEM Dog Open Source Project](https://www.instructables.com/STEM-Robot-Dog/)
2. [Embassy Rust Embedded Framework](https://embassy.dev/)
3. [Raspberry Pi Pico W Documentation](https://www.raspberrypi.com/documentation/microcontrollers/raspberry-pi-pico.html)
4. [PCA9685 PWM Driver](https://www.adafruit.com/product/815)
