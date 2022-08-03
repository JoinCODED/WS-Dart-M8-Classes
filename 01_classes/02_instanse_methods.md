We created a wallet for ahmad:

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

In real life, a wallet should have some functionalities, like withdrawing credits or depositing credits. As we said, the class is responsible for manipulating the data in it, so we can add instance methods.

Let's create the `deposit` method:

```dart
class UserWallet {
double credits = 0;

void deposit(double amount){
credits = credits + amount;
}

}
```

We add a method by creating a function inside the class. We can access this method in the same way we accessed our property:

```dart
class UserWallet {
double credits = 0;

void deposit(double amount){
credits = credits + amount;
}

}

void main() {
final ahmadsWallet = UserWallet();
ahmadsWallet.deposit(500);
print(ahmadsWallet.credits);
}
```

Output:

```
500.0
```

Let's add another 10 credits for ahmad using our method:

```dart
void main() {
final ahmadsWallet = UserWallet();
ahmadsWallet.deposit(500);
ahmadsWallet.deposit(10);
print(ahmadsWallet.credits);
}
```

Output:

```
510.0
```

Let's create the withdraw method:

```dart
class UserWallet {
double credits = 0;

void deposit(double amount){
credits = credits + amount;
}

void withdraw(double amount){
credits = credits - amount;
}

}
```

Let's use it to withdraw 100 credits:

```dart
class UserWallet {
double credits = 0;

void deposit(double amount){
credits = credits + amount;
}

void withdraw(double amount){
credits = credits - amount;
}

}

void main() {
final ahmadsWallet = UserWallet();
ahmadsWallet.deposit(500);
ahmadsWallet.deposit(10);
ahmadsWallet.withdraw(100);
print(ahmadsWallet.credits);
}

```

Output:

```
410.0
```

What if our credits are less than the withdraw account?

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
