# Quantum Random Number Generator (QRNG)

A high-performance quantum random number generator implemented using Cirq, featuring optimized parallel quantum circuits for generating true random numbers with exceptional statistical properties.

## Overview

This project implements a quantum random number generator using parallel quantum circuits, optimized through extensive benchmarking to achieve both high performance and excellent statistical quality. The implementation uses Google's Cirq framework and achieves true randomness through quantum mechanical properties.

## Key Features

- **Optimized Parallel Processing**: Uses  parallel quantum circuits for optimal performance
- **High Statistical Quality**: Achieves p-value of 0.9627 and maximum deviation of 1.05%
- **Efficient Generation**: Produces 681+ digits per second
- **Quantum Circuit Design**: Implements a proven pattern of Hadamard and CZ gates
- **Comprehensive Benchmarking**: Includes tools for performance and statistical analysis

## Circuit Design

The quantum circuit employs a specific pattern for each digit generation:
```
(n, 0): ───H───@───────────M('digit_n')───
               │           │
(n, 1): ───H───@───@───────M──────────────
                   │       │
(n, 2): ───H───────@───@───M──────────────
                       │   │
(n, 3): ───H───────────@───M──────────────
```

Key circuit elements:
- Hadamard (H) gates for quantum superposition
- Controlled-Z (CZ) gates for quantum entanglement
- Measurement (M) operations for collapsing quantum states

## Performance Metrics

Statistical quality metrics from optimal configuration (9 parallel digits):
- Generation Rate: 681.07 digits/second
- P-value: 0.9627
- Chi-square: 3.0400
- Maximum Deviation: 1.05%

Distribution Analysis:
```
Digit 0: +0.15%  |  Digit 5: -0.25%
Digit 1: +0.25%  |  Digit 6: -1.05%
Digit 2: +0.15%  |  Digit 7: +0.15%
Digit 3: -0.05%  |  Digit 8: +0.10%
Digit 4: +0.10%  |  Digit 9: +0.45%
```

## Requirements

- Python 3.7+
- Cirq
- NumPy
- SciPy
- Matplotlib

## Installation

```bash
# Clone the repository

# Install dependencies
pip install cirq numpy scipy matplotlib
```

## Benchmarking Tools

The project includes comprehensive benchmarking tools for:
- Parallel scaling analysis
- Statistical quality testing
- Distribution uniformity checking
- Performance optimization

## Implementation Details

### Circuit Implementation
- Each digit uses 4 qubits
- Quantum gates: Hadamard (H) and Controlled-Z (CZ)
- Measurement-based random number extraction
- Rejection sampling for uniform distribution

### Optimization Features
- Parallel quantum circuit execution
- Optimized gate sequences
- Efficient measurement handling
- Statistical validation
