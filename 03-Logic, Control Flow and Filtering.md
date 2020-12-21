# Logic, Control Flow and Filtering
## Comparison operators
<, <=, >, >=, ==, !=
```python
# Numeric comparisons
2 < 3             #returns true
2 == 3            #returns false
2 <= 3            #returns true
"carl" < "chris"  #returns true
```
## Boolean operators
and, or, not
```python
x = 12
x > 5 and x < 15  #returns True

y = 5
y < 7 or y > 13   #returns True
```
for arrays: (numpy)
- logical_and()
- logical_or()
- logical_not()
```python
# Create arrays
import numpy as np
my_house = np.array([18.0, 20.0, 10.75, 9.50])
your_house = np.array([14.0, 24.0, 14.25, 9.0])

# my_house greater than 18.5 or smaller than 10
print(np.logical_or(my_house > 18.5, my_house < 10))

# Both my_house and your_house smaller than 11
print(np.logical_and(my_house < 11, your_house < 11))
```

## if, elif, else (conditional statements)
```python
z = 6
if z % 2 == 0 :
  print("checking" + str(z))
  print("z is divisible by 2")
elif z % 3 == 0 :
  print("z is divisible by 3")
else :
  print("z is neither divisible by 2 nor by 3")
```

## Filtering pandas dataframes
```python
# 1. Get column
brics["area"]

# 2. Compare
is_huge = brics["area"] > 8

# 3. Subset DF
brics[is_huge]    #returns values from the column 'area' that meet the previous condition

# The three previous steps can be straight:
brics[brics["area"] > 8]

# For several conditions:
brics[np.logical_and(brics["area"] > 8, brics["area"] < 10)]
```
```python
# Import cars data
import pandas as pd
cars = pd.read_csv('cars.csv', index_col = 0)
cars

# Extract drives_right column as Series: dr
dr = cars['drives_right']
# Use dr to subset cars: sel
sel = cars[dr == True]
# Print sel
print(sel)

# Previous code can also be
sel = cars[cars['drives_right']]
# Print sel
print(sel)

# Create car_maniac: observations that have a cars_per_cap over 500
car_maniac = cars[cars['cars_per_cap'] > 500]
# Print car_maniac
print(car_maniac)

# Import numpy, you'll need this
import numpy as np
# Create medium: observations with cars_per_cap between 100 and 500
medium = cars[np.logical_and(cars['cars_per_cap'] > 100, cars['cars_per_cap'] < 500)]
# Print medium
print(medium)
```



