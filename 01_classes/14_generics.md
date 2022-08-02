To better understand what generics are, let's take a look at a built-in class we've used in Dart, which is a `list`:

```dart
void main(){
List<int> numbers = [1,2,3];

List<String> words = ["hello","dart","flutter"];
}
```

As you can see in the code above, the type `List` has been called once to hold `int` values and once with `string` values.

How is this possible? and how can we create a class that can take multiple types?

We will build a simplified version of the `List` class to learn this:

```dart
class MyList {
    final List<??> items = [];

    void push(?? item){
        items.add(item);
    }

    ?? pop() => items.removeLast();
}
```

We need `MyList` to be dynamic and accept any type we initialize it with. Our missing pieces here are marked with `??`. For example if `MyList` is going to be for `int` type, the code should be as follows:

```dart
class MyList {
    final List<int> items = [];

    void push(int item){
        items.add(item);
    }

    int pop() => items.removeLast();
}
```

As we agreed, we need it to be dynamic, so we are going to use a `generic`, and we do that by:

1. Telling our class that you will accept a type with the initialization by adding `<T>` after the class name:

```dart
class MyList<T> {
```

2. Replacing each place where we should provide the variable type with the generic `<T>`:

```dart
class MyList<T> {
    final List<T> items = [];

    void push(T item){
        items.add(item);
    }

    T pop() => items.removeLast();
}
```

Now, we can create two lists as follows:

```dart
class MyList<T> {
    final List<T> items = [];

    void push(T item){
        items.add(item);
    }

    T pop() => items.removeLast();
}

void main(){
 final numbers = MyList<int>();
  numbers.push(2);
  numbers.push("word"); // this will give an error because it's a string!
 final words = MyList<String>;
  words.push(2);  // this will give an error because it's an int!
  words.push("word");

}
```
