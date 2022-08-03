Abstract classes are classes that cannot be instantiated. Let's take an example:

```dart
abstract class Person {
}
```

We declare an `abstract` class by adding the `abstract` keyword before the `class` keyword.

```dart
abstract class Person {
}
void main() {
    final person = Person();
}
```

We got the following error because abstract classes cannot be instantiated.

```
Abstract classes can't be instantiated.
```

What's the point if we can't use it? We can extend those classes and override their methods and variables:

```dart
abstract class Person {
    String displayGender();  //abstract method
}

class Boy extends Person {
    @override
    String displayGender(){
        return "boy";
    }
}

class Girl extends Person {
    @override
    String displayGender(){
        return "girl";
    }
}

void main() {
final personOne = Boy();
final personTwo = Girl();
print(personOne.displayGender());
print(personTwo.displayGender());
```

Output:

```
boy
girl
```

Still don't feel this is useful? What if we want to create a function that allows boys only to enter? we can now refer to both `personOne` and `personTwo` as the type `Person`, like this:

```dart
bool amIAllowed(Person person){
  return person.displayGender() == "boy";
}
```

```dart
void main() {
final boy = Boy();
final girl = Girl();
print(amIAllowed(boy));
}
```

Output:

```
true
```

The conclusion is: Abstract classes can help us define an `interface` that can be implemented by subclasses.
