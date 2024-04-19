# Hate-Speech-and-Fake-Content-Using-a-Cluster-Based-Approach

## Project Overview


## Data Collection and Pre-processing

In this project, we have scraped data from Twitter and YouTube based on the following claims:

- China is using corona as a biological weapon.
- Tablighi jamat using COVID-19 as biological terrorism.
- Farmer protest link to Khalistan.
- Wrestler protest.
- Shaheen Bagh women getting paid CAA.
- GPS chips installed in 2000 notes.
- Hindus are under threat.
- Pathan movie insulting Hindu.
- Adani and Edinburgh report.

We applied pre-processing steps to clean the data, such as removing special characters. We utilized AI4Bharat tools such as IndicXlit for transliteration from code-mixed Hindi and English (Hinglish) to complete Hindi. Subsequently, we employed IndicTrans2 to translate the Hindi data to English.

## Data Pre-Processing Flow



## Encoder-Only Model Utilization

We used various encoder models to extract embeddings from the data. These embeddings were then stored in ".pt" format (PyTorch Tensor) for further analysis.

### For English Text
- BERT
- XLM-Roberta
- ALBERT
- ELECTRA

### For Hindi Text

- mBERT (Multi-Lingual BERT)
- XLM-Roberta
- ALBERT

## Model Architecture

After that, we built a shared-layer architecture where one layer is for processing hate data and another layer is for processing fake data, and we obtained the results.
