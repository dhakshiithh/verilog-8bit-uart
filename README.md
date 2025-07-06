# ⚡ 8-bit UART Implementation in Verilog

This project implements a simple **8-bit UART (Universal Asynchronous Receiver Transmitter)** supporting asynchronous serial communication with **1 start bit, 8 data bits, and 1 stop bit**. It includes modular transmitter and receiver designs along with a baud rate generator.

---

## 📂 Modules

- `Uart8.v`: Top-level UART module
- `Uart8Transmitter.v`: Transmitter state machine
- `Uart8Receiver.v`: Receiver state machine
- `BaudRateGenerator.v`: Generates baud rate enable pulses
- `UartStates.vh`: State definitions header

---

## ⚙️ Features

- Configurable baud rate using clock prescaler
- Separate TX and RX modules with independent state machines
- Framing error detection for invalid start/stop bits
- Fully synthesizable clean Verilog design

---

## 🧪 Simulation (Icarus Verilog)

```bash
# Compile
iverilog -o uart_tb Uart8.v Uart8Transmitter.v Uart8Receiver.v BaudRateGenerator.v UartStates.vh Uart8_tb.v

# Run
vvp uart_tb

# View waveform
gtkwave dump.vcd
