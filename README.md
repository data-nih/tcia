# The Cancer Imaging Archive (TCIA) Collections

`data-nih/tcia`

**The Cancer Imaging Archive (TCIA)** is a public resource that hosts de-identified medical images of cancer. Data are organized into **collections** grouped by disease, modality, or research focus. Most radiology images are shared in **DICOM** format, with additional supporting information (clinical, genomics, outcomes, expert annotations) when available.

This repository provides **curated, analysis-ready derivatives** for selected TCIA collections, focused on brain tumor cohorts with rich imaging and clinical annotation. Raw archives remain hosted on TCIA; this repo mirrors key NIfTI and diffusion derivatives and tracks their provenance for use with DSI Studio and related workflows.

---

## Contents

Currently included TCIA collections:

* [UPenn-GBM: Advanced MRI, Clinical, Genomics & Radiomics](#upenn-gbm-advanced-mri-clinical-genomics--radiomics)
* [UCSF-PDGM: Preoperative Diffuse Glioma MRI](#ucsf-pdgm-preoperative-diffuse-glioma-mri)

Each release folder contains:

* Imaging data in **NIfTI** (structural, FLAIR, contrast-enhanced T1, etc.)
* When available, DSI Studio–ready **SZ/GQI/QSDR** derivatives for diffusion MRI
* Basic subject-level metadata and QC tables (where provided by the source)

For full clinical, genomic, and outcome variables, please refer to the original TCIA collection pages.

---

## UPenn-GBM: Advanced MRI, Clinical, Genomics & Radiomics

**Release:** `upenn-gbm`
**Source:** The University of Pennsylvania glioblastoma (UPenn-GBM) cohort (TCIA)

This collection includes multi-parametric MRI and rich clinical/genomic annotation for **de novo glioblastoma (GBM)** patients:

* **Imaging:**

  * Multi-parametric MRI (mpMRI) including T1w, T2w, FLAIR, and contrast-enhanced T1w
  * Skull-stripped and co-registered volumes in NIfTI format
* **Segmentations:**

  * Computer-aided and neuroradiologist-corrected tumor subregion labels
  * Whole-brain and tumor subregion masks in NIfTI format
* **Non-imaging data (in source TCIA):**

  * Clinical outcomes, genomics, tumor progression
  * Radiomic features and challenge-ready labels

This dataset is suitable for:

* Tumor segmentation benchmarking
* Radiomics and radiogenomics
* Survival/outcome modeling and progression studies

**License**

* Creative Commons Attribution 4.0 International (**CC BY 4.0**)

**Citation**

* Bakas S, Sako C, Akbari H, Bilello M, Sotiras A, Shukla G, Rudie JD, Santamaría NF, Kazerooni AF, Pati S, Rathore S.
  *The University of Pennsylvania glioblastoma (UPenn-GBM) cohort: Advanced MRI, clinical, genomics, & radiomics.*
  Scientific Data. 2022; 9(1):453.

**Data Source**

* TCIA collection page:
  [https://wiki.cancerimagingarchive.net/pages/viewpage.action?pageId=70225642](https://wiki.cancerimagingarchive.net/pages/viewpage.action?pageId=70225642)

---

## UCSF-PDGM: Preoperative Diffuse Glioma MRI

**Release:** `ucsf-pdgm`
**Source:** UCSF Preoperative Diffuse Glioma MRI Dataset (UCSF-PDGM, TCIA)

UCSF-PDGM provides preoperative MRI from **501 adult patients** with histopathologically confirmed WHO grade II–IV diffuse gliomas:

* **Cohort:**

  * 501 subjects, preoperative imaging only
  * WHO grades II–IV with associated genomic markers (e.g., IDH, MGMT, 1p/19q)
* **Imaging:**

  * Standard and advanced MRI:

    * 3D T2 and T2/FLAIR
    * SWI
    * DWI and HARDI (55-direction)
    * Pre- and post-contrast T1w
    * 3D ASL perfusion
* **Genomics & clinical:**

  * IDH mutation, MGMT methylation, 1p/19q co-deletion
  * Clinical and demographic metadata (via TCIA)
* **Segmentations:**

  * Multi-compartment tumor segmentations:

    * Enhancing tumor
    * Non-enhancing/necrotic tumor
    * FLAIR hyperintensity/edema
  * Initial AI segmentations refined by radiologists and reviewed by experts

These data support:

* AI-based tumor segmentation and grading
* Radiogenomic modeling of IDH, MGMT, and related biomarkers
* Comparative analysis with other glioma resources (e.g., TCGA-GBM, BraTS, UPenn-GBM)

**License**

* Creative Commons Attribution 4.0 International (**CC BY 4.0**)

**Citation**

* Calabrese, E., Villanueva-Meyer, J., Rudie, J., Rauschecker, A., Baid, U., Bakas, S., Cha, S., Mongan, J., & Hess, C. (2022).
  *The University of California San Francisco Preoperative Diffuse Glioma MRI (UCSF-PDGM) (Version 4).*
  The Cancer Imaging Archive. DOI: 10.7937/tcia.bdgf-8v37

---

## Licensing and Use

* All content in this repository respects the **original TCIA licenses** (e.g., CC BY 4.0) and usage conditions.
* Users must:

  * Follow the **TCIA data citation and usage guidelines** for each collection.
  * Cite both the **original TCIA dataset** and the associated **primary publications**.

When using derivatives or curated subsets from `data-nih/tcia`, please add an acknowledgement such as:

> “Derived imaging files were curated via the Pittsburgh Fiber Data Hub (`data-nih/tcia`) from TCIA collections.”

---

## Notes

* This repository does **not** host original DICOM archives; these remain on TCIA servers.
* NIfTI and diffusion derivatives here are provided to facilitate downstream analysis (e.g., tractography, radiomics, segmentation benchmarking).
* Users are encouraged to perform their own QC and methodological checks before drawing scientific conclusions.

---
