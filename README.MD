# RISC-V CPU Series — XH-1

Welcome to the initial documentation for the **XH-series**, a family of custom processors based on the **RISC-V instruction set architecture (ISA)**.

The XH-series is a planned family of **four processors**, beginning with **XH-1**, a custom **128-core RISC-V CPU** currently in the research and development phase.

The XH-series is being developed as an exploration into large-scale processor architecture, multicore design, parallel execution, and the practical implementation of a high-core-count RISC-V system. XH-1 serves as the foundation of the series and will establish many of the architectural concepts, design methodologies, and engineering principles that may influence the processors that follow.

The remaining processors — **XH-2, XH-3, and XH-4** — will be developed after sufficient research and experience has been gained from XH-1.

---

## What is the XH-Series?

The **XH-series** is a family of custom RISC-V processors designed around the idea of building increasingly capable and sophisticated multicore CPUs.

The first processor in the series, **XH-1**, is designed around a **128-core architecture**. Rather than being a conventional single-core processor or a small multicore system, XH-1 is intended to investigate the challenges involved in coordinating a large number of CPU cores within a single processor design.

The series will explore areas such as:

* High-core-count CPU architecture
* RISC-V ISA implementation
* Parallel execution
* Multicore organization
* Inter-core communication
* Memory hierarchy design
* Cache architecture
* Core-to-core synchronization
* Hardware scheduling and coordination
* Interrupt handling
* Shared and distributed resources
* On-chip communication
* Verification of large multicore systems
* FPGA and/or hardware implementation
* Performance scaling
* Future CPU architectural extensions

The exact implementation of these components is still being researched and will be documented as the XH-1 architecture matures.

---

# XH-1

**XH-1 is the first processor in the XH-series and the foundation for all future development.**

At its core, XH-1 is a **custom 128-core RISC-V CPU**.

The processor is intended to demonstrate and investigate how a large number of RISC-V cores can operate together as a single coherent processing system.

Instead of focusing exclusively on increasing the complexity of an individual CPU core, XH-1 places significant emphasis on **scaling the number of cores** and understanding the architectural problems that emerge when many processing units must work together.

### Core Count

**XH-1: 128 CPU cores**

The 128 cores are intended to operate as part of a unified processor architecture, with the exact organization of the cores, memory system, interconnect, caches, and other shared resources being defined during the research phase.

The core count is one of the defining characteristics of XH-1 and provides the basis for much of the project's architectural research.

---

# Why 128 Cores?

Modern computing workloads increasingly benefit from parallel execution. While increasing the performance of a single CPU core remains important, there are fundamental architectural and practical limits to continuously increasing single-thread performance.

A high-core-count design approaches the problem from another direction: instead of relying entirely on one extremely powerful execution engine, the processor provides a large number of independent processing units capable of executing work concurrently.

With **128 cores**, XH-1 is intended to explore questions such as:

* How should 128 cores be organized?
* How should the cores communicate?
* How should memory be shared between them?
* How can contention for shared resources be minimized?
* How should interrupts be distributed?
* How should synchronization be handled?
* How does performance scale as additional cores are enabled?
* What types of workloads benefit most from the architecture?
* What bottlenecks emerge when moving from a small multicore system to a much larger one?

These questions are central to the research behind XH-1.

---

# RISC-V

The XH-series uses **RISC-V** as its underlying instruction-set architecture.

RISC-V provides an open and extensible ISA foundation upon which the XH-series can build its own processor implementations.

This allows the project to concentrate on the architecture and implementation of the CPU itself while retaining compatibility with the broader RISC-V ecosystem where appropriate.

The exact RISC-V ISA configuration used by XH-1 will be documented as the design is finalized. This includes the supported base ISA, extensions, privilege levels, and any implementation-specific features.

If the XH-series introduces custom instructions or extensions, they will be documented separately and clearly distinguished from standard RISC-V functionality.

---

# Multicore Architecture

One of the primary research areas of XH-1 is the organization of its **128 processing cores**.

