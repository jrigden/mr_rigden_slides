# A Guide To Python Lists
---

## What are lists?

A Python data type that holds a collection of other Python objects


---

## Examples

```
counts = [5, 125, 1, -1]
```

A list of numbers

---

## Examples

```
shapes = ['circle', 'triangle', 'square']
```

A list of `str`

---

## Examples

```
x = 8
mixed = ["apple", 5, x]
```

A list of mixed objects

---

## For Loops

`list` objects are iterables. They can be used in for loops.

```
shapes = ['circle', 'triangle', 'square']
for shape in shapes:
    print(shape)
```

```
circle
triangle
square
```

---

## Create an empty list

```
shapes = []
print(shapes)
```

```
[]
```
---

## Count List Items

```
shapes = ['circle', 'triangle', 'square']
count = len(shapes)
print(count)
```

```
3
```

---

## Add an Item to the List

```
shapes = ['circle', 'triangle', 'square']
shapes.append('pentagram')
for shape in shapes:
    print(shape)
```

```
circle
triangle
square
pentagram
```

---

## Accessing an Item in List

```
shapes = ['circle', 'triangle', 'square']
print(shapes[0])
```

```
circle
```

Counting starts at 0


---

## Accessing an Item in List

```
shapes = ['circle', 'triangle', 'square']
print(shapes[2])
```

```
square
```

---

## Pop last item from list

```
data = [1, 2, 3, 4, 5]
x = data.pop()
print(x)
print(data)
```

```
5
[1, 2, 3, 4]
```
---

## Insert an Item in List

```
shapes = ['circle', 'triangle', 'square']
shapes.insert(1,'digon')
print(shapes)
```

```
['circle', 'digon', 'triangle', 'square']
```

---

## Update Items in List

```
shapes = ['circle', 'triangle', 'square']
shapes[1] = 'purple'
print(shapes)
```

```
['circle', 'purple', 'square']
```

---

## Find If Item Is in List

```
shapes = ['circle', 'triangle', 'square']
if 'circle' in shapes:
    print('yes')
else:
    print('no')
```

```
yes
```

---

## Find If Item Is in List

```
shapes = ['circle', 'triangle', 'square']
if 'doggy' in shapes:
    print('yes')
else:
    print('no')
```

```
no
```

---

## Find Of Index Item in List

```
shapes = ['circle', 'triangle', 'square']
location = shapes.index('triangle')
print(location)
```

```
1
```

---

## Count Instance of in List

```
data = [1, 2, 1, 5, 1]
count = data.count(1)
print(count)
```

```
3
```

---

## Delete specific item from list

By index

```
shapes = ['circle', 'triangle', 'square']
del shapes[1]
print(shapes)
```

```
['circle', 'square']
```

---

## Delete specific item from list

By Value

```
shapes = ['circle', 'triangle', 'square']
shapes.remove('circle')
print(shapes)
```

```
['triangle', 'square']
```

---

## Delete specific item from list

```
data = [1, 2, 3, 4, 5]
x = data.pop(2)
print(x)
print(data)
```

```
3
[1, 2, 4, 5]
```

Remember we start at 0


---

## Sorting Lists


```
data = [22, 3, 88, 10, 3.1]
data.sort()
print(data)
```

```
[3, 3.1, 10, 22, 88]
```

---

## Reverse Lists


```
data = [1, 2, 100, 231, 2000]
data.reverse()
print(data)
```

```
[2000, 231, 100, 2, 1]
```

---

## Combining lists

Concatenate

```
less_than_five = [1, 2, 3, 4]
more_than_five = [6, 7, 8, 9]
less_than_ten = [1, 2, 3, 4] + [6, 7, 8, 9]
print(less_than_ten)
```

```
[1, 2, 3, 4, 6, 7, 8, 9]
```

---

## Copying Lists

Warning

```
shapes = ['circle', 'triangle', 'square']
more_shapes = shapes
del more_shapes[1]
print(shapes)
```

```
['circle', 'square']
```

---

## Copying Lists

Python 3.3+ Only

```
shapes = ['circle', 'triangle', 'square']
more_shapes = shapes.copy()
del more_shapes[1]
print(shapes)
print(more_shapes)

```

```
['circle', 'triangle', 'square']
['circle', 'square']
```

What about Python 2?
Don't Use Python 2.

---

## Sorting Lists


```
data = [22, 3, 88, 10, 3.1]
data.sort()
print(data)
```

```
[3, 3.1, 10, 22, 88]
```

---

## Slicing Lists

Slice takes a start and end index value

```
data = [1, 2, 3, 4, 5, 6, 7, 8, 9]
cut_data = data[2:4]
print(cut_data)
print(data)
```

```
[3, 4]
```
