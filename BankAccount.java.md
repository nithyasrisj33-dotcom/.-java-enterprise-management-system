**BankAccount.java **  
public class BankAccount {  
    private int accountNumber;  
    private String accountHolder;  
    private double balance;  
  
    public BankAccount(int accountNumber, String accountHolder, double balance) {  
        this.accountNumber = accountNumber;  
        this.accountHolder = accountHolder;  
        this.balance = balance;  
    }  
  
    public int getAccountNumber() {  
        return accountNumber;  
    }  
  
    public String getAccountHolder() {  
        return accountHolder;  
    }  
  
    public double getBalance() {  
        return balance;  
    }  
  
    public void deposit(double amount) {  
        balance += amount;  
        System.out.println("Amount Deposited Successfully");  
    }  
  
    public void withdraw(double amount) {  
        if (amount <= balance) {  
            balance -= amount;  
            System.out.println("Amount Withdrawn Successfully");  
        } else {  
            System.out.println("Insufficient Balance");  
        }  
    }  
}  