A processor with this many cores introduces substantially different design considerations compared with a conventional 2-, 4-, or 8-core CPU.

The architecture must account for communication and resource sharing between a large number of independent execution units.

Areas of particular interest include:

### Core Organization

The physical and logical organization of the 128 cores will determine how efficiently they can communicate and access shared resources.

The final architecture may organize cores into groups, clusters, tiles, or another structure depending on the results of the research.

### Interconnect

A high-core-count processor requires an efficient method for moving information between cores and shared components.

The interconnect is therefore a critical part of XH-1.

The design will investigate how requests, responses, interrupts, synchronization operations, and memory transactions can move through the processor without creating unnecessary bottlenecks.

### Memory System

With 128 cores potentially executing simultaneously, memory bandwidth becomes a significant architectural consideration.

The XH-1 memory system will therefore be designed with scalability in mind.

Documentation will cover areas such as:

* Memory hierarchy
* Caches
* Cache coherency
* Shared memory
* Memory controllers
* Memory bandwidth
* Access latency
* Atomic operations
* Synchronization
* Memory ordering

The exact implementation will be documented once these components have been finalized.

---

# Parallelism

The primary advantage of a 128-core processor is the amount of potential parallelism it provides.

In an ideal workload, many independent operations could execute simultaneously across different cores. In practice, however, achieving useful scaling requires careful consideration of dependencies, synchronization, memory access, scheduling, and communication overhead.

XH-1 will therefore investigate not only the number of available cores, but also how effectively those cores can be utilized.

Performance measurements will eventually be used to evaluate questions such as:

* How efficiently does the system scale with additional cores?
* What workloads benefit from large-scale parallelism?
* Where do synchronization bottlenecks occur?
* How much overhead is introduced by inter-core communication?
* How does memory contention affect scaling?
* At what point does adding additional parallel execution provide diminishing returns?

---

# Design Goals

The exact goals of XH-1 may evolve throughout the research phase, but the initial objectives include:

### 1. Build a 128-Core RISC-V Processor

The primary objective is to develop a functional processor containing **128 RISC-V CPU cores**.

### 2. Explore Scalable Multicore Architecture

XH-1 is intended to investigate architectures that remain practical as the number of cores increases.

### 3. Establish the XH Architecture

The first processor will establish the architectural foundation from which the remaining XH processors can evolve.

### 4. Develop a Verifiable Design

A large multicore processor introduces a significant verification challenge. XH-1 will therefore place substantial emphasis on simulation, testing, and verification.

### 5. Identify Architectural Bottlenecks

The project will be used to identify limitations in interconnects, memory systems, synchronization mechanisms, and other parts of the architecture.

### 6. Create a Foundation for Future CPUs

The lessons learned from XH-1 will inform the design of XH-2, XH-3, and XH-4.

---

# Research Areas

Development of XH-1 may involve research across several areas of computer architecture.

## CPU Core Design

Each of the 128 cores requires a processor implementation capable of executing the selected RISC-V instruction set.

Research may include:

* Datapath design
* Register files
* ALUs
* Control logic
* Instruction decoding
* Branch handling
* Pipeline design
* Exceptions
* Interrupts
* Atomic operations
* Privileged execution

## Cache and Memory Architecture

The memory hierarchy is especially important in a 128-core processor.

Research will consider:

* L1 caches
* Higher-level caches
* Cache coherency
* Shared memory
* Memory ordering
* Memory bandwidth
* Latency
* Contention
* Atomic memory operations

## Inter-Core Communication

The cores must be able to communicate and coordinate efficiently.

This includes research into:

* Core-to-core messaging
* Shared memory
* Synchronization primitives
* Interrupt delivery
* Interconnect topology
* Request routing
* Arbitration
* Congestion

## Verification

Verification becomes increasingly difficult as system complexity increases.

XH-1 will therefore require testing at multiple levels:

1. Individual instruction verification
2. Individual core verification
3. Multicore subsystem verification
4. Memory-system verification
5. Interconnect verification
6. Full 128-core system verification

