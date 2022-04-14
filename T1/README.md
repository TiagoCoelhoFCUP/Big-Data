# Movie Recommender System

For this project we were proposed to develop a movie recommendation system through a keyword search. The proposed work consists of the reading, its subsequent pre-processing and storage in Google Cloud Storage, of raw data based on the information contained in MovieLens and IMDB. 

Subsequently, the pre-processed data will be converted into BigQuery tables through a Loader Cloud Function activated by a publish/subscribe system. 

Finally, the recommendation system works through a Search Cloud Function that is in charge of queries to BigQuery tables in order to return the desired list of results. It was also suggested to us to implement different strategies besides the keyword search (extra work) such as weight based search and Jaccard index.

For the entire implementation we used Google Colab for Python programming, Apache Spark for the manipulation and creation of the datasets, SQL to perform the queries to the stored tables, as well as the Google Cloud technologies previously mentioned.  

You can interact with the recommender through the form bellow, available in the Ipython Notebook uploaded:

![image](https://user-images.githubusercontent.com/13381706/163411062-2ceaa9fd-4b38-4b28-98a9-eb5327b418a9.png)

For more implementation details, make sure to read the full report on the development of this project.

