List | Tuple | Set | List
===================
---------
    Data structures
	
List
------------------
> - General purpose
> - Most widely used data structure
> - Grow and shrink size as needed
> - Sequence type
> - Sortable

Tuple
------------------
> - Immutable (cant't add/change)
> - Useful for fixed data
> -  Faster than Lists
> -  Sequence type

Set
------------------
> - Store non-duplicate items
> - Very fast access vs Lists
> - Mat Set ops (union, intersect)
> - Unordered

Dict
------------------
> - Key/Value pairs
> - Associative array, like java HashMap
> - Unordered


> **Note:**
Data Structures in python can hold any data type
eg. integers, strings, objects, floating point even lists.
The data does not need to be homogeneous you can mix and match data

Sequences (String, List, Tuple )
------------------

#### indexing
> - Access any item in the sequence using its index

#### String
```python
x = 'frog'
print (x[3])    # prints 'g'
```

#### List
```python
x = ['pig', 'cow', 'horse']
print (x[1])    # prints 'cow'
```

#### slicing

> - Slice out substrings, sublists, subtuples using indexes [start:end+1:step]
```python
x = 'computer'
x[1:4]      # Result's 'omp'    # Explanation: selects 1 to 3

#similarly
x[1:6:2]    # Result's 'opt'    # Explanation: selects 1, 3, 5

x[-1]   # -1 is last item in sequence
x[3]
x[-3:]
x[2]
x[:2]
```

#### adding/concatenating

> - Combine 2 sequences of the same type using +

#### String
```python
x = 'horse' + 'shoe'
print (x)       # prints 'horseshoe'
```

#### List
```python
x = ['pig', 'cow'] + ['horse']
print (x)       # prints ['pig', 'cow', 'horse']
```

#### multiplying
> - Multiply a sequence using *

#### String
```python
x = 'bug' * 3
print (x)       # prints 'bugbugbug'
```

#### List
```python
x = [8, 5] * 3
print (x)       # prints [8, 5, 8, 5, 8, 5]
```


#### checking membership
> - Test wheather an item is **in** or **not in** a sequence

#### String
```python
x = 'bug'
print (u in x)       # prints True
```

#### List
```python
x = ['pig', 'cow', 'horse']
print ('cow' not in x)       # prints False
```


#### iterating
> - Iterate through the items in a sequence

#### Item
```python
x = [7, 8, 3]
for item in x:
    print (item * 2)        # prints 14, 16, 6
```

#### Index & Item
```python
x = [7, 8, 3]
for index, item in enumerate(x):
    print (index, item)         # prints 0 7 1 8 2 3
```

#### number of items
> - Count the number of items in a sequence

#### String
```python
x = 'bug'
print (len(x))      # prints 3
```

#### List
```python
x = ['pig', 'cow', 'horse']
print (len(x))      # prints 3
```

#### minimum
> - Find the minimum item in a sequence lexicographically
> - alpha or numeric types, but cannot mix types

#### String
```python
x = 'bug'
print (min(x))       # prints 'b'
```

#### List
```python
x = ['pig', 'cow', 'horse']
print (min(x))       # prints 'cow' #how and why cow???
```

#### maximum
> - Find the maximum item in a sequence lexicographically
> - alpha or numeric types, but cannot mix types

#### String
```python
x = 'bug'
print (max(x))       # prints 'u'
```

#### List
```python
x = ['pig', 'cow', 'horse']
print (max(x))       # prints 'pig' #how and why cow???
```

#### sum
> - Find the sum of item in a sequence
> - entire sequence must be numeric type

#### String -> Error
```python
x = [5 , 7, 'bug']
print (sum(x))       # error!
```

#### List
```python
x = [2, 5, 8, 12]
print (sum(x))       # prints 27
print (sum(x[-2:]))  # prints 20
```

## 6:48
https://www.youtube.com/watch?v=R-HLU9Fl5ug