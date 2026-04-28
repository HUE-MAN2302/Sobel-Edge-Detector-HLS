# Sobel-Edge-Detector-HLS
Hardware acceleration of a Sobel Edge Filter using Xilinx Vivado HLS for Kintex-7
# Hardware-Accelerated Sobel Edge Detection 🚀

## Overview
[cite_start]This project implements a hardware-accelerated Sobel Edge Detection algorithm using **Xilinx Vivado High-Level Synthesis (HLS)**. [cite_start]By moving the computationally intensive edge detection process from a sequential CPU to dedicated FPGA hardware, this design achieves massive parallel processing and ultra-low latency suitable for real-time video feeds[cite: 3, 51].

## Key Performance Metrics
* [cite_start]**Processing Time:** ~0.67 milliseconds for a complete 256x256 image frame (approx. 1,493 FPS)[cite: 6, 152].
* [cite_start]**Resource Utilization (Kintex-7 FPGA):** Highly efficient, consuming only 7% LUTs, 3% BRAM, and 8% DSPs[cite: 6, 154].
* [cite_start]**Interface Protocol:** AXI-Stream (axis) for seamless video pipeline integration[cite: 4, 103].

## System Architecture
[cite_start]The system utilizes a 3-stage hardware pipeline[cite: 4]:
1. [cite_start]**AXIvideo2Mat:** Converts incoming AXI-Stream video into a 2D matrix[cite: 106].
2. [cite_start]**Sobel Filter:** Computes Gx and Gy gradients in a 3x3 neighborhood using parallel hardware logic[cite: 108, 109].
3. [cite_start]**Mat2AXIvideo:** Converts the processed binary edge map back into an AXI-Stream for output[cite: 114].

## Verification Flow
[cite_start]This design was rigorously verified at three levels[cite: 129]:
* [cite_start]**C Simulation:** Software mathematical proof using a custom C++ testbench without external libraries like OpenCV[cite: 125, 134].
* [cite_start]**RTL Synthesis:** Hardware translation generating Verilog/VHDL code via Vivado HLS 2019.2[cite: 145].
* [cite_start]**C/RTL Co-simulation:** Gate-level waveform verification confirming bit-accurate results and proper AXI handshaking[cite: 159, 171].

## Results
*(Insert your Before/After photo of the girl here)*
*(Insert your Blue Block Design diagram here)*

## Tech Stack
* C++ 
* [cite_start]Xilinx Vivado HLS 2019.2 [cite: 119]
* Xilinx Vivado Design Suite
* [cite_start]Target: Kintex-7 FPGA (xc7k325tffg900-2) [cite: 123]
