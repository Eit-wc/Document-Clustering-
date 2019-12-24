# Document-Clustering

This project used for automatic document clustering by using Natural language processing (NLP). This system will read all the PDF files in the given folder and group them by content.

## Technique
* Word embedding
* Word Vector Averaging
* Affinity propagation

## Necessary package
* [tika](https://github.com/chrismattmann/tika-python)    (for reading PDF)
* [polyglot](https://github.com/aboSamoor/polyglot) (for multiple language NLP)
* [sklearn](https://github.com/scikit-learn/scikit-learn)

## How to use
This project has bee created on [google colab](https://colab.research.google.com), so I recommend to try on [google colab](https://colab.research.google.com) before work on a local machine.

### Create dataset
To test the system, I create the script to automate downloading and convert the Wikipedia page into the PDF file. This script searches the keywords from [Wiki_Keywords.csv]("https://raw.githubusercontent.com/Eit-wc/Document-Clustering-/master/src/files/Wiki_Keywords.csv") and finds the link for another language (Thai and Japanese).

* Enter [1_DocumentExtraction.ipynb](https://colab.research.google.com/github/Eit-wc/Document-Clustering-/blob/master/src/1_DocumentExtraction.ipynb)
* Mount the google drive by running the first part
* Run the second part, the script will download the Wikipedia page and save the PDF files into the google drive ("Goole Drive/Colab Notebooks/files/documents/").

### run the clustering
* Enter [main.ipynb](https://colab.research.google.com/github/Eit-wc/Document-Clustering-/blob/master/src/main.ipynb)
* Mount the google drive
* Detect the language
* Text processing
* Calculate document vector
* Cluster the document by using document vector
* The result will show on "Goole Drive/Colab Notebooks/files/result.csv"

# Results and discussion 

After I get this assignment the time constraint is the most concern point of this project. Because of my lagging of knowledge in the NLP field, I have no time to trial and error to make the model. The best solution is using the exiting library that has a pre-trained model. The goal of this project is to classify the document, Doc2Vec is the first tool that I have to select. However, there has no Doc2Vec project that has multiple language support. After research some paper[1](https://cs.stanford.edu/~quocle/paragraph_vector.pdf)[2](https://openreview.net/pdf?id=HyNbtiR9YX), I found the Word Vector Averaging has the potential to solve this problem. This information leads me to the [polyglot](https://github.com/aboSamoor/polyglot) that can get the word vector in multiple languages. Furthermore, [polyglot](https://github.com/aboSamoor/polyglot) also can detect the language.

## Prepare dataset

To test the ability of the proposed system, I have to prepare the document. The [1_DocumentExtraction]( https://github.com/Eit-wc/Document-Clustering-/blob/master/src/1_DocumentExtraction.ipynb) script has been create to generate the dataset. I define the 10 categories of the document as shown in the following table.

| Define group | Category | Keywords |
| --- | --- | --- |
| 0 | Animal | Cat, Dog, Kangaroo, Bird, Penguin |
| 1 | Food | Hamburger, Steak, Omelette, Bacon, Sushi |
| 2 | Country | Thailand, Singapore, France, Japan, Austalia |
| 3 | City | London, Tokyo, Bangkok, Paris, Canberra |
| 4 | Vehicle | Car, Motorcycle, Bicycle, Bus, Train |
| 5 | Fruit | Berry, Avocado, Apple, Banana, Durian |
| 6 | Movie | Star_Wars, Back_to_the_Future, The_Lion_King, The_Terminator, Toy_Story |
| 7 | President and Prime minister | Donald_Trump, Barack_Obama, Xi_Jinping, Vladimir_Putin, Justin_Trudeau |
| 8 | Currency | United_States_dollar, Singapore_dollar, Japanese_yen, Thai_baht, Renminbi |
| 9 | Businessman | Elon_Musk, Jack_Ma, Warren_Buffett, Bill_Gates, Mark_Zuckerberg |

The [script]( https://github.com/Eit-wc/Document-Clustering-/blob/master/src/1_DocumentExtraction.ipynb) uses the keywords and search the Wikipedia page in English. From the English page, the script search URL for another language (Thal and Japanese). Next, all Wiki page has saved to Google Drive ("Goole Drive/Colab Notebooks/files/documents/") in PDF format. The total files is 150 files (5 [keywords] * 10 [category] * 3 [language] = 150 [files]).

## Clustering process

To clustering the documents, I apply the Word Vector Averaging to calculate the document vector. The common clustering method is the K-Means method. However, I assume that we never know the number of clusters in this problem. For this reason, I decide to use the Affinity propagation method, because this method doesn't need the number of clusters.

### Clustering result

The result of language detection and document clustering has shown in the following table.

|Filename|Language|Label|
| --- | --- | --- |
|0_Cat_ja.pdf|ja|9|
|0_Cat_th.pdf|th|2|
|0_Cat_en.pdf|en|8|
|1_Bacon_en.pdf|en|8|
|1_Bacon_th.pdf|th|2|
|1_Omelette_ja.pdf|ja|9|
|1_Omelette_th.pdf|th|2|
|1_Omelette_en.pdf|en|8|
|1_Steak_ja.pdf|ja|9|
|1_Steak_th.pdf|th|2|
|1_Steak_en.pdf|en|8|
|1_Hamburger_ja.pdf|ja|9|
|1_Hamburger_th.pdf|th|2|
|1_Hamburger_en.pdf|en|8|
|0_Penguin_ja.pdf|ja|9|
|0_Penguin_th.pdf|th|2|
|0_Penguin_en.pdf|en|8|
|0_Bird_ja.pdf|ja|9|
|0_Bird_th.pdf|th|2|
|0_Bird_en.pdf|en|8|
|0_Kangaroo_ja.pdf|ja|9|
|0_Kangaroo_th.pdf|th|2|
|0_Kangaroo_en.pdf|en|8|
|0_Dog_th.pdf|th|2|
|0_Dog_ja.pdf|ja|9|
|0_Dog_en.pdf|en|8|
|2_France_th.pdf|th|2|
|2_France_en.pdf|en|0|
|2_Singapore_ja.pdf|ja|1|
|2_Singapore_th.pdf|th|2|
|2_Singapore_en.pdf|en|0|
|2_Thailand_ja.pdf|ja|1|
|2_Thailand_th.pdf|th|2|
|2_Thailand_en.pdf|en|0|
|1_Sushi_ja.pdf|ja|9|
|1_Sushi_th.pdf|th|2|
|1_Sushi_en.pdf|en|8|
|1_Bacon_ja.pdf|ja|9|
|3_London_ja.pdf|ja|4|
|3_London_th.pdf|th|2|
|3_London_en.pdf|en|0|
|2_Austalia_ja.pdf|ja|1|
|2_Austalia_th.pdf|th|2|
|2_Austalia_en.pdf|en|0|
|2_Japan_ja.pdf|ja|1|
|2_Japan_th.pdf|th|2|
|2_Japan_en.pdf|en|0|
|2_France_ja.pdf|ja|1|
|4_Car_th.pdf|th|2|
|4_Car_en.pdf|en|3|
|3_Canberra_ja.pdf|ja|4|
|3_Canberra_th.pdf|th|2|
|3_Canberra_en.pdf|en|0|
|3_Paris_ja.pdf|ja|4|
|3_Paris_th.pdf|th|2|
|3_Paris_en.pdf|en|0|
|3_Bangkok_ja.pdf|ja|4|
|3_Bangkok_th.pdf|th|2|
|3_Bangkok_en.pdf|en|0|
|3_Tokyo_ja.pdf|ja|4|
|3_Tokyo_th.pdf|th|2|
|3_Tokyo_en.pdf|en|0|
|5_Apple_ja.pdf|ja|9|
|5_Apple_th.pdf|th|2|
|5_Apple_en.pdf|en|8|
|5_Avocado_ja.pdf|ja|9|
|5_Avocado_th.pdf|th|2|
|5_Avocado_en.pdf|en|8|
|5_Berry_ja.pdf|ja|9|
|5_Berry_th.pdf|th|2|
|4_Train_ja.pdf|ja|5|
|5_Berry_en.pdf|en|8|
|4_Train_th.pdf|th|2|
|4_Train_en.pdf|en|3|
|4_Bus_ja.pdf|ja|5|
|4_Bus_th.pdf|th|2|
|4_Bus_en.pdf|en|3|
|4_Bicycle_ja.pdf|ja|5|
|4_Bicycle_th.pdf|th|2|
|4_Bicycle_en.pdf|en|3|
|4_Motorcycle_ja.pdf|ja|5|
|4_Motorcycle_th.pdf|th|2|
|4_Motorcycle_en.pdf|en|3|
|4_Car_ja.pdf|ja|5|
|6_Toy_Story_ja.pdf|ja|7|
|6_Toy_Story_th.pdf|th|2|
|6_Toy_Story_en.pdf|en|6|
|6_The_Terminator_ja.pdf|ja|7|
|6_The_Terminator_th.pdf|th|2|
|6_The_Terminator_en.pdf|en|6|
|6_The_Lion_King_ja.pdf|ja|7|
|6_The_Lion_King_th.pdf|th|2|
|6_Back_to_the_Future_ja.pdf|ja|7|
|6_The_Lion_King_en.pdf|en|6|
|6_Back_to_the_Future_th.pdf|th|2|
|6_Back_to_the_Future_en.pdf|en|6|
|6_Star_Wars_ja.pdf|ja|7|
|6_Star_Wars_th.pdf|th|2|
|6_Star_Wars_en.pdf|en|6|
|5_Durian_ja.pdf|ja|9|
|5_Durian_th.pdf|th|2|
|5_Durian_en.pdf|en|8|
|5_Banana_ja.pdf|ja|9|
|5_Banana_th.pdf|th|2|
|5_Banana_en.pdf|en|8|
|7_Xi_Jinping_ja.pdf|ja|10|
|7_Xi_Jinping_th.pdf|th|2|
|7_Xi_Jinping_en.pdf|en|0|
|7_Barack_Obama_ja.pdf|ja|10|
|7_Barack_Obama_th.pdf|th|2|
|7_Barack_Obama_en.pdf|en|14|
|7_Donald_Trump_ja.pdf|ja|10|
|7_Donald_Trump_th.pdf|th|2|
|7_Donald_Trump_en.pdf|en|14|
|8_Thai_baht_th.pdf|th|2|
|8_Thai_baht_en.pdf|en|12|
|8_Japanese_yen_ja.pdf|ja|11|
|8_Japanese_yen_th.pdf|th|2|
|8_Japanese_yen_en.pdf|en|12|
|8_Singapore_dollar_ja.pdf|ja|11|
|8_Singapore_dollar_en.pdf|en|12|
|8_Singapore_dollar_th.pdf|th|2|
|8_United_States_dollar_ja.pdf|ja|11|
|8_United_States_dollar_th.pdf|th|2|
|8_United_States_dollar_en.pdf|en|12|
|7_Justin_Trudeau_th.pdf|th|2|
|7_Justin_Trudeau_ja.pdf|ja|10|
|7_Justin_Trudeau_en.pdf|en|14|
|7_Vladimir_Putin_ja.pdf|ja|10|
|7_Vladimir_Putin_th.pdf|th|2|
|7_Vladimir_Putin_en.pdf|en|0|
|9_Mark_Zuckerberg_ja.pdf|ja|13|
|9_Mark_Zuckerberg_en.pdf|en|14|
|9_Mark_Zuckerberg_th.pdf|th|2|
|9_Bill_Gates_ja.pdf|ja|13|
|9_Bill_Gates_th.pdf|th|2|
|9_Bill_Gates_en.pdf|en|14|
|9_Warren_Buffett_ja.pdf|ja|13|
|9_Warren_Buffett_th.pdf|th|2|
|9_Warren_Buffett_en.pdf|en|14|
|9_Jack_Ma_ja.pdf|ja|13|
|9_Jack_Ma_th.pdf|th|2|
|9_Jack_Ma_en.pdf|en|14|
|9_Elon_Musk_th.pdf|th|2|
|9_Elon_Musk_ja.pdf|ja|13|
|9_Elon_Musk_en.pdf|en|14|
|8_Renminbi_ja.pdf|ja|11|
|8_Renminbi_th.pdf|th|2|
|8_Renminbi_en.pdf|en|12|
|8_Thai_baht_ja.pdf|ja|11|

| Clustering group| Files|
| --- | --- |
| 0 | 2_France_en.pdf 2_Singapore_en.pdf 2_Thailand_en.pdf 3_London_en.pdf 2_Austalia_en.pdf 2_Japan_en.pdf 3_Canberra_en.pdf 3_Paris_en.pdf 3_Bangkok_en.pdf 3_Tokyo_en.pdf 7_Xi_Jinping_en.pdf 7_Vladimir_Putin_en.pdf |
| 1 | 2_Singapore_ja.pdf 2_Thailand_ja.pdf 2_Austalia_ja.pdf 2_Japan_ja.pdf 2_France_ja.pdf |
| 2 | 0_Cat_th.pdf 1_Bacon_th.pdf 1_Omelette_th.pdf 1_Steak_th.pdf 1_Hamburger_th.pdf 0_Penguin_th.pdf 0_Bird_th.pdf 0_Kangaroo_th.pdf 0_Dog_th.pdf 2_France_th.pdf 2_Singapore_th.pdf 2_Thailand_th.pdf 1_Sushi_th.pdf 3_London_th.pdf 2_Austalia_th.pdf 2_Japan_th.pdf 4_Car_th.pdf 3_Canberra_th.pdf 3_Paris_th.pdf 3_Bangkok_th.pdf 3_Tokyo_th.pdf 5_Apple_th.pdf 5_Avocado_th.pdf 5_Berry_th.pdf 4_Train_th.pdf 4_Bus_th.pdf 4_Bicycle_th.pdf 4_Motorcycle_th.pdf 6_Toy_Story_th.pdf 6_The_Terminator_th.pdf 6_The_Lion_King_th.pdf 6_Back_to_the_Future_th.pdf 6_Star_Wars_th.pdf 5_Durian_th.pdf 5_Banana_th.pdf 7_Xi_Jinping_th.pdf 7_Barack_Obama_th.pdf 7_Donald_Trump_th.pdf 8_Thai_baht_th.pdf 8_Japanese_yen_th.pdf 8_Singapore_dollar_th.pdf 8_United_States_dollar_th.pdf 7_Justin_Trudeau_th.pdf 7_Vladimir_Putin_th.pdf 9_Mark_Zuckerberg_th.pdf 9_Bill_Gates_th.pdf 9_Warren_Buffett_th.pdf 9_Jack_Ma_th.pdf 9_Elon_Musk_th.pdf 8_Renminbi_th.pdf |
|3| 4_Car_en.pdf 4_Train_en.pdf 4_Bus_en.pdf 4_Bicycle_en.pdf 4_Motorcycle_en.pdf |
|4| 3_London_ja.pdf 3_Canberra_ja.pdf 3_Paris_ja.pdf 3_Bangkok_ja.pdf 3_Tokyo_ja.pdf |
|5| 4_Train_ja.pdf 4_Bus_ja.pdf 4_Bicycle_ja.pdf 4_Motorcycle_ja.pdf 4_Car_ja.pdf |
|6| 6_Toy_Story_en.pdf 6_The_Terminator_en.pdf 6_The_Lion_King_en.pdf 6_Back_to_the_Future_en.pdf 6_Star_Wars_en.pdf |
|7| 6_Toy_Story_ja.pdf 6_The_Terminator_ja.pdf 6_The_Lion_King_ja.pdf 6_Back_to_the_Future_ja.pdf 6_Star_Wars_ja.pdf |
|8| 0_Cat_en.pdf 1_Bacon_en.pdf 1_Omelette_en.pdf 1_Steak_en.pdf 1_Hamburger_en.pdf 0_Penguin_en.pdf 0_Bird_en.pdf 0_Kangaroo_en.pdf 0_Dog_en.pdf 1_Sushi_en.pdf 5_Apple_en.pdf 5_Avocado_en.pdf 5_Berry_en.pdf 5_Durian_en.pdf 5_Banana_en.pdf |
|9| 0_Cat_ja.pdf 1_Omelette_ja.pdf 1_Steak_ja.pdf 1_Hamburger_ja.pdf 0_Penguin_ja.pdf 0_Bird_ja.pdf 0_Kangaroo_ja.pdf 0_Dog_ja.pdf 1_Sushi_ja.pdf 1_Bacon_ja.pdf 5_Apple_ja.pdf 5_Avocado_ja.pdf 5_Berry_ja.pdf 5_Durian_ja.pdf 5_Banana_ja.pdf |
|10| 7_Xi_Jinping_ja.pdf 7_Barack_Obama_ja.pdf 7_Donald_Trump_ja.pdf 7_Justin_Trudeau_ja.pdf 7_Vladimir_Putin_ja.pdf |
|11| 8_Japanese_yen_ja.pdf 8_Singapore_dollar_ja.pdf 8_United_States_dollar_ja.pdf 8_Renminbi_ja.pdf 8_Thai_baht_ja.pdf |
|12| 8_Thai_baht_en.pdf 8_Japanese_yen_en.pdf 8_Singapore_dollar_en.pdf 8_United_States_dollar_en.pdf 8_Renminbi_en.pdf |
|13| 9_Mark_Zuckerberg_ja.pdf 9_Bill_Gates_ja.pdf 9_Warren_Buffett_ja.pdf 9_Jack_Ma_ja.pdf 9_Elon_Musk_ja.pdf |
|14| 7_Barack_Obama_en.pdf 7_Donald_Trump_en.pdf 7_Justin_Trudeau_en.pdf 9_Mark_Zuckerberg_en.pdf 9_Bill_Gates_en.pdf 9_Warren_Buffett_en.pdf 9_Jack_Ma_en.pdf 9_Elon_Musk_en.pdf |

The result has shown that the proposed system has the potential to group the document into the logical groups.

| Clustering group | Detail |
| --- | --- |
| 0 | Place in English |
| 1 | Country in Japanese |
| 2 | ** Thai language documents ** |
| 3 | Vehicle in English |
| 4 | City in Japanese |
| 5 | Vehicle in Japanese |
| 6 | Movie in English |
| 7 | Movie in Japanese |
| 8 | ** Food, fruit and animal in English ** |
| 9 | ** Food, fruit and animal in Japanese ** |
| 10 | President and Prime minister in Japanese |
| 11 | Currency in Japanese |
| 12 | Currency in english |
| 13 | Bussnessman in Japanese |
| 14 | Celebrity in English |

![Data visualization](https://github.com/Eit-wc/Document-Clustering-/tree/master/src/files/Result_Graph.png)

## Problems and solution

The proposed system doesn't group the document as I define but the result is reasonable. The system tries to separate the document by language. The first problem is group 2 that is all Thai documents. This problem caused by the word's vector in a different language gives a different vector as shown in the following. The "dog" in Thai and Japanese give a farther than the "cat" in the same language. I believe this problem can solve by cluster the document by separate language. The other solution is to try to translate the non-English language into English before calculate the word vector.

```
dog_en = Word('dog','en').vector
cat_en = Word('cat','en').vector
dog_th = Word('หมา','th').vector
dog_ja = Word('犬','ja').vector

dist_en2th = np.linalg.norm(dog_en-dog_th)
dist_en2ja = np.linalg.norm(dog_en-dog_ja)
dist_ja2th = np.linalg.norm(dog_th-dog_ja)
dist_cat2dog = np.linalg.norm(cat_en-dog_en)

print(f'Vector distance dog_en -> dog_th = {dist_en2th}')
print(f'Vector distance dog_en -> dog_ja = {dist_en2ja}')
print(f'Vector distance dog_ja -> dog_th = {dist_ja2th}')
print(f'\nVector distance cat_en -> dog_en = {dist_cat2dog}')
```

output

```
Vector distance dog_en -> dog_th = 33.494232177734375
Vector distance dog_en -> dog_ja = 40.79993438720703
Vector distance dog_ja -> dog_th = 24.6937255859375

Vector distance cat_en -> dog_en = 15.844327926635742
```

The other problem is groups 8 and 9 because the vector distance of three categories (food, fruit, and animal) is shorter than another category. I believe after separate the document by language and apply the vector normalize for each language the vector of these three categories will have more space to classify. 
