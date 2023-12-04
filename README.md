# Naive Bayes Classification
## Introduction
Many studies have been carried out recently in the area of document classification, with a focus on applications such as spam filtering, email categorisation, website classification, knowledge repository creation, and ontology mapping.
However, having a human read through and accurately categorise an item by hand takes a lot of time and labor. Recent text mining research has shown increased interest in automatic document categorisation studies as a means of addressing this challenge[1]. Because of its ease of use throughout both the training and classification stages, the Naïve Bayes text classifier has gained widespread usage. Numerous researchers have demonstrated that, despite being less accurate than other discriminative algorithms (like SVM), it is nevertheless sufficient for text classification across a wide range of domains. Using naïve Bayes models, every attribute
 
Comparing Naïve Bayes models to other text classifiers, they are more computationally efficient since they permit each attribute to contribute equally and independently from other attributes to the final result.

## Summary
This document outlines a comprehensive approach to addressing the challenge of imbalanced datasets in Data Mining. The focus is on a specific case study involving the use of Large Language Model (LLM) generated data to improve an existing dataset of prompts and essays. The project demonstrates how Naive Bayes classification works on different values of smoothing.

## Project Overview
The project started with the analysis of two distinct datasets: `train_essays.csv` and `train_prompts.csv`. The initial task involved merging these datasets based on a shared `prompt_id`, followed by a division into training and development sets. This process was critical for modeling.

### Addressing Imbalance with LLM-Generated Data
Recognizing the imbalance in the original dataset, a Large Language Model was employed to generate approximately 450 new data entries. This step was pivotal in creating a balanced dataset, thereby reducing the risk of model bias and enhancing the robustness of the analyses.

### Data Preprocessing and Feature Engineering
The preprocessing phase involved a systematic approach to tokenization and vocabulary building. By breaking down essays into individual words and constructing a comprehensive vocabulary, a solid foundation for feature extraction was established, essential for the effective application of the Naive Bayes Classifier.

### Implementation of Naive Bayes Classifier
At the core of the solution is the Naive Bayes Classifier, optimized for text data classification. It is adept at distinguishing between human-generated and LLM-generated essays, employing a combination of word frequency analysis and conditional probability calculations.

Word Frequency Analysis

Counters Initialization:
countPerWord keeps track of how many times each word appears across all essays.
countPerClassAndWord is a nested dictionary. For each class (human-generated or LLM-generated), it records the frequency of each word.

Iterating Through the Data:
The for loop iterates over each essay in the training data.
tokenize(entry['text']) breaks down each essay into individual words.

Counting Word Frequencies:
The inner loop iterates over unique words in each essay.
If a word is in our predefined vocabulary, its count is incremented in both countPerWord and countPerClassAndWord.

Conditional Probability

Word Probability Calculation:
wordProbability maps each word to its likelihood of occurrence in the entire dataset.
It's calculated by dividing the frequency of each word by the total number of entries.

Class-Conditional Word Probability:
classWordProbability is a nested dictionary where each class (human-generated or LLM-generated) has its own dictionary mapping words to their probabilities.
For each class, the probability of a word is the frequency of that word in the class divided by the total number of entries in that class.

### Integration of Smoothing Techniques
A key enhancement to the classifier was the incorporation of smoothing techniques. This approach is vital for addressing the limitations posed by unseen words in the training data, ensuring that the model remains accurate and reliable even when encountering new or rare words.


### Model Evaluation and Results
The performance of the classifier was rigorously evaluated using the development dataset. The focus was on the impact of different smoothing values on the model's accuracy, revealing critical insights into the optimal configuration of the classifier for this specific dataset.

Top Predictive Words for Human: [('plumer', 1.3333333333333335), ('know', 1.3333333333333335), ('decides', 1.3333333333333335), ('official', 1.3333333333333335), ('myself', 1.3333333333333335), ('could', 1.3333333333333335), ('he', 1.3333333333333335), ('says', 1.3333333333333335), ('you', 1.3333333333333335), ('my', 1.3333333333333335)]
Top Predictive Words for LLM: [('planetary', 4.0), ('missions', 4.0), ('debris', 4.0), ('captivate', 4.0), ('discovery', 4.0), ('collaboration', 4.0), ('imagination', 4.0), ('exploration', 4.0), ('poised', 4.0), ('cryptography', 4.0)]

### Conclusions
The analysis yielded valuable insights, particularly in identifying key predictive words for each class. This aspect of the study not only enhanced the understanding of the model's decision-making process but also provided linguistic insights into the differences between human and LLM-generated texts. On Kaggle, a score of 62.5 was achieved, and on a local machine with 450 LLM samples, an accuracy of 76.98% was obtained.

### References
Thanh, T. and Pham Minh Thu (2020). Classification optimization for training a large dataset with Naïve Bayes. Journal of Combinatorial Optimization, 40(1), pp.141–169. doi:https://doi.org/10.1007/s10878-020-00578-0.
‌
 
Soria, D., Garibaldi, J.M., Ambrogi, F., Biganzoli, E.M. and Ellis, I.O. (2011). A ‘non-parametric’ version of the naive Bayes classifier. Knowledge-Based Systems, 24(6), pp.775–784. doi:https://doi.org/10.1016/j.knosys.2011.02.014.
‌
Dai, W., Xue, G.-R., Yang, Q. and Yu, Y. (n.d.). Transferring Naive Bayes Classifiers for Text Classification. [online] Available at: https://cdn.aaai.org/AAAI/2007/AAAI07-085.pdf [Accessed 3 Dec. 2023].
‌
ieeexplore.ieee.org. (n.d.). Decision for Vertical Handover based on Naive Bayes Algorithm | IEEE Conference Publication | IEEE Xplore. [online] Available at: https://ieeexplore.ieee.org/abstract/document/9036820 [Accessed 3 Dec. 2023].

## Instructions for Running the Source Code

### Running the Code in Jupyter Notebook
1. **Open the Jupyter Notebook**:
    - Ensure that Jupyter Notebook is installed on your system.
    - Navigate to the directory containing the `data-mining-NBC-local.ipynb` file.

2. **Run the Notebook**:
    - Open Jupyter Notebook, you can run the cells sequentially.
    - To run all cells in the notebook, go to the menu and click on `Kernel > Restart & Run All`.

### Running the Code on Kaggle
1. **Upload to Kaggle**:
    - Log in to your Kaggle account.
    - Upload the `data-mining-kaggle.ipynb` file directly to Kaggle by clicking on `File > Import Notebook`.

2. **Run the Notebook on Kaggle**:
    - After uploading, the notebook will open in the Kaggle editor.
    - Run the cells by clicking on the 'Run All' button at the top of the notebook.
    - Ensure that you have the necessary data files in the environment where you are running the notebook.
