# Side-Channel Timing Attacks on RSA: Implementation & Countermeasures

This repository contains the practical research-based implementation for **Track D: Cryptanalysis of Side-Channel Vulnerabilities** for the Cryptography course under the supervision of **Teacher Muhammad Talha**.

## Project Overview
While RSA is mathematically secure against traditional brute-force attacks, physical software implementations can leak critical cryptographic parameters through execution time variations. This project simulates a local timing adversary targeting a non-constant-time Square-and-Multiply modular exponentiation routine and verifies a robust **Cryptographic Blinding** countermeasure to neutralize the attack vector.

### Core Components Included
1. **Vulnerable Implementation:** Square-and-Multiply modular exponentiation algorithm with distinct conditional execution delays simulating branch timing leaks.
2. **Dynamic Defensive Layout:** Cryptographic Blinding countermeasure that injects random dynamic noise vectors to separate timing traces from key identities.
3. **Statistical Profile Engine:** High-fidelity simulation using system performance counters (`time.perf_counter()`) to capture runtime latency distributions.

---

## Technical Specifications & Parameters
- **RSA Target Keys:** $n = 3233, e = 17, d = 2753$
- **Simulation Iterations:** 50 random ciphertext executions 
- **Language Stack:** Python 3.13 
- **Key Metrics Captured:** Execution variance profiling, attack accuracy mappings, memory metrics under 34 MB footprint.

---

## Execution & Deployment Guide

### 1. Prerequisites & Environment Setup
Ensure you have Python 3 installed on your environment. To visualize the statistical evaluation charts, install the required graphing dependency using pip:
```bash
pip install matplotlib

2. Running the Core Pipeline
To execute the cryptographic simulation engine and save the benchmark profile charts, run the main file via the terminal:
python main.py

3. Expected Outputs
Upon successful execution, the script will:

Output performance runtime statistics directly to your terminal.

Display a dynamic execution latency map showcasing vulnerable spikes versus blinded noise filters.

Save a high-fidelity visual layout named side_channel_analysis.png inside your workspace directory.
