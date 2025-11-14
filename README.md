# **The Cancer Imaging Archive (TCIA) Collections**

**The Cancer Imaging Archive (TCIA)** hosts de-identified cancer imaging datasets, organized by disease, modality, or research focus. Most collections share imaging in **DICOM**, sometimes accompanied by clinical, genomic, and expert annotation.

This repository provides **curated, analysis-ready NIfTI derivatives** for selected TCIA brain tumor collections.  
Where possible, diffusion MRI derivatives (**SZ / GQI / QSDR**) are provided in formats compatible with **DSI Studio**.  
Raw TCIA DICOM archives remain on TCIA servers; only derived files are mirrored here.

---

# **UPenn-GBM — Advanced MRI, Clinical, Genomics & Radiomics**

**Release tag:** `upenn-gbm`  
**Source:** University of Pennsylvania Glioblastoma (UPenn-GBM) TCIA Collection  

This collection provides multi-parametric MRI, clinical outcomes, tumor segmentations, and genomic features for **de novo glioblastoma (GBM)**.

### **Included data**

- **Imaging**
  - T1w, T2w, FLAIR, contrast-enhanced T1w  
  - Skull-stripped, co-registered NIfTI volumes  
- **Segmentations**
  - Tumor subregions (expert-corrected): enhancing, non-enhancing, edema  
- **Non-imaging (via TCIA)**
  - Clinical outcomes  
  - Genomics  
  - Radiomics features  
- **Applications**
  - Tumor segmentation benchmarking  
  - Radiogenomics  
  - Progression modeling and survival prediction  

### **License**

**CC BY 4.0**

### **Citation**

Bakas S. et al., *Scientific Data* (2022) 9:453  
*The University of Pennsylvania glioblastoma (UPenn-GBM) cohort: Advanced MRI, clinical, genomics, & radiomics.*

### **Linux / macOS — bash download**

```bash
curl -s https://api.github.com/repos/data-nih/tcia/releases/tags/upenn-gbm | jq -r '.assets[].browser_download_url' | xargs -n1 -P4 curl -LO
````

### **Windows PowerShell 5.x download**

```powershell
(Invoke-RestMethod "https://api.github.com/repos/data-nih/tcia/releases/tags/upenn-gbm").assets | ForEach-Object { Invoke-WebRequest $_.browser_download_url -OutFile (Split-Path $_.browser_download_url -Leaf) }
```

---

# **UCSF-PDGM — Preoperative Diffuse Glioma MRI**

**Release tag:** `ucsf-pdgm`
**Source:** UCSF Preoperative Diffuse Glioma MRI (TCIA)

This dataset contains preoperative MRI for **501 adult patients** with WHO grade II–IV diffuse gliomas, including advanced diffusion and perfusion imaging.

### **Included data**

* **Cohort**

  * 501 subjects
  * WHO grade II–IV
  * Genomic markers: IDH, MGMT, 1p/19q
* **Imaging**

  * 3D T2, 3D T2/FLAIR
  * SWI
  * DWI + **55-direction HARDI**
  * Pre/post-contrast T1w
  * 3D ASL perfusion
* **Segmentations**

  * Enhancing tumor
  * Non-enhancing / necrotic tumor
  * FLAIR hyperintensity (edema)
  * Radiologist-refined BraTS-ensemble AI segmentations
* **Applications**

  * AI segmentation
  * Radiogenomics (IDH, MGMT prediction)
  * Comparative glioma research (vs. BraTS, TCGA-GBM, UPenn-GBM)

### **License**

**CC BY 4.0**

### **Citation**

Calabrese, E. et al. (2022).
*The University of California San Francisco Preoperative Diffuse Glioma MRI (UCSF-PDGM).*
TCIA. DOI: 10.7937/tcia.bdgf-8v37

### **Linux / macOS — bash download**

```bash
curl -s https://api.github.com/repos/data-nih/tcia/releases/tags/ucsf-pdgm | jq -r '.assets[].browser_download_url' | xargs -n1 -P4 curl -LO
```

### **Windows PowerShell 5.x download**

```powershell
(Invoke-RestMethod "https://api.github.com/repos/data-nih/tcia/releases/tags/ucsf-pdgm").assets | ForEach-Object { Invoke-WebRequest $_.browser_download_url -OutFile (Split-Path $_.browser_download_url -Leaf) }
```

---

# **Licensing and Use**

* All derivatives follow the **original TCIA collection licenses** (mostly CC BY 4.0).
* Users must comply with:

  * TCIA **data usage and citation** requirements
  * Citations of the **primary publications** for each dataset
* When using curated derivatives from this repository, please add:

> “Derived imaging files were curated via the Pittsburgh Fiber Data Hub (`data-nih/tcia`) from TCIA collections.”

---

# **Notes**

* This repository **does not include** the original DICOM archives (hosted on TCIA).
* NIfTI and diffusion derivatives are provided for convenience and downstream analysis (tractography, radiomics, segmentation research).
* Users should perform their own QC and methodological validation before scientific reporting.


