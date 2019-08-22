# python

### pip
- if a module is already installed
```bash
$ python -c "import math"
$ echo $?
```

### random
- list all attributes of an object `<object_name>.__dict__.keys()
`
- `class collections.defaultdict([default_factory[, ...]])`
- `|=` ior: `var |= value` is short for `var = var | value`
- lambda `lambda x, y: x + y` then `_(1, 2)` outputs `3`, which is the same as the immediately invoked function execution (IIFE) `(lambda x, y: x + y)(1, 2)`
- the keyword argument unpacking syntax in a list of arguments
  - `*args`: argument unpacking
  - `**kwargs`: keyword argument unpacking
  ```
  args = (1, 2, 3)  # usually a tuple, always an iterable[1]
  f(*args) → f(1, 2, 3)
  # and
  kwargs = {"a": 1, "b": 2, "c": 3}  # usually a dict, always a mapping*
  f(**kwargs) -> f(a=1, b=2, c=3)
  ```

- enumerate: loop over with an automatic counter

```py
for counter, value in enumerate(some_list):
  print(counter, value)
```

```py
my_list = ['apple', 'banana', 'grapes', 'pear']
for c, value in enumerate(my_list, 1): # here "1" is the optional start index
    print(c, value)

# Output:
# 1 apple
# 2 banana
# 3 grapes
# 4 pear
```

### Classes and Objected-oriented Programming in Python

- Object is an instance of the Class

```py
class Shark:
    # constructor method (to initalize data)
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def swim(self):
        print(self.name + " is swimming.")

    def be_awesome(self):
        print(self.name + " is being awesome.")


def main():
    # Set name of Shark object
    sammy = Shark("Sammy", 5)
    sammy.swim()
    sammy.be_awesome()

if __name__ == "__main__":
    main()
```

- object inheritance

```Python
# Parent class
class Dog:

    # Class attribute
    species = 'mammal'

    # Initializer / Instance attributes
    def __init__(self, name, age):
        self.name = name
        self.age = age

    # instance method
    def description(self):
        return "{} is {} years old".format(self.name, self.age)

    # instance method
    def speak(self, sound):
        return "{} says {}".format(self.name, sound)


# Child class (inherits from Dog class)
class RussellTerrier(Dog):
    def run(self, speed):
        return "{} runs {}".format(self.name, speed)


# Child class (inherits from Dog class)
class Bulldog(Dog):
    def run(self, speed):
        return "{} runs {}".format(self.name, speed)


# Child classes inherit attributes and
# behaviors from the parent class
jim = Bulldog("Jim", 12)
print(jim.description())

# Child classes have specific attributes
# and behaviors as well
print(jim.run("slowly"))
```

### closure

- for encapsulation
