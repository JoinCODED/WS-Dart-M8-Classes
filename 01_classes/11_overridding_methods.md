We can override a method in the super class with a more specialized version, let's modify our previous example:

```dart
class Animal {
    void move() => print('walking');
}

class Fish extends Animal {

}

void main() {
final dog = Animal();
dog.move();
final shark = Fish();
shark.move();
}
```

To override the `move` method from the superclass in our `Fish` class, we can use the `@override` notation:

```dart
class Animal {
    void move() => print('walking');
}

class Fish extends Animal {
    @override
    void move() => print('swimming');
}

void main() {
final dog = Animal();
dog.move();
final shark = Fish();
shark.move();
}
```

Output:

```
walking
swimming
```

But what if we want to call the `move` method and extend its functionality like this:

```dart
class Animal {
    void move() => print('walking');
}

class Fish extends Animal {
    @override
    void move() {
        move();
        print("Swimming");
    }
}

void main() {
final dog = Animal();
dog.move();
final shark = Fish();
shark.move();
}
```

Output:

```
walking
swimming
```

We expect it to print `walking` then `swimming`, but what will actually happen is whats called recursion, which means that a function is calling it self multiple times until your device runs out of memory, because dart thinks we are calling the `move` method that is in the subclass `Fish`.

To tell dart we need it to run the `move` method from the superclass we add `super` before the function:

```dart
class Animal {
    void move() => print('walking');
}

class Fish extends Animal {
    @override
    void move() {
        super.move();
        print("Swimming");
    }
}

void main() {
final dog = Animal();
dog.move();
final shark = Fish();
shark.move();
}
```

Output:

```
walking
walking
Swimming
```
