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

Note: We used these claims as a reference to classify the particular record as Fake or Non-Fake.

We applied pre-processing steps to clean the data, such as removing special characters. We utilized AI4Bharat tools such as IndicXlit for transliteration from code-mixed Hindi and English (Hinglish) to complete Hindi. Subsequently, we employed IndicTrans2 to translate the Hindi data to English.

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

## Data Pre-Processing and Embedding Extraction Workflow

![Data-Pre-Processing-Flow](https://github.com/Sai-Kartheek-Reddy/Hate-and-Fake-Speech-Detection/blob/main/2.%20Translation%20and%20Transliteration/Data%20Pre-Processing%20Steps.png)

## Multi-Tasking Model Architecture

After that, we built a shared-layer architecture where one layer is for processing hate data and another layer is for processing fake data, and we obtained the results.

## Data Loading and Preprocessing:

- It loads a dataset from an Excel file containing hate speech and fake content labels.
- Embeddings are loaded from a .pt file using PyTorch and converted to NumPy arrays.
- The labels for fake and hate speech are prepared and converted into NumPy arrays.
- The data is split into training and testing sets using train_test_split.

## Custom Dataset and Data Loaders:

- Defines a custom dataset class, MultiTaskDataset, to handle the embeddings and labels for both tasks.
- Creates data loaders for training and testing using the custom dataset.

## Model Architecture:

- Defines a multi-task classification model using TensorFlow.
- The model consists of two branches, one for detecting fake content and the other for detecting hate speech.
- Each branch has a dense layer with ReLU activation followed by a dense layer with a linear activation.

![Hate-and-Fake-Shared-Layer-Architecture](https://github.com/Sai-Kartheek-Reddy/Hate-and-Fake-Speech-Detection/blob/main/3.%20Encoder%20Only%20Models/Code/Model%20Architecture.jpg)


## Model Training:

- Compiles the model using hinge loss as the loss function and Adam optimizer.
- Trains the model for a specified number of epochs.
- Calculates and stores metrics such as accuracy, precision, recall, and F1 score for each epoch.

## Evaluation and Metrics:

- Evaluates the model on the test set and calculates metrics such as accuracy, precision, recall, and F1 score for both tasks.
- Tracks the highest F1 score and the epoch at which it occurred for each task.
- Prints classification reports for both tasks and the overall F1 score for the test data.

## Visualization:

- Plots the accuracy and F1 score over epochs for both tasks.
