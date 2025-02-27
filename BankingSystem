package simpBank;

import java.util.ArrayList;
import java.util.Scanner;


 // This code handles user interaction.
 
public class BankingSystem {
    private static final Scanner scanner = new Scanner(System.in); // Scanner for user input
    private static final ArrayList<BankAccount> allAccounts = new ArrayList<>(); // List of all accounts
    private static BankAccount activeAccount = null; // The selected account

    public static void main(String[] args) {
        System.out.println("\nWelcome to the Simple Banking System");

        while (true) {
            // Display menu options
            System.out.println();
            System.out.println("1. Open New Account");
            System.out.println("2. Deposit Money");
            System.out.println("3. Withdraw Money");
            System.out.println("4. View Balance");
            System.out.println("5. Switch Account");
            System.out.println("6. Exit");
            System.out.println();

            System.out.print("Choose an option: ");
            int choice = getValidIntegerInput(); // Grabs User input

            switch (choice) {
                case 1 -> openNewAccount(); // Create a new account
                case 2 -> { if (isAccountSelected()) depositFunds(); } // Deposit money
                case 3 -> { if (isAccountSelected()) withdrawFunds(); } // Withdraw money
                case 4 -> { if (isAccountSelected()) viewBalance(); } // View account balance
                case 5 -> switchAccount(); // Switch to another account
                case 6 -> {
                    System.out.println("Thanks for using our bank! Have a great day.");
                    return; // Exit program
                }
                default -> System.out.println("Invalid choice! Please select a valid option.");
            }
        }
    }

    
     // Opens a new bank account with an initial deposit.
     
    // Gets the name and deposit
    private static void openNewAccount() {
        System.out.print("Enter your full name: ");
        String name = scanner.nextLine(); 

        System.out.print("Enter initial deposit amount: ");
        double initialDeposit = getValidDoubleInput(); 

        // Create and store the new account
        BankAccount newAccount = new BankAccount(name, initialDeposit);
        allAccounts.add(newAccount);
        activeAccount = newAccount;

        System.out.println("Account successfully created!");
        newAccount.showAccountDetails(); 
    }

    
     // Deposits funds into the active account.
     
    private static void depositFunds() {
        System.out.print("Enter the amount to deposit: ");
        double amount = getValidDoubleInput(); // Get deposit amount
        activeAccount.deposit(amount); // Deposit into account
    }

    
     // Withdraws funds from the active account.
     
    private static void withdrawFunds() {
        System.out.print("Enter the amount to withdraw: ");
        double amount = getValidDoubleInput(); // Get withdrawal amount
        activeAccount.withdraw(amount); // Withdraw from account
    }

    
     // Displays the balance of the active account.
     
    private static void viewBalance() {
        System.out.println("Your current balance is: $" + activeAccount.getBalance());
    }

    
     // Switches to another available account.
     
    private static void switchAccount() {
        if (allAccounts.isEmpty()) {
            System.out.println("⚠️ No accounts available! Create one first.");
            return;
        }

        //Show available accounts
        System.out.println("\nAvailable Accounts:");
        for (int i = 0; i < allAccounts.size(); i++) {
            System.out.println((i + 1) + ". " + allAccounts.get(i).getOwnerName());
        }

        System.out.print("Enter the account number to switch to: ");
        int index = getValidIntegerInput(); //Get account selection

        //Validate and switch account
        if (index >= 1 && index <= allAccounts.size()) {
            activeAccount = allAccounts.get(index - 1);
            System.out.println("✅ Switched to account: " + activeAccount.getOwnerName());
        } else {
            System.out.println("❌ Invalid selection! Please choose a valid account.");
        }
    }

    
     //Checks if an account is chosen before performing an action.
     // return true if an account is selected, false otherwise.
     
    private static boolean isAccountSelected() {
        if (activeAccount == null) {
            System.out.println("No account selected! Please create or switch to an account first.");
            return false;
        }
        return true;
    }

    
     // Gets a valid integer input from the user.
     // return a valid integer entered by the user.
     
    private static int getValidIntegerInput() {
        while (true) {
            try {
                return Integer.parseInt(scanner.nextLine().trim()); // Parse input as integer
            } catch (NumberFormatException e) {
                System.out.print("Invalid input! Please enter a number: ");
            }
        }
    }

    
     // Gets a valid double input from the user.
      // return a valid positive double entered by the user.
    
    private static double getValidDoubleInput() {
        while (true) {
            try {
                double value = Double.parseDouble(scanner.nextLine().trim()); // Parse input as double
                if (value >= 0) return value;
                else System.out.print("Invalid amount! Enter a positive number: ");
            } catch (NumberFormatException e) {
                System.out.print("Invalid input! Please enter a valid number: ");
            }
        }
    }
}
