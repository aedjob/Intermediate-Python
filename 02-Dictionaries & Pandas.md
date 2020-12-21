# Dictionaries & Pandas
## Dictionaries, Part 1
### List (not convenient)
```python
pop = [45, 12, 67]
countries = ["afghanistan", "albania", "algeria"]

ind_alb = countries.index("albania")

ind_alb       #returns position in list countries
pop[ind_alb]  #returns population of albania
```
### Dictionary (best option!)
```python
pop = [45, 12, 67]
countries = ["afghanistan", "albania", "algeria"]

...
    
world = {"afghanistan":45, "albania":12, "algeria":67}
world["albania"]    #returns population of albania
```
```python
# Definition of dictionary
europe = {'spain':'madrid', 'france':'paris', 'germany':'berlin', 'norway':'oslo' }

# Print out the keys in europe
print(europe.keys())

# Print out value that belongs to key 'norway'
print(europe['norway'])
```

## Dictionaries, Part 2
- Keys have to be immutable objects (can't use a list inside a dictionary)
To modify objects inside a dictionary
```python
world['sealand'] = 0.000027     #adds/updates object "sealand" to dictionary world with the assigned value
world

"sealand" in world      #checks if "sealand" is in dictionary world (True/False)

del(world["sealand"])   #deletes object from dictionary
world
```

| list | dictionary |
| ---- | ---- |
| indexed by range of numbers  | indexed by unique keys  |
| collection of values, order matters, select entire subsets  | lookup table with unique keys |

```python
# Definition of dictionary
europe = {'spain':'madrid', 'france':'paris', 'germany':'berlin', 'norway':'oslo' }

# Add italy to europe
europe["italy"] = "rome"

# Print out italy in europe
print('italy' in europe)

# Add poland to europe
europe["poland"] = "warsaw"

# Print europe
print(europe)

# Definition of dictionary
europe = {'spain':'madrid', 'france':'paris', 'germany':'bonn',
          'norway':'oslo', 'italy':'rome', 'poland':'warsaw',
          'australia':'vienna' }

# Update capital of germany
europe['germany'] = 'berlin'

# Remove australia
del(europe['australia'])

# Print europe
print(europe)

# Dictionary of dictionaries
europe = { 'spain': { 'capital':'madrid', 'population':46.77 },
           'france': { 'capital':'paris', 'population':66.03 },
           'germany': { 'capital':'berlin', 'population':80.62 },
           'norway': { 'capital':'oslo', 'population':5.084 } }


# Print out the capital of France
print(europe['france']['population'])

# Create sub-dictionary data
# Add data to europe under key 'italy'
europe['italy'] = {'capital':'rome', 'population':59.83}

# Print europe
print(europe)
```

## Pandas, Part 1
```python
import pandas as pd

dict = {                                            #create dictionary
    "country":["Brazil","Russia","India"],
    "capital":["Brasilia","Moscow","New Delhi"],
    "area":[8,10,3],
    "population":[200,143,1205],
    }

brics = pd.DataFrame(dict)          #create dataframe from dictionary
brics.index = ["BR","RU","IN"]      #add labels
brics = pd.read_csv("path/to/brics.csv", index_col = 0)     #import csv file
```
```python
# Pre-defined lists
names = ['United States', 'Australia', 'Japan', 'India', 'Russia', 'Morocco', 'Egypt']
dr =  [True, False, False, False, True, True, True]
cpc = [809, 731, 588, 18, 200, 70, 45]

# Import pandas as pd
import pandas as pd

# Create dictionary my_dict with three key:value pairs: my_dict
my_dict = {
    'country': names,
    'drives_right': dr,
    'cars_per_cap': cpc,
}

# Build a DataFrame cars from my_dict: cars
cars = pd.DataFrame(my_dict)

# Definition of row_labels
row_labels = ['US', 'AUS', 'JPN', 'IN', 'RU', 'MOR', 'EG']

# Specify row labels of cars
cars.index = row_labels

# Print cars
print(cars)

# Import pandas as pd
import pandas as pd

# Import the cars.csv data: cars
cars = pd.read_csv('cars.csv', index_col = 0)

# Print out cars
print(cars)
```

## Pandas, Part 2
### Index and data select
- square brackets
- advanced methods:
    - loc (label-based) - can access rows and columns at the same time
    - iloc (integer position-based)
```python
# Column access []
brics["country"]    #access the whole variable (one dimensional array)
brics[["country"]]    #access the whole variable (column)
brics[["country", "capital"]]   #access the two variables

# Row access []
brics[1:4]      #access row 1 to 4

# Row access loc
brics.loc[["RU", "IN"]]     #access "RU" and "IN" rows (with loc)

# Row & column loc
brics.loc[["RU", "IN"], ["country","capital"]]      #access the defined rows and columns
brics.loc[:, ["country","capital"]]      #access the defined columns and ALL rows

# Row access iloc
brics.iloc[[1]]         #access row 1 (based on position instead of label "RU")
brics.iloc[:, [0,1]]    #access all rows and columns 0 and 1
```
```python
# Import cars data
import pandas as pd
cars = pd.read_csv('cars.csv', index_col = 0)

# Print out drives_right value of Morocco
print(cars.loc[['MOR'],['drives_right']])

# Print sub-DataFrame
print(cars.iloc[[4,5],[1,2]])

# Import cars data
import pandas as pd
cars = pd.read_csv('cars.csv', index_col = 0)

# Print out drives_right column as Series
print(cars['drives_right'])

# Print out drives_right column as DataFrame
print(cars.loc[:,['drives_right']])

# Print out cars_per_cap and drives_right as DataFrame
print(cars.loc[:,['cars_per_cap','drives_right']])
```

