# Document-Clustering

This project use for automatic document clustering by using Natural language processing (NLP). This system will read all the PDF files in given folder and group them by content.

## Technique
* Word embedding
* Word Vector Averaging
* Affinity propagation

## Necessary package
* tika    (for reading PDF)
* polyglot (for multiple language NLP)
* sklearn

## How to use
This project has bee created on [google colab](https://colab.research.google.com), so I recommend to try on [google colab](https://colab.research.google.com) before move to local machine.

### Create dataset
To test the system, I create the script to automate download and convert Wikipedia page into the PDF file. This script search the keywords from [Wiki_Keywords.csv]("https://raw.githubusercontent.com/Eit-wc/Document-Clustering-/master/src/files/Wiki_Keywords.csv") and find the link for other language (Thai and Japanese).

* Enter [1_DocumentExtraction.ipynb](https://colab.research.google.com/github/Eit-wc/Document-Clustering-/blob/master/src/1_DocumentExtraction.ipynb)
* Mount the google drive by run first part
* Run the second part, the script will download the Wikipedia page and save the PDF files into the google drive ("Goole Drive/Colab Notebooks/files/documents/").

### run the clustering
* Enter [main.ipynb](https://colab.research.google.com/github/Eit-wc/Document-Clustering-/blob/master/src/main.ipynb)
* Mount the google drive
* Detect the language
* Text processing
* Calculate document vector
* Cluster the document by using document vector
* The result will show on "Goole Drive/Colab Notebooks/files/result.csv"

## Results and discussion 

[TODO]

|filename|language|label|
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


|Group| Files|
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
