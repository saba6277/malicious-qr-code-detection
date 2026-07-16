\# Dataset



\## Source



The experiments use the \*\*Benign and Malicious QR Codes\*\* dataset available from Kaggle.



https://www.kaggle.com/datasets/samahsadiq/benign-and-malicious-qr-codes



\---



\## Dataset Organization



After downloading, organize the dataset as follows:



```text

Data/

└── raw/

&#x20;   ├── benign/

&#x20;   └── malicious/

```



\---



\## Dataset Preparation



Running



```

01\_dataset\_preparation.ipynb

```



automatically performs:



\- Dataset loading

\- Image preprocessing

\- Metadata generation

\- Dataset integrity verification

\- Train/validation/test splitting



\---



\## Generated Files



The notebook automatically generates:



\- Processed datasets

\- Metadata files

\- Dataset statistics

\- Train/validation/test splits



These files are stored under



```text

Data/processed/

Data/metadata/

```

