Suppose we have the following code:

```dart
class Animal {
    void breathe() => print('breathing');
}

class Fish extends Animal {

}

class Human extends Animal {


}
void main() {

}
```

Given the code above, both humans and fish can `breathe` because both extend `animal`, and both of them can `swim` as well, but not all `animal`s can `swim`, so we can't add this method to the `animal` class. The solution is to create what's called a `mixin`:

```dart
mixin Swimming {
    void swim() => print("swim");
}
```

We created a mixin called `Swimming` and added the `swim` method to it. Now, we can use this mixin with any class that needs it, using the `with` keyword:

```dart
class Fish extends Animal with Swimming {

}

class Human extends Animal with Swimming{


}
```
