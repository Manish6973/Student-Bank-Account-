#include<iostream>
using namespace std;
class BankAccount {
   
    public:
    string AHN; // Account Holder's Name 
    string AN; // Account Number
    string AT; // Account Type
    double AB; // Account Balance
    double AD; // Account Deposit   
    double AW; // Account Withdraw
    double ACB; // Account Current Balance
    void createAccount() {
        cout << "Enter Account Holder's Name: ";
        cin >> AHN;
        cout << "Enter Account Number: ";
        cin >> AN;
        cout << "Enter Account Type (Savings/Current): ";
        cin >> AT;
        AB = 0.0; // Initial balance is set to 0
        cout << "Account created successfully!" << endl;
    }
    void deposit() {
        cout << "Enter amount to deposit: ";
        cin >> AD;
        AB += AD; // Update balance
        cout << "Amount deposited successfully!" << endl;
        cout << "Current Balance: " << AB << endl;
    }
    void withdraw() {
        cout << "Enter amount to withdraw: ";
        cin >> AW;
        if (AW > AB) {
            cout << "Insufficient balance!" << endl;
        } else {
            AB -= AW; // Update balance
            cout << "Amount withdrawn successfully!" << endl;
            cout << "Current Balance: " << AB << endl;
        }
    }
    void displayAccountDetails() {
        cout << "------------------------------------------" <<endl;
        cout<<"ACCOUNT HOLDER NAME"<<"\t\t"<<"Account Number"<<"\t\t"<<"ACCOUNT TYPE"<<endl;
        cout<<  AHN <<"\t\t\t\t"<<AN<<"\t\t\t\t"<<AT<< endl;
        cout << "------------------------------------------" << endl;
        cout << "Account Balance"<<"\t\t\t" <<"ACCOUNT WITHDEAW"<<endl;
        cout<<"\t"<<AB <<"\t\t\t"<<AW<< endl;

        cout << "------------------------------------------" << endl;
    }
    void currentBalance() {
        ACB = AB; // Current balance is the same as account balance
        cout << "Current Balance: " << ACB << endl;
    }
    void deleteAccount() {
        AHN = ""; // Clear account holder's name
        AN = ""; // Clear account number
        AT = ""; // Clear account type
        AB = 0.0; // Reset balance to 0
        cout << "Account deleted successfully!" << endl;
    }
};
int main() {
    BankAccount account;
    int choice;
    
    do {
        cout << "Bank Account Management System" << endl;
        cout << "1. Create Account" << endl;
        cout << "2. Deposit" << endl;
        cout << "3. Withdraw" << endl;
        cout << "4. Display Account Details" << endl;
        cout << "5. Current Balance" << endl;
        cout << "6. Delete Account" << endl;
        cout << "7. Exit" << endl;
        cout << "Enter your choice: ";
        cin >> choice;
        system("cls"); // Clear the console screen (optional, for better user experience
        switch (choice) {
            case 1:
                account.createAccount();
                break;
                 
            case 2:
                account.deposit();
                break;
                
            case 3:
                account.withdraw();
                break;
                 
            case 4:
                account.displayAccountDetails();
                break;
               
            case 5:
                account.currentBalance();
                break;
                    
            case 6:
                account.deleteAccount();
                break;
            case 7:
                cout << "Exiting..." << endl;
                break;
            default:
                cout << "Invalid choice! Please try again." << endl;
        }
    } while (choice != 7);

    return 0;
}

