# ALPACA

### Augmenting Multi-Label Prediction via Structured Data in Addition to Convolutional Attention

The remote repository for this project can be found on [github.com/tlaifer/caml-mimic](https://github.com/tlaifer/caml-mimic)

It was forked from the initial caml-mimic implemenation [github.com/jamesmullenbach/caml-mimic](https://github.com/jamesmullenbach/caml-mimic)
- original documentation is linked [here](docs/caml-mimic-readme.md)

## Adaptations from existing repository
- add alpaca model, augment dataloader, training 
- add static feature generation
- upgrade to gensim 3.6.0
- upgrade to pytorch 1.8.1

## Data Pre-Processing & Model Training

All data pre-processing & model training steps can be found in the provided [project-notebook](project-notebook.ipynb), which is broken into 3 parts
1. MIMIC-III noteevents pre-processing
2. MIMIC-III demographic, meds pre-processing
3. Model Training

The notebook as sample codes for training a new model. One may run `python training.py -h` for a full list of input arguments and flags.

## Running on Remote

After data setup is complete, we leveraged google colab for model training & tuning at [this link](https://colab.research.google.com/drive/1gDP0JGmkB5GgK3jdnH1Zk25NtI-wUC2r?usp=sharing)
## Data & File Setup
One needs access to the MIMIC-III dataset for this project, which can be found here: https://mimic.physionet.org/gettingstarted/access/

The primary data sets of interest are:

1. NOTEEVENTS.csv
2. DIAGNOSES_ICD.csv
3. PROCEDURES_ICD.csv
4. D_ICD_DIAGNOSES.csv
5. D_ICD_PROCEDURES.csv
6. ADMISSIONS.csv
7. PRESCRIPTIONS.csv

Where data sets 1-5 were used in the initial paper, and 6-7 are introduced for alpaca.

ensure the files are saved in the following way:

```
mimicdata
|   D_ICD_DIAGNOSES.csv
|   D_ICD_PROCEDURES.csv
|   ICD9_descriptions (already in repo)
└───mimic3/
|   |   NOTEEVENTS.csv
|   |   DIAGNOSES_ICD.csv
|   |   PROCEDURES_ICD.csv
|   |   ADMISSIONS.csv
|   |   PRESCRIPTIONS.csv
|   |   *_hadm_ids.csv (already in repo)
```

note, static feature data is saved already in
- meds_feature_dict.json (meds)
- static_feature_dict.json (static)
## Trained Models
Models trained as part of this report are in the `project_models` directory.