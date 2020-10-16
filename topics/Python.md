Python
============

### Installation
| Command | Description |
| ------- | ----------- |
| `pip freeze > requirements.txt` | Save installed Python packages in a new txt file |
| `pip install -r requirements.txt` | Install these packages in a new environment |

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
| def squares(nums):<br>    result = []<br>    for i in nums: <br>       result.append(i`*`i) <br>    return result<br>    my_nums = squares((1,2,3,4,5)) <br>    print(my_nums)| 
xx |


- List-based function that returns square numbers:
```
def squares(nums):
    result = []
    for i in nums:
        result.append(i*i)
    return result

my_nums = squares((1,2,3,4,5))
print(my_nums)
``` 
- Generator-based function that returns square numbers:
```
def squares(nums):
    for i in nums:
        yield (i*i)

my_nums = squares([1,2,3,4,5])
for num in my_nums:
    print (num)
``` 


### Tuples
**Tuple is an immutable and hashable list.**
#### Tuple Unpacking
```
>>> lax_coordinates = (33.9425, -118.408056)
>>> latitude, longitude = lax_coordinates # tuple unpacking
```
| Command | Description |
| ------- | ----------- |
| `a, b = b, a` | Swapping variables with tuple unpacking without using a temporary variable |
| `print(*t)` | Prefixing an argument with * will also unpack the tuple *t* |

### Various

| Command | Description |
| ------- | ----------- |
| `{:.n%}".format(number)` | Format number as percentage. *n* is the number of decimal places|


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
