# Case Study: Hacker Statistics
## Random numbers
```python
# Random generators
import numpy as np
np.random.rand()      #pseudo-random numbers

np.random.seed(123)   #by setting the same seed, you get the same random numbers everytime
np.random.rand()

# Coin toss
import numpy as np
np.random.seed(123)
coin = np.random.randint(0,2)  #randomly generate 0 or 1
print(coin)
if coin == 0:
    print('heads')
else:
    print('tails')
```
```python
# Numpy is imported, seed is set
import numpy as np
np.random.seed(123)

# Starting step
step = 50

# Roll the dice
dice = np.random.randint(1,7)

# Finish the control construct
if dice <= 2 :
    step = step - 1
elif dice >= 3 and dice <=5 :
    step = step + 1
else :
    step = step + np.random.randint(1,7)

# Print out dice and step
print(dice, step)
```

## Random walk
random walk = succession of n random steps
```python
# Head or tails (not random walk, just independent steps)
import numpy as np
np.random.seed(123)
outcomes = []
for x in range(10) :
    coin = np.random.randint(0, 2)
    if coin == 0 :
        outcomes.append('heads')
    else:
        outcomes.append('tails')
print(outcomes)                   #outcomes: ['heads', 'tails', 'heads', etc...]

# Hear or tails: Random walk
import numpy as np
np.random.seed(123)
tails = [0]
for x in range(10):
    coin = np.random.randint(0,2)
    tails.append(tails[x] + coin)
print(tails)                      #tails: [0, 0, 1, 1, 1, 2, 2, 3, etc...] (increasing 1 each time tails)
```



