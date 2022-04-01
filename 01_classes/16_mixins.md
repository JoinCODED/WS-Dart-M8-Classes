Suppose we have the following code:

```dart
class Animal {
    void breath() => print('breathing');
}

class Fish extends Animal {

}

class Human extends Animal {


}
void main() {

}
```

Giving the code above, both humans and fish can `breath` because both extends `human`, and both of them can `swim` also, but not all `animal`s can `swim`, so we can't add this method to the `animal` class, the solution is to create whats so called a `mixin`:

```dart
mixin Swimming {
    void swim() => print("swim");
}
```

We created a mixin called `Swimming` and added the `swim` method in it, and now when can use this mixin with any class that needs it using the `with` keyword:

```dart
class Fish extends Animal with Swimming {

}

class Human extends Animal with Swimming{


}
```
