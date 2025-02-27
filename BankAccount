package simpBank;

import java.util.Random;


 // Makes account and holds all info
 
class BankAccount {
    private String ownerName; // Account owner name
    private String accountId; // account ID
    private double balance;   // Account balance

   
     // Constructor to initialize a new account.
      
    public BankAccount(String ownerName, double initialDeposit) {
        this.ownerName = ownerName;
        this.accountId = generateAccountNumber(); // Generate a unique account number
        this.balance = initialDeposit;
    }

    
     // Deposits funds into the account.
    public void deposit(double amount) {
        if (amount > 0) {
            balance += amount;
            System.out.println("Deposit successful! New balance: $" + balance);
        } else {
            System.out.println("Can't deposit a negative amount.");
        }
    }

    
     // Withdraws funds from the account if sufficient balance is available.
   
    public void withdraw(double amount) {
        if (amount > 0 && amount <= balance) {
            balance -= amount;
            System.out.println("Withdrawal successful! Remaining balance: $" + balance);
        } else if (amount > balance) {
            System.out.println("Insufficient funds! You only have $" + balance);
        } else {
            System.out.println("Invalid withdrawal amount.");
        }
    }

    
     // Gets the current balance of the account.
    
    public double getBalance() {
        return balance;
    }

    
     // Shows the account details.
     
    public void showAccountDetails() {
        System.out.println("\nAccount Holder: " + ownerName);
        System.out.println("Account ID: " + accountId);
        System.out.println("Balance: $" + balance);
    }

    
    // Makes a unique 8-digit account ID.
    
    private String generateAccountNumber() {
        return "BA" + (10000000 + new Random().nextInt(90000000)); // make unique ID
    }

    // Gets the account owner's name.
    
    public String getOwnerName() {
        return ownerName;
    }
}
