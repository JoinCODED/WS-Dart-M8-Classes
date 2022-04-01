We create a wallet for ahmad:

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

But in real life, a wallet should have some functionalities, like withdrawing credits or deposit credits, and as we said, the class is responsible for manipulating the data in it, so we can add `instance methods`.

Let's create the `deposit` method:

```dart
class UserWallet {
double credits = 0;

void deposit(double amount){
credits = credits + amount;
}

}
```

Adding a method is by creating a function inside the class, and we can use access this method in the same way we accessed our property:

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
500
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
510
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

And let's use it to withdraw 100 credit:

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
410
```

But what if our credits are less than the withdraw account?

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
