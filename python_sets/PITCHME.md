# A Guide To Python Sets

---

## What are sets?

A Python data type that holds an unordered collection of unique objects.

Very similar to lists.

---

## Membership Requirements

Objects must be hashable.

Dictionaries, lists, and other sets are not hashable.

Numbers, strings, and tuples are hashable.

---

## Create and empty sets

```
shapes = set()
```

---

## Create a set with members
```
shapes = {'circle', 'triangle', 'square'}
print(shapes)
```

```
{'square', 'circle', 'triangle'}
```

---

## Create a set with duplicate members
```
shapes = {'circle', 'circle', 'triangle', 'square'}
print(shapes)
```

```
{'square', 'circle', 'triangle'}
```

We still end up with just one 'circle'

---

## Sets are iterables

```
shapes = {'circle', 'circle', 'triangle', 'square'}
for shape in shapes:
    print(shape)
```

```
square
circle
triangle
```

---

## Add item to set

```
shapes = set()
shapes.add('circle')
print(shapes)
```

```
{'circle'}
```

---

## Add duplicate items to set

```
shapes = set()
shapes.add('circle')
shapes.add('circle')
print(shapes)
```

```
{'circle'}
```

Still just one circle

---

## Add multiple items to set

```
shapes = set()
shapes.update(['circle', 'triangle', 'square'])
print(shapes)
```

```
{'square', 'circle', 'triangle'}
```

---

## Count members of a set

```
shapes = set()
shapes.update(['circle', 'triangle', 'square'])
count = len(shapes)
print(count)
```

```
3
```

---

## Count members of a set

```
shapes = set()
shapes.update(['circle', 'triangle', 'square'])
count = len(shapes)
print(count)
```

```
3
```

---


## Membership test

```
shapes= {'circle', 'triangle', 'square']}
if 'circle' in shapes:
    print("There is a circle")
```

```
There is a circle
```

---

## Accessing a member of a set

```
shapes = set()
shapes.update(['circle', 'triangle', 'square'])
print(shapes[1])
```

```
TypeError: 'set' object does not support indexing
```

---

## Remove a member from a set

`discard` removes a member if present.

```
shapes = {'circle', 'triangle', 'square'}
shapes.discard('circle')
print(shapes)
```

```
{'square', 'triangle'}
```

---

## Remove a member from a set

Even if it does not exist

```
shapes = {'circle', 'triangle', 'square'}
shapes.discard('doggy')
print(shapes)
```

```
{'square', 'circle', 'triangle'}
```

---

## Remove a member from a set

`remove` removes member but throws error if it does not exist.

```
shapes = {'circle', 'triangle', 'square'}
shapes.remove('doggy')
print(shapes)
```

```
KeyError: 'doggy'
```

---

## Remove an arbitrary member of the set

```
shapes = {'circle', 'triangle', 'square'}
shape = shapes.pop()
print(shape)
```

```
square
```

Your mileage may very

---

## Remove all members from a set

`clear` remove all members from the set.
```
shapes = {'circle', 'triangle', 'square'}
shapes.clear()
print(shapes)
```

```
set()
```

---

## Set Equality

```
shapes = {'circle', 'triangle', 'square'}
more_shapes = {'circle', 'triangle', 'square'}
if shapes == more_shapes:
    print('Sets are equal')
else:
    print('Sets are not equal')
```

```
Sets are equal
```

---


## Set Equality

```
shapes = {'circle', 'triangle', 'square'}
more_shapes = {'circle', 'triangle', 'square', 'pentagon'}
if shapes == more_shapes:
    print('Sets are equal')
else:
    print('Sets are not equal')
```

```
Sets are equal
```
Set are only equal if each and every member of the set is contained in the other. Subset and superset are not equal.

---

## Copy a set

Warning

```
shapes = {'circle', 'triangle', 'square'}
more_shapes = shapes
more_shapes.discard('circle')
print(shapes)
```

```
{'square', 'triangle'}
```

---

## Copy a set


```
shapes = {'circle', 'triangle', 'square'}
more_shapes = shapes.copy()
more_shapes.discard('circle')
print(shapes)
```

```
{'square', 'circle', 'triangle'}
```

---


## Frozen Sets

Immutable Sets. They can not be changed. Frozen Sets are hashable.

```
shapes = frozenset(['circle', 'triangle', 'square'])
shapes.add('pentagon')
```

```
AttributeError: 'frozenset' object has no attribute 'add'
```

---


# Taking it to the next level

---

## Difference


```
doctors = {'Bob', 'Dave', 'Mary'}
parents = {'Bob', 'Katie', 'Susie'}
difference = doctors.difference(parents)
print(difference)
```

```
{'Mary', 'Dave'}
```

Mary and Dave are in doctors but not parents. Bob in in both.

---

## Difference

doctors = {'Bob', 'Dave', 'Mary'}
parents = {'Bob', 'Katie', 'Susie'}
difference = doctors - parents
print(difference)
```
doctors = {'Bob', 'Dave', 'Mary'}
parents = {'Bob', 'Katie', 'Susie'}
difference = parents.difference(doctors)
print(difference)
```

```
{'Susie', 'Katie'}
```

Susie and Katie are in doctors but not parents. Bob in in both.

---

## intersection

```
doctors = {'Bob', 'Dave', 'Mary'}
parents = {'Bob', 'Katie', 'Susie'}
result = doctors.intersection(parents)
print(result)
```

```
{'Bob'}
```

Bob is the only on in both sets.

---

## issubset

```
data = {1, 2, 3, 4, 5, 6}
subdata = {4, 5, 6}
result = subdata.issubset(data)
print(result)
```

```
True
```

---

## issuperset

```
data = {1, 2, 3, 4, 5, 6}
subdata = {4, 5, 6}
result = data.issuperset(subdata)
print(result)
```

```
True
```

---
