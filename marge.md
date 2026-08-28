# MaRGE: Magnetic Resonance GUI Environment

## Project Overview
MaRGE is an open-source graphical user interface and control platform designed specifically for low-field MRI scanners utilizing the Red Pitaya hardware architecture. It provides researchers and operators with a direct, intuitive means to interact with the MRI hardware, perform vital tune-ups, and acquire raw data.

## Documentation and Resources

To help you navigate the MaRGE ecosystem, the documentation is divided into several categories within the [official GitHub Wiki](https://github.com/josalggui/MaRGE/wiki):

### 1. Setup and Installation Guides
If you are setting up MaRGE for the first time, refer to the step-by-step installation manuals:
* **Ubuntu Installation:** [Installing MaRGE and MaRCoS from scratch (Ubuntu)](https://github.com/josalggui/MaRGE/wiki/Setting-up-MaRGE-and-MaRCoS-from-scratch-(Ubuntu))
* **Windows Installation:** [Installing MaRGE and MaRCoS from scratch (Windows)](https://github.com/josalggui/MaRGE/wiki/Setting-up-MaRGE-and-MaRCoS-from-scratch-(Windows))
* **Hardware Configuration:** Detailed instructions on setting up the physical system and multichannel configurations are available in the [Hardware configuration](https://github.com/josalggui/MaRGE/wiki/Hardware-configuration-new) section.

### 2. User Manuals and Usage How-Tos
For day-to-day operations and scanning procedures, the following resources are provided:
* **Interface Description:** A [breakdown of the GUI elements](https://github.com/josalggui/MaRGE/wiki/Interface-description) and their functions.
* **Autocalibration & Localizers:** Step-by-step How-Tos for [Setting up autocalibration](https://github.com/josalggui/MaRGE/wiki/Setting-up-autocalibration) and [Setting up localizer](https://github.com/josalggui/MaRGE/wiki/Setting-up-localizer) scans.
* **Running Sequences:** Instructions on how to [Run custom sequences](https://github.com/josalggui/MaRGE/wiki/Run-custom-sequences) and manage standard imaging protocols.

### 3. Developer Guidance
For engineers looking to extend the platform or analyze raw data:
* **Sequence Development:** Learn how to create your own sequences using [PyPulseq integration within MaRGE](https://github.com/josalggui/MaRGE/wiki/Create-your-own-sequence-PyPulseq-version).
* **Data Structures:** Documentation on the raw data structure exported by MaRGE, which is crucial for feeding into reconstruction pipelines like MRpro.
* **Advanced Reconstruction:** Guides on integrating advanced reconstruction techniques with Tyger.
