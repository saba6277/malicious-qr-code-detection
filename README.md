\# A Dual Representation Framework for Malicious QR Code Detection Using Fused Feature Learning and Deep Visual Modeling



<p align="center">



!\[Python](https://img.shields.io/badge/Python-3.11-blue)



!\[TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-orange)



!\[PyTorch](https://img.shields.io/badge/PyTorch-2.x-red)



!\[LightGBM](https://img.shields.io/badge/LightGBM-Baseline-green)



!\[Status](https://img.shields.io/badge/Status-Major%20Revision-yellow)



!\[License](https://img.shields.io/badge/License-MIT-lightgrey)



</p>



> 📄 \*\*Paper\*\*

>

> \*\*A Dual Representation Framework for Malicious QR Code Detection Using Fused Feature Learning and Deep Visual Modeling\*\*

>

> \*\*Repository Status:\*\* Private Research Repository

>

> \*\*Manuscript Status:\*\* Major Revision





\## ✨ Key Features



\- Dual-representation malicious QR-code detection framework



\- Four evaluated learning models



\- Handcrafted and deep feature learning



\- Comprehensive dataset validation



\- Artifact analysis



\- Robustness evaluation



\- Fully reproducible experimental pipeline





\## Overview



Malicious Quick Response (QR) codes have become an increasingly common attack vector for phishing, malware distribution, credential theft, and other cyber threats. While many existing detection approaches rely on decoding the embedded content before analysis, this project investigates whether malicious QR codes can be identified directly from their visual appearance using modern machine learning and deep learning techniques.



This repository provides the complete implementation of a dual-representation framework that combines handcrafted feature engineering with deep visual representation learning for malicious QR code detection. Two complementary learning paradigms are explored: a feature-based branch using TabNet and an image-based branch using MobileNetV2.



To provide a comprehensive experimental evaluation, two additional baseline models are implemented:



\- LightGBM

\- Lightweight CNN (reconstructed from Mishra \& Sarkhi)



Beyond model comparison, the repository includes extensive validation experiments designed to improve the reliability and reproducibility of the study. These include duplicate detection, label-shuffle sanity checks, dataset artifact analysis, metadata-only baselines, and robustness evaluation under multiple realistic image degradations.



All experiments are organized into a reproducible seven-notebook pipeline that follows the complete workflow from dataset preparation through final model evaluation and reliability analysis.



\---



\## 📑 Table of Contents

\## 📁 Repository Structure

\## 🔄 Experimental Workflow

\## 📓 Notebook Description

\## 🤖 Models Included

\## 📂 Dataset

\## ⚙️ Installation

\## ▶️ Reproducing the Experiments

\## 📊 Experimental Results

\## 💻 Hardware and Software

\## 📖 Citation

\## 📜 License

\## 👥 Authors

\## 📧 Contact



\---



\## 📁 Repository Structure



```text

malicious-qr-code-detection/

│

├── Data/

│   ├── raw/

│   ├── processed/

│   └── metadata/

│

├── Models/

│

├── Results/

│

├── Documentation/

│

├── Notebooks/

│   ├── 01\_dataset\_preparation.ipynb

│   ├── 02\_feature\_extraction\_and\_fusion.ipynb

│   ├── 03\_tabnet.ipynb

│   ├── 04\_mobilenetv2.ipynb

│   ├── 05\_lightgbm\_baseline.ipynb

│   ├── 06\_lightweight\_cnn\_baseline.ipynb

│   └── 07\_dataset\_validation\_and\_reliability.ipynb

│

├── README.md

├── requirements.txt

├── environment.yml

├── LICENSE

└── CITATION.cff

```



\### Top-Level Directories



| Folder | Description |

|---------|-------------|

| \*\*Data\*\* | Original dataset, processed datasets, and metadata files generated during preprocessing. |

| \*\*Notebooks\*\* | Complete experimental pipeline, from dataset preparation to reliability analysis. |

| \*\*Models\*\* | Saved trained models and model checkpoints. |

| \*\*Results\*\* | Performance metrics, prediction files, figures, confusion matrices, and evaluation outputs. |

| \*\*Documentation\*\* | Supplementary documentation describing reproducibility, datasets, and notebooks. |



\---



\## 🔄 Experimental Workflow



```text

&#x20;               Dataset

&#x20;                  │

&#x20;                  ▼

&#x20;     Dataset Preparation

&#x20;                  │

&#x20;                  ▼

&#x20;Feature Extraction \& Fusion

&#x20;         ┌────────┴────────┐

&#x20;         ▼                 ▼

&#x20;     TabNet          MobileNetV2

&#x20;         │                 │

&#x20;         ├──────┐    ┌─────┤

&#x20;         ▼      ▼    ▼     ▼

&#x20;    LightGBM  Mishra CNN

&#x20;                │

&#x20;                ▼

&#x20;       Performance Evaluation

&#x20;                │

&#x20;                ▼

&#x20;   Dataset Validation \& Reliability

```



\---



\## 📓 Notebook Description



The repository is organized as a sequential seven-notebook pipeline. Each notebook performs a specific stage of the experimental workflow and should be executed in numerical order.



| Notebook | Purpose | Main Outputs |

|-----------|---------|--------------|

| \*\*01\_dataset\_preparation.ipynb\*\* | Loads the dataset, performs preprocessing, verifies data integrity, generates metadata, and creates the train/validation/test splits. | Clean dataset, metadata files, dataset splits |

| \*\*02\_feature\_extraction\_and\_fusion.ipynb\*\* | Extracts handcrafted QR-code features, performs feature fusion, normalization, and prepares the feature matrix used by the learning models. | Fused feature matrix |

| \*\*03\_tabnet.ipynb\*\* | Trains and evaluates the proposed TabNet classifier using the fused feature representation. | Trained TabNet model, predictions, evaluation metrics |

| \*\*04\_mobilenetv2.ipynb\*\* | Fine-tunes MobileNetV2 on QR-code images and evaluates the image-based deep learning model. | Trained MobileNetV2 model, predictions, evaluation metrics |

| \*\*05\_lightgbm\_baseline.ipynb\*\* | Implements the LightGBM baseline for comparison with the proposed methods. | LightGBM model, feature importance, evaluation metrics |

| \*\*06\_lightweight\_cnn\_baseline.ipynb\*\* | Reconstructs and evaluates the lightweight CNN architecture proposed by Mishra \& Sarkhi. | CNN model, training history, evaluation metrics |

| \*\*07\_dataset\_validation\_and\_reliability.ipynb\*\* | Performs duplicate detection, leakage analysis, artifact analysis, sanity checks, and robustness evaluation. | Validation reports, robustness results, reliability analysis |



\---



\## 🤖 Models Included



Four learning models are implemented and evaluated in this repository. Two models constitute the proposed framework, while two additional models are included as baseline methods for comparative evaluation.



| Model | Category | Learning Strategy | Role |

|--------|----------|-------------------|------|

| \*\*TabNet\*\* | Proposed | Feature-based deep learning | Proposed model |

| \*\*MobileNetV2\*\* | Proposed | Image-based transfer learning | Proposed model |

| \*\*LightGBM\*\* | Baseline | Gradient boosting | Classical machine-learning baseline |

| \*\*Lightweight CNN (Mishra \& Sarkhi)\*\* | Baseline | Convolutional neural network | Deep-learning baseline |



The proposed framework investigates two complementary representations of malicious QR codes. TabNet operates on fused handcrafted features extracted from QR-code images, whereas MobileNetV2 learns directly from image pixels through transfer learning. The LightGBM and lightweight CNN implementations provide reference baselines to assess the effectiveness of the proposed approaches.



\---



\## 📂 Dataset



The experiments were conducted using the \*\*Benign and Malicious QR Codes\*\* dataset, which is publicly available through Kaggle.



\### Dataset Summary



| Property | Value |

|----------|-------|

| Task | Binary image classification |

| Classes | Benign QR codes / Malicious QR codes |

| Total images | 200,000 |

| Class balance | Balanced |

| Image format | PNG |

| Source | Kaggle |



\### Download



The dataset is \*\*not included\*\* in this repository because of its size and licensing restrictions.



Download it directly from Kaggle:



https://www.kaggle.com/datasets/samahsadiq/benign-and-malicious-qr-codes



After downloading, organize the dataset as follows:



```text

Data/

└── raw/

&#x20;   ├── benign/

&#x20;   └── malicious/

```



Running \*\*01\_dataset\_preparation.ipynb\*\* will automatically generate:



\- processed datasets

\- metadata files

\- train/validation/test splits

\- preprocessing reports



These generated files are stored inside the `Data/processed/` and `Data/metadata/` directories.



\---



\## ⚙️ Installation



\### Prerequisites



Before running the notebooks, ensure that the following software is installed:



\- Python 3.11 (or later)

\- Git

\- Jupyter Notebook or JupyterLab

\- Google Colab (optional)

\- CUDA-compatible GPU (recommended for deep learning notebooks)



\### Clone the Repository



```bash

git clone https://github.com/saba6277/malicious-qr-code-detection.git

cd malicious-qr-code-detection

```



\### Install Required Packages



```bash

pip install -r requirements.txt

```



Alternatively, if you use Conda:



```bash

conda env create -f environment.yml

conda activate malicious-qr

```



\---



\## ▶️ Reproducing the Experiments



The notebooks should be executed sequentially because each stage depends on the outputs generated by previous notebooks.



| Step | Notebook | Description |

|------|----------|-------------|

| 1 | 01\_dataset\_preparation.ipynb | Dataset preparation and preprocessing |

| 2 | 02\_feature\_extraction\_and\_fusion.ipynb | Feature extraction and fusion |

| 3 | 03\_tabnet.ipynb | Proposed feature-based model |

| 4 | 04\_mobilenetv2.ipynb | Proposed image-based model |

| 5 | 05\_lightgbm\_baseline.ipynb | Machine-learning baseline |

| 6 | 06\_lightweight\_cnn\_baseline.ipynb | CNN baseline |

| 7 | 07\_dataset\_validation\_and\_reliability.ipynb | Validation, artifact analysis, and robustness evaluation |



\---



\## 📊 Experimental Results



The repository reproduces all experiments presented in the accompanying manuscript, including:



\- Feature-based learning using TabNet

\- Image-based learning using MobileNetV2

\- LightGBM baseline

\- Lightweight CNN baseline

\- Dataset validation and integrity analysis

\- Artifact analysis

\- Robustness evaluation



Detailed quantitative results are reported in the manuscript.



\---



\## 💻 Hardware and Software



Experiments were developed and evaluated using:



| Component | Specification |

|----------|---------------|

| Language | Python |

| Deep Learning | TensorFlow / Keras |

| Machine Learning | LightGBM |

| Additional Frameworks | PyTorch, OpenCV, Scikit-learn |

| Development Platform | Google Colab |



\---



\## 📖 Citation



If you use this repository in your research, please cite the associated manuscript once it becomes publicly available.



GitHub users may also use the repository citation provided in:



```text

CITATION.cff

```



\---



\## 📜 License



This project is distributed under the MIT License.



See the `LICENSE` file for details.



\---



\## 👥 Authors



\- \*\*Saba Hussein Rashid\*\* \*(Corresponding Author)\* — Tikrit University, Iraq

\- Aya Abdullateef Ezat — Northern Technical University, Iraq

\- Hiba Hani Rahim — Tikrit University, Iraq

\- Noor Walid Khalid — Tikrit University, Iraq



\---



\## 📧 Contact



\*\*Corresponding Author\*\*



Saba Hussein Rashid



\- ORCID: https://orcid.org/0009-0005-8239-7279

\- GitHub: https://github.com/saba6277



For questions related to the implementation, reproducibility, or the manuscript, please open a GitHub Issue after the repository becomes public.

