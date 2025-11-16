# MSCS 634 Project Deliverable 2


## Summary of the dataset, modeling process, and evaluation results.


The project used a Kaggle dataset with 6,607 student records to figure out what factors influence exam scores. This data included 20 different features for each student, such as their study hours, attendance, and parental involvement. Before building any models, the data was cleaned by filling in a small amount of missing information and checking for any duplicate rows.

The main goal was to predict a student's Exam_Score. To do this, different types of regression models were built and compared, including simple, multiple, and polynomial models. A key step was "feature engineering," which involved converting all 20 data columns into 24 usable features for the models to analyze.

The results showed that the number of features was the most critical factor. A model using only one feature performed poorly, but models using all 24 features saw a massive 121% improvement. The most complex model (Polynomial Degree 3) failed completely, performing just as badly as the simplest one. The best models like Lasso, Ridge, and standard Multiple Linear all performed equally well, explaining about 77% of the score variance and predicting scores with an average error of just ±1.8 points.


## Meaningful insights and key observations about model performance.

Based on the regression models, there were multiple factors that influenced what the final exam score if the student will be. There was no single factor that would best predict the score of the student. This is why the multiple linear regression performed extremely well compared to single factor linear regression.While several models ended up at the top, their performance was nearly identical, meaning the special "regularization" techniques didn't offer a real advantage over the standard multiple linear model. The key was finding a balance; the simplest model was too basic, and the most complicated ones performed poorly. The best model seems to be Lasso as it is reliable and can explain about 77% of the variation in exam scores, and its predictions are typically accurate within ±1.8 points.

## Challenges encountered and describe how they were addressed.

One of the main challenges I faced was running polynomial regression with higher-degree values, such as 4 and 5. These higher degrees required a significantly larger amount of computation due to the increased number of features, which made the process slow and resource-intensive. To address this, I decided to omit degrees 4 and 5 and instead focused on completing the calculations for degree 3, which only took a few minutes. By analyzing the performance of degrees 1, 2, and 3, I was able to gain a clear understanding of the trend and expected performance for higher-degree models without overloading the system.

Another challenge I faced was understanding why Ridge and Lasso regularization seemed to have little effect. The cross-validated R² scores were almost identical across different alpha values, making it hard to tell if regularization was helping. To address this, I expanded the alpha range to include very small values (0.0001) and very large values (up to 1000), increased precision to six decimal places to detect subtle differences, and added analysis to separate the small alpha range (where models performed best) from values that were too extreme. I also implemented automatic detection and explanations for cases where regularization had minimal impact. From this, I realized that the model was not heavily overfitting, so regularization offered little additional benefit.
