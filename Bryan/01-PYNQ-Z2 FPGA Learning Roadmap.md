# PYNQ-Z2 FPGA Learning Roadmap

From Basic Digital Logic to Retro Games, Hardware Acceleration, and Machine Learning

## 1. Introduction

The PYNQ-Z2 is an excellent platform for learning FPGA design, digital hardware, computer architecture, and hardware acceleration.

Unlike Arduino or ESP32 boards, which primarily execute software instructions on a processor, the PYNQ-Z2 allows you to design digital circuits that operate concurrently.

The board combines:

- Dual-core ARM Cortex-A9 processor for software applications.
- Xilinx Zynq-7020 FPGA for custom digital logic.
- 220 DSP48E1 slices for arithmetic acceleration.
- Block RAM for high-speed on-chip storage.
- HDMI, audio, Ethernet, buttons, LEDs, and expansion connectors for practical projects.

Official board information: [AMD PYNQ-Z2 Board Overview](https://www.amd.com/en/corporate/university-program/aup-boards/pynq-z2.html?utm_source=chatgpt.com)

### Learning objectives

The goal is not simply to write code that runs on an FPGA board. It is to understand how real digital hardware works.

By the end of the learning path, you should be able to design registers, counters, state machines, memory interfaces, and hardware pipelines; implement interactive games; and compare software execution with dedicated FPGA acceleration.

## 2. Recommended development environment

The primary development platform will be Windows 11.

| Software       | Purpose                                              | Download                                                                                                             |
| -------------- | ---------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------- |
| AMD Vivado     | FPGA design, synthesis, timing analysis, programming | [Official site](https://www.amd.com/en/products/software/adaptive-socs-and-fpgas/vivado.html?utm_source=chatgpt.com) |
| VS Code        | RTL source editing                                   | [Download](https://code.visualstudio.com/?utm_source=chatgpt.com)                                                    |
| Icarus Verilog | Lightweight Verilog simulation                       | [Windows installer](https://bleyer.org/icarus/?utm_source=chatgpt.com)                                               |
| GTKWave        | Viewing simulation waveforms                         | [Official site](https://gtkwave.sourceforge.net/?utm_source=chatgpt.com)                                             |
| Python         | Test automation and data analysis                    | [Download](https://www.python.org/downloads/?utm_source=chatgpt.com)                                                 |
| PYNQ           | ARM–FPGA integration and Python control              | [Official site](https://www.pynq.io/?utm_source=chatgpt.com)                                                         |

Recommended approach: Begin with Icarus Verilog and GTKWave. They allow you to complete the initial exercises without having the physical board.

Later, use Vivado to synthesize the designs, analyze FPGA resource utilization, and program the PYNQ-Z2.

## 3. Phase 1 — Learning the physical board

[TU/e PYNQ Pages](https://images.openai.com/static-rsc-4/qadTR6SxDGdvGjwS0wM6PLa0zGmqLbYaCE2uRKYReHfOTpV3cndDkYGYAYx0Vif_mpBS46eNVfaOy8mt9-ov5lc06nmVtrAlIkafmQBLZmL3XtYQ0W04LCEuGRFY_XKsXJgTQiAqBaFPq05VkvFQAp4sWlY5T1HVkaCjpgW92yM?purpose=inline)

Start with simple projects that demonstrate how FPGA logic interacts with physical components.

| Project               | Hardware           | Concepts                 |
| --------------------- | ------------------ | ------------------------ |
| Button-controlled LED | Buttons, LEDs      | GPIO, synchronous inputs |
| Binary counter        | Clock, LEDs        | Registers, counters      |
| RGB LED controller    | RGB LEDs           | PWM, clock enable        |
| Reaction timer        | Buttons, LEDs      | FSM, timers              |
| Random LED selector   | LEDs, buttons      | LFSR, state machines     |
| UART communication    | USB/UART interface | Serial protocols         |

### Recommended official tutorials

AMD/Xilinx University Program — FPGA Design Flow

[Open the FPGA Design Flow Tutorial](https://xilinx.github.io/xup_fpga_vivado_flow/?utm_source=chatgpt.com)

A practical introduction to Vivado, FPGA synthesis, implementation, constraints, and programming. Includes PYNQ-Z2-compatible exercises.

Xilinx Digital Design Tutorial

[GitHub — Digital Design Using Vivado](https://github.com/Xilinx/xup_digital_design_tutorial?utm_source=chatgpt.com)

Includes PYNQ-Z2 reference materials, constraint files, and example designs.

Official PYNQ Workshop

[GitHub — PYNQ Workshop](https://github.com/Xilinx/PYNQ_Workshop?utm_source=chatgpt.com)

Contains demonstrations of board peripherals, GPIO, overlays, Pmod interfaces, and ARM–FPGA communication.

## 4. Phase 2 — Learning FPGA through games

Games provide an enjoyable way to learn digital logic because the results are immediately visible.

[Electronic Arcade Smash-A-Mole – Mastermind Toys](https://images.openai.com/static-rsc-4/Q8-PGv4tLoCS9eklowXCmZA2X7jCcqjdVt5dkSZCvhzOZJT0w375p6s7W4HE0zgDB9noFWSqEtkdW_wjdqvzMUYcKwVekF0KWVzk8ZV7XwNi2ni4BbrKHxwWHHOS1M_WjBDxg-nW8ufVDTJYMzPLAms-zeTt907S_43KR6y2z-0?purpose=inline)

Project 1 — Whack-a-Mole

Existing PYNQ-Z2 project

Randomly illuminate one of four LEDs. The player must press the corresponding button before the timer expires.

Learn: FSM, counters, button debouncing, pseudo-random number generation.

[Download the PYNQ-Z2 Whack-a-Mole project](https://github.com/JinhenLee/XUP-PYNQ-Deep-Dive-Project?utm_source=chatgpt.com)

Start with the existing example, then rebuild the core game logic in Verilog.

[Hasbro Simon, Geschicklichkeitsspiel](https://images.openai.com/static-rsc-4/bqah7RSPNEtGD6ZlsBEb_DurQlT7MJg-lJnYfTQ8n3a2dlziuUeTHfydMZXS-z1cKx_d42tdeUFACAJkTShFuxToy4pSpPmcl87kLaUJoQuudOQQtzMV-mWyXWm87I7_L7r1WxPa3sGqHdq3rMWz22nukHaKXWWXAHtg7ZJQNBg?purpose=inline)

Project 2 — Simon Memory Game

Custom project

The board displays a sequence of colored LED flashes. The player must reproduce the sequence using the buttons.

Learn: Registers, memory arrays, FSM, timing control.

This project can be implemented entirely with the board's built-in LEDs and buttons.

[Pong, el famoso arcade que dio pie a la industria del videojuego, cumple 50 años](https://images.openai.com/static-rsc-4/gb5wqsBUth98wgClWR-sTxkWnLmNttkIFPL-zalDialTPeKL8Cmb8dXTWBvV2xM35QkO-0KZTU65qQKv-LMt_k6kgPtnpr0ye91W8z13YpGcE62V_f6Xxf0e2nAJNKmq46_f_JtdpoX-Sur42ayT0NKlYRAghwzcum3Hqy_3u-I?purpose=inline)

Project 3 — Pong

HDMI integration required

Build a two-player Pong game using the board's buttons and HDMI output.

Learn: Video timing, pixel coordinates, collision detection, counters, and parallel logic.

[GitHub — PYNQ-Z2 HDMI Output Example](https://github.com/nxquangce/pynq_z2_hdmi_out_nomem?utm_source=chatgpt.com)

First generate a test pattern, then a moving square, and finally the complete Pong game.

[How to Create a Snake Game in Minutes Using Unity | by Carol Reed | Medium](https://images.openai.com/static-rsc-4/wF3GR6z1dNz-M0apwx2by7FWOWnR2PlCkjnABtlMQH9b96HwdmrqjxVZTMFwmjreFWy6RWpsAlgUsCc9hXvAEOPBtk2k8gjvoQ-wwaFM6ZC5SgB3SEYxkSd__7M92aO9mkUTj-fxRZIyVxqRmipccYlZ4JYk4bKtevBswO0QQeg?purpose=inline)

Project 4 — Snake

FPGA game adaptation

Implement the classic Snake game with four directional buttons and HDMI output.

Learn: Memory, game-state management, collision detection, video generation.

[GitHub — FPGA Snake Game](https://github.com/IEEE-NITK/Return_Of_The_Snake?utm_source=chatgpt.com)

The reference project targets another FPGA board and uses VGA. Its game logic can be adapted to PYNQ-Z2, but the video interface must be replaced.

### Advanced gaming: Retro arcade hardware

An interesting long-term project is recreating a classic computer or arcade machine using FPGA logic.

[GitHub — BeebFpga](https://github.com/hoglet67/BeebFpga?utm_source=chatgpt.com)

BeebFpga is an FPGA implementation of the BBC Micro computer, with support for PYNQ-Z2. It is a useful example of how FPGA logic can reproduce a complete historical computer system.

Projects involving classic arcade games are significantly more complex and should be explored after becoming comfortable with memory, video timing, processors, and peripheral interfaces.

## 5. Phase 3 — Understanding Hardware Acceleration

One of the most important reasons to learn FPGA design is to understand how specialized hardware can outperform software for certain workloads.

The key concepts are:

- Parallelism: Multiple operations can execute simultaneously.
- Pipelining: Different stages process different data in the same clock cycle.
- DSP blocks: Dedicated hardware performs arithmetic efficiently.
- Memory architecture: Data movement often determines performance.
- Latency vs. throughput: Faster throughput does not always mean lower latency.

### Project 5 — FIR Filter and Matrix Multiplication

Objective: Implement the same mathematical operation using ARM software and FPGA hardware.

Compare three implementations:

1. C program running on the ARM CPU.
2. Sequential FPGA design using a shared multiplier.
3. Parallel FPGA design using multiple DSP blocks.

Measure execution time, clock cycles, throughput, LUT utilization, DSP utilization, and memory usage.

Recommended resource:

[AMD University Program — High-Level Synthesis Tutorials](https://github.com/Xilinx/xup_high_level_synthesis_design_flow?utm_source=chatgpt.com)

This repository provides PYNQ-Z2-supported HLS exercises and source files, including arithmetic and signal-processing applications.&#x20;

[image](https://www.google.com/s2/favicons?domain=https://github.com\&sz=32)

GitHub



### Project 6 — Real-Time Video Processing

[Segmentação baseada em bordas - Sobel e Canny](https://images.openai.com/static-rsc-4/xf1CPU1i8Ul4tmuOqCysYP-BihI-R5diYklBxlzWpRs9jLkUalo5oTKaQ9DnNqEC2K0ovOEZ5NPPfBjsKRmIiJnYA4WDXa8YgDwW2naXYNDvesnoQrVSDEfOY855EQg1uP36X8TYYfYT5J9iI5ASgzN4i0Bkei9NivRU3tmOIHo?purpose=inline)

Objective: Process live camera images using dedicated FPGA logic.

Example pipeline:

`Camera → Frame Buffer → FPGA Sobel Filter → HDMI Display`

A Sobel filter calculates image gradients to identify edges.

The FPGA can process pixels through a streaming pipeline instead of requiring the CPU to execute the same sequence of instructions for each pixel.

Existing PYNQ-Z2 project:

[GitHub — PYNQ-Z2 Sobel Filter with HDMI](https://github.com/aclich/PYNQ-Z2_sobel_filter_HDMI?utm_source=chatgpt.com)

The project includes hardware files and a Jupyter Notebook. Its author reports approximately 24 FPS with FPGA acceleration versus 10 FPS with OpenCV software in their demonstration. The example uses PYNQ 2.5 and Vivado 2020.1, so compatibility should be checked before rebuilding it.&#x20;

[image](https://www.google.com/s2/favicons?domain=https://github.com\&sz=32)

GitHub



### Project 7 — MNIST Handwritten Digit Recognition

[Introduction to Deep Learning](https://images.openai.com/static-rsc-4/8UHiz7yKTjL6E0H1KGfWlYrgrkOQ2P1Fd4oBcCzUjcWG3_pA9c_k3OZ3gjLYCIH_8t291Nr4GLEx8JT1y6G0-bmrLRGOfmfUHAmhhCmFzPhYUFRBhLJnMOGl9Pnbp4vFwIXmK9nmZ7k693vZCfcYqN-8SsNXFk4aqoMfnrrxFr8?purpose=inline)

Objective: Implement a small neural network using FPGA hardware.

A suggested first architecture is:

28 × 28 Input Image

Flatten — 784 Values

Dense Layer — 64 Neurons

Fixed-point Multiply + Accumulate

ReLU + Output Layer

Digit Prediction: 0–9

Begin by training a simple network in Python, then quantize its weights and implement inference using FPGA logic.

Recommended repositories:

A. [MNIST FPGA Accelerator for PYNQ-Z2](https://github.com/junwha/MNIST-FPGA-Accelarator?utm_source=chatgpt.com)

Implements a streaming neural-network accelerator using 1-bit quantization. Includes HLS source code, weights, test data, and performance-comparison notebooks. The author reports approximately 10× speedup over their NumPy implementation.&#x20;

[image](https://www.google.com/s2/favicons?domain=https://github.com\&sz=32)

GitHub



B. [Yonsei University — FPGA CNN Accelerator Labs](https://github.com/h23yonsei/fpga-cnn-accelerator-labs?utm_source=chatgpt.com)

Particularly recommended because it includes nine progressive labs, from basic Verilog through FIFO, memory, UART, AXI, Sobel filtering, and finally an MNIST CNN on PYNQ-Z2.

The repository provides RTL, self-checking testbenches, and build scripts.&#x20;

[image](https://www.google.com/s2/favicons?domain=https://github.com\&sz=32)

GitHub



C. [AMD FINN — Quantized Neural Network Acceleration](https://github.com/Xilinx/finn-examples?utm_source=chatgpt.com)

A more advanced framework for building low-precision neural-network accelerators. Consider this after understanding basic FPGA arithmetic, memory, and streaming architectures.

## 6. Suggested learning sequence

The projects are ordered by difficulty, but you do not need to complete every project before exploring something more interesting.

| Level | Project                  | Main learning objective        |
| ----- | ------------------------ | ------------------------------ |
| 1     | Buttons and LEDs         | GPIO and registers             |
| 2     | Whack-a-Mole             | Timers and state machines      |
| 3     | Simon Memory Game        | Registers and memory           |
| 4     | RGB PWM Controller       | Counters and PWM               |
| 5     | HDMI Test Patterns       | Video timing                   |
| 6     | Pong                     | Video and game logic           |
| 7     | Snake                    | Memory and collision detection |
| 8     | FIR / Matrix Accelerator | DSP and pipelining             |
| 9     | Sobel Video Accelerator  | Streaming computation          |
| 10    | MNIST Neural Network     | Quantization and hardware AI   |

## 7. Hardware and accessories

Most introductory projects require only the PYNQ-Z2 board and a Windows computer.

Additional equipment becomes useful as the projects become more advanced.

| Equipment                              | Used for                                |
| -------------------------------------- | --------------------------------------- |
| MicroSD card                           | Booting the PYNQ operating system       |
| USB cable and appropriate power supply | Programming and powering the board      |
| HDMI monitor and cable                 | Pong, Snake, video experiments          |
| USB webcam                             | Image processing                        |
| Pmod OLED                              | Small displays                          |
| Pmod joystick                          | Game controls                           |
| Pmod sensors                           | Digital interfaces and data acquisition |

Check voltage levels and connector compatibility before attaching external hardware.

Official setup and board files:

- [PYNQ Getting Started Documentation](https://pynq.readthedocs.io/en/v3.1/getting_started.html?utm_source=chatgpt.com)
- [PYNQ Operating System Images — PYNQ-Z2 under Previous Downloads](https://www.pynq.io/?utm_source=chatgpt.com)
- [Vivado Board Files and XDC Constraints](https://github.com/Xilinx/PYNQ/blob/master/docs/source/overlay_design_methodology/board_settings.rst?utm_source=chatgpt.com)

The official PYNQ Workshop was developed around PYNQ v2.6, so using the matching image may make reproducing its examples easier.&#x20;

[image](https://www.google.com/s2/favicons?domain=https://github.com\&sz=32)

Xilinx/PYNQ_Workshop · GitHub



## 8. FPGA learning communities

These communities are useful when troubleshooting, exploring new projects, or learning from other FPGA developers.

- [PYNQ Support Forum](https://discuss.pynq.io/?utm_source=chatgpt.com) — Board-specific projects, overlays, and technical support.
- [Reddit r/FPGA](https://www.reddit.com/r/FPGA/?utm_source=chatgpt.com) — FPGA design discussions and career advice.
- [element14 FPGA Community](https://community.element14.com/technologies/fpga-group/?utm_source=chatgpt.com) — Projects, tutorials, and hardware demonstrations.
- [HDLBits](https://hdlbits.01xz.net/wiki/Main_Page?utm_source=chatgpt.com) — Online Verilog practice exercises.
- [Nandland](https://nandland.com/learn-verilog/?utm_source=chatgpt.com) — Beginner-friendly Verilog lessons and videos.

For GitHub projects, open the repository and select Code → Download ZIP to obtain the available source files. Some projects also provide prebuilt bitstreams or releases. A GitHub repository does not necessarily include a ready-to-run PYNQ-Z2 image.

## 9. Final learning goal

The goal is to progress through three levels of understanding.

Level 1 — Make it work. Build circuits that interact with real buttons, LEDs, displays, and sensors.

Level 2 — Understand how it works. Explain the registers, state machines, memory, timing, and data paths inside each project.

Level 3 — Make it faster. Design parallel and pipelined hardware, measure actual performance, and understand the tradeoffs between CPU software and FPGA logic.

By the end of this roadmap, you should have experience not only with FPGA programming but also with the fundamentals of digital hardware architecture, embedded SoC design, and specialized computing accelerators.

Recommended starting point: Complete the simulation labs first, then move to Whack-a-Mole and Pong on the physical board. After those, try the FIR accelerator and the Yonsei MNIST labs. This progression combines enjoyable projects with increasingly serious hardware engineering.
