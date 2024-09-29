# Lab Report: 03
### Date of Submission: 30 September 2024
____

### Experiment No: 01
<h3 align = "justify"> Name of the Experiment: To write a C++ program to implement a class called BankAccount that has private member variables for account number and balance. Include member functions to deposit and withdraw money from the account.</h3>

### Theory: 
<p align = "justify" >As C++ is an object-oriented programming language, we can create classes that can contain different member variables and methods. Then creating object of that class we can access those members. <br><br> The syntax for declaring class: </p>

```cpp
class ClassName
{
  //declaration of members
};

```

### Code:
```cpp
#include <iostream>
#include <string>
#include <cmath>
#include <conio.h>
using namespace std;

class BankAccount
{
private:
    int accountNo;
    long double balance;

public:
    void giveInfo()
    {
        cout << "Enter Account No: " << endl;
        cin >> accountNo;
        cout << "Enter Current Balance: " << endl;
        cin >> balance;
    }

    void deposit(int d)
    {
        balance = balance + d;
        cout << "Deposit Successful. \nNew Balance: " << balance << "Tk." << endl;
    }
    void withdraw(int w)
    {
        if (balance >= w)
        {
            balance = balance - w;
            cout << "Receive your money. \nNew Balance: " << balance << "Tk." << endl;

        }
        else
        {
            cout << "Insufficient Balance. \nBalance: " << balance << "Tk." << endl;

        }
    }
};

int main ()
{
    BankAccount acc1;
    acc1.giveInfo();

    int choose;

    cout << "Choose an option (1 or 2: \n1. Deposit Money \n2. Withdraw Money." << endl;
    cin >> choose;

    switch (choose)
    {
    case 1 :
        int d;
        cout << "Enter Deposit Amount: ";
        cin >> d;
        acc1.deposit(d);
        break;

    case 2 :
        int w;
        cout << "Enter Withdrawal Amount: ";
        cin >> w;
        acc1.withdraw(w);
        break;

    default :
        cout << "Invalid Input. Transaction cancelled" << endl;
    }
    getch();

}

```

### Output:
**For Deposit:** <br> <br>
![Screenshot 2024-09-29 222047](https://github.com/user-attachments/assets/e8b3dd0c-9385-4694-a672-bc81d889db05)

**For Withdraw:** <br> <br>
![Screenshot 2024-09-29 222120](https://github.com/user-attachments/assets/881ef4e4-2bf0-4752-8057-2d1825410ec4)

### Discussion and Conclusion:
<p align = "justify" >From the experiment, we can learn how classes and objects can be created in C++. At the same time, we found that how the use of OOP that is the use of classes and objects can make our code shorter and reusable..</p>


