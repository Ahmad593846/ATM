# ATM

#include<iostream>
using namespace std;

class BankAccount {
private:
	double balance;
public:



	BankAccount(double initialBalance) {
		balance = initialBalance;
	}

	void checkBalance() {
		cout << "Current Balance: " << balance << endl;
	}

	void withdraw(double amount) {
		if(amount < balance) {
			balance -= amount;
			cout << "Withdrawal Successful.\n New Balance: " << balance << endl;
		} else {
			cout << "Insufficient Funds." << endl;
		}
	}
};

int main(){




	BankAccount account(5000);

	while(true) {
		cout << "\n1. Check Balance\n2. Withdraw\n3. Exit" << endl;
		int choice;
		cout << "Enter your choice: ";
		cin >> choice;

		switch(choice) {
			case 1:
				account.checkBalance();
				break;
			case 2:
				double amount;
				cout << "Enter amount to withdraw: ";
				cin >> amount;
				account.withdraw(amount);
				break;
			case 3:
				return 0;
			default:
				cout << "Invalid choice. Please try again." << endl;
		}
	}

	return 0;
}
