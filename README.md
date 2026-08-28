# Online Interactive User and Developer Guide: Open-Source Platform for Low-Field MRI

## 1. Project Overview

The development of accessible, open-source tools for magnetic resonance imaging (MRI) is a crucial step toward democratizing medical imaging and fostering reproducible research. This project—developed as part of the broader consortium efforts of A<sup>4</sup>IM Project—aims to establish a comprehensive open-source platform specifically tailored for low-field MRI systems. The primary objective of this platform is to facilitate the rigorous benchmarking of commercial low-field MRI scanners against established low-field MRI reference systems (such as the D1 reference system). Furthermore, the platform is meticulously designed to support reproducibility studies across different institutions and hardware configurations. 

To achieve these ambitious goals, the platform provides a complete end-to-end ecosystem that encompasses both hardware and software layers. It enables precise low-field MRI scanner control, allowing operators to perform vital tune-ups and system adjustments necessary for optimal image quality. Beyond scanner control, the platform features robust mechanisms for raw data export and retrieval, ensuring that researchers have unfettered access to the unmodified signals acquired during scans. This raw data can then be fed into advanced image reconstruction pipelines that include sophisticated post-processing algorithms. Finally, to promote data sharing and collaborative research, the platform ensures seamless connectivity to an open, cloud-based platform containing a centralized database. By integrating these diverse components—from pulse sequence design and hardware control to image reconstruction and cloud storage—the consortium has created a modular, highly flexible environment that serves both as a comprehensive user guide for clinicians and operators, and as a detailed developer guide for engineers and researchers looking to extend the platform's capabilities.

## 2. Hardware Architectures
As part of the project, different sites integrated different hardware solutions into their low-field MRI systems: the Nexus Console and the MaRCoS console. Each solution requires a distinct software stack.

### 2.1. Red Pitaya / MaRCos
The Red Pitaya is a highly accessible, cost-effective, and compact hardware platform that has gained significant traction in the open-source engineering community. Often described as a "Swiss Army knife" for test and measurement, it is utilized in this project for foundational scanner control, pulse generation, and signal acquisition.
The Red Pitaya hardware is directly supported by the **MaRCoS** and **MaRGE** software projects. These projects provide the necessary firmware and interfaces to transform the Red Pitaya into a functional MRI spectrometer. They handle the intricate timing requirements for transmitting RF pulses and receiving the faint MRI signals, making the Red Pitaya an excellent choice for low-cost setups, portable low-field systems, and fundamental reproducibility studies.

Scanhub provides a device SDK that can be used to integrate additional hardware types. However, a Red Pitaya implementation is not currently available.

### 2.2. Nexus Console (Spectrum-Instrumentation)
For applications requiring higher fidelity, greater computational power, and advanced real-time capabilities, the project also produced the **Nexus Console** hardware architecture. This setup is driven by high-end measurement cards from Spectrum-Instrumentation. The Nexus hardware offers superior analog-to-digital and digital-to-analog conversion rates, making it suitable for advanced low-field imaging techniques. It supports the integration of additional sensor information. 
The Nexus hardware is natively supported by the **Scanhub** overarching platform and the dedicated **NEXUS Console** software framework. Developers looking to leverage the full power of Scanhub's integrated workflows currently rely on the Nexus hardware ecosystem.

## 3. Core Capabilities and Project Contributions

To fully address the diverse requirements of modern low-field MRI research, the platform's features are categorized into distinct thematic areas. The following sections detail how each open-source project (within the consortium) contributes to these core capabilities.
The different hardware architectures and their associated software stacks allow a system-specific software environment to be assembled by combining modules based on different open-source projects.

### 3.1. Developer Guide
Due to the different hardware architectures and associated software stacks, it is not possible to provide a single, continuous guide that applies to all systems. Instead, this guide provides an overview of the available modules and their respective purposes, helping developers identify which components are suitable for a particular system or task. It also refers directly to the individual documentation resources for each module. These documents are maintained and updated by the respective projects.

* [**MRSEQ**](./mrseq.md) offers extensive developer documentation for pulse sequence programming and image reconstruction pipelines, aiding researchers in creating low-field optimized sequences.
* [**MRpro**](./mrpro.md) acts as a developer foundation for data handling, allowing engineers to build custom reconstruction algorithms and cloud integrations via its well-documented API.
* [**Pulseq / PyPulseq**](./pulseq.md) provides the ultimate developer toolkit for hardware-agnostic sequence design, complete with tutorials on implementing advanced methods like FOV shifting.
* [**MaRGE**](./marge.md) provides detailed developer interfaces (in Python and GUI-driven environments, respectively) to interact closely with the underlying hardware.

