# Naive Bayes Classification

## Instructions for Running the Source Code

### Running the Code in Jupyter Notebook

1. **Open the Jupyter Notebook:**
   - Ensure that you have Jupyter Notebook installed on your system. 
   - Navigate to the directory containing the `data-mining-NBC-local.ipynb` file.
2. **Run the Notebook:**
   - open jupyter notebook, you can run the cells sequentially.
   - To run all cells in the notebook, you can go to the menu and click on `Kernel` > `Restart & Run All`.

### Running the Code on Kaggle

1. **Upload to Kaggle:**
   - Log in to your [Kaggle](https://www.kaggle.com/) account.
   - You can upload the `data-mining-kaggle.ipynb` file directly to Kaggle by clicking on `File` > `Import Notebook`.

2. **Run the Notebook on Kaggle:**
   - After uploading, the notebook will open in the Kaggle editor.
   - Run the cells by clicking on the 'Run All' button at the top of the notebook.

Please ensure that you have the necessary data files in the environment where you are running the notebook.

## Executive Summary

This document outlines a comprehensive approach to addressing the challenge of imbalanced datasets in Data Mining. My focus is on a specific case study involving the use of Large Language Model (LLM) generated data to improve an existing dataset of prompts and essays. The project demonstrates how Naive Bayes classification work on different values of smoothing.

## Project Overview

The project started with the analysis of two distinct datasets: `train_essays.csv` and `train_prompts.csv`. My initial task involved the merging of these datasets based on a shared `prompt_id`, followed by a division into training and development sets. This process was critical for modeling.

## Addressing Imbalance with LLM-Generated Data

Recognizing the imbalance in the original dataset, I employed a Large Language Model to generate approximately 450 new data entries. This step was pivotal in creating a balanced dataset, thereby reducing the risk of model bias and enhancing the robustness of my upcoming analyses.

## Data Preprocessing and Feature Engineering

The preprocessing phase involved a systematic approach to tokenization and vocabulary building. By breaking down essays into individual words and constructing a comprehensive vocabulary, I established a solid foundation for feature extraction, essential for the effective application of my Naive Bayes Classifier.

## Implementation of Naive Bayes Classifier

At the core of my solution is the Naive Bayes Classifier, optimized for text data classification. Making it adept at distinguishing between human-generated and LLM-generated essays, employing a combination of word frequency analysis and conditional probability calculations.

### Integration of Smoothing Techniques

A key enhancement to my classifier was the incorporation of smoothing techniques. This approach is vital for addressing the limitations posed by unseen words in the training data, ensuring that my model remains accurate and reliable even when encountering new or rare words.

## Model Evaluation and Results

The performance of my classifier was rigorously evaluated using the development dataset. I focused on the impact of different smoothing values on the model's accuracy, revealing critical insights into the optimal configuration of my classifier for this specific dataset.

## Insights and Conclusions

My analysis yielded valuable insights, particularly in identifying key predictive words for each class. This aspect of the study not only enhanced my understanding of the model's decision-making process but also provided linguistic insights into the differences between human and LLM-generated texts. On kaggle I got a score of 62.5 and on my local machine with 450 LLM samples I got an accuracy of 76.98%

In conclusion, Naive Bayes Classifier augmented with smoothing techniques, proved to be a tool in text classification among human and LLM generated essays.