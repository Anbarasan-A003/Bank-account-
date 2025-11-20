# Bank-account-

import java.util.*;
class bankaccount{
    int accno;
    String name;
    double balance;
    bankaccount(String hname,int acc,double intialbalance){
        accno=acc;
        name=hname;
        balance = intialbalance;
    }
    void display() {
        System.out.println("\n--- Account Details ---");
        System.out.println("Name: " + name);
        System.out.println("Account Number: " + accno);
        System.out.println("Balance: " + balance);
    }
    void deposite(double amount){
        balance+=amount;
    }
    void withdrawal(double amount){
        if(amount>balance){
            System.out.println("Insufficient balance");

        }
        else{
            balance-=amount;
        }
    }
}
public class Main{
    public static void main(String[] args){
        Scanner sc=new Scanner(System.in);
        System.out.println("Enter acc holder name: ");
        String hname=sc.nextLine();
        System.out.println("Enter acc num: ");
        int acc=sc.nextInt();
        System.out.print("Enter Initial Balance: ");
        double bal = sc.nextDouble();
        bankaccount ac = new bankaccount(hname, acc, bal);
        System.out.println("Enter deposite Amount");
        ac.deposite(sc.nextDouble());
        System.out.println("Enter amount to be withdrawal");
        ac.withdrawal(sc.nextDouble());
        ac.display();
    }
}
