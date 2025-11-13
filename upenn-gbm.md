# **UPENN-GBM – Multi-parametric MRI for De Novo Glioblastoma (University of Pennsylvania Health System)**
The **UPENN-GBM** collection provides **multi-parametric magnetic resonance imaging (mpMRI)** scans and corresponding **clinical, histopathologic, and radiomic** data from **630 patients** with **de novo glioblastoma (GBM)**.  
The dataset was curated by the **University of Pennsylvania Health System** and released through **The Cancer Imaging Archive (TCIA)** as a comprehensive, open-access imaging resource for studying glioblastoma biology, segmentation reproducibility, and radiogenomic biomarkers.

Each subject includes co-registered and skull-stripped mpMRI scans together with **automated and manually corrected tumor segmentation labels** that delineate histologically distinct subregions (enhancing core, necrotic core, edema, etc.). These segmentations were refined and approved by expert **board-certified neuroradiologists**, enabling quantitative analyses without repeated manual annotation.

The dataset also provides a large panel of **radiomic features**, **clinical outcomes**, and **molecular data**, supporting cross-disciplinary research linking imaging, histology, and genomics. For a subset of cases, matched **H&E-stained whole-slide histopathology images** from resected tumor tissue are available, enabling radiology–pathology correlation.

---

## Overview

- **Dataset name:** UPENN-GBM (Multi-parametric MRI for De Novo Glioblastoma)  
- **Institution:** University of Pennsylvania Health System  
- **Repository:** The Cancer Imaging Archive (TCIA)  
- **Species:** Human  
- **Subjects:** 630 patients  
- **Cancer type:** Glioblastoma multiforme (GBM)  
- **Data types:** MRI (DICOM/NIfTI), segmentation labels, histopathology, demographics, molecular and radiomic features  
- **Total size:** ~357 GB  
- **Version:** 2 (Updated 2022-10-24)  
- **DOI:** [10.7937/TCIA.709X-DN49](https://doi.org/10.7937/TCIA.709X-DN49)  
- **License:** Creative Commons Attribution 4.0 International (CC BY 4.0)  

---

## Imaging and Data Modalities

| Data Type | Format | Description | Size | Access |
|------------|---------|-------------|-------|--------|
| **MRI Images** | DICOM | mpMRI scans including T1, T1-Gd, T2, and FLAIR | 139.4 GB | [Download via NBIA Data Retriever](https://www.cancerimagingarchive.net/nbia-download/) |
| **MRI + Segmentation** | NIfTI | Co-registered mpMRI with tumor and whole-brain segmentation labels | 69 GB | Requires IBM Aspera Connect |
| **Histopathology Images** | NDPI | Digitized H&E slides from resected tumors | 149 GB | Requires IBM Aspera Connect |
| **Clinical Data** | CSV | Demographics, molecular tests, and outcomes | 64.9 KB | Direct download |
| **Radiomic Features** | ZIP/CSV | CaPTk-extracted intensity, texture, and morphologic features | 15.4 MB | Direct download |
| **Radiology–Pathology Mapping** | CSV | Links imaging and histology IDs | 2.5 KB | Direct download |
| **Acquisition Parameters** | CSV | MRI scanner and sequence details | 194 KB | Direct download |
| **Data Availability per Subject** | CSV | File completeness summary | 125 KB | Direct download |
| **Radiomic Parameter File** | CSV | CaPTk configuration reference | 3.8 KB | Direct download |

---

## Study Description

This dataset integrates **clinical**, **imaging**, and **molecular** data to enable large-scale computational and translational research in glioblastoma.  
All MRI volumes were **preprocessed** (skull stripping and co-registration) prior to segmentation, which was performed via an **automated pipeline** followed by **manual expert correction**.  
Derived features include:
- Intensity and histogram-based measures  
- Volumetric and morphological statistics  
- Textural parameters (GLCM, GLRLM, etc.)  
- Radiomic descriptors consistent with **CaPTk** and **IBSI** standards  

The dataset supports:
- Benchmarking of **automated tumor segmentation algorithms**  
- **Radiogenomic association studies** linking imaging phenotypes to molecular subtypes  
- **Outcome prediction** (e.g., overall survival, progression-free survival)  
- Radiology–pathology correlation and **cross-modality feature harmonization**

---

## Data Access

All data are publicly available through **[The Cancer Imaging Archive (TCIA)](https://www.cancerimagingarchive.net/)**.  
Use of **NBIA Data Retriever** or **IBM Aspera Connect** is required for large downloads.

**Version 2 Updates (October 2022):**
- Added digitized histopathology (NDPI format)  
- Added radiology–pathology mapping CSV  
- Harmonized radiomic feature files and metadata  

---

## Citation

> Bakas, S., Sako, C., Akbari, H., Bilello, M., Sotiras, A., Shukla, G., Rudie, J. D., Flores Santamaria, N., Fathi Kazerooni, A., Pati, S., Rathore, S., Mamourian, E., Ha, S. M., Parker, W., Doshi, J., Baid, U., Bergman, M., Binder, Z. A., Verma, R., … Davatzikos, C. (2021).  
> *Multi-parametric magnetic resonance imaging (mpMRI) scans for de novo Glioblastoma (GBM) patients from the University of Pennsylvania Health System (UPENN-GBM) (Version 2)*.  
> The Cancer Imaging Archive.  
> [https://doi.org/10.7937/TCIA.709X-DN49](https://doi.org/10.7937/TCIA.709X-DN49)

Users must include this citation in all publications derived from this dataset.

---

## Usage Policy

This collection is released under **CC BY 4.0**, allowing sharing and adaptation for any purpose (including commercial), provided appropriate attribution is given.  
All users must comply with the **[TCIA Data Usage Policy and Restrictions](https://www.cancerimagingarchive.net/data-usage-policy/)**.

---

## Acknowledgments

This dataset was developed through the collaboration of the **University of Pennsylvania Health System**, **The Cancer Imaging Archive (TCIA)**, and the **National Cancer Institute’s Cancer Imaging Program (CIP)**.  
We thank the contributing radiologists, data scientists, and patients for enabling open-access cancer imaging research.

---

## External Resources

- [TCIA Collection Page – UPENN-GBM](https://www.cancerimagingarchive.net/collection/upenn-gbm/)  
- [Imaging Data Commons (IDC)](https://imaging.datacommons.cancer.gov/)  
- [CaPTk: Cancer Imaging Phenomics Toolkit](https://www.med.upenn.edu/cbica/captk/)  

---

© 2025 The Cancer Imaging Archive (TCIA).  
Prepared for redistribution under **data-others/disease/upenn-gbm** by the **Pittsburgh Fiber Data Hub**.

## Release Link
https://github.com/data-nih/tcia/releases/tag/upenn-gbm
