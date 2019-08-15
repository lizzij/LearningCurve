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

### Classes and Objected-oriented Programming in Python
- Object is an instance of the Class
```Python
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
