## Project objectives
This project aims to investigate the evolution of themes in artworks over time, and what themes have trascended our history.

## Dataset:
This project uses a dataset comprising around 120,000 artworks scraped from WikiArt.
Date ranges from 3050 BC to 2023.
www.kaggle.com/datasets/antoinegruson/-wikiart-all-images-120k-link

## Files
wikiart_eda.ipynb - exploratory data analysis

wikiart_NLP.ipynb - natural language processing

final_presentation.pdf - presentation slides for non-technical audience, includes methodology, findings, and next steps

interactive project page: https://art-theme-nlp.streamlit.app

## Preprocessing for NLP
The preprocessing steps include tokenization, lemmantization and stop word removal in multiple languages.

## Part 1: Clustering

The first method I explored is clustering. I first used SentenceTransformers to calculate embeddings of artwork titles, then reduced feature dimensions using TSNE. Using the reduced features, I used KMeans and DBSCAN to discover clusters within the artwork titles.

Findings: KMeans performed better than DBSCAN. I was able to identify a few clusters - the 'untitled' artworks, 'portrait' and 'illustration' artworks. However, the other clusters are not directly interpretable; I do not observe clear shared characteristics among artworks within these clusters.

## Part 2: Topic Modeling

In this section, I used BERTopic (multilingual model) to perform topic modeling on artwork titles. I first performed topic modeling on the entire artwork dataset to find common themes across history, then performed the same process on each time period. 

Findings: Among all artworks from 3050 BC to present, the 7 common themes of artworks are water scenes, nudity/bath, animals, seated/sleeping scenes, entertainment, fire, body parts.

## Part 3: Word Frequency Analysis

In this section, I analyzed the frequency of specific words over time. First, I used Counter to find out the most common words (words with highest frequency) across the dataset. Then, I analyzed the frequency of some of these words over time. 

Findings: The change in word frequency mirrors social evolution to some extent. 'Annunciation' and 'crucifix' appeared most frequent between 1400 and 1600. The word 'woman' started gaining popularity in the late 1800s. 

## Limitations and Next Steps

1. Better Lemmantization: I used WordNetLemmatizer to lemmatize the artwork titles, but it is not perfect. During the topic modeling, I noticed that some words are not lemmatized, such as bathing and bath, received and receiving. For next steps, better lemmantization could yield better results.
2. More Detailed Descriptions: The dataset contains 120,000 artworks, and the titles are relatively short. This might not be an ideal dataset for Natural Language Processing. If we could obtain a dataset that contains more detailed descriptions, the topic modeling results would be better.
3. Computer Vision: The dataset contains links to each artwork images, which gives us the potential to use computer vision techniques. This could give us more insights into these artworks.

