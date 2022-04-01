We saw how we can inherit the methods and variables of a super class to the sub classes, however, the constructors cannot be directly inherited, let's demonstrate that:

```dart
class Animal {
    Animal({required this.name});
    final String name;
    void eat() => print('eating');
}

class Fish extends Animal {
    void swim() => print('swimming');
}

void main() {
final dog = Animal(name: "bob");
dog.eat();
final shark = Fish();
shark.eat();
shark.swim();
}
```

We added a constructor to our `Animal` class, but as soon as we did that, we got the following error:

```
The superclass 'Animal' doesn't have a zero argument constructor.
```

And to solve this we need to call the super constructor inside the sub class `Fish`:

```dart
class Fish extends Animal {
    Fish() : super();
    void swim() => print('swimming');
}
```

We do this by creating a constructor for the subclass, then a colon `:` then the keyword `super` followed by a parenthesis.

Now in our subclass constructor we require the argument:

```dart
class Fish extends Animal {
    Fish({required name}) : super();
    void swim() => print('swimming');
}
```

And then we pass this argument to the super constructor:

```dart
class Fish extends Animal {
    Fish({required name}) : super(name: name);
    void swim() => print('swimming');
}
```

```dart
void main() {
final dog = Animal(name:"bob");
dog.eat();
final shark = Fish(name:"nemo");
shark.eat();
shark.swim();
}
```
