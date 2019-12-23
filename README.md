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

[todo]
