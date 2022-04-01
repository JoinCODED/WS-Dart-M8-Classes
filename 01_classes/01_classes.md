Classes are the foundation of object oriented programming and we can use them to define new types. So far we have used the basic types of dart, such as bool, int, double, String, List, Set and Map, but those types can't always be used to model the data we need such as modeling a map location or a bank account, and classes will help us model such things.

Classes are like containers that holds the data and the functionalities for manipulating those data.

Let's start with out first class:

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

In the code above, we declared a class called `UserWallet` with one property inside called `credit` to store the balance of the user, then we initialized the credits to `0` by default.

So how are we going to use this class?, We need to create an `instance` of the class:

```dart
class UserWallet {
double credits = 0;
}

void main() {
final ahmadsWallet = UserWallet();
}
```

And this how to create an instance of the `UserWallet` class and store it in the variable `ahmadsWallet`.

After we created a new wallet, we can check the credits of the wallet we created:

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
0
```

As you see, we can access the properties of a class instance by adding a `.` then the name of the property.

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
500
```

And we can declare multiple instances of a class, for example, let's create a wallet for `omar` and give him `100` credits:

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
500
100
```
