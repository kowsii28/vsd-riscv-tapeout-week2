# vsd-riscv-tapeout-week2
BabySoC Fundamentals &amp; Functional Modelling


📘 Week 2 — SoC Fundamentals & BabySoC
🎯 Objectives

Understand what a System-on-Chip (SoC) is and why it is used.

Identify core components of a typical SoC.

Learn about BabySoC, a minimalist learning platform.

Explore functional modelling and its role in RTL design.

Gain hands-on experience with Icarus Verilog and GTKWave for simulation.

📖 Theory / Background
🔹 1. What is a System-on-Chip (SoC)?

An SoC integrates a complete computing platform onto a single silicon die, combining:

Processing, memory, and peripherals

Bus/interconnect for internal communication

Power, clock, and reset management

Aspect	Description
Heterogeneous blocks	CPU core(s), memory subsystems, programmable logic, analog IP, peripherals (UART, SPI, GPIO, timers, etc.)
On-chip interconnect	Bus or Network-on-Chip (NoC) for low-latency data routing
Design hierarchy	Specification → Functional Model → RTL → Gate-level → Physical layout
Why SoC?	Reduces BOM cost, improves performance & power, shortens time-to-market, enables compact devices
🔹 2. Core Components of a Typical SoC
Block	Primary Role	Typical Example
CPU / Processor Core	Executes software and general-purpose compute	ARM Cortex-M0, RISC-V RV32IMC
Memory Subsystem	Stores program code, data, temporary results	SRAM, ROM, Flash, Cache, External DDR
Peripherals	Interface to external devices or internal functions	UART, SPI, I²C, GPIO, Timers, PWM, ADC/DAC
Interconnect / Bus	Routes transactions between masters & slaves	AHB/APB, Wishbone, TileLink, AXI
Debug & Trace	Inspect internal state during software development	JTAG, ETM, Serial-Wire Debug
Power Management	Clock gating, voltage scaling, power islands	PMU, DVFS controller
Reset & Clock	Stable timing and deterministic startup	PLLs, clock dividers, reset synchronizers

💡 Note: CPU typically sits at the center, connected via interconnect to memory and peripherals. High-performance memory uses fast buses; low-power I/O uses simpler buses.

🔹 3. Why BabySoC? – A Minimalist Learning Platform
Aspect	BabySoC	Typical Commercial SoC
Complexity	<10k LOC; a handful of modules (simple CPU FSM, RAM, UART, timer, bus)	Hundreds of IP blocks; millions of RTL lines
Visibility	All signals visible in GTKWave	Many nets hidden or optimized
Tool-chain	Open-source simulation (Icarus Verilog)	Often requires commercial tools
Learning focus	Functional modelling, understanding block behavior	RTL optimization, timing closure, floor-planning
Extensibility	Adding peripherals or tweaking bus requires few Verilog files	Adding features needs deep architectural changes

Key Benefits for Students:

Architectural Insight: Observe CPU ↔ bus ↔ memory ↔ peripherals in real-time.

Rapid Prototyping: Test benches run quickly with Icarus Verilog.

Verification Foundations: Stimulus generators, checkers, and coverage models are reusable.

🔹 4. The Role of Functional Modelling
Design Stage	Goal	Typical Artefacts
Specification	Define features, performance, I/O	Requirement docs, block diagrams, use-cases
Functional Modelling	Validate behavior at high level before RTL	Behavioral Verilog/SystemVerilog modules, testbenches, stimulus scripts
RTL Design	Convert functional description into synthesizable hardware	Clock-edge triggered RTL, FSMs, datapaths
Synthesis & Physical	Map RTL to gates, place & route	Gate-level netlist, floorplan, timing reports
Post-silicon	Verify silicon matches spec	Silicon bring-up, hardware debug, firmware validation

Why Functional Modelling Matters:

Fast Feedback: Runs faster than RTL simulation; exposes architectural mismatches early.

Architecture Exploration: Experiment with bus topologies, memory sizes, or peripheral protocols.

Verification Scaffolding: Testbenches can be reused for later RTL verification.

BabySoC Workflow:

Each block described behaviorally (e.g., UART echoes received bytes).

Concise Verilog testbenches drive simulation.

Signals observed in GTKWave.

Verified behavioral modules refined into synthesizable RTL.

📊 Summary

SoC integrates compute, memory, peripherals, and interconnect on a single die.

Core components: CPU, memory hierarchy, peripherals, bus, debug, power, clock/reset.

BabySoC mirrors essential SoC blocks in a small, open-source framework.

Functional modelling bridges high-level specification and RTL, enabling rapid validation and reusable verification frameworks.

Hands-on BabySoC simulation with Icarus Verilog and GTKWave provides foundational SoC design and verification experience.
