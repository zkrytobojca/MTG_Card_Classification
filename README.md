# MTG_Card_Classification - ML Project about Magic: the Gathering TCG

## About

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