The verification methodology will be documented alongside the processor implementation.

---

# XH-Series Roadmap

The initial XH-series consists of four planned processors:

| Processor | Core Count | Status                    | Role                                  |
| --------- | ---------: | ------------------------- | ------------------------------------- |
| **XH-1**  |    **128** | 🔬 Research & Development | Foundation of the XH-series           |
| **XH-2**  |        TBD | ⏳ Planned                 | Future-generation processor           |
| **XH-3**  |        TBD | ⏳ Planned                 | Future-generation processor           |
| **XH-4**  |        TBD | ⏳ Planned                 | Final processor of the initial series |

The specifications of XH-2 through XH-4 have intentionally not been fixed at this stage.

The architecture of each future processor will be influenced by the findings from the previous generation. This means that the XH-series roadmap is evolutionary rather than being a rigid set of predetermined specifications.

---

# Current Development Status

> **XH-1 is currently in the research and development phase.**

The architecture is subject to change.

At this stage, documentation may describe proposed designs, experimental concepts, or research directions rather than finalized hardware.

To avoid confusion, documentation will distinguish between different stages of implementation:

* **Proposed** — under consideration
* **Research** — currently being investigated
* **Experimental** — being tested
* **Implemented** — present in the design
* **Verified** — tested and confirmed
* **Deprecated** — no longer part of the intended design
* **Planned** — intended for future development

A feature should not be considered part of the final XH-1 specification unless it has been explicitly marked as such.

---

# Documentation

This repository is the central documentation repository for the XH-series.

Documentation will cover both the **individual CPU cores** and the **system as a whole**.

As development progresses, the repository may contain documentation covering:

```text
XH-Series
│
├── Architecture
│   ├── ISA
│   ├── Privilege Model
│   ├── Registers
│   └── Memory Model
│
├── XH-1
│   ├── CPU Core
│   ├── 128-Core Organization
│   ├── Pipeline
│   ├── Cache System
│   ├── Memory System
│   ├── Interconnect
│   ├── Interrupt System
│   └── Verification
│
├── XH-2
│
├── XH-3
│
└── XH-4
```

The structure is expected to evolve as the project becomes more mature.

---

# Project Philosophy

XH-1 is not intended to be merely a collection of CPU cores.

The primary challenge is building a **coherent processor around 128 cores**.

A design containing many cores can theoretically provide substantial parallel processing capability, but core count alone does not determine performance. The architecture surrounding those cores — particularly the memory system, interconnect, synchronization mechanisms, and resource management — plays a major role in determining how effectively the cores can be utilized.

For this reason, XH-1 treats the processor as a complete system rather than focusing exclusively on the individual CPU core.

The project will prioritize:

* Scalability
* Modularity
* Verifiability
* Clear architectural boundaries
* Reproducibility
* Documentation
* Measurable performance
* Iterative development

---

# Future Development

Once XH-1 has reached a sufficiently mature state, the project will move toward the next generation of the XH-series.

The transition to XH-2 will be informed by the practical experience gained from building the 128-core XH-1 system.

This may include improvements to:

* CPU core performance
* Core organization
* Cache hierarchy
* Memory bandwidth
* Interconnect performance
* Synchronization
* Power efficiency
* Verification
* Software support
* Scalability

The same process will continue through XH-3 and XH-4.

The intention is for each processor to represent a meaningful step forward rather than simply being a minor revision of the previous design.

---

# Summary

**XH-1 is the first processor in the XH-series: a custom 128-core RISC-V CPU currently in research and development.**

The project focuses on the design and implementation of a large-scale multicore processor, with particular attention given to scalability, parallel execution, memory architecture, inter-core communication, and verification.

XH-1 will establish the foundation for the three processors that follow.

The long-term goal of the XH-series is to explore how a custom RISC-V architecture can evolve across multiple generations while addressing the increasingly complex challenges associated with high-performance, high-core-count processor design.

**XH-1 is where the XH-series begins — 128 cores, one architecture, and a foundation for everything that follows.**

