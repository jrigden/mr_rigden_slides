
# A Guide To Python Generators and Yield Statements

---

Quick review of iterables and list comprehesions

---

# Iterables

An iterable is an object that can be iterated over

In other words, an object that can be used in a `for` loop.

Exampes: `lists`,`str`, `tuple`

---

# Iterables

## For Loops

```
data = [0, 1, 2, 3, 4]
for each in data:
    print(each)
```

```
0
1
2
3
4
```
---

# Iterables

## List Comprehension

```
data = [0, 1, 2, 3, 4]
result = [x*x for x in data]
for each in result:
    print(each)
```

```
0
1
4
9
16
```

---

# Iterables

## Range()

```
for each in range(5):
    print(each)
```

```
0
1
2
3
4
```

---

# Iterables

## List Comprehension with Range()

```
result = [x*x for x in range(5)]
for each in result:
    print(each)
```

```
0
1
4
9
16
```

---

## Generators

Generators are functions that allow you to declare a function and have it behave like an iterator.

```
new_generator = (x*x for x in range(5))
for each in new_generator:
    print(each)
```

```
0
1
4
9
16

```

---

## Generators

Unlike a list, a generator only can be used once. 

Once it is empy. It is empty.


```
for each in new_generator:
    print(each)
```

Will not output anything



---

## Yield

`yield` is a keyword like `return`.


```
def generatorGenerator():
    for x in range(5):
        yield x*x


new_generator = generatorGenerator()

for each in new_generator:
    print(each)

```

```
0
1
4
9
16

```

---

## Yield

Each time we iterate over `new_generator`, we step through the function. 

```
def multiYield():
    yield "Hello"
    yield "World"
    yield "!"


for each in multiYield():
    print(each)
```

```
Hello
World
!
```


---

## Yield

```
def multiYield():
    x = 5
    yield x
    x = x + 5
    yield x
    x = x * x
    yield x


for each in multiYield():
    print(each)

```
```
5
10
100
```
---


## Why?

These generators are lazy. They only work on demand. Save cpu and memory.


```
import sys
result = [x*x for x in range(1000000)]
memory_size = sys.getsizeof(result)
print(memory_size)
```

```
8697464
```

We have to calulate the square of 1,000,000 numbers and store them in memory. What happend when it is 1,000,000^n numbers?

Or we can use generators that will do it one at a time.

---

## Fibonacci

Every Python tutorial about `yield` and generators must include a Fibonacci sequence.

---

## Fibonacci

```
def fibonacci():
    a = 0
    b = 1
    while True:
        yield a
        old_a = a
        a = b
        b = old_a + b

for each in fibonacci():
    print(each)
    if each > 20:
        break

```
Without `break` loop would be endless.





