# **UCSF-PDGM – University of California San Francisco Preoperative Diffuse Glioma MRI**
The **UCSF-PDGM** collection provides **preoperative multi-parametric brain MRI** and matched **molecular, clinical, and follow-up data** for adult patients with histopathologically confirmed **WHO grade II–IV diffuse gliomas**. All patients were scanned at the **University of California San Francisco (UCSF)** using a **standardized 3T MRI protocol** that emphasizes predominantly 3D acquisitions and includes advanced **diffusion (HARDI)** and **perfusion (ASL)** imaging.

In total, the dataset comprises **495 subjects** (501 MRI exams) with harmonized mpMRI, tumor segmentations (aligned to BraTS standards), and curated **IDH and MGMT biomarker status**. This resource is designed to support AI and quantitative imaging research in areas such as **automated tumor segmentation, radiogenomics, survival prediction, and treatment response modeling**. All data are fully preoperative; prior tumor treatment is an exclusion criterion (biopsy allowed).

---

## Overview

- **Dataset name:** UCSF-PDGM – UCSF Preoperative Diffuse Glioma MRI  
- **Institution:** University of California San Francisco  
- **Repository:** The Cancer Imaging Archive (TCIA)  
- **Species:** Human  
- **Subjects:** 495 patients (501 exams)  
- **Tumor types:** WHO grade II–IV diffuse glioma  
- **Data types:** MRI (NIfTI), bval/bvec, tumor segmentations, clinical and molecular data  
- **Total size:** ~142 GB (imaging + annotations)  
- **Latest version:** Version 5 (updated 2025-05-30)  
- **DOI:** [10.7937/TCIA.BDGF-8V37](https://doi.org/10.7937/TCIA.BDGF-8V37)  
- **License:** Creative Commons Attribution 4.0 International (CC BY 4.0)  

---

## Study Population and Biomarkers

- **Population:** Adult patients with histopathologically confirmed **grade II–IV diffuse gliomas**  
- **Inclusion:** Preoperative MRI, initial tumor resection, genetic testing at a single center (2015–2021)  
- **Exclusion:** Any prior brain tumor treatment (except biopsy)  

**Genetic biomarkers:**

- **IDH mutation status** available for all tumors  
- **MGMT promoter methylation** available for **grade III–IV** gliomas  
- **1p/19q codeletion** reported for a subset of cases  

**Grade distribution (501 cases):**

- Grade II: 55 cases (11%)  
- Grade III: 42 cases (9%)  
- Grade IV: 403 cases (80%)  

There is a consistent **male predominance** (~56–60%) across grades. IDH mutations are common in lower-grade gliomas (83% of grade II, 67% of grade III) and rare in grade IV (8%). MGMT hypermethylation is present in ~63% of grade IV gliomas.

---

## Imaging Protocol

All MRIs were acquired **preoperatively** on a **3.0T GE Discovery 750** scanner using an **8-channel head coil**. The standardized protocol includes:

- **Structural:**
  - 3D T2-weighted
  - 3D T2/FLAIR-weighted
  - Susceptibility-weighted imaging (SWI)
  - Pre- and post-contrast T1-weighted (3D)

- **Diffusion:**
  - 2D **55-direction HARDI** diffusion sequence  
  - Derived maps: DWI, FA, MD, AD, RD (via FSL Eddy + DTIFIT)

- **Perfusion:**
  - 3D **arterial spin labeling (ASL)** perfusion imaging  

Gadolinium-based contrast agents used:
- Gadobutrol (Gadovist): 0.1 mL/kg  
- Gadoterate (Dotarem): 0.2 mL/kg  

---

## Image Pre-processing and Tumor Segmentation

**Pre-processing:**

- HARDI data corrected with **FSL Eddy** (eddy current correction with outlier replacement; no topup)  
- Tensor fitting with **FSL DTIFIT** (simple least squares)  
- All contrasts registered and resampled to each subject’s **T2/FLAIR space** (1 mm isotropic) using **ANTs** non-linear registration  
- Skull stripping performed with a public deep-learning model:  
  - https://github.com/ecalabr/brain_mask  

**Tumor segmentation:**

- Multicompartment segmentation performed as part of the **BraTS 2021** pipeline  
- Initial automated segmentation using an ensemble of prior BraTS-winning models  
- Manual corrections by trained radiologists, with final approval by two expert reviewers  
- Segmented compartments:
  - Enhancing tumor  
  - Non-enhancing / necrotic tumor  
  - FLAIR hyperintense abnormality (“edema” region)  

These labels support:
- Benchmarking of segmentation algorithms  
- Radiomics and radiogenomics analyses  
- Survival and progression modeling  

---

## Data Access

All data are hosted on **TCIA** and are publicly accessible.

**Version 5 changes (2025-05-30):**

- Fixed a header issue in **DTI_eddy_noreg** by providing NIfTI files in **original orientation and spacing** (post-FSL eddy, prior to further processing)  
- Added **rotated bvecs** for each exam (FSL eddy outputs)  

**Download resources:**

| Content | Data Type | Format | Subjects | License | Access |
|---------|-----------|--------|----------|---------|--------|
| Images & annotations | MR images + segmentations | NIfTI + BVEC | 495 | CC BY 4.0 | Download via IBM Aspera (142 GB) |
| Clinical data | Demographic, molecular, diagnosis, follow-up | CSV | 495 | CC BY 4.0 | Direct CSV download |
| bval files | Diffusion b-values | BVAL/ZIP | — | CC BY 4.0 | Direct download |
| bvec files | Rotated diffusion b-vectors | BVEC/ZIP | — | CC BY 4.0 | Direct download |

Access details and download links are available on the TCIA collection page.

---

## External Tools and Resources

- **Skull stripping model:**  
  https://github.com/ecalabr/brain_mask/  

- **Related datasets and benchmarks:**  
  - RSNA-ASNR-MICCAI BraTS 2021 challenge dataset  

---

## Citation

Users **must** cite the dataset as:

> Calabrese, E., Villanueva-Meyer, J., Rudie, J., Rauschecker, A., Baid, U., Bakas, S., Cha, S., Mongan, J., Hess, C. (2022).  
> *The University of California San Francisco Preoperative Diffuse Glioma MRI (UCSF-PDGM) (Version 5)* [dataset].  
> The Cancer Imaging Archive.  
> [https://doi.org/10.7937/TCIA.BDGF-8V37](https://doi.org/10.7937/TCIA.BDGF-8V37)

---

## Usage Policy

The UCSF-PDGM collection is distributed under **CC BY 4.0**, allowing reuse and adaptation (including commercial use) with appropriate attribution.  
Users must comply with the **[TCIA Data Usage Policy and Restrictions](https://www.cancerimagingarchive.net/data-usage-policy/)**.

---

## Source

- TCIA collection page – UCSF-PDGM:  
  *(search “UCSF-PDGM” on The Cancer Imaging Archive)*  
- About TCIA:  
  https://www.cancerimagingarchive.net/  

---

© 2025 The Cancer Imaging Archive (TCIA).  
Prepared for redistribution under **data-others/disease/ucsf-pdgm** by the **Pittsburgh Fiber Data Hub**.

## Release Link
https://github.com/data-nih/tcia/releases/tag/ucsf-pdgm
