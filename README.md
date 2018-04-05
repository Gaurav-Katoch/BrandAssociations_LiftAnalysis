
Description
-------------------------------------------------------------------------------------------------------------------------
This analysis involved scraping conversation messages among different users on a car forum and analyzing them to see relationship between various car brands and their respective attributes. Also, different brands were analyzed with respect to each other to see which brands are frequently mentioned together.

Notes
-------------------------------------------------------------------------------------------------------------------------
- The code has been written used Python3 using Jupiter notebook as interface

- The code needs to be executed in a sequential fashion as in certain case previously created tables are referred to later

**Approach**
------------------------------------------------------------------------------------------------------------------------
Conversion messages on a car forum were scraped using BeautifulSoup and Selenium. Basic text processing techniques such as word tokenization, stopword removal, stemming and lemmatization were applied to ger relevant words.   
Using tokenized words data, [lift ratio](http://r-statistics.co/Association-Mining-With-R.html) between different brands was calculated which is the ratio of number of times 2 brands were mentioned in a particular post divided by number of times each of them were mentioned in the post individually.  
The highest lift ratio were then plotted on a [Multidimensional scaling](https://en.wikipedia.org/wiki/Multidimensional_scaling) plot to see which brands are closely related with one another and mentioned frequently. 
To see which brands are closely linked with attributes such as performance, price, class, liftratio was calculated in a similar fashion described above to see how closely these brands are associated with each of these variables. 
This analysis can be useful while branding a car and understanding close competitors.  
The analysis can be further improved by calculating distances between two brands mentioned in a post and also distances between attributes and brands mentioned to see which brands/attributes are more closely associated. Also, sentiment analysis can be used here to check for the context in which a brand and attribute are mentioned.  

Installing libraries and packages
-----------------------------------------------------------------------------------------------------------------------
To run the notebook, following list of packages must be installed in the system:
-  Pandas
-  Numpy
-  bs4
    -  ```from bs4 import BeautifulSoup```
-  selenium
- nltk
- re

To scrap data for car reviews from the website, Chrome was used as the web browser. 
- Download [latest Chromedriver](https://sites.google.com/a/chromium.org/chromedriver/downloads) and transfer unzipped file to /usr/bin
- Run ```from selenium import webdriver```
      ```driver = webdriver.Chrome()```

**nltk** is a Natural Language toolkit and is used for natural language processing. Following libraries need to be imported form the toolkit:  
- ```from nltk.corpus import brown```
- ```from nltk.corpus import stopwords```
- ```from nltk.stem import WordNetLemmatizer```

**Mac OS:**
- To download libraries and packages being loaded in first block of the code, go to Terminal and download packages using 
```pip install package-name ```
- If pip throws an error due to packages not being a part of pip anymore, use ```conda install package-name``` , this is an Anaconda command and directly downloads packages in Anaconda . 

**Windows:**
- Open Windows command prompt and enter ```py -3.6 -m pip install package-name```

-------------------------------------------------------------------------------------------------------------------------
