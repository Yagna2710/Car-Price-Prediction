# Car-Price-Prediction
 A Machine Learning project for predicting car selling prices.
Introduction
The objective of this project is to develop a regression model to accurately predict car selling prices using a dataset containing various attributes such as fuel type, years of service, showroom price, number of previous owners, kilometers driven, seller type, and transmission type. This project follows a structured approach involving data preprocessing, model selection, training, evaluation, and fine-tuning.
________________________________________
1. Data Preprocessing
The dataset was loaded and examined for missing values and outliers. The key steps taken include:
•	Handling Missing Values:
Missing values were removed to maintain consistency across the dataset.
•	Feature Engineering:
A new feature, 'Car_Age' (calculated as the difference between the current year and the manufacturing year), was created to enhance the model's predictive ability. The original 'Year' column was then dropped.
•	Encoding Categorical Variables:
Categorical columns such as 'Fuel_Type', 'Seller_Type', and 'Transmission' were encoded using LabelEncoder to convert them into numerical representations.
•	Feature Scaling:
The data was scaled using StandardScaler to ensure uniformity across all features.
________________________________________
2. Model Selection & Training
Various regression models were evaluated to determine their predictive performance, with the Random Forest Regressor being selected due to its ability to handle complex data and provide accurate predictions.
•	Model Training:
The model was trained using the training dataset to learn patterns between input features and the target variable (selling prices).
•	Hyperparameter Tuning:
The Random Forest model was fine-tuned using RandomizedSearchCV with the following hyperparameters:
o	Number of Estimators: 50, 100, 200
o	Max Depth: None, 10, 20, 30
o	Min Samples Split: 2, 5, 10
o	Min Samples Leaf: 1, 2, 4
The best model was selected based on cross-validation performance.
________________________________________
3. Evaluation
The model was evaluated using the following metrics:
•	Mean Squared Error (MSE)
•	Root Mean Squared Error (RMSE)
•	Mean Absolute Error (MAE)
The results are summarized below:
Model	MSE	RMSE	MAE
Random Forest	155.6	12.47	8.23
Tuned Random Forest	148.2	12.17	7.96
The tuned Random Forest model demonstrated better performance, achieving the lowest MSE, RMSE, and MAE.
________________________________________
4. Feature Importance
The feature importance was analyzed using the Random Forest model. The most significant features affecting car selling prices include:
•	Showroom Price
•	Kilometers Driven
•	Car Age
•	Fuel Type
•	Transmission Type
These features had the highest impact on the prediction accuracy.
________________________________________
5. Visualization
The model's performance was visualized using bar plots to compare MSE and RMSE values before and after hyperparameter tuning. This visualization highlights the improvement achieved by fine-tuning.
________________________________________
6. Real-World Applications
The developed model can be utilized by car dealerships and individual sellers to predict the selling price of used cars based on their attributes. This assists in:
•	Setting competitive prices for used cars.
•	Making data-driven decisions during negotiations.
•	Helping buyers assess the fair market value of cars.
________________________________________
7. Deployment
The model was deployed as a Flask web application where users can input car attributes and receive an estimated selling price. The application takes inputs like fuel type, car age, kilometers driven, seller type, and transmission type, and predicts the selling price using the trained model.
________________________________________
8. Conclusion
The tuned Random Forest Regressor proved to be the most effective model for predicting car selling prices, demonstrating improved accuracy after hyperparameter optimization. This approach provides a robust and reliable method for estimating car prices in the used car market.
