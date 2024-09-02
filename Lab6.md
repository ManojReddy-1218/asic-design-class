# Conversion of TL-Verilog to Verilog with Sandpiper: Simulation and Waveform Analysis

## Aim

This project demonstrates the comparison of RISC-V pre-synthesis simulation outputs using Icarus Verilog, GTKWave, and Makerchip. The RISC-V processor is initially designed using TL-Verilog in the Makerchip IDE. To implement the design on an FPGA, it is first converted to Verilog using the Sandpiper-SaaS compiler. Pre-synthesis simulations are then performed using the Icarus Verilog and GTKWave tools.

## Prerequisites

Before beginning, ensure that you have the following tools and libraries installed on your system:
- **Python**: Version 3
- **Python3-venv**: For creating isolated Python environments
- **pip**: Python package installer
- **Git**: Version control system
- **Icarus Verilog**: Open-source Verilog simulator
- **GTKWave**: Waveform viewer
- **Docker**: For containerization support
- **Sandpiper-SaaS**: TL-Verilog to Verilog compiler

## Step-by-Step Process

Follow these steps to set up and run the RISC-V pre-synthesis simulation:

1. **Install Required Packages**:

First, install the necessary packages and tools on your system. Run the following commands:

 ```bash
    sudo apt update
    sudo apt install -y make python python3 python3-pip git iverilog gtkwave docker.io
    sudo chmod 666 /var/run/docker.sock
    sudo apt-get install python3-venv
 ```

2. **Set Up Python Environment**:

Set up a Python virtual environment and install the required Python packages:

 ```bash
    cd ~
    python3 -m venv .venv
    source ~/.venv/bin/activate
    pip install pyyaml click sandpiper-saas
 ```

3. **Clone the Repository**:                                                                                                                                      

Clone the VSDBabySoC repository into your home directory:

```bash
    git clone https://github.com/manili/VSDBabySoC.git
 ```

4. **Replace TL-Verilog File**:                                                                                                                              

Replace the existing `.tlv` file in the `VSDBabySoC/src/module` directory with your custom RISC-V `.tlv` file. This file should contain the RISC-V processor design that you want to simulate.

5. **Navigate to the Project Directory**:

 Change your working directory to the cloned repository:

```bash
    cd VSDBabySoC
 ```

6. **Convert TL-Verilog to Verilog**:

Use the Sandpiper-SaaS compiler to convert your TL-Verilog design into Verilog:

 ```bash
    sandpiper-saas -i ./src/module/*.tlv -o rvmyth.v --bestsv --noline -p verilog --outdir ./src/module/
  ```

7. **Create Pre-Synthesis Simulation File**:

Run the following command to create the `pre_synth_sim.vcd` file, which is necessary for simulation:

 ```bash
    make pre_synth_sim
 ```

8. **Compile and Simulate RISC-V Design**:

Compile the Verilog files and run the simulation using Icarus Verilog:

```bash
    iverilog -o output/pre_synth_sim.out -DPRE_SYNTH_SIM src/module/testbench.v -I src/include -I src/module
 ```

9. **Run the Simulation Output**:

Navigate to the output directory and execute the simulation output file to generate the waveform:

 ```bash
    cd output
    ./pre_synth_sim.out
 ```

10. **View Simulation Results with GTKWave**:

 Use GTKWave to view the waveform of the simulation results:

```bash
    gtkwave pre_synth_sim.vcd
```

11. **Analyze the Waveforms**:

 Use GTKWave to analyze the output waveforms. Compare different runs to verify the functionality and performance of your RISC-V processor design.
 
###  GTKWave Output Waveform

![verilog](https://github.com/user-attachments/assets/6d55c95a-8b6a-4d95-9525-1ccf3eb38f6d)


### Comparison of Output Waveforms

![output](https://github.com/user-attachments/assets/4906dfef-0bef-4924-96e1-000252e1a699)


## Conclusion
The waveform outputs from GTKWave and Makerchip matched perfectly, validating the RISC-V processor design's accuracy and consistency. This alignment confirms that the design of RISC-V core processor is robust.
