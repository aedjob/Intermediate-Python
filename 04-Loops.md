# Loops
## while loop
repeating an action until a condition is met
```python
error = 50

while error > 1:
    error = error / 4
    print(error)
```
## for loop
```python
fam = [1.73, 1.68, 1.71, 1.89]
for height in fam :
    print(height)     #prints each element one by one

for index, height in enumerate(fam) :
    print("index" + str(index) + ":" + str(height))     #prints each element one by one as well as the index
```
```python
# areas list
areas = [11.25, 18.0, 20.0, 10.75, 9.50]

# Change for loop to use enumerate() and update print()
for index, y in enumerate(areas) :
    print("room " + str(index) + ": " + str(y))
    
# house list of lists
house = [["hallway", 11.25], 
         ["kitchen", 18.0], 
         ["living room", 20.0], 
         ["bedroom", 10.75], 
         ["bathroom", 9.50]]
         
# Build a for loop from scratch
for x, y in house:
    print("the " + x + " is " + str(y) + " sqm")
```

## Loop Data Structures Part 1
```python
# Dictionary
world = {"afghanistan":30.55,
         "albania":2.77,
         "algeria":39.21 }
for k, v in world.items() : 
    print(k + "--" + str(v))
    
# Numpy arrays
import numpy as np
np_height = np.array([21, 32, 23, 23])
np_weight = np.array([76, 46, 98, 66])
bmi = np_weight / np_height ** 2
for val in bmi:
    print(val)

# 2D numpy arrays
import numpy as np
np_height = np.array([21, 32, 23, 23])
np_weight = np.array([76, 46, 98, 66])
meas = np.array([np_weight, np_height])
for val in np.nditer(meas) :
    print(val)
```
- Dictionary
    - for `key, val in my_dict.items() :`
- Numpy array
    - `for val in np.nditer(my_array) :`


