# AI-driven Healthcare

A collection of applied machine-learning projects in medical imaging and clinical diagnosis, spanning computer vision on CT/mammography and radiomics-based classification.

## Contents

| # | Project | Domain | Context |
|---|---|---|---|
| 1 | [`abdomen-multi-disease-detection/`](abdomen-multi-disease-detection/) | Abdominal CT — multi-disease detection | TEKNOFEST 2022, Healthcare AI Competition |
| 2 | [`mammography-abnormality-detection/`](mammography-abnormality-detection/) | Screening mammography — BI-RADS / breast composition / tissue cropping | TEKNOFEST 2023, Healthcare AI Competition |
| 3 | [`papilodem-radiomics/`](papilodem-radiomics/) | Fundus/OCT radiomics — papilledema classification | Üsküdar University, AI course final project |

## Projects

### [Abdomen Multi-Disease Detection](abdomen-multi-disease-detection/)

Detects six acute abdominal conditions (appendicitis, cholecystitis, pancreatitis, kidney/ureteral stone, diverticulitis, aortic aneurysm/rupture/dissection) from CT imaging. Developed for TEKNOFEST 2022's *"Computer Vision-Based Disease Detection for the Abdomen Region"* category.

### [Mammography Abnormality Detection](mammography-abnormality-detection/)

Preprocessing and tissue-cropping pipeline (pectoral-muscle removal, CLAHE enhancement, ROI cropping, YOLOv5-based breast-tissue detector) built for TEKNOFEST 2023's *"BI-RADS Category and Breast Composition Estimation in Screening Mammography"* category.

### [Papilledema Radiomics](papilodem-radiomics/)

Patient-level binary classification of papilledema vs. normal optic discs from 746 radiomic features, with MRMR feature selection, Optuna-tuned ensemble models, calibration, and SHAP explainability.

## License

Each project folder retains its own license where applicable (see the `LICENSE` file inside `mammography-abnormality-detection/`). Original content in this repository is licensed under [MIT](LICENSE).
