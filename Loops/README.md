
Problem

Considering the “title” column of the file “ticketmaster.csv”, the code that you write should be able to determine 

- Using NLP (any NLP library) classify the title into the following sentiment categories (Need Help Understanding, Application Error, New Feature Request, Terminate Service)
- Find the product entities using entity recognition.
- The csv file should be pulled into a database in MySQL. The code should directly access data from the table in the database.
- The output data has to be added into a new field in the same table. 


Approach:

1. **Importing Libraries** - NLTK, spacy, Pandas, Numpy etc

2. **Establishing a connection between Local Jupyter Notebook and mYsql** for this I have used Pymysql Package by giving the host, password and db details. 
MySQL is a server-based database management system. One server might contain multiple databases. To interact with a database, you must first establish a connection with the server.  To create a connection between the MySQL database and the python application, the connect() method of mysql. connector module is used. Pass the database details like HostName, username, and the database password in the method call. The method returns the connection object. The general workflow of a Python program that interacts with a MySQL-based database is as follows:

    --  Connect to the MySQL server.\
    --  Create a new database.\
    --  Connect to the newly created or an existing database.\
    --  Execute a SQL query and fetch results.\
    --  Inform the database if any changes are made to a table.\
    --  Close the connection to the MySQL server.  

3. **Defining methods for cleaning data. removing stopwords, punctuation and numbers.** Cleaning of an NLP task depends on the use case, few practises involve building the model without cleaning to preserve the "context" of the model

4. **Building the model** In Natural Language Processing the general understanding of text is trained on massive corpus, such as all Wikipedia entries of a given language. As a result so called WordEmbeddings represent each word as a high dimensional vector. Additionally, this concept can be easily expanded from words to sentences (StackedEmbeddings) or entire documents (DocumentEmbeddings).
The basic idea is to create a label vector, which represents the 4 labels/categories as vectors and calculate the cosine distance of each label (A) to the title vector (B). The label with the highest similarity or is higher than a certain threshold will be assigned to the user rating. Here as we are given the task of single label, I did not use threshold.
So, we have shifted our attention to the “meaning” behind the label.
![image](https://user-images.githubusercontent.com/57020870/119206991-93d10b00-ba51-11eb-80cd-7873e7f6b944.png)
\
For this purpose ,I have downloaded sentence transformers BERT package. SentenceTransformers is a Python-Pytorch framework for state-of-the-art sentence, text and image embeddings.
details - https://www.sbert.net/index.html#

5. **Coding the approach** After downloading and importing the packages, Coded the above approach for getting the most similar Label for each title
6. **Finding the Product Entities** Used Spacy Entity recognition model to find all the entities and filter the "Product" entity
7. **Writing the Label column back into SQL Database** After getting the label for each title, writing the same into a new field into SQL Table

