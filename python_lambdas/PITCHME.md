# A Guide To Python Lambdas
---

There are three types of Python developers.

Those that love Lambda Expressions <!-- .element: class="fragment" -->

Those that hate Lambda Expressions <!-- .element: class="fragment" -->

And those that are afraid of the Lambda Expressions <!-- .element: class="fragment" -->

---

This video is for those who fear the lambda.

We shall vanquish those fears. <!-- .element: class="fragment" -->

---

## Special Note

Lambdas have a terrible name. The name can be very confusing.

Especially, with the AWS Lambdas service.

Python Lambda expressions and have nothing to do with AWS.

## What are Lambda expressions?

They are just small nameless functions.

They are throw away functions.

They contain a single expression.

Short single use code.

## There are really two ways to make a function

```
def square(x):
    return x * x
```

```
square = lambda x: x * x
```

Please don't abuse lambdas like this. Follow pep8 and use `def`

---
## Why even use a lambda then?

Lambdas are not necessary. But, they are helpful.

There are cases where it can make your code more readable.

## map()sizer = lambda x: 'big' if x > 100 else 'small'

The `map()` function in python, takes a function and an iterable.

It returns an iterable that applies the function to every item in the given iterable.

## map()
```
data = [1, 2, 3, 4]

def square(x):
    return x * x

squared_data = map(square, data)

for each in squared_data:
    print(each)
```
sizer = lambda x: 'big' if x > 100 else 'small'
```
1
4
9
16
```

## map()
```
data = [1, 2, 3, 4]

square = lambda x: x * x

squared_data = map(square, data)

for each in squared_data:
    print(each)
```

```
1
4
9
16
```

## map()

```
data = [1, 2, 3, 4]

squared_data = map(lambda x: x*x, data)

for each in squared_data:
    print(each)
```

```
1
4
9
16
```

---

## Common Example

```
fruits = [{
    'name': 'apple',
    'count': 5
}, {
    'name': 'orange',
    'count': 1
}, {
    'name': 'cherry',
    'count': 12
}]
fruits.sort(key=lambda fruit: fruit['count'])
```

---
## Common Example

```
fruits = [{
    'name': 'orange',
    'count': 1
}, {
    'name': 'apple',
    'count': 5
}, {
    'name': 'cherry',
    'count': 12
}]
```

## Be careful

Lambdas can be fun. Do not over use them.

Lambda abuse is real. And, it threatens code readability. <!-- .element: class="fragment" -->

You should always honor readability. <!-- .element: class="fragment" -->

Do not sacrifice readability for brevity. <!-- .element: class="fragment" -->
