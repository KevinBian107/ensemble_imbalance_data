# The Data Science Life Cycle 📊
* Porject Website: https://kevinbian107.github.io/ensemble-imbalanced-data/
* This Repository is for UCSD 2024 Winter DSC 80 Final Project
* No raw data is pushed onto Github, just the analysis and predictive models themselves are in the repository.
* [Here](https://drive.google.com/file/d/1kIbMz6jlhleiZ9_3QthmUnifoSds_2EI/view) is the link to the original data set

# Helper Util Functions
The `utils` folder contains all python functions needed for this project, teh jupytar notebooks all calls the python file for function purpose. Jupytar notebook here is only for visulization. **All important code are in the python file and applied to the DataFrame using the `.pipe()` function for clear data transformation purposes**.

- food_data: raw data folder containing 2 data frame, one for reviews & rating and one for recipe

- utils
    - `dsc80_utils.py`: Some visulization of DataFrame tools
    - `eda.py`: All transformation functions, outlier checking, normalization, special groupby functions,..., anything for **Explorative Data Analysis** purposes
    - `graph.py`: Some lareg graphing functions for visualizations
    - `missing_m.py`: For assessing **Missngness Mechanism**

- Developer Jupytar Notebooks:
    - `planning.ipynb`: Full empty rubrics for this project
    - `eda.ipynb`: Main **Explorative Data Analysis** notebook, describing _data characteristics_
    - `missing_m.ipynb`: Assessing the **Missingess Mechanism** of the data set
    - `permutation.ipynb`: Conducting hypothesis testings
    - `model.ipynb`: Building a **Baseline model** for prediction
    - `word2vec.ipynb`: Basic Introduction to the idea of NLP word conversion to vector distributional representation
    
- Full Report
    - `report.ipynb`: Full report of the project

# Data Set Casting Logics
1. `int`: [name, contributor_id, user_id, recipe_id, ]
    - quantitative or qualitative, but cannot perform mathamatical operations (**quntitative discrete**)
    - `name` is the name of recipe
    - `contributor_id` is the author id of the recipe _(shape=7157)_
    - `recipe_id` is the id of teh recipe _(shape=25287)_
        - `id` from the original dataframe also is the id of the recipe, dropped after merging
    - `user_id` is the id of the reviewer _(shape=8402)_
2. `List`: [tags, steps, description, ingredients, review]
    - qualitative, no mathamatical operation (**qualitative discrete**)
3. `int`: [n_steps, minutes, n_ingredients, rating]
    - quantitative mathamatical operations allowed (**quantitative continuous**)
4. `float`: [avg_rating, calories, total_fat sugar, sodium, protein, sat_fat, carbs]
    - quantitative mathamatical operations allowed (**quantitative continuous**)
5. `Timestamp`: [recipe_date, review_date]
    - quantitative mathamatical operations allowed (**quantitative continuous**)

# Predictive Question
We are using the original big DataFrame for predicting rating and we want to predict `rating` as a classfication problem, prdicting `rating` (5 catagories) in the user_id DataFrame to demonstarte understanding of user preference.
