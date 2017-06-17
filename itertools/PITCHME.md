# A Guide To Python’s itertools

---

## Setup

import itertools

import operator

---

## count()

```
itertools.count(start=0, step=1)
```
Make an iterator that returns evenly spaced values starting with number start.

---

## count()

```
for i in itertools.count(10,3):
	print(i)
	if i > 20:
		break

```

```
10
13
16
19
22
```

---

## cycle()

```
itertools.cycle(iterable)
```

Make an iterator that cycles through an iterator endlessly.

---

## cycle()

```
count = 0
colors = ['red', 'orange', 'yellow', 'green',
          'blue', 'violet']
for color in itertools.cycle(colors):
    print(color)
    count += 1
    if count > 10:
        break
```

```
red
orange
yellow
green
blue
indigo
violet
red
orange
yellow
green

```

---

## repeat()

```
itertools.repeat(object[, times])
```
Repeat object over and over again. Unless, there is a <code>times</code> arguement.

---

## repeat()

```
food = "spam"
for i in itertools.repeat(food, 5):
	print(i)
```

```
spam
spam
spam
spam
spam

```

---

## repeat()

```
food = "spam"
for i in itertools.repeat(food):
	print(i)
```

Infinite Spam

---

## accumulate()
```
itertools.accumulate(iterable[, func])
```

Make an iterator that returns results of functions.

---

## accumulate()

```
data = [1, 2, 3, 4, 5]
result = itertools.accumulate(data, operator.mul)
for each in result:
    print(each)


```

```
1
2
6
24
120

```

```
operator.mul(1, 2)
2
operator.mul(2, 3)
6
operator.mul(6, 4)
24
operator.mul(24, 5)
120
```

---

## accumulate()

```
data = [5, 2, 6, 4, 5, 9, 1]
result = itertools.accumulate(data, max)
for each in result:
    print(each)
```

```
5
5
6
6
6
9
9

```

```
5
max(5, 2)
5
max(5, 6)
6
max(6, 4)
6
max(6, 5)
6
max(6, 9)
9
max(9, 1)
9
```
 ---

## accumulate()
```
data = [5, 2, 6, 4, 5, 9, 1]
result = itertools.accumulate(data)
for each in result:
    print(each)
```

```
5
7
13
17
22
31
32

```
```
5
5 + 2 = 7
7 + 6 = 13
13 + 4 = 17
17 + 5 = 22
22 + 9 = 31
31 + 1 = 32

---

## chain()
Takes a series of iterables and return them as one long iterable.

 ```
colors = ['red', 'orange', 'yellow', 'green', 'blue']
shapes = ['circle', 'triangle', 'square', 'pentagon']

result = itertools.chain(colors, shapes)
for each in result:
    print(each)
```

```
red
orange
yellow
green
blue
circle
triangle
square
pentagon
```

---

##compress()

```
itertools.compress(data, selectors)
```

Filter one iterable with another.

---

##compress()

```
shapes = ['circle', 'triangle', 'square', 'pentagon']
selections = [True, False, True, False]

result = itertools.compress(shapes, selections)
for each in result:
    print(each)
```

```
circle
square
```


---

##dropwhile()

```
itertools.dropwhile(predicate, iterable)
```
Make an iterator that drops elements from the iterable as long as the predicate is true; afterwards, returns every element.

---

##dropwhile()

```
data = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 1]

result = itertools.dropwhile(lambda x: x<5, data)
for each in result:
    print(each)
```

```
5
6
7
8
9
10
1
```

```
 1 < 5:  True,  drop
 2 < 5:  True,  drop
 3 < 5:  True,  drop
 4 < 5:  True,  drop
 5 < 5:  False, return surviving items
```

----


##takewhile()
```
itertools.dropwhile(predicate, iterable)
```
Kind of the opposite of dropwhile()

Make an iterator that returns elements from the iterable as long as the predicate is true.

```
data = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 1]

result = itertools.takewhile(lambda x: x<5, data)
for each in result:
    print(each)
```

```
1
2
3
4

```

```
 1 < 5:  True,  keep going
 2 < 5:  True,   keep going
 3 < 5:  True,   keep going
 4 < 5:  True,   keep going
 5 < 5:  False, stop and drop
```

----


##filterfalse()
```
itertools.filterfalse(predicate, iterable)
```

Make an iterator that filters elements from iterable returning only those for which the predicate is False.


```
data = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
result = itertools.filterfalse(lambda x: x<5, data)
for each in result:
    print(each)

```

```
5
6
7
8
9
10
```

```
 1 < 5:  True,  drop
 2 < 5:  True,  drop
 3 < 5:  True,  drop
 4 < 5:  True,  drop
 5 < 5:  False, keep
 6 < 5:  False, keep
 7 < 5:  False, keep
 8 < 5:  False, keep
 9 < 5:  False, keep
10 < 5:  False, keep
```

---

## groupby()

```
itertools.groupby(iterable, key=None)
```

Simply put, this function groups things together. Ok. This one is complicated.

---

## groupby()
```
robots = [{
    'name': 'blaster',
    'faction': 'autobot'
}, {
    'name': 'galvatron',
    'faction': 'decepticon'
}, {
    'name': 'jazz',
    'faction': 'autobot'
}, {
    'name': 'metroplex',
    'faction': 'autobot'
}, {
    'name': 'megatron',
    'faction': 'decepticon'
}, {
    'name': 'starcream',
    'faction': 'decepticon'
}]
```

---

## groupby()

We need to sort them.

```
bots  = sorted(robots, key=operator.itemgetter('faction'))
```

---

## groupby()

```

