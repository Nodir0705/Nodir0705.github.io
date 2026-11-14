---
layout: page
title: Resume
permalink: /resume/
hide_page_title: true
custom_css: resume
description: "Resume of Nodirbek Makhtumov — AI/ML Engineer; computer vision on edge hardware, NPU deployment, RAG, and network security."
---

<header class="resume-header">
  <div class="resume-header-text">
    <h1 class="resume-name">Nodirbek Makhtumov</h1>
    <p class="resume-role">AI/ML Engineer</p>
    <div class="resume-social" aria-label="Profiles">
      <a href="{{ site.profiles.github }}" target="_blank" rel="noopener noreferrer" aria-label="GitHub">{% include icon.html name="github" %}</a>
      <a href="{{ site.profiles.linkedin }}" target="_blank" rel="noopener noreferrer" aria-label="LinkedIn">{% include icon.html name="linkedin" %}</a>
      <a href="mailto:{{ site.email }}" aria-label="Email">{% include icon.html name="email" %}</a>
    </div>
  </div>
  <div class="resume-header-actions">
    <div class="resume-pdf-row">
    <a href="{{ site.baseurl }}/assets/Nodirbek_Makhtumov_Resume.pdf" download class="btn btn-primary">Resume (EN) {% include icon.html name="arrow-down" %}</a>
    <a href="{{ site.baseurl }}/assets/Nodirbek_Makhtumov_Resume_KR.pdf" download class="btn btn-primary">이력서 (KR) {% include icon.html name="arrow-down" %}</a>
    <a href="{{ site.baseurl }}/assets/Nodirbek_Makhtumov_Resume_UZ.pdf" download class="btn btn-primary">Rezyume (UZ) {% include icon.html name="arrow-down" %}</a>
    </div>
    <div class="resume-pdf-row">
    <a href="{{ site.baseurl }}/assets/Nodirbek_Makhtumov_Portfolio.pdf" download class="btn">Portfolio (EN) {% include icon.html name="arrow-down" %}</a>
    <a href="{{ site.baseurl }}/assets/Nodirbek_Makhtumov_Portfolio_KR.pdf" download class="btn">포트폴리오 (KR) {% include icon.html name="arrow-down" %}</a>
    <a href="{{ site.baseurl }}/assets/Nodirbek_Makhtumov_Portfolio_UZ.pdf" download class="btn">Portfolio (UZ) {% include icon.html name="arrow-down" %}</a>
    </div>
  </div>
</header>

## Summary

AI/ML Engineer with 3+ years building and shipping production computer vision systems that run on edge hardware. I own the full path: model design and training, TensorRT/ONNX quantization, deployment to NVIDIA Jetson and Hailo-8 / RK3588 NPUs, and the FastAPI and Docker services around them. I validate models with per-class metrics, adversarial robustness tests and per-hardware measurements rather than a single headline accuracy.

## Skills Summary

| Category           | Tools & techniques                                                                                                                                       |
| ------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Programming & Tools | Python (primary), C++, SQL, TypeScript, Git/GitHub, GitLab, GitHub Actions CI                                                                           |
| ML Frameworks      | PyTorch, TensorFlow, Keras, Scikit-Learn, Ultralytics (YOLO), OpenCV, InsightFace, Hugging Face Transformers, SAM2                                       |
| Computer Vision    | Object detection, semantic / instance segmentation, OCR, multi-object tracking, face recognition (ArcFace), pose estimation                              |
| Model Optimization | Quantization, pruning, TensorRT, ONNX Runtime, DLA offloading, backbone replacement and A/B evaluation                                                   |
| Edge Hardware      | NVIDIA Jetson (Orin NX, Orin Nano), Hailo-8 NPU, RK3588 NPU (Orange Pi 5), Raspberry Pi 4/5, Android tablets                                             |
| LLM & RAG          | Claude API (structured outputs, prompt caching, Batch API), LLM evaluation, Ollama, Qwen, hybrid retrieval (bge-m3 + BM25), Chroma, rerankers, citation checking |
| Serving & Systems  | FastAPI, Flask, Docker, REST API, PostgreSQL, SQLite, concurrent multi-stream serving, eBPF/XDP, Suricata, nftables, Linux (Ubuntu)                       |
| Evaluation         | Per-class metrics, adversarial robustness testing, Grad-CAM, FPS / latency / jitter benchmarking, W&B, MLflow, TensorBoard                                |

## Work Experience

### AI/ML Engineer

**Netvision Telecom** &#124; **April 2023 - Present** &#124; **Daejeon, South Korea**

- **Smart Waste Truck Vision:** Built YOLO waste classification and volume estimation for garbage trucks. Replaced the **YOLOv8** backbone with **ResNet50** (1×1 conv adapters into the PANet neck) and moved ResNet layers onto the **Jetson DLA**, cutting GPU memory by **~30%** on Orin NX; deployed on the truck after quantization and **TensorRT** conversion.
- **Rail-Wheel Gap Measurement:** Combined a lightweight segmentation model with **RANSAC** boundary extraction and a custom point-stabilization algorithm for curved edges, served over **FastAPI** with **PostgreSQL** logging at **25+ FPS across 4 concurrent camera streams**.
- **SAM2 Video Auto-Labeling:** Built a tool that propagates labels through a whole video from one first-frame prompt and exports YOLO and COCO datasets, making dataset building **10×+ faster**.
- **Research Intern (Apr - Sep 2023):** Built and deployed YOLO models on Jetson Orin Nano, applied latency optimization and quantization, and collected and labeled training data.

