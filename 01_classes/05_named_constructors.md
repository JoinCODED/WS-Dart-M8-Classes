The constructor we used till now is called a default constructor. But there's another types of constructors, and we will learn about the `named` constructors.

Lets have this code as a starting point:

```dart
class UserWallet {

UserWallet(this.credits, this.holderName);

double credits = 0;
String holderName = "";

void deposit(double amount){
credits = credits + amount;
}

void withdraw(double amount){
    if(amount < credits){
        credits = credits - amount;
    }
}

}

void main (){
    final ahmadsWallet = UserWallet(100,"ahmad");
}

```

We have a wallet system that requires you to enter the credits and the holder name, but let's assume we wanna add a crypto wallet feature, and as you know, whats special about crypto wallets is that they doesn't have an account holder.

But our constructor requires 2 arguments, but using `named` constructors, we can create another constructor:

```dart
class UserWallet {

UserWallet(this.credits, this.holderName);
UserWallet.crypto(this.credits);

double credits = 0;
String holderName = "";

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

And we can use this constructor like this:

```dart
void main (){
    final ahmadsWallet = UserWallet(100,"ahmad");
    final cryptoWallet = UserWallet.crypto(200);
    print(ahmadsWallet.holderName);
    print(cryptoWallet.holderName);
}
```

Output:

```
ahmad
```
