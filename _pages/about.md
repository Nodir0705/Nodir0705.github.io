---
layout: page
title: About
permalink: /about/
description: "Nodirbek Makhtumov — AI/ML Engineer in Daejeon, Korea, building computer vision that runs on edge hardware."
---

I'm an AI/ML engineer based in Daejeon, South Korea. For 3+ years I have built computer vision systems that run on edge hardware: NVIDIA Jetson boards, Hailo-8 and RK3588 NPUs, Raspberry Pi and Android tablets. I own the path from model design and training through quantization and TensorRT/ONNX conversion to the FastAPI and Docker services around the model.

Since April 2023 I've worked at Netvision Telecom, first as a paid research intern and full-time since September 2023. For smart waste collection trucks I replaced the YOLOv8 backbone with ResNet50 so those layers run on the Jetson DLA, which cut GPU memory by about 30% on a Jetson Orin NX and let the vision model share one board with the fleet-management software. I also built a rail-wheel gap measurement pipeline that runs at 25+ FPS across 4 concurrent camera streams, and a SAM2 tool that labels a whole video from one first-frame prompt.

I take freelance contracts too. On a smart truck parking system, error analysis showed that perspective distortion caused most OCR failures; a deskew stage in front of EasyOCR raised truck-ID accuracy from 76% to 92% on the client's cameras. For a face recognition attendance kiosk I built the same pipeline in Python, in C++ and on a Hailo-8 NPU, so the hardware could be chosen by measurement.

I care about how a model is measured: per-class metrics, adversarial robustness tests, and latency and jitter on the target device, not a single headline accuracy. My personal projects follow the same habit: an IoT security gateway on an Orange Pi 5, a robustness study of a malware image classifier, and Smart Pointer, which highlights the part of a slide a presenter is talking about. There's more on the [projects page]({{ site.baseurl }}/projects/).

I studied Computer Science at Woosong University in Daejeon (2019 – 2023), and in 2024 I mentored a capstone computer-vision team there that placed 1st of 200+ teams. I speak Uzbek natively, English fluently, and Korean and Russian at a conversational level. I hold an E-7 visa and am authorized to work in South Korea.