### 3.2. Scanner Control
Direct interaction with the physical hardware is necessary for executing sequences and acquiring data.
* [**NEXUS Console**](./nexus_console.md) serves as the primary software engine for driving the Spectrum-Instrumentation hardware, executing Pulseq sequences with high fidelity.
* [**MaRGE / MaRCoS**](./marge.md) provide the necessary firmware and software interfaces to control the Red Pitaya hardware, managing the precise timing requirements for RF transmission and reception. MaRGE provides the UI while MaRCos the underlying scanner control.
* [**Scanhub**](./scanhub.md) provides an overarching, high-level control interface (UI). New types of hardware can communicate with this control interface by incorporating a device-SDK. In NEXUS Console this device SDK is already integrated.

### 3.3. Tune-up and Adjustments
Before scanning, operators must calibrate the system to ensure optimal signal-to-noise ratios and image quality.
* [**MaRGE**](./marge.md) includes specific modules for autocalibration and localizer setup, allowing users to fine-tune the Red Pitaya hardware parameters directly from the interface.
* [**NEXUS Console**](./nexus_console.md) provides the necessary tools to adjust the Spectrum-Instrumentation measurement cards, handling complex adjustments.
* [**Scanhub**](./scanhub.md) integrates these calibration routines into its patient and exam management workflows, ensuring that necessary tune-ups are performed before data acquisition begins.

### 3.4. User Guide
Beyond developer tools, the platform must be accessible to radiographers, clinicians, and researchers focused on application rather than engineering.
* [**Scanhub**](./scanhub.md) the Scanhub user guide is still under development. Demonstration videos are available.
* [**MaRGE**](./marge.md) offers a wiki acting as a manual for its graphical interface, guiding advanced users through setting up protocols and executing custom scans on the hardware.

### 3.5. Raw Data Export
Access to unadulterated raw k-space data is a fundamental requirement for reproducibility and advanced benchmarking.
* [**Scanhub**](./scanhub.md) features robust mechanisms via Filesystem for raw data export, ensuring that the signals acquired by the Nexus hardware are securely packaged and easily retrievable for offline analysis.
* [**MaRGE**](./marge.md) handles the raw data structure generated by the Red Pitaya, allowing users to export data for integration into external post-processing pipelines.

### 3.6. Image Reconstruction
Translating raw k-space data into interpretable medical images requires sophisticated algorithms.
* [**MRpro**](./mrpro.md) is a dedicated framework specifically designed for this task. It takes raw data and applies advanced reconstruction algorithms, including those required to correct low-field specific artifacts. The trajectory can be calculated when a Pulseq file is provided.
* **MRSEQ** contributes by providing integrated tools that bridge the gap between how a pulse sequence was designed and how the resulting data should be reconstructed.
* [**MaRGE**](./marge.md) provides simple integrated reconstruction methods. External reconstructions for example utilizing Tyger can also be added. 

### 3.7. Post-Processing
After initial reconstruction, further processing may be required for analysis or visualization.
* [**MRpro**](./mrpro.md) continues its role here by offering pipelines for post-processing the reconstructed images, preparing them for final storage or immediate clinical review.
* [**Scanhub**](./scanhub.md) acts as the orchestrator, ensuring that the post-processed images are correctly linked to the patient metadata and the original raw data. Additional post-processing methods can be added by adjusting this orchestration process.

### 3.8. Database Connection
To foster collaborative research and data sharing, the platform connects to centralized storage solutions.
* [**MRpro**](./mrpro.md) provides the software infrastructure required to push reconstructed images and associated metadata to open, cloud-based databases.
* [**Scanhub**](./scanhub.md) manages the local data workflows and ensures seamless connectivity between the physical scanner environment and these overarching cloud-based platforms, ensuring data is safely archived and easily accessible for global reproducibility studies.

## 4. Conclusion
This open-source platform represents a significant leap forward in low-field MRI research. By providing a clear dichotomy of hardware support—the accessible Red Pitaya via MaRGE/MaRCoS, and the high-performance Nexus system via Scanhub—the consortium has ensured that the platform can scale from basic educational setups to advanced research environments. The elimination of proprietary black boxes across all capabilities—from scanner control and tune-ups to image reconstruction and database connectivity—allows for unprecedented transparency. This transparency is the cornerstone of the platform's ability to serve as a reliable benchmarking tool against existing systems and as the foundation for future reproducibility studies in low-field MRI.
