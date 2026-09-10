# ECE-2112-PA-3

### **Made by: Evan James G. Paciencia|2ECE-C**

This repository contains Programming Assignment 3 for the course "Advanced Computer Programming" of S.Y. 2026-2027. This assignment covers three problems of PYTHON DATA ANALYSIS (PANDAS) of about Module 3 - Pandas
## A. POSITIONAL AND LABEL-BASED SLICING

Display the shape and the complete list of column names of cars. Using positional slicing, create cars 6-10 by selecting rows 6-10 of the dataset, where the first data row is row 1. From cars 6 to 10, display only the columns Model, mpg, cyl, hp, and gear, in that order. The row selection in part (b) must use iloc; the column selection in part (c) must use column labels.

<br>The following functions and methods were used:<br>
`pd.read_csv()` - Loads a CSV file to a Pandas DataFrame <br>
`.shape` - Gets the number of rows and columns of a DataFrame <br>
`.columns` - Gets the column names of a DataFrame <br>
`.iloc[]` - Selects rows and columns using row and column index <br>
`.tolist()` - Converts the Pandas Index into a Python list



<br>These built-in functions and methods were then combined to produce a Python code that meets the requirements: Load the cars.csv dataset into a DataFrame named cars, display its shape and column names, select rows 6 to 10 using positional slicing, and display only Model, mpg, cyl, hp, and gear from those rows.<br><br>

```python
cars=pd.read_csv('cars.csv')
cars_6_to_10=cars.iloc[5:10,[0,1,2,3, 4,10]]
print("shape is", cars_6_to_10.shape,"\ncomlumn is", cars_6_to_10.columns.tolist())
cars_6_to_10
```

## B. MODEL LOOKUP

Use Boolean indexing on the Model column to answer both requests. Display the complete row for Toyota Corolla. For Pontiac Firebird, display only Model, mpg, hp, and wt. Store the two results in toyota and pontiac, respectively. Do not use a hard-coded row number to locate either model.

<br>The following functions and methods were used:<br>
`.loc[]` - selects using labels/names <br>
`.DataFrame` - A table in Pandas that stores data in rows and columns <br>

<br>These built-in functions and methods were then combined to produce a Python code that meets the requirements: Find Toyota Corolla and Pontiac Firebird using their model values instead of row numbers, then store the results in toyota and pontiac.<br><br>

```python
toyota=pd.DataFrame(cars).loc[pd.DataFrame(cars)['Model']=='Toyota Corolla']
pontiac=pd.DataFrame(cars).loc[pd.DataFrame(cars)['Model']=='Pontiac Firebird',['Model','mpg','hp','wt']]

```

## C. MULTI-MODEL SUBSETTING

Create a DataFrame named selected cars containing only the records for three models: Datsun 710, Lotus Europa, and Ferrari Dino. For these records, retain only the Model, mpg, cyl, hp, and gear columns. Select the rows by their model values rather than by row numbers. Display selected cars and their shape. The final DataFrame must contain exactly three rows and five columns.

<br>The following functions and methods were used:<br>
`.loc()` -  selects using labels/names <br>
`.shape` - Gets the number of rows and columns of a DataFrame <br>
`.DataFrame` - A table in Pandas that stores data in rows and columns <br>

<br>These built-in functions and methods were then combined to produce a Python code that meets the requirements: Select the records for Datsun 710, Lotus Europa, and Ferrari Dino using their model values, retain only Model, mpg, cyl, hp, and gear, and display the resulting DataFrame and its shape.<br><br>

```python
selected_cars=pd.DataFrame(cars).loc[
    (pd.DataFrame(cars)['Model']=='Datsun 710') | 
     (pd.DataFrame(cars)['Model']=='Lotus Europa') |
    (pd.DataFrame(cars)['Model']=='Ferrari Dino'), ['Model', 'mpg', 'cyl', 'hp','gear']]
print("shape is", selected_cars.shape)
selected_cars
```

# Edit/History Log

Created: 9/10/2026 <br>Last edited: 9/10/2026 <br>
