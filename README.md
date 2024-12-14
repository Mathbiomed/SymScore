# SymScore
A symbolic regression-based tool for generating interpretable and accurate score tables for shortened clinical questionnaires

# SymScore
A symbolic regression-based tool for generating interpretable and accurate score tables for shortened clinical questionnaires

# Input the excel file containing survey response
Simply input the name of the Excel file containing the survey response. For example:
filename = "survery_response.xlsx"

The Excel file must contain the input variables as column names (e.g age, weight, BMI, etc) and the target variables. 
For regression tasks, the target variable is the total score of the input variables and for the classification tasks, the target variable is the diagnosis, where the entry is 0 for not having the disease and 1 as not having the disease.

Furthermore, the specific task should be specified here. For the variable task:
Write 0 for regression task and write 1 for classification task.


# Inputs for regression task
(Ignore this if your task is a classification task) 
Input the necessary information regarding the shortened questionnaire responses:

1. Selected categorical variables
For categorical questions where the responses increase with increasing severity, please provide the column names for the selected categorical variables and the response list.
For example, if the selected questions have column names 23, 28, 39, 51, 58, 60, then write selected_categorical_variables = [23, 28, 39, 51, 58, 60]

2. Categorical response list
If the possible responses are 1 - No, 2 - Slight, 3 - Moderate, 4 - Severe, then write down
categorical_response_list = [1, 2, 3, 4]

3. Maximum number of items in questionnaire
Please also input the maximum number of items in the questionnaire. For example, for the MCQI, there are 60 total items so max_items = 60.


# Inputs for classification task
(Ignore this if your task is a regression task) 
Input the necessary information regarding the shortened questionnaire responses:

1. Diagnosis column
Here, indicate the column name that contains the target value. In this case, the diagnosis for COMISA has column name 1. OSA so we write diagnosis_column = "1. OSA".

2. Selected categorical variables
For categorical questions where the responses increase with increasing severity, please provide the column names for the selected categorical variables and the response list. For example, if the selected questions have column names "ISI1a", "ISI1b", "ISI1c", "ISI2", "ISI5", then write categorical_items = ["ISI1a", "ISI1b", "ISI1c", "ISI2", "ISI5"].

3. Categorical response list
Additionally, if the possible responses are 1 - No, 2 - Slight, 3 - Moderate, 4 - Severe, then write down categorical_response_list = [1, 2, 3, 4]

4. Binary variables
If the questions contain binary variables, then indicate it. For example, for the variable sex, write categorical_items_binary = ['sex'] and binary_variables = ['Male', 'Female']

5. Float variablles
Similarly indicate the float variables by writing the column names. For example here, float_items = ["age", "weight", "BMI"].

6. Step size
Please also indicate the step sizes for the float items. These step sizes indicate how accurate you want your response grouping to be. For example, a step size of 1 will check if the grouping is optimal for every 1-step increase in value, while a step size of 10 will check for groupings after every 10 unit increase.
