# Film Junky Union: A System for Filtering and Categorizing Movie Reviews

**Project Description**: <br> The Film Junky Union is interested in developing a system for filtering and categorizing movie reviews. The goal is to train a model to automatically detect negative reviews with an F1 score of at least 0.85.

**Dataset**: <br> Datasets from IMBD movie reviews was used for this project. 

**Exploratory Data Analysis (EDA):** Plots and preprocessing <br>
1. Plots created to display Number of Movies Over Years and Number of Reviews Over Year, Reviews per Year, and rating distribution between our training and testing sets.
2. Evaluation function for the machine learning models that takes in a model, training features, training target, test features, and test target and returns evaluation metrics including F1 score,  Receiver Operating Characteristic Area Under the Curve (ROC-AUC), Average Precision Score (APS), and accuracy. 
3. Normalization step to ensure that all models will accept text in lowercase without any non-alphabetic characters. 

**Model Development:** <br>

Model 0 - Constant/ Dummy Model: we create a dummy model to serve as baseline for comparison and evaluating other models. <br>
Accuracy: 0.5 <br>
F1: 0.0<br>
APS: 0.5<br>
ROC AUC: 0.5<br>

Model 1 - NLTK, TF-IDF and LR: We used NLTK for text preprocessing, TF-IDF for feature extraction, and Logistic Regression as the classifier model.  The results are: <br>
Accuracy: 0.88<br>
F1 Score: 0.88<br>
APS: 0.95<br>
ROC AUC: 0.95<br>


Model 2 -  spaCy, TF-IDF and LR: We used spaCy for text preprocessing, TF-IDF for feature extraction, and Logistic Regression as the classifier model. The results are:<br>
Accuracy: 0.87<br>
F1 Score: 0.80<br>
APS: 0.94<br>
ROC AUC: 0.95<br>
Model 2 does NOT meet the project criteria F! score. <br>


Model 3 - spaCy, TF-IDF and LGBMClassifier: We used spaCy for text preprocessing, TF-IDF for feature extraction, and LightGBM Classifier as the classifier. The results are:<br>
Accuracy: 0.85<br>
F1 Score: 0.85<br>
APS: 0.93<br>
ROC AUC: 0.93<br>


**Results:** <br> 

The models are tested with new original reviews to evaluate its performance: <br>  
1.'I did not simply like it, not my kind of movie.', <br>  
2.  'Well, I was bored and felt asleep in the middle of the movie.', <br>  
3.  'I was really fascinated with the movie',     <br>  
4.  'Even the actors looked really old and disinterested, and they got paid to be in the movie. What a soulless cash grab.', <br>  
5.   'I didn\'t expect the reboot to be so good! Writers really cared about the source material', <br>  
6.  'The movie had its upsides and downsides, but I feel like overall it\'s a decent flick. I could see myself going to see it again.', <br>  
7.  'What a rotten attempt at a comedy. Not a single joke lands, everyone acts annoying and loud, even kids won\'t like this!', <br>  
8.   'Launching on Netflix was a brave move & I really appreciate being able to binge on episode after episode, of this exciting intelligent new drama.' <br>  

When model 1 was fed new review data to evaluate, we get the following: <br>
Model 1 Predictions: Review 1: 0.16 Review 2: 0.18 Review 3: 0.56 Review 4: 0.13 Review 5: 0.26 Review 6: 0.48 Review 7: 0.05 Review 8: 0.84

Model 1 has the highest accuracy and F1 score and overall the models prediction aligns with the sentiments of the review, assigning low prob for the negative sounding reviews and higher probabilities for the reviews that were actually positive. <br>

Model 2: Accuracy: 0.87, F1 Score: 0.8, APS: 0.94, ROC AUC: 0.95
Model 2 Predictions: Review 1: 0.17 Review 2: 0.08 Review 3: 0.51 Review 4: 0.14 Review 5: 0.23 Review 6: 0.44 Review 7: 0.02 Review 8: 0.91

Model 2 does not meet our project F1 score requirement of being at least 0.85, however its predictions for positive/negative reviews are relatively accurate. 

Model 3: Accuracy: 0.85, F1 Score: 0.85, APS: 0.93, ROC AUC: 0.93
Model 3 Predictions: Review 1: 0.53 Review 2: 0.20 Review 3: 0.58 Review 4: 0.41 Review 5: 0.64 Review 6: 0.55 Review 7: 0.30 Review 8: 0.78

Model 3 meets the F1 score threshold of 0.85 and an accuracy score of 0.85. However, the predictions it generated for the reviews are much higher compare to the probabilities of the other 2 models, meaning model 3 tends to assign higher probability of the reviews being positive even to negative reviews.

**Conclusion:** <br>  the best model that the Film Junky Union should use to detect negative reviews is Model 1, Logistic Regression model using NLTK and TF-IDF, it meets the criteria set by the team and performs relatively well when used to classify our own reviews.






