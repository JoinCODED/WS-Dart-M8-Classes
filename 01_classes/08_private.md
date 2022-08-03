Private variables and methods allow us to mark things as private and prevent accessing them outside the class.

Bringing back our wallet system:

```dart
class UserWallet {
  UserWallet(this.credits, this.pinCode);

  double credits = 0;
  int pinCode = 0000;

  void deposit(double amount) {
    credits = credits + amount;
  }

  void withdraw(double amount) {
    if (amount < credits) {
      credits = credits - amount;
    }
  }

  double getBalance(int pinCode) {
    if (pinCode == this.pinCode) {
      return credits;
    } else {
      return 0;
    }
  }
}
```

In the example above, I created a method that gets the balance only if the pass code is right:

```dart
void main() {
  final ahmadsWallet = UserWallet(100,5555);
  print(ahmadsWallet.getBalance(222));
  print(ahmadsWallet.getBalance(5555));
  print(ahmadsWallet.credits);
}
```

Output:

```
0
100
100
```

We can still access the credits of ahmad, but we can mark it private by adding an `_` underscore before the name:

```dart
class UserWallet {
  UserWallet(this._credits, this.pinCode);

  double _credits = 0;
  int pinCode = 0000;

  void deposit(double amount) {
    _credits = _credits + amount;
  }

  void withdraw(double amount) {
    if (amount < _credits) {
      _credits = _credits - amount;
    }
  }

  double getBalance(int pinCode) {
    if (pinCode == this.pinCode) {
      return _credits;
    } else {
      return 0;
    }
  }
}

void main() {
  final ahmadsWallet = UserWallet(100,5555);
  print(ahmadsWallet.getBalance(222));
  print(ahmadsWallet.getBalance(5555));
  print(ahmadsWallet._credits);

}
```

<!-- You can access the private variables inside the class as well as the same file, so in the example above, we don't get any error because we're trying to access it within the same file even though the variable is declared in a different class -->

Now, we get an error if we try to access the credits!
