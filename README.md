# SENTIMENT ANALYIS

#### **This is a code that gets the reviews and make sentiment analysis for the product is good or not. I took logitech G502 computer mouse comments as an example here**


#### Required libraries

- requests
- BeautifulSoup from bs4
- pandas
- textblob
- google_translate_new
- warnings


##### After importing our libraries (BeautifulSoup, google_trans_new, textblob, requests, pandas and warnings. We define an empty list to convert to dataframe structure after receiving our comments.
##### Header structure (User-Agent) for the Amazon site does not consider us as robots and prevent us from pulling data.
##### We define the function that we send a request to the site (get_soup). We send a request by typing the link of the product we want into "requests.get" and adding "headers" to the end. With BeautifulSoup, we split the data from the lxml method. (can also be done in html)
##### Then, with the "get_reviews" function, we select the previously obtained data as product, title, rating and body part according to the html structure.
##### Next step, we take the product parts in each comment and put it in the empty directory (reviewlist) we defined at the beginning and save it as an excel file. Using the for loop with range, we determine from the beginning how many pages of comments we want to receive. The if part at the end of the for loop is to avoid an error when the last page is reached. 
##### I prefer to 20 pages is enough. Page quantity can be changed upon request 
##### After we scraped the reviews and saved as a excel file(xlsx,csv etc.) we read from documents. (maybe there are those who just want to use the part of the code after this.)
##### We used the option_context property to view the entire code in detail and we limited the reviews to 5000 characters. The program allows this much.
##### After that, translate reviews from any language to English and also add a columns as polaritiy for showing reviews' polarity score with using textblob.
##### Finally, named as positive,negative and notr for polarity scores. We observed how many reviews we have as positive,negative and notr and we visualized below
