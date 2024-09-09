# Titanic Survival Prediction in Julia
## Overview
This project predicts the survival of passengers aboard the Titanic using a Random Forest Classifier implemented in Julia. It involves data preprocessing, feature engineering, model training, and evaluation to achieve the best predictive performance.

## Features
- Data Preprocessing: Handling missing values, encoding categorical variables, and feature scaling.
- Feature Engineering: Creating new features to improve model accuracy.
- Random Forest Classifier: Implemented using the RandomForestClassifier for robust predictions.
- Model Evaluation: Assessing model performance using accuracy and other metrics.
- 
## Technologies Used
- Julia: The programming language used for the entire project.
- DataFrames.jl: For data manipulation and analysis.
- CSV.jl: For loading and handling data.
- DecisionTree.jl: For implementing the Random Forest Classifier.
- Plots.jl: For visualizing the results.
  
# Prerequisites
To run this project, ensure you have Julia installed along with the necessary packages:

```
using Pkg
Pkg.add("DataFrames")
Pkg.add("CSV")
Pkg.add("DecisionTree")
Pkg.add("Plots")
```

# Data visualization
## Group data by the column "Survived"
```
survived = combine(groupby(train_df, "Survived"), nrow=> "Count")
labels = ["Not Survived", "Survived"]
bar(labels, survived.Count, legend=false, text=text=survived.Count)
```

![image](https://github.com/user-attachments/assets/c9a72ec9-08e9-4a2c-87a8-2497b2ceac79)

## Group dataset by Sex column and show only rows where they survived
```
survived_sex = combine(groupby(train_df[train_df.Survived .== 1,:],"Sex"), nrow=>"Count")
labels = ["Male","Female"]
bar(labels, survived_sex.Count, legend=false, text=text=survived_sex.Count)
```

![image](https://github.com/user-attachments/assets/57ac50ab-3377-4c2c-8833-303c17a149ed)

## Group data by PClass column and show only rows where they did not survived
```
death_class = combine(groupby(train_df[train_df.Survived .== 0,:], "Pclass"), nrow=>"Count")
labels = ["First","Second", "Third"]
bar(labels, death_class.Count, legend=false, text=text=death_class.Count)
```

![image](https://github.com/user-attachments/assets/33fe364f-7dad-4b08-bf35-1f5e4a20b5c8)


#Contact
For questions or suggestions, reach out to davidotero856@gmail.com.
