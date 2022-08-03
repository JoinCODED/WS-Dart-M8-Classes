We want to modify our `UserWallet` system to be able to add credits when we initialize the wallet instance. We can achieve that by using `class constructors`:

Below is our class so far:

```dart
class UserWallet {
double credits = 0;

void deposit(double amount){
credits = credits + amount;
}

void withdraw(double amount){
    if(amount < credits){
        credits = credits - amount;
    }
}

}
```

We add a constructor by typing the class name followed by parentheses:

```dart
class UserWallet {

UserWallet();

double credits = 0;

void deposit(double amount){
credits = credits + amount;
}

void withdraw(double amount){
    if(amount < credits){
        credits = credits - amount;
    }
}

}
```

In those parentheses, we can add any argument we need:

```dart
class UserWallet {

UserWallet(double credits);

double credits = 0;

void deposit(double amount){
credits = credits + amount;
}

void withdraw(double amount){
    if(amount < credits){
        credits = credits - amount;
    }
}

}
```

We add curly braces, and we specify what we want to do with this argument:

```dart
class UserWallet {

UserWallet(double credits){
    credits = credits;
}

double credits = 0;

void deposit(double amount){
credits = credits + amount;
}

void withdraw(double amount){
    if(amount < credits){
        credits = credits - amount;
    }
}

}
```

Have you noticed something? It's like we are writing a regular function. However, what's special about this one is that it runs on the initialization of the instance. In the function body, we want to assign the `credits` argument to the `credits` property of our class, but they both have the same name, how can we help Dart differentiate between them?

We use the `this` keyword to refer to the class property:

```dart
class UserWallet {

UserWallet(double credits){
    this.credits = credits;
};

double credits = 0;

void deposit(double amount){
credits = credits + amount;
}

void withdraw(double amount){
    if(amount < credits){
        credits = credits - amount;
    }
}

}
```

As we learned, this function runs when we initialize our instance. That's why we initialize the instance by typing the class name followed by parentheses. Just like calling a function and providing it with the arguments needed, we call the class and give it the arguments needed:

```dart
void main() {
final ahmadsWallet = UserWallet(100);
print(ahmadsWallet.credits);
}
```

Output:

```
100
```

The same rules of named and positional arguments apply to constructor functions.

We can also make the code shorter:

```dart
class UserWallet {

UserWallet(this.credits);

double credits = 0;

void deposit(double amount){
credits = credits + amount;
}

void withdraw(double amount){
    if(amount < credits){
        credits = credits - amount;
    }
}

}
```

We can remove the function body and add `.this` to the argument. Dart is smart enough to know that this is an initializer. We can also remove the type annotation, as Dart will infer it from the class property.
