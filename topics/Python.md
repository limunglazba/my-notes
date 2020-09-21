# Object Oriented Programming

## Resources
- [Corey Shafer's OOP tutorial on YT](https://www.youtube.com/watch?v=ZDa-Z5JzLYM&list=PL-osiE80TeTsqhIuOqKhwlXsIBIdSeYtc)

## Class Variables
- Class variables can be **accessed through class itself or through class instances** 
  - When accessing an attribute, Python will __first check if an instance contains that attribute__. If it doesn't, it will check if its class (or a class it inherits from) contains it. [[1]](https://youtu.be/BJ-VvGyQxho?t=214)

### Attribute Access via \_\_dict__
- \_\_dict__ is a special attribute of every object, containing all the attributes defined for the object itself. 
- It maps the attribute name to its value.

```python
class Employees:
  def __init__(self, first_name, last_name, pay):
     self.first_name = first_name
     self.last_name = last_name
     self.pay = pay
     
emp1 = Employees ('Guy', 'Montag', 1000)
print(emp1.__dict__)
>> {'first_name': 'Guy', 'last_name': 'Montag', 'pay': 1000}
```
