# MTG_Card_Classification - ML Project about Magic: the Gathering TCG

## About
This project was important part of my master's thesis in computer science. It is a machine learning / data science project about classifying cards from the Magic: the Gathering card game based on information about a given card.

First of all, this project required some work in the field of data engineering - that is, creating a good dataset to operate on. I opted to get raw data from Scryfall API and transform it to fit my needs. I transformed ~287MB of JSON data with help of Pandas data frames into a CSV document. Some information aboput cards could be transferred almost unaltered as a new dataset attributes, but others required feature engineering. Important tool in that case turned out to be regular expressions (regex). This technique helped me create 60 custom attributes representing player-created categories of cards (like mana rock, burn spell or removal). 

After dataset was created, the fun part begun. I wanted to train two sets of classifiers:
- card color classifier - able to predict card color based on other information about the card. It could be used as help in creating new cards.
- card indicative price classifier - able to predict card price range based on other information about the card. It could be helpful for traders and players in general when dealing with newly spoiler cards. 

I got to test 4 supervised learning algorithms: 
- Random Forest
- Multi-layer Perceptron (MLPClassifier)
- K Nearest Neighbours (K-NN)
- Adaboost-SAMME

Best hyperparameters for all of them where chosen by grid search algorithm. After the models where trained, they were evaluated using 5-fold cross-validation. 

Each created classifier was composed of small set of binary classifiers that together desided about final class prediction. This way many combinations of coexisting classes could be easily handled with relatively high accuracy.

## Technologies used
- Python (Scikit-learn, Pandas, NumPy, Matplotlib, Pickle, Seaborn)
- Regex
- JSON
- Jupyter Notebook
- Scryfall API (https://scryfall.com/)

## Highlights
Important part of this project was data acquisition, selection, preprocessing and feature engineering, which ultimately led to creation of a data set describing almost all available cards from the studied game. Most recent version had 35341 rows and 504 columns describing Magic: The Gathering cards. Created CSV file containging this dataset is located [HERE](Datasets/mtg_dataset.csv).

During the research, it was determined that the Random Forest classifier turned out to be the most effective among the analyzed algorithms. It achieved the best results both in the card color classification and in the indicative price range classification. 

![image](https://user-images.githubusercontent.com/49489021/204661950-f60f6b32-8aa2-4d43-a4c5-ba924fcec8a8.png)
![image](https://user-images.githubusercontent.com/49489021/204662013-923bfe5e-e7b1-4cdc-bd94-cefc1ab94e7c.png)

Example card classifications were also demonstrated in order to showcase proposed methodology:

![Mana drain](https://user-images.githubusercontent.com/49489021/204663703-4d779768-ea2c-47b9-9a70-5be7b449da1b.png)
![Lightning helix](https://user-images.githubusercontent.com/49489021/204664328-82ff4c73-f85a-4d5a-98cb-2eb7e3070d3b.png)
