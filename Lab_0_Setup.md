# **Lab 0: Setup Instructions for Learn ExecuTorch on Arm**

## **Lab 1**

Lab 1 should ideally be completed on a Raspberry Pi 4 or 5, or similar Arm-based edge device running Linux. It can also be completed on an Arm-based Mac, however more powerful devices such as a Mac may show inverse performance results when comparing PyTorch and ExecuTorch. We perform both ahead-of-time (AOT) compilation and inference on the CPU of the hardware used.

A virtual Python environment running a Python version that supports ExecuTorch is required. It is recommended that the `learn_executorch_on_arm_setup.sh` script is used to create a virtual environment with Python 3.11.14. The script supports both aarch64 macOS and Linux.

```bash
source learn_executorch_on_arm_setup.sh
```

This script creates a virtual Python environment called `CPU_lab_venv`. Launch the Jupyter lab for Lab 1, select this virtual environment as the kernel, and run the lab.

You can launch a lab in VSCode with the Jupyter extension, or from the terminal as follows:

```bash
jupyter lab Lab_1_Transformer_Inference_ExecuTorch.ipynb
```

This will launch a browser window. 

This lab uses models from Hugging Face. If you do not already have an account, it is free to create one [here](https://huggingface.co/join).
You must create an access token [here](https://huggingface.co/settings/tokens). Click `New token`, name it, and then click `Generate token`. Copy your token to a safe place e.g., notes.

Inside your terminal, activate your virtual environment and authenticate your HF token:

```bash
source ./CPU_lab_venv/bin/activate
hf auth login
```

Enter your token when prompted.

You are now ready to start the Lab.

## **Lab 2**

Lab 1 should ideally be completed on a Raspberry Pi 4 or 5 with a PiCamera. Without a PiCamera, 90% of the lab can still be completed. You can also use similar Arm-based edge devices running Linux, or an Arm-based Mac, however more powerful devices such as a Mac may show inverse performance results when comparing PyTorch and ExecuTorch. We perform both ahead-of-time (AOT) compilation and inference on the CPU of the hardware used.

It is recommended that you utilize the `CPU_lab_venv` created for Lab 1, and you can launch using the same method as in Lab 1.

You are now ready to start the Lab.

## **Lab 3**

Lab 3 involves running ahead-of-time compilation on a CPU, but deploying to a Corstone 320 Fixed Virtual Platform (FVP). This is a simulation, running on your CPU, but simulating a Cortex-M85 microcontroller-class CPU connected in a heterogeneous system with an Ethos-U85 NPU.

You are recommended to use a Linux aarch64 or x86 device/instance or an Arm-powered MacBook. Be aware that using a MacBook will require extra steps and can be less straightforward than spinning up a Linux instance. It is **NOT** recommended to use a Raspberry Pi as the FVP simulation will likely be too intensive.

For this lab, you can use the `NPU_lab_venv` created by the `learn_executorch_on_arm_setup.sh` script. Before launching the lab, you must perform several further steps.

1. On your terminal in the base directory of this repo, activate the virtual environment and navigate to the provided `NPU_Lab_ExecuTorch/executorch` folder.
```bash
source ./NPU_lab_venv/bin/activate
cd NPU_Lab_ExecuTorch/executorch
```
2. If on Mac you must install FVPs, otherwise skip to 3 (Linux machines will install FVPs as part of the next stage, but for a Mac they must be pre-installed)
To install the FVPs on Mac - follow these [instructions](https://github.com/Arm-Examples/FVPs-on-Mac) carefully.

3. From the terminal inside the `executorch` directory, run the following two scripts:

```bash
./install_executorch.sh
./examples/arm/setup.sh --i-agree-to-the-contained-eula --enable-mlsdk-deps
```
Both scripts might take some time to install.

You are now ready to start the Lab.
