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

