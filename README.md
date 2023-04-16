
# What can we learn about book bans in the United States from 2021 to 2022?

# Option 1: Directions to Run Our Code from GitHub (Manually)

1. Open a terminal and run `git clone git@github.com:banned-books/project_banned_books.git`
2. Run in the terminal `cd project_banned_books`
3. Run in the terminal `pip3 install requirements.txt`
4. Download our four datasets (which are too large to store in GitHub): 
   - Banned books metadata [![Open In GDrive](https://img.shields.io/badge/Google-4285F4?logo=google&logoColor=fff&style=for-the-badge
)](https://drive.google.com/file/d/1AgDZCOacTbmMABem8ak9Tz_vkK4zk_Iu/view?usp=share_link)
   - Amazon.com reviews on banned books [![Open In GDrive](https://img.shields.io/badge/Google-4285F4?logo=google&logoColor=fff&style=for-the-badge
)](https://drive.google.com/file/d/1G6Up-3I5bBLIdBODLk3m72kjl_afASni/view?usp=share_link)
   - Original U.S. banned books list [![Open In GDrive](https://img.shields.io/badge/Google-4285F4?logo=google&logoColor=fff&style=for-the-badge
)](https://drive.google.com/file/d/1KPs4HP9GyRdAg7nQVV-CemhCcYiWgmMn/view?usp=share_link)
   - Banned book cover images [![Open In GDrive](https://img.shields.io/badge/Google-4285F4?logo=google&logoColor=fff&style=for-the-badge
)](https://drive.google.com/drive/folders/1RhDUK4whl85m9_qLSXFmG80UKFlZfhm0?usp=share_link)
5. Run in the terminal `cd data`
6. Run in the terminal `open .` to open the file location
7. Upload the three datasets in this `data` folder
8. Run in the terminal `cd ../ && jupyter notebook`
9. You can now run our code.

However, we recommend using Option 2 below to use free GPUs in Colab.

# Option 2: Run Our Code in Colab & GDrive (Click the Badges Below as You Read Along)

## Introduction

On September 2022, PEN America (Poets, Essayists, Novelists America) and the American Library Association (ALA) published a report investigating the uptick of book bans in the United States from July 1, 2021 to June 30, 2022.

You can read the original PEN America/ALA report [here](https://pen.org/report/banned-usa-growing-movement-to-censor-books-in-schools/).
You can view their original banned book list dataset [here](https://docs.google.com/spreadsheets/d/1hTs_PB7KuTMBtNMESFEGuK-0abzhNxVv4tgpI5-iKe8/edit#gid=660619424).


*Content warning: This report includes an analysis and discussion about an Amazon.com banned book reviews dataset that document topics such as racism, homophobia, sexual assault, genocide, suicide, trauma, and more.*


## Project Statement

In this project, we are applying the following data science techniques to gain a deeper insight into the book banning movement in the United States from 2021 to 2022:

- topic modeling (unsupervised learning)
- visual similarity (transfer learning)
- sentiment analysis (supervised learning)

We want to dive more into the question: **What can we learn about these banned books in the United States from 2021 to 2022? More specifically, can we use data science techniques to find topics in these banned books (topic modeling), notice visual cues/patterns of the book covers (visual similarity), and/or understand some public opinions (sentiment analysis on banned book Amazon reviews) that possibly illuminate more about this censorship movement?**

You can read the project blog post on [![Open In Medium](https://img.shields.io/badge/Medium-12100E?style=for-the-badge&logo=medium&logoColor=white)](TODO).

## Project Management

We are utilizing **Google Colab** (code / machine learning for reproducibility and free GPU access), **Github** (repository), and **Google Drive** (for large file storage).

![Screenshot of integration of Google Colab, Github, and Google Drive](https://drive.google.com/uc?id=1FtOW4QDqXzs0HWF2__9bBFdLCQibfHhE)

## Datasets

We retrieved the list of banned books from the original dataset of banned books tracked by PEN America & the ALA (from July 1, 2021 to June 30, 2022). The most important variables were the `title` and the `author` of the banned book. Additionally, we used the banned book's `origin_of_challenge` (i.e., whether a ban was created from either political and/or parental pressure or a formal, written challenge) and the `type_of_ban` (i.e., where the banned took place, such as in libraries, classrooms, both libraries and classrooms, or pending investigation). Finally, we manually added the `amazon_url` to the book details (to later feed these urls into our custom web scraper to grab book reviews). The original banned book list contained 1,648 unique banned book titles.

In addition to the PEN America/ALA dataset, we either scraped or manually entered data to build the following custom datasets:

- Goodreads metadata on the list of banned books: We manually entered this data into a `.csv` file to comply with [Goodreads Terms of Use](https://www.goodreads.com/about/terms) which asks us not to scrape their website and not to redistribute their data for commercial purposes. We are using this data solely for educational purposes. We merged this dataset with the original banned book list from PEN America and the ALA above. Our Goodreads dataset is comprised of the 1,648 banned books and the book's `title`, the `author`, the book cover `goodreads_image_url`, the `published_date` (when the book was first published), the book `description`, and the book `goodreads_tags`. You can view that dataset in our Google Drive. [![Open In GDrive](https://img.shields.io/badge/Google-4285F4?logo=google&logoColor=fff&style=for-the-badge
)](https://drive.google.com/file/d/1AgDZCOacTbmMABem8ak9Tz_vkK4zk_Iu/view?usp=share_link)

- Amazon.com reviews on the same list of banned books: We hope to provide a small window into opinion mining and sentiment around these banned books (as it pertains to Amazon.com reviews). These reviews were only scraped from U.S. customers. We followed [Amazon.com Terms of Use policy](https://www.amazon.com/gp/help/customer/display.html?nodeId=202140280) for web scraping by running our custom web scraper in small batches, with timeouts, and during off-peak hours. We are using the data solely for educational purposes. Our custom dataset is comprised of 362,924 Amazon.com reviews. Each review is comprised of the banned book's `title`, the `body` of the review, the review `rating` (one to five stars), and the `review_date`. These reviews span from August 9, 1997, to October 12, 2022. You can easily access and run our custom Amazon.com web scraper in Colab. [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1KlB4ADUxzuiSYdjytVU1e-T6hZOL1jlk?usp=share_link) You can view the Amazon.com banned book reviews in our Google Drive. [![Open In GDrive](https://img.shields.io/badge/Google-4285F4?logo=google&logoColor=fff&style=for-the-badge)](https://drive.google.com/file/d/1G6Up-3I5bBLIdBODLk3m72kjl_afASni/view?usp=share_link)

## Exploratory Data Analysis

We conducted some EDA on our Goodreads and ALA metadata as well as our Amazon.com review dataset. Additionally, we applied Scattertext to our Goodreads and ALA metadata to explore the topics being banned (and their ban frequencies) by either: 1) parental or political pressure or 2) through a written, formal book ban process. You can find our banned book metadata EDA in [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1onxnUEdiLnnVY7O-mES5nWdUV6PSvgaP?usp=share_link) and our Amazon.com banned book reviews EDA in [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/11VtVOWohDFFgzN0UArClYDTYD_er0mug?usp=share_link).

## Topic Modeling (Goodreads + ALA metadata + Amazon.com reviews dataset)

We tried a few topic modeling methodologies: NMF, LDA, Top2Vec, and BERTopic. 

**BERTopic** was our best approach so far with higher coherence, lower perplexity, clear topic diversity, and human interpretable topics and word outputs. You can read that notebook here [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1vZSyz8Dw96DF8z3SpTi8xGrU420yIgB1?usp=share_link). You can find NMF, LDA, and Top2Vec topic modeling work in our Appendix.

## Visual Similarity (Goodreads + ALA metadata)

You can view our transfer learning (visual similarity) work [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1wa_xeP3Nf058z0xCuA7-zIckxkWmAqhg?usp=share_link), our script to build our banned book PixPlot visualization with our tuned UMAP and KMeans parameters [![Open In GDrive](https://img.shields.io/badge/Google-4285F4?logo=google&logoColor=fff&style=for-the-badge)](https://drive.google.com/file/d/1tznvHcwephlZ3SvIILWCp2sb5iLHXk6e/view?usp=share_link), and our pre-built PixPlot WebGL site/assets [![Open In GDrive](https://img.shields.io/badge/Google-4285F4?logo=google&logoColor=fff&style=for-the-badge)](https://drive.google.com/drive/folders/1yUazlILivqESUJdyDhh5kz7QILqR-W4-?usp=share_link).

## Sentiment Analysis (Amazon.com reviews dataset)

## Appendix

- LDA Topic Modeling on Banned Books Metadata and Amazon.com Reviews
- NMF Topic Modeling
- Top2Vec Topic Modeling
- Visual Similarity (Banned Book Cover Image) Recommendation System Proof of Concept (scroll to the bottom of the notebook) [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1wa_xeP3Nf058z0xCuA7-zIckxkWmAqhg?usp=share_link)

## Statement of Work

- **Joan** | EDA and interactive graphs, topic modeling, ethics and considerations, report writing and editing

- **Alexis** | EDA, supervised learning / sentiment analysis, topic modeling, dev environment & dependency & ML compute management, report writing and editing

- **B** | Amazon.com banned book reviews web scraper data acquisition/cleaning, banned book metadata acquisition/cleaning, custom script to download banned book cover images, LDA & BERTopic topic modeling, transfer learning (visual similarity) & custom PixPlot build, basic EDA, proof of concept visual similarity recommendation system, setting up Git org & Google Colab and compute management and GDrive for data, report writing and editing

## Acknowledgements

Thank you to [Envoy-VC/awesome-badges](https://github.com/Envoy-VC/awesome-badges) for providing a repo with clean GitHub badges to put on your README.md.
