**Main.java **  
import java.util.Scanner;  
public class Main {  
    public static void main(String[] args) {  
        Scanner sc = new Scanner(System.in);  
        BankService service = new BankService();  
  
        while (true) {  
            System.out.println("\n1.Create Account\n2.Deposit\n3.Withdraw\n4.Check Balance\n5.Exit");  
            int choice = sc.nextInt();  
  
            if (choice == 5) {  
                System.out.println("Thank You!");  
                break;  
            }  
  
            System.out.print("Enter Account Number: ");  
            int accNo = sc.nextInt();  
  
            BankAccount account = service.findAccount(accNo);  
  
            switch (choice) {  
                case 1:  
                    System.out.print("Enter Name: ");  
                    String name = sc.next();  
                    System.out.print("Enter Initial Balance: ");  
                    double bal = sc.nextDouble();  
                    service.createAccount(accNo, name, bal);  
                    break;  
  
                case 2:  
                    if (account != null) {  
                        System.out.print("Enter Amount: ");  
                        account.deposit(sc.nextDouble());  
                    } else {  
                        System.out.println("Account Not Found");  
                    }  
                    break;  
  
                case 3:  
                    if (account != null) {  
                        System.out.print("Enter Amount: ");  
                        account.withdraw(sc.nextDouble());  
                    } else {  
                        System.out.println("Account Not Found");  
                    }  
                    break;  
  
                case 4:  
                    if (account != null) {  
                        System.out.println("Balance: " + account.getBalance());  
                    } else {  
                        System.out.println("Account Not Found");  
                    }  
                    break;  
  
                default:  
                    System.out.println("Invalid Option");  
            }  
        }  
        sc.close();  
    }  
}  
