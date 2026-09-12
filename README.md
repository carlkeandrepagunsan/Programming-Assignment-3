# Programming-Assignment-3
**Carl Keandre L. Pagunsan | 2ECE-C** <br>
The repository contains the Programming Assignment 3 for the ECE2112 or Advanced Computer Programming and Algorithms Class. The objectives of the assignment are to:
1. load a CSV dataset into a Pandas DataFrame;
2. select rows and columns using positional and label-based indexing;
3. filter records using conditions on a DataFrame column; and
4. extract a well-defined subset of data without changing the source data.

Before the problems were attempted, pandas was first imported into the session for python to be able to use its functions:
```python
import pandas as pd
```
Then, cars.csv was read using the function pd.read_csv so that the data inside the csv can be read and manipulated by the functions used in the assignment.
# A. POSITIONAL AND LABEL-BASED SLICING
Initially, the shape and the column names of the csv file ```cars``` was shown using the ```shape``` and ```columns``` functions:
```python
cars.shape
cars.columns
```
Then, ```iloc``` was used to positionally slice the data using row numbers and store them in the variable ```cars_6_to_10```:
```python
cars_6_to_10 = cars.iloc[5:10]
cars_6_to_10
```
Finally, the model, mpg, cyl, hp, and gear of the cars in those rows were displayed:
```python
cars_6_to_10[['Model', 'mpg', 'cyl', 'hp', 'gear']]
```
# B. MODEL LOOKUP
Using Boolean Indexing, the row for the Toyota Corolla was shown and stored in the ```toyota``` variable, then displayed:
```python
toyota = cars[cars['Model']=='Toyota Corolla']
toyota
```
Then finally, the same was done for the Pontiac Firebird, but using the ```loc``` function to only display the model, mpg, hp, and wt of the car and store it in the ```pontiac``` variable:
```python
pontiac = cars.loc[cars['Model']=='Pontiac Firebird', ['Model', 'mpg', 'hp', 'wt']]
pontiac
```
# C. MULTI-MODEL SUBSETTING
The task was to create a DataFrame named selected_cars containing only the records for the models Datsun 710,
Lotus Europa, and Ferrari Dino while only showing the columns model, mpg, cyl, hp, and gear.
The task was completed using Boolean Indexing in order to use the specific model name to search, and then the OR or |operator to be able to search for each model in one line. Finally, the ```loc``` function was used to extract only the specific columns needed, finally the shape was shown for the required check.
```python
selected_cars = cars.loc[(cars['Model']=='Datsun 710') | (cars['Model']=='Lotus Europa') | (cars['Model']=='Ferrari Dino'), ['Model', 'mpg', 'cyl', 'hp', 'gear']]
selected_cars.shape
```
## VERSION HISTORY
September 3, 2026 - README file created <br>
September 12, 2026 - Details added
