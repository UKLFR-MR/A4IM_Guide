# Pulseq and PyPulseq

## Project Overview
Pulseq is an open-source standard for defining MRI pulse sequences in a hardware-independent manner. PyPulseq is its Python implementation, which allows researchers to write sequences using familiar Python syntax. This project utilizes PyPulseq to generate complex, reproducible sequences that can be deployed across various hardware setups.

## Documentation and Resources

The Pulseq ecosystem is vast and well-documented by the global MRI research community. 

### 1. Core Documentation and Manuals
* **Pulseq File Format:** The current The current Pulseq file format definition is available [here](https://pulseq.github.io/specification.pdf) in the PDF gotmat.  definition is available [here](https://pulseq.github.io/specification.pdf) in the PDF gotmat. 
* **PyPulseq GitHub Repository:** The primary source for installation instructions, source code, and API references is the official repository. It contains the fundamental manuals required to get started with sequence programming in Python.

### 2. Tutorials, Workshops, and Videos
Because pulse sequence design can be complex, the community provides extensive educational materials:
* **Basic and Advanced Tutorials:** This [repository](https://github.com/pulseq/tutorials) contains a collection of various Pulseq tutorials covering both the most initial aspects and more advanced topics. It currently contains FID, PRESS, GRE, EPI and some non-Cartesian imaging examples alsong with the Matlab source code, raw data examples and example reconstruction scripts.
* **MR Physics with Pulseq:** This [repository](https://github.com/pulseq/mr-physics-with-pulseq) is based on materials for the Ph.D. student training program of the German Chapter of the ISMRM and is being developed further. In this course, basic and advanced concepts of MR physics are introduced through theoretical lectures by MR experts and followed by the corresponding hands-on exercises. All lecture slides are available as PDFs. The repository is focused on pyPulseq that is configured to run directly in your browser as interactive Notebooks. Visit MR Physics with Pulseq repository.
* **ISMRM Virtual Meeting Series:** Materials of the two Three-Day ISMRM Virtual Meeting Series dedicated to Vendor-Agnostic Pulse Sequence Programming with Pulseq that we have held up to now are archived in the following repositories: [Pulseq ISMRM Virtual Meeting - November 15-17, 2023](https://github.com/pulseq/ismrm-virtual-meeting--november-15-17-2023) and [Pulseq ISMRM Virtual Meeting - February 24-26, 2026](https://github.com/pulseq/ISMRM-Virtual-Meeting--February-24-26-2026). The repositories contain the detailed program, meeting materials, presentation slides, tailor-made tutorials and discussion boards. Recoded videos of the presentations of the February 2026 meeting can be accesses at the [ISMRM Virtual Meeting Archive](https://www.ismrm.org/virtual_meetings/2026-02-24-UM/).
* **Video Records of the Pulseq User Group:** Recordings from past User Group meetings are highly recommended both for new users and experts. They are available [here](https://www.youtube.com/@HarmonizedMRI).
* **Jupyter Notebook Tutorials:** The abovementioned repositories often include interactive notebooks that allow users to simulate sequence behavior before deploying them to physical hardware like the Nexus Console. See for example [here](https://github.com/pulseq/mr-physics-with-pulseq) or [here](https://github.com/pulseq/ISMRM-2025-Surfing-School-Hands-On-Open-Source-MR).

### 3. Advanced Methodologies
For developers looking to implement cutting-edge techniques, the documentation includes specialized How-Tos for recent advancements:
* **Field-of-View (FOV) Shifting:** Guides on implementing FOV adjustments within your sequence code programmatically *will be available soon*.
* **Auto-Labeling Methods:** Documentation on integrating automated data labeling directly into the sequence acquisition phase to streamline post-processing *will be available soon*.
