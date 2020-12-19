# Capstone - Data Scraping & Analysis!

Hello! This repository contains the data scraping and analysis code for this interactive project that is written in Python using Jupyter Notebooks. Web scraping frameworks such as Selenium and BeautifulSoup were used for the data construction process, while NLP frameworks such as Regex and NTLK are used in the analysis. 

## How to Navigate this Repo?
This repository is organised by the scraping and analysis of each publication, namely: The South China Morning Post, The Hong Kong Free Press, and China Daily. In each of these folders, there are data, notebooks, and pickles subfolders to organise the flow of data and analysis.

### Request Library - HKFP + SCMP
For these two publications, a sitemap scraper was used to find all of the URLs of the web domain. Next, the Request library was used to scrap the title, author, topic tags, and available summary of each URL. 

#### SCMP
Only URLs with the tag ```/news/``` were scraped between 2012-2020 November. The selection of this date range reflects the time span of when the SCMP started to upload their news articles to thier websites in earnest. Example: ```https://www.scmp.com/news/hong-kong/health-environment/article/3109853/coronavirus-hong-kongs-executive-council-signs```. This came up to a total of 172395 articles. However, news articles from wire news sources such as Reuters or Bloomberg were included in this count. After cleaning those out, in addition to broken links and missing authors or titles, 92251 SCMP news articles remained. Out of those 92251 articles, a subset of 31618 articles which contained the ```/china/``` tag in the URL were taken to perform the sentiment analysis in a [Google Colab Notebook](https://colab.research.google.com/drive/1h23ZIYabZ5Wb3NB-jH9LF8hZgpDGBFXf#scrollTo=07cy4zCVM_Ub).

#### HKFP
Only URLs with the a date were scraped because only news articles had a date in the URL. Example:  ```https://hongkongfp.com/2020/02/24/pictures-hundreds-protest-tuen-muns-dancing-aunties-police-deploy-pepper-spray/```. All of the news articles were scraped (from 2015-2020 November), and similarly cleaned to remove news articles from wire news sources. This came up to 14364 HKFP articles. The author was unable to find a way to limit the search of HKFP to articles only pertaining to China or Hong Kong, although assuming that the HKFP, which is a local paper, mostly writes about Chinese and Hong Kongese affairs, is somewhat fair assumption. NOT USED IN CURRENT INTERACTIVE.

### Selenium Library - China Daily
The structure of the China Daily website with a Hong Kong search query ```https://www.chinadailyhk.com/article/hong_kong/index.html``` allowed for the an instantaneous HTML download of the page to get all of the titles. However, one needed to click the ```Load More``` button at the bottom of the page to all of the articles. Thus, Selenium was used to simulate a browswer user clicking the button repeatedly until all of the articles were shown. The HTML source was then downloaded and then scraped using BeautifulSoup for the text data. 10740 China Daily articles were scraped after cleaning broken entries. NOT USED IN CURRENT INTERACTIVE.

## Full Data?
Data that requires combining multiple datasets from different publications are in the Full Data folder. The only application where this was necessary was exporting data from this repository to a [Google Colab Notebook](https://colab.research.google.com/drive/1xkpP0azVmy_WdN93q1fDe7VyNRM2dsUN#scrollTo=LzelwT_mj_HU) for sentiment analysis using deep learning. This is done due to the computational power of GPUs afforded by Google Colab's free cloud computing. NOT USED IN CURRENT INTERACTIVE.

1. ```train_test_val_data.csv``` includes the combined HKFP + China Daily training set. HKFP aritc


