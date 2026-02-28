![arm-education-logo](./Education_horizontal_violet.png)

# Learn ExecuTorch on Arm: Practical Labs Collection

Welcome to the **Learn ExecuTorch on Arm: Practical Labs Collection**! In these hands-on sessions, you will explore how PyTorch models can be exported and lowered to the ExecuTorch Runtime for more effective, lightweight, minimalist inference at the Edge. This will cover deploying to CPUs, particularly via the XNNPACK backend, for transformer-based and CNN models, before covering deployment to other hardware backends, such as the Arm Ethos-U Neural Processing Unit (NPU), understanding the TOSA IR, use of Fixed Virtual Platforms, and use of tools such as Google's Model Explorer. This is **NOT** a substitute for [official documentation](https://docs.pytorch.org/executorch/stable/index.html), but provides an accessible, supplementary entry point to learn more about ExecuTorch and get started quickly with limited background in Edge AI, providing theoretical understanding and practical implementation skills.

1) **Edge AI Inference on Arm using the ExecuTorch Runtime + XNNPACK and Kleidi AI** - CPU Inference on Raspberry Pi 5 (Arm-powered) - PyTorch vs ExecuTorch at the Edge for Transformer-based Models
- Can be completed on Raspberry Pi, or Arm-powered MacBook

2) **Efficient Image Classification Using ExecuTorch on Raspberry Pi** - CPU Inference on Raspberry Pi 5 (Arm-powered) - MobileNetV2 CNN, Quantization, and Example Application
- Can be completed on Raspberry Pi + PiCamera, or Arm-powered MacBook if not completing PiCamera section

3) **Accelerating ExecuTorch on Arm Ethos-U Neural Processing Units** - NPU Inference on Ethos-U Fixed Virtual Platform (FVP) - Understanding TOSA, Google Model Explorer
- Can be completed on Linux device (aarch64 or x86) or Arm-powered MacBook (with extra steps required for MacBook)

> Note: Regardless of hardware, all labs are executable documentation in the Jupyter Notebook style, so can be read for their educational value without running the code.

### More labs coming soon...

## Intended Audiences

This Lab is designed for industry ML engineers with no-to-low ExecuTorch experience, who want to understand how & why to deploy AI inference applications at the Edge using the ExecuTorch runtime. It is also well-suited for Embedded Engineers with a basic fundamentals AI/ML knowledge, interested in incorporating ML in their Embedded/Edge applications. Students wanting to learn more will also find this accessible and useful, and academics, teachers, and trainers are encouraged to incorporate these resources into their teaching, for free, subject to the attached EULA in `LICENSE.md`.

Those who want to build or refresh fundamentals can first complete introductory and intermediate material such as the [Intro to AI](https://www.edx.org/learn/computer-science/arm-education-introduction-to-ai) or [Optimizing Generative AI on Arm](https://www.edx.org/learn/computer-science/arm-education-ai-on-arm) course.

---

## Getting Started

- Look at `Lab_0_Setup.md` and follow the steps before attempting the labs.

## Interested in Contributing?

We are open to accepting contributed labs from the community. We intend to release future labs, and would be delighted to hear from professional developers, academics, or even students, who would be interested in collaborating. 

Alternatively, raise a PR with your lab, fitting the style, and send us an email at education@arm.com, and we can work with you to potentially accept it, with all due credit given.

## License
You are free to fork or clone this material. See `LICENSE.md` for the complete license.

> Lab 2 was produced from original content contributed by [Professor Marcelo Rovai](https://github.com/Mjrovai) at UNIFEI University, in collaboration with Matt Cossins from Arm.

## Inclusive Language Commitment
Arm is committed to making the language we use inclusive, meaningful, and respectful. Our goal is to remove and replace non-inclusive language from our vocabulary to reflect our values and represent our global ecosystem.
 
Arm is working actively with our partners, standards bodies, and the wider ecosystem to adopt a consistent approach to the use of inclusive language and to eradicate and replace offensive terms. We recognise that this will take time. This course may contain references to non-inclusive language; it will be updated with newer terms as those terms are agreed and ratified with the wider community. 
 
Contact us at education@arm.com with questions or comments about this course. You can also report non-inclusive and offensive terminology usage in Arm content at terms@arm.com.

---
