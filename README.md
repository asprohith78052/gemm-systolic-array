# GEMM Systolic Array Matrix Multiplier

A parameterized SystemVerilog implementation of a
systolic array-based matrix multiplier for GEMM (General Matrix Multiplication).

## Overview

This project implements a parameterized systolic array architecture
designed for GEMM operations.

Systolic arrays allow data to be passed between processing elements in a
rhythmic manner, reducing repeated memory read operations and enabling
efficient matrix computations.

## Architecture

The design consists of four main components:

- **MAC Element** – Combinational Multiply-Accumulate element
- **PE Element** – Processing Element
- **DE Element** – Delay Element
- **Systolic Mesh** – Top-level mesh consisting of PEs and DEs

### High-Level Architecture

```text
              Matrix A
                 |
                 v
        +-------------------+
        |   Systolic Mesh   |
        |                   |
        | PE -> PE -> PE    |
        |  |    |    |      |
        |  v    v    v      |
        | PE -> PE -> PE    |
        |  |    |    |      |
        |  v    v    v      |
        +-------------------+
                 |
                 v
              Matrix C
```
## RTL Components

| File | Description |
|------|-------------|
| `mac.sv` | Multiply-Accumulate element |
| `pe.sv` | Processing Element |
| `de.sv` | Delay Element |
| `systolic_mesh.sv` | Top-level systolic mesh |

## Verification

The current repository contains the RTL implementation of the
parameterized GEMM systolic array.

The verification environment is not included in this repository at
present.

### Assertions

The verification includes checks for:

- Reset clearing PE accumulator outputs
- Output stability when enable is deasserted
- X/Z detection on inputs and outputs
- Reset and enable behavior during operation

## Applications

Systolic arrays can be used for computationally intensive matrix
operations such as:

- AI/ML accelerators
- Matrix multiplication
- Convolution operations
- Hardware acceleration

## Authors

- Rohith
- Guru Charan

This project was developed as a collaborative academic VLSI
design and verification project.

## License

Apache License 2.0
