# bushfireanalysis
Complete quantitative, forecast-driven analysis of Australian bushfire data.

The given dataset consists of monthly rainfall in millimetres in the Sydney catchment area from 1960 to 2020, as well as the total hectares burnt in bushfires in the same period. Whilst we initially (naïvely) treat rainfall in the relevant year as the predictor variable and the hectares burnt as as the variable to be forecast, we will proceed to more complicated time-series methods. In particular, we will utilise models that rely on data not just from the current period, but previous time-steps, and place appropriate weightings on the remoteness of such time-steps. The final model structure will involve feeding in several time-steps, each with monthly rainfall in a twelve-dimensional vector, and previous year bushfire data as a scalar in each step. Whilst the cessation of aggregation reduces the explainability of the model, doing so gives the recurrent neural network as much flexibility as possible to find the most complex relationships between monthly rainfall and bushfire severity.

## Repository structure
The repository follows a standard structure:
* [input](https://github.com/charlieoneill11/diabeticretinopathy/tree/main/input) contains both the patient data as well as the notebooks used to clean and feature engineer. The main datasets for prediction are `df_one_year.csv`, which has the accompanying kfold cross-validation grouped dataset `df_one_year_fold.csv`. Train and test splits, of the same name, have also been provided.
* [notebooks](https://github.com/charlieoneill11/diabeticretinopathy/tree/main/notebooks) contains notebooks used for experimenting and producing results. The notebooks are in order of the above three tasks.
* [src](https://github.com/charlieoneill11/diabeticretinopathy/tree/main/src) contains the Python scripts allowing the user to train and evaluate different models on the required dataset from the command line. The main script is [train.py](https://github.com/charlieoneill11/diabeticretinopathy/blob/main/src/train.py), which relies on the other scripts for configuration, dataset retrieval and argument parsing.

## Results
The results of the analysis is compiled in [Report.pdf](https://github.com/charlieoneill11/bushfireanalysis/blob/main/Bushfire_Report_Final.pdf).
