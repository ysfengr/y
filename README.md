from abc import ABC, abstractmethod

class Animal(ABC):
    def __init__(self, name):
        self.__name = name

    def get_name(self):
        return self.__name

    @abstractmethod
    def sound(self):
        pass

class Dog(Animal):
    def sound(self):
        return "Woof! Woof!"

class Cat(Animal):
    def sound(self):
        return "Meow..."

class Horse(Animal):
    def sound(self):
        return "Neighing!"

class Person:
    def __init__(self, first_name):
        self.first_name = first_name

    def greeting(self):
        return f'Hello, I am {self.first_name}.'

    def play_with_pet(self, any_animal):
        pet_name = any_animal.get_name()
        pet_noise = any_animal.sound()
        print(f"{self.first_name} plays with {pet_name}: It says '{pet_noise}'")

my_dog = Dog("Buddy")
my_cat = Cat("Whiskers")
my_horse = Horse("Spirit")

me = Person("Yousef")

print(me.greeting())
print("-" * 20)
me.play_with_pet(my_dog)
me.play_with_pet(my_cat)
me.play_with_pet(my_horse)
