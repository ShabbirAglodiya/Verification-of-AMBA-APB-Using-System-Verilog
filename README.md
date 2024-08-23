# Verification-of-AMBA-APB-Using-System-Verilog

This repository contains the design and verification of an APB (Advanced Peripheral Bus) protocol using SystemVerilog. The design includes a simple APB slave module, a testbench for simulating and verifying the functionality, and various components such as generator, driver, monitor, and scoreboard classes to facilitate the verification process.

# Overview
APB is a low-power peripheral bus used to connect low-bandwidth peripherals to the main memory system. This repository provides an implementation of the APB slave interface and its verification environment using SystemVerilog and UVM methodology.

# Testbench Components

APB Slave (apb_s): Implements a simple APB slave that performs read and write operations. It has internal memory of 16 locations, each storing 8-bit data. It checks for address, address validity, and data validity errors.

Interface (abp_if): Defines the APB interface signals including clock, reset, address, write data, read data, and control signals.

Transaction Class: Defines a transaction object that stores the address, data, control signals, and other relevant information for a single APB transaction.

Generator Class: Randomly generates transactions to stimulate the DUT. It sends the generated transactions to the driver using a mailbox.

Driver Class: Drives the transactions onto the APB interface. It receives transactions from the generator and applies them to the DUT.

Monitor Class: Monitors the APB signals, captures transaction details, and sends them to the scoreboard for verification.

Scoreboard Class: Verifies the correctness of the transactions. It checks if the data written to the APB slave matches the data read back.

Environment Class: Instantiates and connects the generator, driver, monitor, and scoreboard classes. It manages the simulation flow including pre-test setup, test execution, and post-test checks.

# Outputs
Text Output: The simulation will output messages to the console indicating the status of the transactions, data matches, and any errors detected.

Waveform Output: A VCD file dump.vcd will be generated, which can be viewed using waveform viewers like GTKWave to visualize the signal transitions and verify the protocol behavior.
