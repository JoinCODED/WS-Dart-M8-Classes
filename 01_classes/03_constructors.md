We want do modify our UserWallet system to be able to add credits when we initialize the wallet instance, and we can achieve that using `class constructors`:

Here's our class so far:

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

We add a constructor by typing the same class name followed by parenthesis:

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

And in those parenthesis, we can add any arguments we need:

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

Then we add curly braces, and we specify what we wanna do with this argument:

```dart
class UserWallet {

UserWallet(double credits){
    credits = credits;
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

Have you noticed something?, it's like we are writing a normal function, but what's special in this function is that it runs on the initialization of the instance, so in the function body we want to assign the `credits` argument to the `credits` property of our class, but they both have the same name, so how can we help dart differentiate between them?

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

As we learned, this function runs when we initialize our instance, thats why we initialize the instance by typing the class name followed by parenthesis, just like we call a function and provide it with the arguments needed, we call the class and give it the arguments needed:

void main() {
final ahmadsWallet = UserWallet(100);
print(ahmadsWallet.credits);
}

Output:

```
100
```

And the same rules for named an positional arguments applies on constructor functions.

But, we can also make the code shorter:

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

We can remove the function body and add `.this` to the argument name and dart is smart enough to know that this is an initializer, and we can also remove the type annotation as dart will infer it from the class property.
