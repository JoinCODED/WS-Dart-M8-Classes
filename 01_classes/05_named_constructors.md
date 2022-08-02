The constructor that we used till now is called a default constructor. However, there are other types of constructors. We will learn about the `named` constructors.

Let's have the following code as a starting point:

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

We have a wallet system that requires you to enter the credits and the holder name. Let's assume we want to add a crypto wallet feature. As you know, what's special about crypto wallets is that they don't have an account holder.

As you can see, our constructor requires two arguments, but uses `named` constructors.

To solve this issue, we can create another constructor:

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

Now, we can use the above constructor as follows:

```dart
void main (){
    final ahmadsWallet = UserWallet(100,"ahmad");
    final cryptoWallet = UserWallet.crypto(200);
    print(ahmadsWallet.holderName);
    // The following print won't print anything, is it here on purpose? 👀
    print(cryptoWallet.holderName);
}
```

Output:

```
ahmad
```
