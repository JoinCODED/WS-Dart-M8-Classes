In the previous example, we can replace all the `extends` keyword with `implements` keyword:

```dart
abstract class Person {
    String displayGender();  //abstract method
}

class Boy implements Person {
    @override
    String displayGender(){
        return "boy";
    }
}

class Girl implements Person {
    @override
    String displayGender(){
        return "girl";
    }
}
```

And as you can see nothing has changed, so whats the difference between extending and implementing an abstract class?

With `extends` you can extend only **one** superclass, and you **must** override any abstract method present in the super class.

With `implements` you can implement **multiple** classes, and you **must** override any method weather its abstract or not.
