# **Lab 0: Setup Instructions for Learn ExecuTorch on Arm**

## **Lab 1**

Lab 1 should ideally be completed on a Raspberry Pi 5/4 or similar Arm-based edge device running Linux. It can also be completed on an Arm-based Mac - however more powerful devices such as a Mac may show inverse performance results when comparing PyTorch and ExecuTorch. We perform both ahead-of-time (aot) compilation, and we run inference, on the CPU of the hardware used.

A virtual python environment running a python version that supports executorch is required. It is recommended to use the `learn_executorch_on_arm_setup.sh` script to create a venv with Python 3.11.14. The script supports both aarch64 MacOS and Linux.

```bash
source learn_executorch_on_arm_setup.sh
```

This script creates a virtual python environment called `CPU_lab_venv`. Launch the Jupyter lab for Lab 1, select this venv as the kernel, and run the lab.

You can launch a lab in VSCode with the Jupyter extension, or from the terminal as follows:

```bash
jupyter lab Lab_1_Transformer_Inference_ExecuTorch.ipynb
```

This will launch a a browser window.

## **Lab 2**

Lab 1 should ideally be completed on a Raspberry Pi 5/4 with a PiCamera. Without a PiCamera, 90% of the lab can still be completed, so you can also use similar Arm-based edge devices running Linux, or an Arm-based Mac - however more powerful devices such as a Mac may show inverse performance results when comparing PyTorch and ExecuTorch. We perform both ahead-of-time (aot) compilation, and we run inference, on the CPU of the hardware used.

It is recommended that you utilise the `CPU_lab_venv` created for Lab 1, and you can launch using the same method as in Lab 1.

## **Lab 3**

Lab 3 involves running ahead-of-time compilation on a CPU, but deploying to a Corstone 320 Fixed Virtual Platform (FVP). This is a simulation, running on your CPU, but simulating a Cortex-M85 microcontroller-class CPU connected in a heterogeneous system with an Ethos-U85 NPU.

For this lab, you can use the `NPU_lab_venv` created by the `learn_executorch_on_arm_setup.sh` script. Before launching the lab, you must perform several further steps.

- FVP install, Mac and Linux

- Clone executorch and esnure location correct and does not interfere with other labs

- install_executorch.sh

- setup.sh --i-agree-to-the-contained-eula
