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

That takes the height in `cm`. We can initialize an instance of this class and get the height in inches:

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

But there's a nicer way of doing this called a `getter`. Which is a computed value instead of a method:

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

We write `get` between the `type` and the `name`, and we remove the `return` keyword and the `parenthesis`.

We can also define a setter that sets the height in feet:

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
