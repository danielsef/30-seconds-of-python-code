### deep_flatten

Deep flattens a list.

Use recursion. Use `list.extend()` with an empty array (`result`) and the spread function to flatten a list. Recursively flatten each element that is a list.

```python
def spread(arg):
    ret = []
    for i in arg:
        if isinstance(i, list):
            ret.extend(i)
        else:
            ret.append(i)
    return ret


def deep_flatten(arr):
    result = []
    result.extend(
        spread(list(map(lambda x: deep(x) if type(x) == list else x, arr))))
    return result
```

```python
deep_flatten([1, [2], [[3], 4], 5]) # [1,2,3,4,5]
```
