---
layout: post
author: lapseudog
---

# From IML to Numpy
While discovering Python I was looking at some comparison between SAS and Python and tumble upon this comparison ([https://blogs.sas.com/content/sgf/2016/10/12/the-monty-hall-paradox-sas-vs-python/](https://blogs.sas.com/content/sgf/2016/10/12/the-monty-hall-paradox-sas-vs-python/)) and noticed that the “the DO loop” had a pretty, concise and quick piece of code in IML ([https://blogs.sas.com/content/iml/2015/04/01/monty-hall.html](https://blogs.sas.com/content/iml/2015/04/01/monty-hall.html)). This code explores how to code in numpy the equivalent of the IML code, and highlights how remarkably similar the two are.

# Comparative Numpy implementation
below is the code using numpy 1.18.1:

```python
nbSims = 100000
rng = np.random.default_rng(seed= 12345)                # set seed and initialise
car = rng.integers(1, 3, endpoint=True, size=nbSims)    # equivalent of the table distribution
guess = np.full((nbSims), 1)                            # fills with ones
show = np.where(car == 2 , 3 , 2)                       # np.where is equivalent of the choose method
switch = np.where(show == 2 , 3 , 2)
winIfStay = np.mean(np.where(guess == car, 1 ,0 ))      # np.mean is equivalent to the IML mean
winIfSwitch = np.mean(np.where(switch == car, 1 ,0 ))
print("frequencies of winning when staying ", winIfStay)
print("frequencies of winning when switching ", winIfSwitch)
```

this output:
```
frequencies of winning when staying  0.33322
frequencies of winning when switching  0.66678
```


To compare with the SAS equivalent (copy pasted from the second sas link):

```sas
proc iml;
call randseed(54321);
NumSim = 1e5;                               /* number of simulated games */
car = randfun(NumSim, "Table", {1 1 1}/3);  /* unknown door hides car */
guess = j(NumSim, 1, 1);                    /* WLOG, guess door=1 */
show = choose(car=2, 3, 2);                 /* host shows a goat */
switch = choose(show=2, 3, 2);              /* the door you could switch to */
winIfStay = mean(guess=car);                /* (P(win | do not switch) */
winIfSwitch = mean(switch=car);             /* (P(win | switch) */
print winIfStay winIfSwitch;
```

Point of interests:

*   The `integers` funtion is similar to the “table” distribution in SAS
*   np.full fill a matrix with a value
*   np.where is equivalent to IML `choose`