### Freelance AI/ML Engineer — Sales Quoting Agent
{: #freelance-sales}

**Contract** &#124; **October 2026** &#124; **Remote**

- **Quote, Then Ask:** Built an email agent for a company that exports insulated sandwich panels. **Claude** reads the enquiry into a fixed schema, **Python** computes the quote from the Excel price list, Claude writes the reply around the numbers, and the owner gets a **Telegram** card with Approve / Reject. The model never types a price and nothing is sent without Approve.
- **Tested Before Trusted:** **26/26** on the extraction eval (written test emails), 1,513 automated checks, every AI call priced with a daily cap; run against a real inbox in test mode. [sales-quote-agent](https://github.com/Nodir0705/sales-quote-agent)

### Freelance AI/ML Engineer — Face Recognition Kiosk
{: #freelance-face}

**Contract** &#124; **July 2026** &#124; **Remote**

- **Three Pipelines, Measured:** Implemented the same SCRFD + ArcFace pipeline in **Python**, **C++** and on a **Hailo-8 NPU** to choose hardware by measurement. On a Raspberry Pi 5, Python on the CPU vs Hailo-8: median latency 48.08 ms → **5.59 ms** (8.6×), jitter ±27 ms → ±0.29 ms (95× tighter). The C++ port, measured on a Pi 4, only cut loop overhead because the model dominates the cost.
- **Enrollment & Delivery:** Built a five-pose guided enrollment wizard, then used the benchmarks to choose a **Samsung Galaxy Tab** as the target and shipped on-device inference with offline-first SQLite logging and Google Sheets sync. [face-recognition](https://github.com/Nodir0705/face-recognition)

### Freelance AI/ML Engineer — Smart Truck Parking
{: #freelance-truck}

**Contract** &#124; **September 2025 - November 2025** &#124; **Remote**

- **End-to-End System:** Built truck detection, truck-ID recognition and live occupancy streaming solo, with **YOLO** + **ByteTrack** on RTSP cameras and events sent to the backend over REST.
- **Deskewing for OCR:** Error analysis showed perspective distortion was the main failure mode; a deskew stage (contours + perspective transform) in front of **EasyOCR** raised ID accuracy from **76% to 92%**.
- **Open-Source Version:** Published a cleaned version with a rewritten deskew module; on synthetic tilted plates it lifts OCR accuracy from 80.5% to **97.5%**. [smart-truck-parking](https://github.com/Nodir0705/smart-truck-parking)

## Projects

- **[IoT Security Gateway](https://github.com/Nodir0705/iot-gateway-security):** Orange Pi 5 (RK3588S) gateway with **XDP/eBPF** filtering, 244 **Suricata** IoT rules, a flow autoencoder on the **RK3588 NPU** and automatic **nftables** quarantine. Caught **9/9 attack phases** in a 47-minute stress test, with 87/88 expected rules firing.
- **[Malware Classifier Robustness](https://github.com/Nodir0705/malware_classifier):** A MalImg ResNet50 at 99.48% fell to **22%** under PGD attack (each byte changed by at most 2); full adversarial retraining brought it back to **94.15%** for a 2.3-point clean-accuracy cost.
- **HiKorea RAG:** Korean immigration Q&A over 640 official documents with hybrid **bge-m3** + **BM25** retrieval, LLM rerank and citation-checked answers; recall@5 0.706 → **0.824** over dense-only.
- **Worksheet Auto-Grader:** Nanonets-OCR2-3B reads the handout, **Qwen3-4B** grades it, and red-pen marks are written back onto the PDF on an 8 GB GPU; 18/20 on a held-out judge eval.
- **[Smart Pointer](https://github.com/Nodir0705/smart-pointer):** Highlights the part of the slide a presenter is talking about, live, offline and on a CPU: speech-to-text, then a 2-layer **TinyBERT** re-ranker matches each clause to a slide unit in 16 ms. Lit **77.3%** of pointing steps on 7 unseen public decks (synthetic voice; not yet measured on a real talk).
- **Capstone Mentor, Woosong University (2024):** Guided a computer-vision team through image processing and YOLO training; the team placed **1st of 200+**.

## Education

| **Institution**    | **Degree**              | **Duration** |
| ------------------ | ----------------------- | ------------ |
| Woosong University | BSc in Computer Science | 2019 - 2023  |

## Languages

| Language | Proficiency                              |
| -------- | ---------------------------------------- |
| Uzbek    | Native                                   |
| English  | Fluent, professional working proficiency |
| Korean   | Conversational                           |
| Russian  | Conversational                           |

**Visa:** E-7 Special Ability, authorized to work in South Korea.
