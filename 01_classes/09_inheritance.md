Inheritance, Aka Subclassing is used to extend the functionality of an existing class, Let's see how it works:

```dart
class Animal {
    void eat() => print('eating');
}
void main() {
final dog = Animal();
dog.eat();
}
```

Output:

```
eating
```

Here, we have a class for an `animal`, that for now can do one thing, which is `eating`, and we created one instance for a `dog`.

Now what if I wanted another instance for a `shark`, that has one extra functionality which is `swimming`, it is not convenient
to add the `swimming` method to the `animal` class because not all animals can swim. It's also not convenient to create a new class just for `sharks` and rewrite all methods since they share a common functionally which is `eating`.

The solution for this is by creating a `Fish` class that extends all methods from the `animal` class and then add whatever different method we need to add:

```dart
class Animal {
    void eat() => print('eating');
}

class Fish extends Animal {
    void swim() => print('swimming');
}

void main() {
final dog = Animal();
dog.eat();
final shark = Fish();
shark.eat();
shark.swim();
}
```

Output:

```
eating
eating
swimming
```

Notice that we used the `eat` method in the `Animal` class in the `Fish` class because the `Fish` class `extends` the `Animal` class (which is also called the parent class or the super class) and inherit all its methods and variables.
