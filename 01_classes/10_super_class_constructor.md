We saw how the sub classes can inherit the methods and variables from a super class. However, the constructors cannot be directly inherited, let's demonstrate that:

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

We added a constructor to our `Animal` class, but once we did that, we got the following error:

```
The superclass 'Animal' doesn't have a zero argument constructor.
```

To solve this, we need to call the super constructor inside the sub class `Fish`:

```dart
class Fish extends Animal {
    Fish() : super();
    void swim() => print('swimming');
}
```

We do that by creating a constructor for the subclass, followed by a colon `:`, then the keyword `super` followed by parentheses.

Now, in our subclass constructor, we require the argument name:

```dart
class Fish extends Animal {
    Fish({required name}) : super();
    void swim() => print('swimming');
}
```

Then, we pass this argument to the super constructor:

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
