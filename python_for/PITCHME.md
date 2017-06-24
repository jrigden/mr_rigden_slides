# A Guide To Python For Loops
---

```
for <variable> in <sequence>:
	<statements>
```

---
## Example

```
data = [1, 2, 3, 4, 5]
for number in data:
    print(number)
```

```
1
2
3
4
5
```
---

## Iterables

Data that can be looped over. A sequence of data.

Common examples: `lists`, `str`, `tuples`


---
## break

`break` stop the loop.

```
data = [1, 2, 3, 4, 5]
for number in data:
    if number == 3:
        break
    print(number)
```

```
1
2
```
---
## continue

`continues` stops the current iteration on the loop and moves on to the next.

```
data = [1, 2, 3, 4, 5]
for number in data:
    if number == 3:
        continue
    print(number)
```

```
1
2
4
5
```
---
## else

`else` executes when the expression is false, but not when the loop is terminated by a `break`

```
data = [1, 2, 3, 4, 5]
for number in data:
    print(number)
else:
    print('Out of numbers')
```

```
1
2
3
4
5
```

---
## else

```
data = [1, 2, 3, 4, 5]
for number in data:
    if number == 3:
        break
    print(number)
else:
    print('Out of numbers')
```

```
1
2
```

---
## pass

`pass` statement does nothing. Used when the program requires no action.


```
data = [1, 2, 3, 4, 5]
for number in data:
    pass
```
