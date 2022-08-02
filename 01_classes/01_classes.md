Classes are the foundation of object oriented programming. We can use them to define new types.
So far, we've used the basic types of Dart, such as bool, int, double, String, List, Set and Map, but those types can't always be used to model the data we need, such as modeling a map location or a bank account. However, classes can help us model such data.

Classes are like containers that hold the data and the functionalities to manipulate those data.

Let's start with our first class:

```dart

class UserWallet {

}

void main() {

}
```

We declare a class by using the `class` keyword, followed by the name of the class in `Pascal` case.

```dart
class UserWallet {
double credits = 0;
}

void main() {

}
```

In the code above, we declared a class called `UserWallet` with one property inside called `credit` to store the balance of the user, then we initialized the credits to `0`.

To use this class, we need to create an `instance` of it as shown below:

```dart
class UserWallet {
double credits = 0;
}

void main() {
final ahmadsWallet = UserWallet();
}
```

We created an instance of the `UserWallet` class and stored it in the variable `ahmadsWallet`.

After creating a new wallet, we can check the credits of the wallet we created:

```dart
class UserWallet {
double credits = 0;
}

void main() {
final ahmadsWallet = UserWallet();
print(ahmadsWallet.credits);
}
```

Output:

```
0.0
```

As you can see, we can access the properties of a class instance by adding a `.`, then the name of the property.

We can also set the value of a property:

```dart
class UserWallet {
double credits = 0;
}

void main() {
final ahmadsWallet = UserWallet();
ahmadsWallet.credits = 500;
print(ahmadsWallet.credits);
}
```

Output:

```
500.0
```

We can declare multiple instances of a class. For example, we can create a wallet for `Omar` and give him `100` credits:

```dart
class UserWallet {
double credits = 0;
}

void main() {
final ahmadsWallet = UserWallet();
final omarsWallet = UserWallet();

ahmadsWallet.credits = 500;
omarsWallet.credits = 100;

print(ahmadsWallet.credits);
print(omarsWallet.credits);
}
```

Output:

```
500.0
100.0
```
