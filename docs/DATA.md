# How to obtain the CICIoT2023 dataset

This repository does **not** redistribute the CICIoT2023 dataset.
The dataset is provided by the Canadian Institute for Cybersecurity (CIC) at the
University of New Brunswick under a license requiring individual user registration.

## Steps

1. Visit the official dataset page:
   **https://www.unb.ca/cic/datasets/iotdataset-2023.html**
2. Click **"Download the dataset"** which links to:
   **http://cicresearch.ca/IOTDataset/CIC_IOT_Dataset2023/**
3. Fill out CIC's form and accept the terms.
4. Download **`CSV.zip`** (~1.33 GB compressed). Do **not** download the PCAP archive.
5. Upload to your Google Drive at
   `MyDrive/composite_resilience_framework/data/raw/CSV.zip`.
6. Run the notebooks in order.

## Dataset summary

- 33 attack types in 7 categories plus benign traffic
- 105 real IoT devices
- 46,776,700 labeled network flows
- 39 numeric features per flow

## Data hygiene note

CICIoT2023 contains a small number of `inf` values in the `Rate` feature.
Notebook 04 documents the percentile-based replacement procedure used here;
the cleaning record is saved as `results/data_cleaning_record.json`.
