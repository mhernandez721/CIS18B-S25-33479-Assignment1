# CIS18B-S25-33479-Assignment1

This program does the following

* Open a new bank account
* Deposit money
* Withdraw money
* View account balance
* Switch between multiple accounts

# Project Structure

goober (packet)
* BankingSystem.java   Handles user interactions and menu options
* BankAccount.java     Manages individual bank accounts
* README.md            Documentation file

# How does it work

Banking system handles all the user input and outputs. From the menu using a switch case to deposits, widthdraws and account creation, sending them to Bankaccount for it to process them in the back end.


BankAccount is more like the backend of the whole program. It grabs all the inputs from BankingSystem and process them. This one creates the account ID using 8-digit codes, processing widthdraws and deposits and storing those details. We store multiple accounts here too.
