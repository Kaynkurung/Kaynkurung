
```
#include <iostream>
#include <string>
using namespace std;

// Payment class to represent a payment and its details
class Payment {
private:
    string recipient;
    float amount;
    string currency;
public:
    Payment(string _recipient, float _amount, string _currency) {
        recipient = _recipient;
        amount = _amount;
        currency = _currency;
    }
    void display() {
        cout << "Recipient: " << recipient << endl;
        cout << "Amount: " << amount << " " << currency << endl;
    }
};

// User class to represent a user of the payment platform app
class User {
private:
    string name;
    float balance;
public:
    User(string _name, float _balance) {
        name = _name;
        balance = _balance;
    }
    void display_balance() {
        cout << "Your balance is: " << balance << endl;
    }
    void make_payment(Payment p) {
        if (balance < p.amount) {
            cout << "Insufficient funds." << endl;
        } else {
            balance -= p.amount;
            cout << "Payment successful." << endl;
        }
    }
};

int main() {
    // Create two users with initial balances
    User user1("Alice", 100.0);
    User user2("Bob", 50.0);

    // Display user balances
    user1.display_balance();
    user2.display_balance();

    // Create a payment and display its details
    Payment payment("Bob", 25.0, "USD");
    payment.display();

    // Make the payment from user1 to user2
    user1.make_payment(payment);
    user2.make_payment(payment);

    // Display updated user balances
    user1.display_balance();
    user2.display_balance();

    return 0;
}
```


