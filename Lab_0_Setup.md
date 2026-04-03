# **Lab 0: Setup Instructions for Learn ExecuTorch on Arm**

## **Lab 1**

Lab 1 should ideally be completed on a Raspberry Pi 4 or 5, or similar Arm-based edge device running Linux. It can also be completed on an Arm-based Mac, however more powerful devices such as a Mac may show inverse performance results when comparing PyTorch and ExecuTorch. This is because PyTorch benefits from highly optimized CPU backends on powerful laptop/desktop-class hardware, whereas on a Raspberry Pi or other embedded/edge device, ExecuTorch’s lightweight runtime and lower overhead make it better suited to constrained CPUs, leading to improved performance and efficiency. We perform both ahead-of-time (AOT) compilation and inference on the CPU of the hardware used.

A virtual Python environment running a Python version that supports ExecuTorch is required. It is recommended that the `learn_executorch_on_arm_setup.sh` script is used to create a virtual environment with Python 3.11.14. The script supports both aarch64 macOS and Linux.

```bash
source learn_executorch_on_arm_setup.sh
```

This script creates a virtual Python environment called `CPU_lab_venv`. Launch the Jupyter lab for Lab 1, select this virtual environment as the kernel, and run the lab.

You can launch a lab in VSCode with the Jupyter extension, or from the terminal as follows:

```bash
jupyter lab Lab_1_Transformer_Inference_ExecuTorch.ipynb
```

This will output a URL, which can be entered into your browser to launch the lab.

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

Lab 2 should ideally be completed on a Raspberry Pi 4 or 5 with a PiCamera. Without a PiCamera, 90% of the lab can still be completed. You can also use similar Arm-based edge devices running Linux, or an Arm-based Mac, however more powerful devices such as a Mac may show inverse performance results when comparing PyTorch and ExecuTorch. We perform both ahead-of-time (AOT) compilation and inference on the CPU of the hardware used.

It is recommended that you utilize the `CPU_lab_venv` created for Lab 1, and you can launch using the same method as in Lab 1.

You are now ready to start the Lab.

## **Lab 3**

Lab 3 involves running ahead-of-time compilation on a CPU, but deploying to a Corstone 320 Fixed Virtual Platform (FVP). This is a simulation, running on your CPU, but simulating a Cortex-M85 microcontroller-class CPU connected in a heterogeneous system with an Ethos-U85 NPU.

You are recommended to use a Linux aarch64 or x86 device/instance or an Arm-powered MacBook. Be aware that using a MacBook will require extra steps and can be less straightforward than spinning up a Linux instance. It is **NOT** recommended to use a Raspberry Pi as the FVP simulation will likely be too intensive.

A good option is to use an Arm-based AWS instance. If you would like to use AWS, follow these steps, otherwise skip to 1:

**Launch an AWS EC2 instance**  
   - Go to Amazon EC2 and create a new instance.
   - **Select key pair**: Create a key for SSH connection (e.g., `yourkey.pem`).
   - **Choose an AMI**: Use the `Ubuntu 22.04` AMI as the operating system.
   - **Instance type**: Select `m7g.xlarge` (Graviton-based instance with Arm Neoverse cores).
   - **Storage**: Add 64 GB of root storage.

**Connect to the instance via SSH**  
   Use the following command to establish an SSH connection (replace with your instance details):
   ```bash
   ssh -i "yourkey.pem" -L 8888:localhost:8888 ubuntu@<ec2-public-dns>
   ```

For this lab, you can use the `NPU_lab_venv` created by the `learn_executorch_on_arm_setup.sh` script so make sure to run it if you have not run it on your device. Before launching the lab, you must perform several further steps.

1. On your terminal in the base directory of this repo, activate the virtual environment and navigate to the provided `NPU_Lab_ExecuTorch/executorch` folder.
```bash
source ./NPU_lab_venv/bin/activate
cd NPU_Lab_ExecuTorch/executorch
```

2. If you are using a Mac you must install FVPs, otherwise skip to 3 (Linux machines will install FVPs as part of the next stage, but for a Mac they must be pre-installed)
To install the FVPs on Mac - follow these [instructions](https://github.com/Arm-Examples/FVPs-on-Mac) carefully. Do not install the FVPs inside executorch, instead install them in a neutral directory within your workspace, separate to this repo, and ensure they are on your PATH.

3. From the terminal inside the `executorch` directory, run the following two scripts:

```bash
./install_executorch.sh
./examples/arm/setup.sh --i-agree-to-the-contained-eula 
```
Both scripts might take some time to install.

You are now ready to start the Lab.

Start Jupyter Lab by running:
```bash
jupyter lab Lab_3_Accelerating_ExecuTorch_Ethos_NPU.ipynb
```
Copy the link provided in the terminal output, open it in your local browser, and follow the instructions in the notebooks.

