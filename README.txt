THIS IS FOR THE PAPER: 'Bridging prediction accuracy and interpretability: A hybrid PSO-XGBoost-NLM for analyzing injury severity of EB-motor vehicle crashes in China'

ABSTRACT:
Accurately assessing the severity of motor vehicle collisions involving electric bicycles (EBs) and quantifying the robustness of the causal mechanisms that lead to the severity of such collisions is of crucial importance for evidence-based traffic safety management. This study developed a comprehensive analytical framework that combines Particle Swarm Optimization (PSO) - XGBoost with Nested Logit Model (NLM) to address the trade-off between predictive performance and interpretability. Using 1,026 cases that occurred in China from 2019 to 2024, the PSO algorithm optimized the hyperparameters of XGBoost, and the hybrid model ultimately achieved a test accuracy of 93.08%. The SHAP method was used to reveal the internal decision logic of the model. NLM further quantified the hierarchical influence of core factors on the severity of collisions, confirming that the estimated vehicle speed, driver gender, and vehicle type are the main predictive factors. Notably, the relative risk of fatal collisions for male drivers is significantly higher than that for female drivers, and vehicle speed has a significant hierarchical effect, which significantly increasing the probability of fatal accidents. This integrated PSO-XGBoost-NLM framework provides actionable and hierarchical insights for formulating targeted traffic safety intervention measures.

Description: By applying machine learning techniques and visualization methods, and using the data from the National Automobile Accident In-depth Investigation System, we predict the severity of electric bicycle and motor collision accidents. Finally, a statistical model is employed to quantitatively analyze the effects of various influencing factors.

Dataset Information: The dataset contains the following features, each representing different attributes of individuals:
EB rider characteristics:
Gender:
Type: Categorical (e.g., male, female)
Description: The gender of the individual.

Age group:
Type: Categorical(e.g., 16-25, 26-45, 46-65, >65)
Description: The age of the individual.

Illegal fault:
Type: Categorical(e.g., drinking, speeding, traffic signal violations, other)
Description: The type of illegal acts.

Helmet use:
Type: Categorical(e.g., yes, no)
Description: Check if a helmet is worn.

Driver characteristics:
Gender:
Type: Categorical (e.g., male, female)
Description: The gender of the individual.

Age group:
Type: Categorical(e.g., 16-25, 26-45, 46-65, >65)
Description: The age of the individual.

Driving experience:
Type: Categorical(e.g., ≤10, >10)
Description: The driver's age at the time of driving.

Illegal fault:
Type: Categorical(e.g., drinking, speeding, traffic signal violations, other)
Description: The type of illegal acts.

Vehicle characteristics:
Estimated speed:
Type: Categorical(e.g., <25, 25-40, 41-64, ≥65)
Description: The speed of the vehicle.

Vehicle type:
Type: Categorical(e.g., passenger cars, wagon, non-motorized two-wheelers/tricycles, semi-trailer tractor and trailer, buses)
Description: The type of the vehicle.

Vehicle age:
Type: Categorical(e.g., ≤5, 6-9, ≥10)
Description: The usage time of the vehicle.

Maneuver mode:
Type: Categorical(e.g., go straight, turn left, turn right, other)
Description: The operating status of the vehicle.

Environmental/temporal characteristics:
Weather:
Type: Categorical(e.g., cloudy, clear, rain)
Description: The weather conditions at the time of the accident.

Lighting conditions:
Type: Categorical(e.g., daylight, dark, dawn or dusk)
Description: The lighting conditions at the time of the accident.

Road surface:
Type: Categorical(e.g., dry, wet)
Description: The road conditions at the time of the accident.

Season:
Type: Categorical(e.g., spring, summer, autumn, winter)
Description: The season at the time of the accident.

Weekend:
Type: Categorical(e.g., yes, no)
Description: Whether the accident occur on the weekend.

Code Information: 
Accident.ipynb: Core analysis script. In this script, the entire process of data loading, PSO optimization of XGBoost model, multi-model comparison, and SHAP interpretability analysis is integrated.

NL.ipynb: Core analysis script for the Nested Logit Model (NLM), focusing on the nested logistic regression modeling and factor analysis for the classification of motor vehicle collision accidents.

Usage Instructions: The project codes are all in Jupyter Notebook format (.ipynb), supporting interactive running and result viewing. The steps to use them are as follows:
1. Make sure Jupyter Notebook is installed locally;
2. Save the code files (Accident.ipynb, NL.ipynb) to the local directory;
3. Open the terminal/command line, enter the directory where the code is located, and execute the command to start the Notebook:
4. In the Jupyter interface popped up in the browser, double-click the target file to open it;
5. Click "Cell" → "Run All" to execute all the code, or run cell by cell to view the real-time output results;
6. After the code runs, the visual charts will be automatically saved to the directory where the code is located, and the model evaluation results will be output in text/Excel format.

Requirements: The code was written in 12th Gen Intel(R) Core (TM) i7-12700H (2.30 GHz) processor, Win11 64-bit operating system, and 16.0 GB RAM. The foundational setup for the paper's results includes Python 3.8 and some packages dependencies such as scikit-learn, pandas, matplotlib, etc. It is important to note that variations in hardware and software configurations may lead to fluctuations in the results.

Method:
Since the NAIS contains sensitive data such as accident details, the files we are currently uploading have been processed to handle missing values, encoded for categorical features, and split between features and target variables.
For the PSO-XGBoost model, we use 5-fold cross-validation within the optimization framework to adjust the hyperparameters in the training data. Once the optimal parameters are determined, each model will be retrained on the entire training set and evaluated on a separate holdout test set. Model performance is measured using metrics such as accuracy, precision, recall, and F1 score. SHAP, a powerful model for explaining machine learning models, is used to visualize the predicted results.
NLM specifically uses some of the important feature factors obtained from PSO-XGBoost-SHAP through quantitative analysis. This part does not involve computer models.

Citations: 
This manuscript has not been published yet. Therefore, no citation content is included here for the time being. If it is published, we will make necessary amendments.

License & Contribution Guidelines：
This project is for academic research use only. All codes and datasets are provided exclusively for the review and reproduction of the manuscript. Commercial use, distribution, or modification without permission is prohibited. For questions or correspondence, please contact the corresponding author.
