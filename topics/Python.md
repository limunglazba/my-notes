Python
============

### Installation & Setup
| Command | Description |
| ------- | ----------- |
| `pip freeze > requirements.txt` | Save installed Python packages in a new txt file |
| `pip install -r requirements.txt` | Install these packages in a new environment |
| `sys.path` | The list of directories searched by Python is given by the sys.path variable (import sys first) |

### System
| Command | Description |
| ------- | ----------- |
| `sys.getsizeof(a)` | Returns size of object *a* |

### Lists
#### Slice notation
| Command | Description |
| ------- | ----------- |
| `a[start:stop]` | access items on list *a* from start through stop-1 |
| `a[start:]` | access items on list *a* from start until the end of the list|
| `a[:stop]` | access items on list *a* from the beginning through stop-1 |
| `a[:]` | access every item on list *a*|
| `a[start:stop:step]` | start through not past stop, by step |
| `a[-2:]` | last two items in the list |
| `a[::-1]` | all items in the list, reversed|

#### List comprehensions (listcomps)
- Can be used to create Cartesian product from iterables: e.g. produce a list of T-shirts available in 2 colors and 3 sizes:
```
colors = ['black', 'white']
sizes = ['S', 'M', 'L']
tshirts = [(color, size) for color in colors for size in sizes]
```
#### Generator Expression (genexp) [1](https://www.youtube.com/watch?v=bD05uGo_sVI)
- Generator Expression uses less memory than listcomps because it doesn't return all data at once like a list does. It has the same syntax as listcomps, but uses parentheses () rather than brackets [].
- Best used when list is an intermediary, such as summing the results. Use listcomps when you need the list as the final product.
- In order to make any adjustments to the genexp or fetch data from it, you need to convert it to a list first:
```
a = i for i in range (1000)
list(a)[0]
>>> 0
```

### List vs Generator
- Function that returns square numbers based on a list or a generator:

| List | Generator |
| ------- | ----------- |
| def squares(nums): <br>&nbsp;&nbsp;result = [] <br>&nbsp;&nbsp;for i in nums: <br>&nbsp;&nbsp;&nbsp;&nbsp;result.append(i`*`i) <br>&nbsp;&nbsp;return result<br><br>my_nums = squares(`[1,2,3,4,5]`) <br>print(my_nums)| def squares(nums): <br>&nbsp;&nbsp;for i in nums: <br>&nbsp;&nbsp;&nbsp;&nbsp;yield (i`*`i) <br><br>my_nums = squares(`[1,2,3,4,5]`) <br>for num in my_nums: <br>&nbsp;&nbsp;print(num) |

### Tuples
**Tuple is an immutable and hashable list.**

| Command | Description |
| ----------------- | ----------- |
| `lax_coordinates = (33.9425, -118.408056)` <br> `latitude, longitude = lax_coordinates` | Tuple unpacking |
| `a, b = b, a` | Swapping variables with tuple unpacking without using a temporary variable |
| `print(*t)` | Prefixing an argument with * (asterisk) will also unpack the tuple or list *t* - see also *Grabbing excess items* under *Various* |

### Named Tuples
**Produces subclasses of tuple enhanced with field names and a class name — helps debugging.**

| Command | Description |
| ----------------- | ----------- |
| `from collections import namedtuple` | Importing named tuple from collections package |
| `City = namedtuple('City', 'name country population coordinates')` <br> `tokyo = City('Tokyo', 'JP', 36.933, (35.689722, 139.691667))` | Creating a named tuple class *City* with 4 attributes|

### Code Optimisation
- Apply to a function with @profile
- Profiles the function using cProfile, and prints out a report
- Example below from [S. Mathôt](https://www.youtube.com/watch?v=8qEnExGLZfY&ab_channel=SebastiaanMath%C3%B4t)
```python
import cProfile, pstats, io

def profile(fnc):
    
    """A decorator that uses cProfile to profile a function"""
    
    def inner(*args, **kwargs):
        
        pr = cProfile.Profile()
        pr.enable()
        retval = fnc(*args, **kwargs)
        pr.disable()
        s = io.StringIO()
        sortby = 'cumulative'
        ps = pstats.Stats(pr, stream=s).sort_stats(sortby)
        ps.print_stats()
        print(s.getvalue())
        return retval

    return inner
```


### Various

| Command | Description |
| ------- | ----------- |
| `{:.n%}".format(number)` | Format number as percentage. *n* is the number of decimal places|
| `a, b, *rest = range(5)` | Variable *rest* will grab all remaining items (2-4)|

- Loops through values in a list but skips all 'f' letters
```python
string = 'flower'
for i in (x for x in string if x != 'f'):
    print(i)
```
- Split string into a list of characters
```python
string = 'flower'
res = [] 
res[:] = string
```
