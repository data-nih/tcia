# UCSF Preoperative Diffuse Glioma MRI Dataset (UCSF-PDGM)

**License**  
[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)

**Data Citation**  
Calabrese, E., Villanueva-Meyer, J., Rudie, J., Rauschecker, A., Baid, U., Bakas, S., Cha, S., Mongan, J., & Hess, C. (2022). *The University of California San Francisco Preoperative Diffuse Glioma MRI (UCSF-PDGM) (Version 4)*. The Cancer Imaging Archive. [DOI: 10.7937/tcia.bdgf-8v37](https://doi.org/10.7937/tcia.bdgf-8v37)

---

## 📄 Overview

UCSF-PDGM provides MRI data from **501 adult patients** with histopathologically confirmed **grade II-IV diffuse gliomas**, all acquired **preoperatively** using a **standardized 3T MRI protocol**. This dataset extends previous public resources (e.g., TCGA-GBM, BraTS) by including:

- Advanced MRI techniques: **3D sequences, ASL perfusion, and HARDI diffusion**
- Genomic biomarkers: **IDH mutation and MGMT methylation**
- Expert-reviewed, multi-compartment **tumor segmentation**

---

## 📊 Dataset Summary

| Feature                      | Details                                   |
|-----------------------------|-------------------------------------------|
| Total subjects              | 501                                       |
| Tumor grades                | II (11%), III (9%), IV (80%)              |
| Male predominance           | ~60% across all grades                    |
| IDH mutations               | 83% (grade II), 67% (grade III), 8% (IV)  |
| MGMT methylation (grade IV) | 63%                                       |
| 1p/19q co-deletion          | 20% (II), 5% (III), <1% (IV)              |

---

## 🧠 Imaging Protocol

- Scanner: GE Discovery 750 (3T), 8-channel head coil  
- Sequences:
  - 3D T2, T2/FLAIR, SWI
  - DWI and HARDI (55-direction)
  - Pre/post-contrast T1
  - 3D ASL perfusion
- Contrast agents: Gadobutrol (0.1 mL/kg), Gadoterate (0.2 mL/kg)

---

## ⚙️ Preprocessing

- **DWI Processing**: Eddy correction + DTIFIT (FSL 6.0.2) → MD, AD, RD, FA maps  
- **Registration**: All contrasts resampled to T2/FLAIR space (1 mm³) via ANTs  
- **Skull-stripping**: Deep learning model ([GitHub](https://github.com/ecalabr/brain_mask))  

---

## 🧩 Tumor Segmentation

- Initial segmentation using ensemble models from BraTS challenge  
- Manual corrections by radiologists, reviewed by experts  
- Segmented regions:
  - Enhancing tumor  
  - Non-enhancing/necrotic tumor  
  - FLAIR abnormality (edema)

---

## 🔬 Research Impact

UCSF-PDGM complements existing glioma datasets and enhances opportunities for:

- **AI-based tumor segmentation**
- **Radiogenomic prediction of IDH and MGMT status**
- **Generalizable models** using standardized, high-resolution imaging

We hope this dataset will advance AI applications in neuro-oncology and inspire new methods for glioma analysis.

## Release Link
https://github.com/data-nih/tcia/releases/tag/ucsf-pdgm
