# NLP-Based-work


#Jupyter notebook after uploading to github, there were changes in the notebook plotly visualizations

In this Notebook, I will be doing EDA and train Entity recognition model on a tab separated text file.

The basic assumption which I made during this work:

Sentences give more detail than individual words, So upon visual inspection of the text file, I found that whenever there is an empty line in the text file, that can be deemed as a line break, thus dividing the text file into ~3400 sentences.
Index of the Notebook
Index of the Notebook
 - Import of relavant libraries


 - Exploratory Data Analysis
     - 1. Removing Null columns
     - 2. Visualising the Entity distribution
     - 3. What are those words in the Recognised Entities?(WordCloud)
     - 4. Most Frequent Entities
     - 5. Basic Text Cleaning and Topic Modelling
     - 6. Word Count Distribution in a Sentence without links and stopwords
     - 7. Character Count Distribution in a Sentence without links and stopwords
     - 8. Top 5 Positive & Negative Sentences and POS tagging
     - 9. Deeper Correlation Analysis into Text Sentences with links and stopwords
     - 10. Top Bigram
 
 
 - Entity Recognition problem
     - 1. Naive Approach (Submission -1 csv file )
     - 2. NER with Spacy (Submission -2 ner model)
     
I came up with the above two solutions and go with the second approach as its learning the model from the sentences, So basically its learning the pattern of sentences rather than the words directly which we have seen in Naive approach.
 
 
 - Evaluation metrics of the model
