Statistical Analysis on E-Commerce Reviews, with Sentiment Classification using Bidirectional Recurrent Neural Network (RNN)
===

![](https://img.shields.io/badge/DOI-cs.CL%2F1805.03687-blue.svg)
[![DOI](https://zenodo.org/badge/121918154.svg)](https://zenodo.org/badge/latestdoi/121918154)

The full paper on this project may be read at [ResearchGate](https://goo.gl/1z43ax), [Academia.edu](https://www.academia.edu/36114302/Statistical_Analysis_on_E-Commerce_Reviews_with_Sentiment_Classification_using_Bidirectional_Recurrent_Neural_Network), and [arXiv.org](https://arxiv.org/abs/1805.03687).

The scripts used for data visualization and the [dataset](https://www.kaggle.com/nicapotato/womens-ecommerce-clothing-reviews) used were from [Nick Brooks](https://github.com/nicapotato)' Kaggle [report on Women's Clothing E-commerce Review](https://www.kaggle.com/nicapotato/guided-numeric-and-text-exploration-e-commerce/notebook).

## Abstract

Understanding customer sentiments is of paramount importance in marketing strategies today. Not only will it give companies an insight as to how customers perceive their products and/or services, but it will also give them an idea on how to improve their offers. This paper attempts to understand the correlation of different variables in customer reviews on a women clothing e-commerce, and to classify each review whether it recommends the reviewed product or not and whether it consists of positive, negative, or neutral sentiment. To achieve these goals, we employed univariate and multivariate analyses on dataset features except for review titles and review texts, and we implemented a bidirectional recurrent neural network (RNN) with long-short term memory unit (LSTM) for recommendation and sentiment classification. Results have shown that a recommendation is a strong indicator of a positive sentiment score, and vice-versa. On the other hand, ratings in product reviews are fuzzy indicators of sentiment scores. We also found out that the bidirectional LSTM was able to reach an F1-score of 0.88 for recommendation classification, and 0.93 for sentiment classification.

## Citation

To cite the repository/software, kindly use the following BibTex entry:

```
@misc{abien_fred_agarap_2018_1188376,
  author       = {Abien Fred Agarap},
  title        = {AFAgarap/ecommerce-reviews-analysis: v0.1.0-alpha},
  month        = mar,
  year         = 2018,
  doi          = {10.5281/zenodo.1188376},
  url          = {https://doi.org/10.5281/zenodo.1188376}
}
```

## Usage

If Jupyter Notebook or Jupyter Lab is not installed, run the following code

```
# installing jupyter notebook
pip3 install jupyter
```

```
# installing jupyter lab
pip3 install jupyterlab
```

Note that just either one of the packages above may be used. Installing both of them is not a requirement. 

The notebook for the data visualizations and text classification in this paper is available [here](https://github.com/AFAgarap/ecommerce-reviews-analysis/blob/master/Analysis%20on%20E-Commerce%20Reviews%2C%20with%20Sentiment%20Classification%20using%20Bidirectional%20Recurrent%20Neural%20Network%20(RNN).ipynb).

## Results

All experiments in this study were conducted on a laptop computer with Intel Core(TM) i5-6300HQ CPU @ 2.30GHz x 4, 16GB of DDR3 RAM, and NVIDIA GeForce GTX 960M 4GB DDR5 GPU. The review texts and labels (*recommendation indicator*) in the [dataset](https://www.kaggle.com/nicapotato/womens-ecommerce-clothing-reviews) were partitioned in the following fashion: 60% for training dataset, 20% for the validation dataset, and 20% for the testing dataset. The sentiment label for each review text were tagged using [NLTK](https://www.nltk.org/)'s sentiment analyzer.

|Task|Test Accuracy|Test Loss|
|----|-------------|---------|
|Recommendation classification|~88.2678%|~0.572342|
|Sentiment classification|~92.8414%|~0.453205|

**Table 1. Test Accuracy and Test Loss using Bidirectional RNN with LSTM.**

|Class|Precision|Recall|F1-Score|Support|
|-----|---------|------|--------|-------|
|Not recommended|0.70|0.65|0.68|847|
|Recommended|0.92|0.94|0.93|3679|
|Average/Total|0.88|0.88|0.88|4526|

**Table 2. Statistical Report on Recommendation Classification using Bidirectional LSTM.**

|Class|Precision|Recall|F1-Score|Support|
|-----|---------|------|--------|-------|
|Negative|0.47|0.50|0.49|289|
|Neutral|0.31|0.18|0.23|22|
|Positive|0.96|0.96|0.96|4215|
|Average/Total|0.93|0.93|0.93|4526|

**Table 3. Statistical Report on Sentiment Classification using Bidirectional LSTM.**

The dataset used had an imbalanced frequency distribution for classes in *recommendation indicator*, and through NLTK sentiment analyzer, classes in review *sentiment*. It is noticeable that the model used had relatively better predictive performance towards the class with the highest frequency distribution, i.e. *recommended* and *positive sentiment*. 

## License

```
Copyright 2018 Abien Fred Agarap

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```
