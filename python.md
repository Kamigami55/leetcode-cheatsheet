# Python - LeetCode Cheatsheet

Just enough Python cheatsheet for LeetCode

[Go back to full list](./README.md)

Written in Python 3.10

---

# Basic

## Primitive Types

```python
my_int    = 1
my_float  = 2.3
my_str    = 'hello'
my_list   = [0, 1, 2]
my_tuple  = (0, 1, 2)
my_dict   = {'a': 1, 'b': 2}
my_set    = {0, 1, 2}
my_bool   = True
my_none   = None
```

### Casting

```python
float(1)      # 1.0
int(1.9)      # 1
int("1")      # 1
str(1)        # '1'
float("1.9")  # 1.9
```

### String Operations

```python
hi = "Hello"
len(hi)            # 5
hi[0]              # 'H'
"He" in hi         # True
"world" not in hi  # True
hi[0:2]            # 'He'
"He" + "llo"       # 'Hello'
hi.upper()         # 'HELLO'
hi.lower()         # 'hello'
"a,b,c".split(",") # ['a', 'b', 'c']
for char in "string":                   # iterate over characters
for index, char in enumerate("string"): # iterate over characters and indexes
ord("a")            # 97, ordinal of character
ord('c') - ord('a') # 2
chr(97)             # 'a'
```

## Function

```python
def my_func(param1, param2):
  return param1 + param2

my_func(1, 2) # 3
```

## Arithmetic

```python
3 + 2   # 5
3 - 2   # 1
3 * 2   # 6
3 / 2   # 1.5
3 // 2  # 1
3 % 2   # 1
3 ** 2  # 9
```

## Control Flow

### If Else

```python
if a == b:
  print("a is equal to b")
elif a > b:
  print("a is greater than b")
else:
  print("a is less than b")
```

### While loop

```python
while True:
  break
  continue
```

### For Loop

```python
for val in [1, 2, 3]:
```

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
arr.remove(21)        # [20, 3, 4, 30],     Remove by value


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

## Hash Table

Use Python's `Dict`

```python
ht = {}
ht = {'a': 1, 'b': 2}
ht['a']                 # Get
ht['c'] = 3             # Add, Set
del ht['a']             # Delete
if 'c' in ht:           # Check exist
len(ht)                 # Length
for k, v in ht.items(): # Iterate
  # ...
```

## Heap

Use `heapq` built-in module

```python
import heapq
h = [2,3,4,1,5]
heapq.heapify(h)                    # h is now a min heap
smallest = heapq.heap[0]            # 1
smallest = heapq.heappop(h)         # 1
len(h)                              # 4
heapq.heappush(h, 1)                # put 1 back into the heap, stay on the top of the heap, because it is the smallest
smallest = heapq.heappushpop(h, 0)  # push 0 and pop the smallest
```

## Set

```python
s = set()
s.add(1)
if 1 in s: # True
s.discard(1)
```

## Matrix

```python
matrix = [
  [1, 2, 3],
  [4, 5, 6],
  [7, 8, 9]
]

for r in range(len(matrix)):
  for c in range(len(matrix[0])):
    print(matrix[r][c])
```

## Queue

```python
from collections import deque
q = deque()
q.appendleft(1)
q.appendleft(2)
q.appendleft(3)

q.pop()  # 1
q.pop()  # 2
q.pop()  # 3
if q:    # False, check empty
```

## Stack

```python
st = []
st.append(1)
item = st.pop() # 1
len(st)
```

# Algorithms

## Binary search

### Using `bisect` module

`bisect` stands for bisection ([Doc](https://docs.python.org/3/library/bisect.html))

```python
import bisect
def binary_search(arr, val):
  pos = bisect.bisect_left(arr, val)
  return pos if pos != len(arr) and arr[pos] == val else -1

arr = [0, 2, 4]
binary_search(arr, 2)   # 1
binary_search(arr, 1)   # -1 (not found)
```

### Manual

```python
def binary_search(arr, target):
  left, right = 0, len(arr) - 1
  while left <= right:
    mid = (left + right) // 2
    if arr[mid] == target:
      return mid
    elif arr[mid] < target:
      left = mid + 1
    else:
      right = mid - 1
  return -**1**

arr = [0, 2, 4]
binary_search(arr, 2)   # 1
binary_search(arr, 1)   # -1 (not found)
```

### Find insertion position

Using `bisect` module

```python
import bisect
arr = [0, 2, 4]
index_right_for_insert = bisect.bisect(arr, 2)                           # 2
index_right_for_insert = bisect.bisect(arr, 1)                           # 1
with_lambda            = bisect.bisect(arr, 20, key=lambda val: val*10)  # 2
index_right_for_insert = bisect.bisect_right(arr, 2)                     # 2, `bisect_right` is `bisect`
index_left_for_insert  = bisect.bisect_left(arr, 1)                      # 1
index_left_for_insert  = bisect.bisect_left(arr, 2)                      # 1
```

## Random

```python
import random
random.randint(0, 10) # 0 ~ 10
```
