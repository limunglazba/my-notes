Python
============

### Installation

| Command | Description |
| ------- | ----------- |
| `pip freeze > requirements.txt` | Save installed Python packages in a new txt file |
| `pip install -r requirements.txt` | Install these packages in a new environment |




### Object Oriented Programming

#### Resources
- [Corey Shafer's OOP tutorial on YT](https://www.youtube.com/watch?v=ZDa-Z5JzLYM&list=PL-osiE80TeTsqhIuOqKhwlXsIBIdSeYtc)


#### Class Variables[[1]](https://www.youtube.com/watch?v=BJ-VvGyQxho)
- Class attributes can be **accessed through class itself or through class instances** 
- When accessing an attribute through an instance, Python will __first check if an instance contains that attribute__. If it doesn't, it will check if its class (or a class it inherits from) contains it. [[1]](https://youtu.be/BJ-VvGyQxho?t=214)

##### Class Constructor \_\_init__
- Runs every time an instance is made

##### Attribute Access via \_\_dict__
- \_\_dict__ is a special attribute of every object, containing all the attributes defined for the object itself. 
- It maps the attribute name to its value.

```python
class Employees:
  def __init__(self, first_name, last_name, pay):
     self.first_name = first_name
     self.last_name = last_name
     self.pay = pay
     
emp_1 = Employees ('Guy', 'Montag', 1000)
print(emp_1.__dict__)

>>> {'first_name': 'Guy', 'last_name': 'Montag', 'pay': 1000}
```


#### classmethods and staticmethods[[1]](https://www.youtube.com/watch?v=rq8cL2XMM5M)
- **Regular methods** automatically take in the **instance as the first argument**
```python
def fullname(self):
  return f'{self.first_name} {self.last_name}'
fullname(emp_1)
>>> 'Guy Montag'
```
- **classmethod** has a decorator **@classmethod** at the top and **class as the first argument**
```python
@classmethod
def set_raise_amt(cls, amount):
  cls.raise_amt = amount
```
- **staticsmethod** has a decorator **@staticmethod** at the top and **don't pass anything automatically**
- This means they behave like a normal function - they are included in the class because they have a logical connection with it
- If the method doesn't uses the class or its instance, it should probably be a static method


#### Inheritance and subclasses
- **Subclasses** inherits attributes and methods from the parent class, which we can then override or add new functionalities without affecting the parent class
- **Method Resolution Order** defines the chain of inheritance in which order Python checks for attributes and methods (child \>\> parent \>\> generic object class)
- Use **super()** for accessing methods of base classes:
```python
class Developer(Employee):
    def __init__(self, first, last, pay, prog_lang):
        super().__init__(first, last, pay)
        self.prog_lang = prog_lang
```





### Type hints
| Command | Returns | Source |
| ```python
def greeting(name: str) -> str:
    return 'Hello ' + name
``` | ----------- | [Python tricks: Type hints and static type checking YT intro video](https://www.youtube.com/watch?v=rytP_vIjzeE) |

- 



### Various
- Loops through values in a list but skips all 'f' letters
```python
string = 'flower'
for i in (x for x in string if x != 'f'):
    print(i)
```
