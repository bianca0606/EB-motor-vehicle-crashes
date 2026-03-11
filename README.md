## Description
This project focuses on the collection, analysis and visualization of data related to collisions between electric bicycles(EBs) and motor vehicles. The aim is to uncover the underlying patterns of collision accidents through structured datasets and reusable code, providing data support for traffic management, safety analysis and policy formulation. The project includes a preprocessed dataset of motor vehicle collision accidents, as well as code scripts for data cleaning, analysis and visualization.
## Dataset Information
### Data Source
The dataset is derived from the National Automobile Accident In-depth Investigation System (NAIS), covering core dimensions such as the characteristics of EB riders (such as gender, age group, violation behavior, whether wearing a helmet), driver characteristics (such as gender, age group, driving experience, violation behavior), vehicle characteristics (such as estimated speed, vehicle type, vehicle age, driving mode), and environmental/time characteristics (such as weather, lighting conditions, road conditions, season, weekend).
### Data file structure
- EB-motor crashes (NAIS).xlsx: Raw encoded collision accident data, in Excel format, containing the complete core dimension information of 1,026 accident cases.
- codebook.xlsx: Data encoding file, explaining the meaning of the numerical codes in the EB-motor crashes (NAIS) file.
### Data time range
All registered electric bicycle and motor vehicle collision accident data from January 2019 to December 2024.
### Data size
A total of 1026 records, covering most of the electric bicycle and motor vehicle accident types in China.
## Code Information
### Code Structure
- Accident.ipynb: Core analysis script. In this script, the entire process of data loading, PSO optimization of XGBoost model, multi-model comparison, SHAP interpretability analysis is integrated, including 7 core steps:
1. Data loading and preprocessing (missing value check, feature/label separation, standardization, dataset division);
2. Define PSO particle swarm optimizer class to implement hyperparameter optimization logic;
3. Define XGBoost model fitness function, set the boundary of parameters to be optimized;
4. Execute PSO optimization, output the optimal parameters and draw the convergence curve;
5. Based on the optimal parameters, train the XGBoost model, evaluate the performance of the test set, generate confusion matrix, feature importance graph;
6. Conduct SHAP interpretability analysis, generate visual results such as feature importance, dependency graph, force diagram, decision diagram, etc.;
7. Compare the performance of PSO-XGBoost, basic XGBoost, random forest, BP neural network, and output the evaluation index table and visual comparison chart.
- NL.ipynb: Core analysis script of the Nested Logit Model (NLM), focusing on the nested logistic regression modeling and impact factor analysis for motor vehicle collision accidents. The main functions are as follows:
1. Data preprocessing: implement missing value deletion, 3σ principle outlier filtering, high collinearity variable elimination, feature standardization, and sample balance processing based on the accident risk nested structure;
2. Nested structure definition: divide accident classification into low-risk/high-risk nested layers, complete the encoding conversion of the target variable and nested layers;
3. Model core construction: define the negative log-likelihood function of the nested Logit model, implement the calculation of layer internal/inter-layer utility functions and probability derivation;
4. Model fitting: use L-BFGS-B optimization algorithm to fit the model, solve all parameters including inclusive value (IV), layer internal coefficients, and layer inter-coefficients;
5. Result analysis: output the convergence status, log-likelihood value, inclusive value (IV), and interpretation, generate the table of layer internal/inter-layer coefficients, quantify the influence intensity of core variables on accident classification;
6. Visualization: draw the bar chart of the influence intensity of core variables, mark the threshold of strong/medium/weak influence, and save the visualization result.
### Code Language and Style
The core code is written in Juypter notebook.
## User Instructions ‎
### Environment Preparation
You need to install the required Python libraries for the project in advance. Ensure that the running environment meets the requirements.
### Code Usage
The code of this project is in Jupyter Notebook format (.ipynb), supporting interactive running and result viewing. The usage steps are as follows:
1. Make sure Jupyter Notebook is installed locally;
2. Save the code files (Accident.ipynb, NL.ipynb) to the local directory;
3. Open the terminal/command line, enter the directory where the code is located, and execute the command to start the Notebook:
4. In the Jupyter interface popped up in the browser, double-click the target file to open it;
5. Click "Cell" → "Run All" to execute all the code, or run cell by cell to view the real-time output results;
6. After the code runs, the visual charts will be automatically saved to the directory where the code is located, and the model evaluation results will be output in text/Excel format.
## Requirements
### Basic environment requirements
Python version: ≥ 3.8 (recommended 3.9~3.11, compatible with stable versions of all dependent libraries)
Operating system: Windows/macOS/Linux (no special system restrictions)
### Core dependent libraries
The following are the Python libraries required to run all the code in this project:
|Libraries     |               |
|--------------|---------------|
| pandas       |scikit-learn   |                                                              
| numpy        | xgboost       |
| scipy        | shap          |
| matplotlib   | openpyxl      |  
| seaborn      |               | 
## Methodology
### Data preprocessing
- Missing values: Remove samples with missing core fields;
- Outliers: Filter extreme values of continuous variables based on the 3σ principle;
- Collinearity: Eliminate features with a correlation coefficient greater than 0.7;
- Standardization: Z-score standardize continuous features.
### Model methods
- Nested Logit model: Divide the nested layers according to accident risk (low/high), and fit parameters using the L-BFGS-B algorithm;
- PSO-XGBoost: Use the PSO algorithm to optimize the hyperparameters of XGBoost, and compare it with the basic XGBoost/RF/BP neural network;
- Interpretability: Analyze feature contribution using the SHAP framework, and supplement the interpretation of nested Logit coefficients.
	
	
	
	
