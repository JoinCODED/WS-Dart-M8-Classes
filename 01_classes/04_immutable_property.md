Let's add another property for the account holder name:

```dart
class UserWallet {

UserWallet(this.credits, this.holderName);

double credits = 0;
String holderName;

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

We created two methods, withdraw and deposit credits, but we don't want the user to change the account holder name like this:

```dart
void main() {
final ahmadsWallet = UserWallet(100,"ahmad");
ahmadsWallet.holderName = "omar";
print(ahmadsWallet.holderName);
print(ahmadsWallet.credits);
}
```

Output:

```
omar
100
```

We can mark the account holder name property as immutable by making it final:

```dart
class UserWallet {

UserWallet(this.credits, this.holderName);

double credits = 0;
final String holderName;

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

**Note:** If all of your class's properties are immutable (final), you should declare the constructor as `const`, example:

```dart
class Example{
    const Example(this.x,this.y)
    final x;
    final y;
}
```
