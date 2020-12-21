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

## if, elif, else







