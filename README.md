# What can we learn about book banning in the United States?
### Tracked by PEN America and the American Library Association (from July 1, 2021 - June 30, 2022)

You can read the original report [here](https://pen.org/report/banned-usa-growing-movement-to-censor-books-in-schools/).
You can view their original banned book list dataset [here](https://docs.google.com/spreadsheets/d/1hTs_PB7KuTMBtNMESFEGuK-0abzhNxVv4tgpI5-iKe8/edit#gid=660619424) (also linked in the original report).

## Introduction

In this project, we are applying the following techniques on two custom datasets:

- topic modeling (unsupervised learning)
- sentiment analysis (supervised learning)
- visual similarity (transfer learning)

## Datasets

We scraped or manually entered the following custom datasets:

1) **Goodreads metadata on a list of banned books** in the United States (2021 to 2022) as provided by the American Library Association and PEN America understand book banning in the United States as noted by the American Library Association (ALA) from 2021 to 2022. We manually entered this data into a csv file to comply with [Goodreads Terms of Use](https://www.goodreads.com/about/terms) which asks us not scrape their site and not to redistribute their data for commercial purposes. We are using this data solely for educational purposes. We merged this dataset with the original banned book list from PEN America and the ALA from [above](https://docs.google.com/spreadsheets/d/1hTs_PB7KuTMBtNMESFEGuK-0abzhNxVv4tgpI5-iKe8/edit#gid=660619424).

2) **Amazon.com reviews on the same list of banned books** (to provide a small window into opinion mining and sentiment around these banned books as it pertains to Amazon.com reviews). These reviews were only scraped from customers commenting in the United States. We followed [Amazon.com Terms of Use](https://www.amazon.com/gp/help/customer/display.html?nodeId=202140280) policy for web scraping by running our scraper in small batches during off-peak hours. We are also not using the data for commercial use and solely for educational purposes. 

You can easily access and run our custom Amazon.com web scraper in Colab. [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1ezec1HS3rCFXAgVp_qgBqMCxO5V3zP9A?authuser=4#scrollTo=zvCIC6Nxg2Ne) 

We are utilizing Google Colab (code / machine learning for reproducibility and free GPU access), Github (repository), and Google Drive (for large file storage).

![Screenshot of integration of Google Colab, Github, and Google Drive](https://drive.google.com/uc?id=1FtOW4QDqXzs0HWF2__9bBFdLCQibfHhE)

## Exploratory Data Analysis

We conducted some EDA on our Goodreads and ALA metadata as well as our Amazon.com review dataset. Additionally, we applied Scattertext to our Goodreads and ALA metadata to explore topics banned (and their ban frequencies) by either: 1) parental or political pressure or 2) through a written, formal book ban process.

## Topic Modeling (Goodreads + ALA metadata + Amazon.com review dataset)

We tried a few topic modeling methodologies: NMF, LDA, Top2Vec, and BERTopic. **BERTopic** is our best approach so far.

## Visual Similarity (Goodreads + ALA metadata)

- Yale Digital Humanities Lab's PixPlot

## Sentiment Analysis (Amazon.com review dataset)

## Appendix

## Statement of Work

- Joan | 
- Alexis |
- B | Amazon.com banned book reviews web scraper data acquisition/cleaning, banned book metadata acquisition/cleaning, cusotm script to download banned book cover images, LDA & BERTopic modeling, transfer learning (visual similarity) & PixPlot, basic EDA, proof of concept visual similarity recommendation system (Appendix)




