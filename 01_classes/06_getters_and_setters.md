Suppose we have the following class:

```dart
class Person{
  Person(this.height);
  double height;

  double heightInInch(){
    return height / 2.54;
  }
}
```

The above class takes the height in `cm`. We can initialize an instance of this class and get the height in inches:

```dart
void main (){
 final ahmad = Person(200);
 print(ahmad.heightInInch());
}
```

Output:

```
78.74015748031496
```

However, there's a better way of doing that, and it's called a `getter`. This is a computed value instead of a method, and it's used to retrieve a particular class filed and save it in a variable:

```dart
class Person{
  Person(this.height);
  double height;

  double get heightInInch => height / 2.54;
}

void main (){
 final ahmad = Person(200);
 print(ahmad.heightInInch);
}
```

We place the `get` keyword between the return type and the name of the variable we want to get. We remove the `parentheses` because no need to define parameters.

We can also define a `setter` that sets the height in feet:

```dart
class Person{
  Person(this.height);
  double height;

  double get heightInInch => height / 2.54;
  set heightInFeet(double height) => this.height = height / 30.48;
}

void main (){
 final ahmad = Person(200);
 print(ahmad.heightInInch);
 ahmad.heightInFeet = 200;
 print(ahmad.height);
}
```

Output:

```
78.74015748031496
6.561679790026247
```
