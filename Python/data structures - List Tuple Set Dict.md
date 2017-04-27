List | Tuple | Set | Dict
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
#### sorting
> - Returns a new list of items in sorted order
> - Does not change the original list

#### String 
```python
x = 'bug'
print (sorted(x))       # prints ['b', 'g', 'u']
```

#### List
```python
x = ['pig', 'cow', 'horse']
print (sorted(x))       # prints ['cow', 'horse', 'pig']
```
#### count (item)
> - Returns count of an item

####  String
```python
x = 'hippo'
print (x.count('p'))       # prints 2
```

#### List
```python
x = ['pig', 'cow', 'cow', 'horse']
print (x.count('cow'))       # prints 2
```

#### index (item)
> - Returns the index of the first occurrence of an item

####  String
```python
x = 'hippo'
print (x.index('p'))       # prints 2
```

#### List
```python
x = ['pig', 'cow', 'cow', 'horse']
print (x.index('cow'))       # prints 1
```
#### unpacking
> - Unpack the n items of a sequence into n variables

#### List
```python
x = ['pig', 'cow', 'cow', 'horse']
a, b, c = x         # a is 'pig'
                    # b is 'cow'
                    # c is 'horse'
```
> **Note:**
The number of cariables must exactly match the length of the list

Lists functions
====================
#### constructors - creating a new list

```python
x = list()
x = ['a', 25, 'dog', 8.43]
x = list(tuple1)        # will give list from a tuple
```

##### List Comprehension:
```python
x = [m for m in range(8)]       # results [0, 1, 2, 3, 4, 5, 6, 7]

```

#### delete
> - Delete a list or an item from a list

```python
x = [5, 3, 8, 6]
del(x[1])       # results [5, 8, 6]

del(x)          # deletes list x
```

#### append
> - Append an item to a list
```python
x = [5, 3, 8, 6]
x.append(7)     # results [5, 3, 8, 6, 7]
```

#### extend
> - Append an sequence to a list
```python
x = [5, 3, 8, 6]
y = [12, 13]
x.extend(y)     # results [5, 3, 8, 6, 7, 12, 13]
```
#### insert
> - Insert an item at given index       x.insert(index, item)

```python
x = [5, 3, 8, 6]
x.insert(1, 7)     # results [5, 7, 3, 8, 6]
x.insert(1, ['a', 'm'])     # results [5, ['a', 'm'], 3, 8, 6]
```

#### pop
> - Pops last item off the list, and returns item
```python
x = [5, 3, 8, 6]
x.pop()     # results [5, 7, 3, 8, 6]
            # and returns 6
            
print(x.pop())  # prints 8
                # x is now [5, 3]
```

#### remove
> - Remove first instance of an item
```python
x = [5, 3, 8, 6, 3]
x.remove(3)     # results [5, 8, 6, 3]
 ```
#### reverse
> - Remove the order of the list
```python
x = [5, 3, 8, 6]
x.reverse()     # results [6, 8, 3, 5]
```
#### sort
> - Sort the list in place
```python
x = [5, 3, 8, 6]
x.sort()     # results [3, 5, 6, 8]
```
> **Note:**
sorted(x) returns a new sorted list without changing the original list x.
x.sort() puts the items of x in sorted order (sorts in place)

Tuples
====================
> - Support all operations for Sequences
> - Immutable, but member objects may be mutable
> - If the contents of a list shouldn't change, use a tuple to prevent items from accidently being added, changed or deleted
> - Tuples are more efficient than lists due to Python's implementation

#### constructors - creating a new tuple
```python
x = ()              # no-item tuple
x = (1, 2, 3)       
x = 1, 2, 3         # parenthesis are optional
x = 2,              # single-item tuple
x = tuple(list1)    # tuple from list
```

#### immutable
> - But member objects may be mutable

```python
x = (1, 2, 3)
del(x[1])           # error!
x[1] = 8            # error!

x = ([1,2], 3)      # 2-item tuple: list and int
del(x[0][1])        # ([1], 3)
```
Sets
====================
#### constructors - creating a new set
```python
x = {3, 5, 3, 5}        # {3,5}
x = set()               # empty set
x = set(list1)          #strips duplicates
```

##### List Comprehension:
```python
x = {3*y for y in range(10) if y>5}
                        # resulting set: {18, 21, 24, 27} in random order
```

#### basic set operations
```python
x.add(item)         #Add item to set x
x.remove(item)      # Remove item from set x
len(x)              # Get length of set x
item in x           # checking membership in x
item not in x
x.pop()             # pop random item from set x
x.clear()           # Delete all items from set x
```
#### standard mathematical set operations
```python
# code                  # Description           # Set Funtion
set1 & set2             # AND                   # Intersection
set1 | set2             # OR                    # Union
set1 ^ set2             # XOR                   # Symmetric Difference
set1 - set2             # in s1 but not in s2   # Difference
set1 <= set2            # set2 contains set1    # Subset
set1 >= set2            # set1 contains set2    # Superset
```

Dictionaries
====================
#### constructors - creating a new dict

```python
x = {'pork':25.3, 'beef':33.8, 'chicken':22.7}
x = dict([('pork',25.3), ('beef',34.4) ,('chicken',22.7)])
x = dict(pork=24.5, beef=33.4)
```

#### basic dict operations
```python
x['beef'] = 25.2            # Add or change item in dict x
del x['beef']               # Remove item from dict x
len(x)                      # Get length of dict x
item in x                   # Check membership in x (only looks
item not in x               # in keys, not in values)
x.clear                     # Delete all items from dict x
del x                       # Delete dict x
```

#### accessing keys and values in a dict

```python 
x.keys()            # returns list of keys in x
x.values()          # returns list of values in x
x.items()           # returns list of key-value tuple pairs in x
item in x.values()  # tests membership in x: returns boolean

# iterating a dict
for key in x:               # iterate keys
    print(key, x[key])      # print key value pair
    
for k, v in x.items():      # iterate key/value pairs
    print(k, v)             # print all key/value pairs

# Note: Entries in a dict are in random order.
```

[video](https://www.youtube.com/watch?v=R-HLU9Fl5ug)