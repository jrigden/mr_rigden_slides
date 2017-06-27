# A Guide To Python While Loops
---

```
while <expression>:
    <statements>
```

---


## Example
```
counter = 0
while counter < 5:
    counter += 1
    print(counter)
```

```
1
2
3
4
5
```
---

## break

`break` stop the loop.

```
counter = 0
while counter < 5:
    counter += 1
    if counter == 3:
        break
    print(counter)
```

```
1
2
```
---
## continue

`continues` stops the current iteration on the loop and moves on to the next.

```
counter = 0
while counter < 5:
    counter += 1
    if counter == 3:
        continue
    print(counter)
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
counter = 0
while counter < 5:
    counter += 1
    print(counter)
else:
    print('Out of numbers')
```

```
1
2
3
4
5
Out of numbers---

```

---
## else

```
counter = 0
while counter < 5:
    counter += 1
    if counter == 3:
        break
    print(counter)
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
while True:
    pass
```