[{
    'name': 'blaster',
    'faction': 'autobot'
}, {
    'name': 'jazz',
    'faction': 'autobot'
}, {
    'name': 'metroplex',
    'faction': 'autobot'
}, {
    'name': 'galvatron',
    'faction': 'decepticon'
}, {
    'name': 'megatron',
    'faction': 'decepticon'
}, {
    'name': 'starcream',
    'faction': 'decepticon'
}]
```
---

## groupby()

```
for key, group in itertools.groupby(bots, key=lambda x: x['faction']):
    print(key)
    print(list(group))
```



 ```
autobot
[{'faction': 'autobot', 'name': 'blaster'}, {'faction': 'autobot', 'name': 'jazz'}, {'faction': 'autobot', 'name': 'metroplex'}]
decepticon
[{'faction': 'decepticon', 'name': 'galvatron'}, {'faction': 'decepticon', 'name': 'megatron'}, {'faction': 'decepticon', 'name': 'starcream'}]
```
@[4-5](First Group aka Autobots)
@[6-7](Second Group aka Decepticons)

---

## islice()
```
itertools.islice(iterable, stop)
itertools.islice(iterable, start, stop[, step])
```
Very much like slice. This function allows you to cut out a piece of an iterable.

---

## islice()

```
colors = ['red', 'orange', 'yellow', 'green', 'blue',]
few_colors = itertools.islice(colors, 2)
for each in few_colors:
    print(each)
```

```
red
orange
```

---

## islice()

```
colors = ['red', 'orange', 'yellow', 'green', 'blue',]
few_colors = few_colors = itertools.islice(colors, 2, 5)
for each in few_colors:
    print(each)
```

```
yellow
green
blue
```

Starts at index 2 and ends at index 5

---

## starmap()
```
itertools.starmap(function, iterable)
```


Make an iterator that computes the function using arguments obtained from the iterable.


---

## starmap()

```
data = [(2, 6), (8, 4), (7, 3)]
result = itertools.starmap(operator.mul, data)
for each in result:
    print(each)
```

```
12
32
21
```

---

## tee()

```
itertools.tee(iterable, n=2)
```
Return n independent iterators from a single iterable.


---

## tee()

```
colors = ['red', 'orange', 'yellow', 'green', 'blue']
alpha_colors, beta_colors = itertools.tee(colors)

for each in alpha_colors:
    print(each)

for each in beta_colors:
     print(each)
```

```
red
orange
yellow
green
blue
red
orange
yellow
green
blue
```

---

## zip_longest()

Make an iterator that aggregates elements from each of the iterables. If the iterables are of uneven length, missing values are filled-in with fillvalue. Iteration continues until the longest iterable is exhausted.


---

## zip_longest()

```
colors = ['red', 'orange', 'yellow', 'green', 'blue',]
data = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10,]
for each in itertools.zip_longest(colors, data, fillvalue=None):
    print(each)
```

```
('red', 1)
('orange', 2)
('yellow', 3)
('green', 4)
('blue', 5)
(None, 6)
(None, 7)
(None, 8)
(None, 9)
(None, 10)


```


---

## combinations()

Creates combinations.

---

## combinations()
```
shapes = ['circle', 'triangle', 'square',]
result = itertools.combinations(shapes, 2)
for each in result:
    print(each)
```

```
('circle', 'triangle')
('circle', 'square')
('triangle', 'square')
```


---

## combinations_with_replacement()

Creates combinations with doubles.


---

## combinations_with_replacement()
```
shapes = ['circle', 'triangle', 'square',]
result = itertools.combinations_with_replacement(shapes, 2)
for each in result:
    print(each)
```

```
('circle', 'circle')
('circle', 'triangle')
('circle', 'square')
('triangle', 'triangle')
('triangle', 'square')
('square', 'square')


```

---

## product()
```
itertools.product(*iterables, repeat=1)
```

Cartesian products from a series of  iterables.

---

## product()

```
num_data = [1, 2, 3]
alpha_data = ['a', 'b', 'c']
result = itertools.product(num_data, alpha_data)
for each in result:
    print(each)
```

```
(1, 'a')
(1, 'b')
(1, 'c')
(2, 'a')
(2, 'b')
(2, 'c')
(3, 'a')
(3, 'b')
(3, 'c')
```

---

## product()

```
        a     b      c
1	a1	b1	c1
2	a2	b2	c3
3	a3	b3	b3

```


---
## permutations()
```
itertools.permutations(iterable, r=None)
```
Return successive r length permutations of elements in the iterable.

If r is not specified or is None, then r defaults to the length of the iterable and all possible full-length permutations are generated.


---
## permutations()

```
alpha_data = ['a', 'b', 'c']
result = itertools.permutations(alpha_data)
for each in result:
    print(each)
```

```
('a', 'b', 'c')
('a', 'c', 'b')
('b', 'a', 'c')
('b', 'c', 'a')
('c', 'a', 'b')
('c', 'b', 'a')
```
