# Deal_Closure_Prediction_Using_ML

### Summary
Develop and compare multiple machine learning models to predict deal outcomes (Won/Lost) using sales activity data to maximize prediction accuracy.
Background
The task is to identify which deals are most likely to be won or lost based on historical sales activities and deal characteristics. This will help prioritize sales efforts and improve conversion rates.

### Dataset Features
The dataset deal_details.xlsx contains the following features for analysis:
•	id: Unique deal identifier
•	email_count: Number of emails sent/received
•	call_count: Number of calls made
•	task_count: Number of tasks created
•	meeting_count: Number of meetings scheduled/held
•	notes_count: Number of notes added
•	conversation_count: Number of conversations tracked
•	deal_size: Monetary value of the deal
•	close_date: Expected/actual close date
•	deal_type: Category/type of deal
•	deal_stage: Target variable (Won/Lost)

### Acceptance Criteria
Data Analysis & Preprocessing
•	Perform exploratory data analysis (EDA) with visualizations
•	Handle missing values and outliers appropriately
•	Create feature engineering (e.g., activity ratios, time-based features)
•	Analyse feature correlations and importance
•	Split data into training, validation, and test sets (70/15/15 or 80/20)

## *************************************************************************************************

## 1. Model Assumptions and Limitations
  ### Assumptions:
  -	The model assumes the historical CRM data reflects real business trends and that patterns found in past deals are predictive of future outcomes.
  -	It also assumes that the input features (e.g., deal type, customer engagement metrics) are reliable, well-labeled, and meaningful for learning.
  -	The binary classification approach assumes only two deal stages: “Closed Won” and “Closed Lost,” with no intermediate or ambiguous outcomes.
  
  ### Limitations:
  - The model may struggle with limited or imbalanced class distribution, especially if “Closed Won” deals are underrepresented.
  - It does not account for real-time changes like competitor moves, pricing strategy shifts, or economic conditions that can affect deal outcomes.
  - Interpretability can be limited, especially in ensemble methods like XGBoost and LightGBM, which act as black boxes for some stakeholders.

## 2. Business Insights and Recommendations
  ### Insights:
  - Deals with frequent sales interactions (calls, emails) and faster follow-up times tend to have higher success rates, highlighting the value of proactive communication.
  -	Certain deal types consistently perform better in terms of closure, suggesting high-value segments for targeted strategies.
  -	Features like time to close and the number of activities help differentiate between successful and lost deals, pointing to operational improvements.
  
  ### Recommendations:
  - Sales teams should prioritize deals with strong interaction history and those matching high-conversion profiles identified by the model.
  - Marketing efforts can be refined to target industries or client types that have historically converted better.
  - Use the model scores to rank and segment ongoing deals in the CRM for smarter pipeline management and better forecasting accuracy.

## 3. Executive Summary with Key Findings
Using CRM activity data and deal characteristics, this machine learning model predicts whether a sales deal will be won or lost. It uses classification algorithms such as Logistic Regression, Random Forest, XGBoost, and LightGBM for robust and scalable prediction.
  
  ### Key Findings:
  - Important predictors included deal type, total activities, industry, and time-to-close, which align closely with business intuition.

## 4.  Model Performance Summary
 
  Several classification algorithms were evaluated to predict deal outcomes, using metrics such as Accuracy, Precision, Recall, F1-score, AUC, and Average Precision. The key observations are:
  - LightGBM and Random Forest both achieved perfect scores across all evaluation metrics, indicating exceptional predictive power and robustness in distinguishing between won and lost deals.
  - XGBoost also performed very well with 97% accuracy and a perfect recall of 1.00, meaning it successfully identified all positive (Closed Won) deals. Its F1-score (0.92) and AUC (0.9933) reflect the strong balance between precision and recall.
  - Logistic Regression, while simple and interpretable, lagged with only 53% accuracy and relatively poor performance on precision and F1-score, making it less suitable for this complex classification task.
  - Stacking and Blending models showed high accuracy (97%) and strong precision-recall tradeoffs. Blending favored precision (1.00), while stacking slightly favored recall (1.00), making them both strong ensemble contenders.
  ####Business Value:
    The model empowers sales teams with data-driven insights to focus their efforts on the most promising deals, optimize communication strategies, and improve closure rates, ultimately leading to better revenue forecasting and operational efficiency.

##Conclusion:
Which model to choose:
-	If we want perfection in every metric, LightGBM is the winner.
-	If the need is caring about catching all "Won" deals (High Recall): Stacking or XGBoost are great.
-	If the need is caring most about precision (No false positives): Blending is a top choice.

Overall, Logistic Regression is best for interpretability, LightGBM and Random Forest consistently outperformed others, making them ideal for production deployment. If interpretability is needed alongside high accuracy, XGBoost or Stacking models provide a good compromise

