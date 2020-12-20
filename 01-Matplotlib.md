# Matplotlib
## Basic plots with Matplotlib
- Visualization
- Data structure
- Control structures
- Case study

```python
import matplotlib.pyplot as plt
year = [1950,1955,1967,1990]
pop = [2,3,5,7]
plt.plot(year,pop)    #replace 'plot' for 'scatter' to scatter plot
plt.show()
```
```python
# Print the last item from year and pop
print(year[-1])
print(pop[-1])

# Import matplotlib.pyplot as plt
import matplotlib.pyplot as plt

# Make a line plot: year on the x-axis, pop on the y-axis
plt.plot(
    year,
    pop
)

# Display the plot with plt.show()
plt.show()
```
```python
# Change the line plot below to a scatter plot
plt.scatter(gdp_cap, life_exp)

# Put the x-axis on a logarithmic scale
plt.xscale('log')

# Show plot
plt.show()
```

## Histogram
- Explore dataset
- **Get idea about distribution** (split by bins)
```python
import matplotlib.pyplot as plt
help(plt.hist)    #shows all the arguments of the function

values = [2,6,2,8,5,4,9,7,6,5,9,3]
plt.hist(values, 
         bins=3)
plt.show()
plt.clf()   #cleans up plot
```

## Customization
- Plot types (color, shapes, labels, axes)
- Depends on data and story to tell

```python
import matplotlib.pyplot as plt
year = [1950, 1955, 1967, 1990]
pop = [2.4, 3.2, 5.1, 7.8]

#Add more data
year = [1800, 1850, 1900] + year
pop = [1.3, 1.5, 2.1] + pop

plt.plot(year,pop)

plt.xlabel('Year')
plt.ylabel('Population')
plt.title('World population projections')
plt.yticks([0, 2, 4, 6, 8, 10],
           ['0', '2B', '4B', '6B', '8B', '10B'])

plt.show()
```
### Scatter plot size
```python
# Import numpy as np
import numpy as np

# Store pop as a numpy array: np_pop
np_pop = np.array(pop)

# Double np_pop
np_pop = np_pop * 2

# Update: set s argument to np_pop
plt.scatter(gdp_cap, life_exp, s = np_pop)

# Previous customizations
plt.xscale('log') 
plt.xlabel('GDP per Capita [in USD]')
plt.ylabel('Life Expectancy [in years]')
plt.title('World Development in 2007')
plt.xticks([1000, 10000, 100000],['1k', '10k', '100k'])

# Display the plot
plt.show()
```
### Scatter plot colors
variable 'col' has been created for argument c (colours) as follows:
`dict = {
    'Asia':'red',
    'Europe':'green',
    'Africa':'blue',
    'Americas':'yellow',
    'Oceania':'black'
}`

```python
# Specify c and alpha inside plt.scatter()
plt.scatter(x = gdp_cap, y = life_exp, 
            s = np.array(pop) * 2,
            c = col,
            alpha = 0.8)

# Previous customizations
plt.xscale('log') 
plt.xlabel('GDP per Capita [in USD]')
plt.ylabel('Life Expectancy [in years]')
plt.title('World Development in 2007')
plt.xticks([1000,10000,100000], ['1k','10k','100k'])

plt.grid(True)      #add grid

# Show the plot
plt.show()
```
