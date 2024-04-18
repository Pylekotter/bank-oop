# Bank - Object-Oriented Programming Practice

This repository contains Python code for a simple banking system implemented using object-oriented programming (OOP) principles. The primary goal of this project was to learn and practice OOP concepts by creating classes and objects to represent different types of bank accounts.

## Classes

### 1. `Account`
- This class represents a generic bank account.
- Attributes:
  - `name`: The name of the account holder.
  - `balance`: The current balance in the account.
  - `min_balance`: The minimum allowed balance for the account.
- Methods:
  - `__init__(self, name, balance, min_balance)`: Initializes the account with the provided name, balance, and minimum balance.
  - `deposit(self, amount)`: Deposits the specified amount into the account.
  - `withdraw(self, amount)`: Withdraws the specified amount from the account if sufficient funds are available.
  - `statement(self)`: Prints the account balance.

### 2. `Current`
- This class represents a current account, which typically allows overdrafts up to a certain limit.
- Inherits from the `Account` class.
- Overrides the `__init__()` method to set a minimum balance of -$1000.
- Overrides the `__str__()` method to provide a custom string representation of the account.

### 3. `Savings`
- This class represents a savings account, which typically does not allow overdrafts.
- Inherits from the `Account` class.
- Overrides the `__init__()` method to set a minimum balance of $0.
- Overrides the `__str__()` method to provide a custom string representation of the account.

## Usage

To create and interact with accounts, follow these steps:

1. Import the necessary classes from the module.
2. Create instances of the `Current` or `Savings` class, passing the account holder's name and initial balance.
3. Use the methods provided by the classes to deposit, withdraw, or check the balance of the accounts.

Example:
```python
from banking import Current, Savings

# Create a current account
current_acc = Current("John Doe", 500)
print(current_acc)  # Output: John Doe's Current Account: Balance $500

# Deposit money into the account
current_acc.deposit(100)
current_acc.statement()  # Output: Account Balance: $600

# Withdraw money from the account
current_acc.withdraw(700)  # Output: Sorry, not enough funds!

