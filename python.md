# Python - LeetCode Cheatsheet

> Work In Progress

Just enough Python cheatsheet for LeetCode

[Go back to full list](./README.md)

Written in Python 3

---

# Basic

## Primitive Types

### Casting

### Base Conversion

### String Manipulation

## Function

## Arithmetic

## Control Flow

---

# Data Structure

## Array

Array in Python is called `List`.

### Init

```python
arr             = [1, 2, 3]
arr_empty       = []
arr_from_range  = list(range(5))        # [0, 1, 2, 3, 4]
specify_size    = [0 for _ in range(5)] # [0, 0, 0, 0, 0]
specify_size_2d = [                     # [[0, 0, 0], [0, 0, 0]]
  [ 0 for _col in range( 3 ) ]
      for _row in range( 2 )
]
```

### Length

```python
arr = [0, 1, 2, 3, 4]
len(arr)        # 5
```

### Access

```python
arr = [0, 1, 2, 3, 4]
arr[0]          # 0
arr[1]          # 1
arr[-1]         # 4
```

### Modify

```python
arr      = [0, 1, 2, 3, 4]
arr[0]   = 10         # [10, 1, 2, 3, 4]
arr[1:3] = [20, 21]   # [10, 20, 21, 3, 4]
arr.append(30)        # [10, 20, 21, 3, 4, 30]
arr.pop(0)            # [20, 21, 3, 4, 30], Remove by index (start from 0)
arr.remove(21)        # [20, 3, 4, 30], Remove by value


```

### Slice

```python
'''
[start:end:step]
start : default 0,        inclusive
end   : default len(arr), exclusive
step  : default 1,
'''
arr[0:2]        # [0, 1]
arr[1:4]        # [1, 2, 3]
arr[1:]         # [1, 2, 3, 4]
arr[:3]         # [0, 1, 2]
arr[:]          # [0, 1, 2, 3, 4]
arr[-2:]        # [3, 4]
arr[-3:-1]      # [2, 3]
arr[::2]        # [0, 2, 4]
arr[::-1]       # [4, 3, 2, 1, 0]
```

### Sort

```python
# Ascending order, in place
arr.sort() # [2, 3, 1] => [1, 2, 3]

# Descending order, in place
arr.sort(reverse=True) # [2, 3, 1] => [3, 2, 1]

# By custom function, in place
students = [
  {'name': 'Alan', 'age': 24},
  {'name': 'Mike', 'age': 36},
  {'name': 'Jack', 'age': 12}
]
students.sort(key = lambda student: student.age)
# students == [
#   {'name': 'Jack', 'age': 12},
#   {'name': 'Alan', 'age': 24},
#   {'name': 'Mike', 'age': 36}
# ]
```

### Reverse

```python
# In place
arr.reverse() # [2, 3, 1] => [1, 3, 2]

arr2 = arr[::-1] # [2, 3, 1] => [1, 3, 2]
```

### Traverse

```python
arr = [0, 1, 2, 3, 4]
for val in arr:
for i, val in enumerate(arr):
```

---

## Tuple

## String

## Hash Table

Use Python's `Dict`

```python
ht =      {}
ht =      {'a': 1, 'b': 2}
ht['a']                 # Get
ht['c'] = 3             # Add, Set
del ht['a']             # Delete
if 'c' in ht:           # Check exist
len(ht)                 # Length
for k, v in ht.items(): # Iterate
  # ...
```

## Heap

## Set

```python
s = set()
s.add(1)
if 1 in s: #true
```

## Matrix

## Linked List

## Pointer

## Queue

```python
# collections auto imported in LeetCode environment
# to import manually, write this:
# `from collections import deque`
q = collections.deque()
q.appendleft(1)
q.appendleft(2)
q.appendleft(3)

q.pop()  # 1
q.pop()  # 2
q.pop()  # 3
if q: # false, check empty
```

## Stack

```python
st = []
st.append(1)
item = st.pop() # 1
len(st)
```

## Tree

## Graph
