# Coursera-course-review-nlp
Performing Sentiment Analysis on reviews scrapped from Coursera.​

##Problem Use cases:
 - Performing Sentiment Analysis on reviews scrapped from Coursera.
 - Validating our model based on user star ratings.
 - Finding the top 5 and bottom 5 courses for each  subject based on the ratio of positive, and negative reviews.

Steps:
 - Data Extraction:
   
      Using Selenium, first scrapped all the course links for 7 different domains, such as technology, healthcare, Maths, Arts and 
      Humanities etc.
      Fetched all the reviews, and star ratings  for each course and assigned a unique ID to each course.
      A total of 75k reviews were fetched.

 - Data Cleaning:
   
       Some reviews are written in different languages. Using TextBlob, I identified the language for each review. I tried translating 
    non-English reviews into English with Google Translate, but I exceeded the free tier limit. So, for further analysis, I have used 
    reviews written in English.
       Converted all textual data into lowercase. Using regex, I removed all non-alpha characters such as special characters, extra 
    spaces, numbers, emoji, etc. Used SymSpellPy to convert each token into the appropriate English word.Removed Stopped words
    Using Lemmatization converted the word into its original form using the POS tag.

 - Data Preprocessing:
   
    Converted star ratings into positive, neutral, and negative
       - Ratings > 3  (Positive, 1)
       - Ratings = 3 (Neutral, 0)
       - Ratings < 3  (Negative, -1)
      To convert textual data into vectors we used the TF-IDF concept, which converted all tokens into numeric values.

 - Data Visualization:
   
     To understand data in a better manner, Performed visualization for the following.
        1) Plotted the number of courses for each subject in horizontal bar charts and the total number of reviews for each subject in             line charts.
        2) Percentage of positive, neutral, and negative reviews for each course.
   
 - Sentiment Analysis:
   
     We Split the data set into train  & test datasets in the ratio 70:30 respectively
    ### 4 Classification models used for prediction
      - Logistic Regression
      - KNN classifier
      - Random Forest
      - Gaussian Naïve Bayes

     - Evaluated model based on precision, recall, and f1 score.Out of 4 Models Random Forest performed the best.Saved our trained 
       model in a pickle file which we can use for further prediction.
   
