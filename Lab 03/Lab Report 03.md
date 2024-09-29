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
<p align = "justify" >From the experiment, we can learn how classes and objects can be created in C++. At the same time, we found that how the use of OOP that is the use of classes and objects can make our code shorter and reusable.</p>

___

### Experiment No: 02
<h3 align = "justify"> Name of the Experiment: To write a C++ program to implement a class called Date that has private member variables for day, month, and year. Include member functions to set and get these variables, as well as to validate if the date is valid.</h3>

### Theory: 
<p align = "justify" >The validity of a date can be checked by using information like the number of days in a month and the number of months in a year. For example, February generally contains 28 days but in the leap year February contains 29 days. So, 29th February is a valid date for leap year but not a valid date for other years.</p>

### Code:
```cpp
#include <iostream>
#include <conio.h>
using namespace std;

class Date
{
private:
    int day;
    int month;
    int year;

public:
    void setDate()
    {
        cout << "Enter Day: ";
        cin >> day;
        cout << "Enter Month: ";
        cin >> month;
        cout << "Enter Year: ";
        cin >> year;
    }

    bool leapYear(int year)
    {
        if ((year % 4 == 0 && year % 100 != 0) || year % 400 == 0)
        {
            return true;
        }

        return false;
    }

    bool validDate()
    {
        if (month < 1 || month > 12)
        {

            return false;
        }
        else if (day < 1 || day > 31)
        {
            return false;
        }

        else if ((month == 4 || month == 6 || month == 9 || month == 11) && day > 30)
        {
            return false;
        }

        else if (month == 2)
        {
            if (leapYear(year))
            {
                if (day > 29) return false;
            }
            else
            {
                if (day > 28) return false;
            }
        }

        return true;
    }

    void display()
    {
        cout << "\nGiven Date: " << day << "/" << month << "/" << year << endl;
    }
};

int main()
{
    Date date;
    date.setDate();

    date.display();

    if (date.validDate())
    {
        cout << "The date is valid." << endl;
    }
    else
    {
        cout << "The date is invalid." << endl;
    }

    getch();
}

```

### Output:
**For Valid Date:** <br> <br>
![Screenshot 2024-09-29 230212](https://github.com/user-attachments/assets/6194a556-1e16-4ca1-bc6f-a0a2a073065a)

**For Invalid Date:** <br> <br>
![Screenshot 2024-09-29 230236](https://github.com/user-attachments/assets/25a5749f-b2e5-45d3-88a3-4bd78dac0bd6)

### Discussion and Conclusion:
<p align = "justify" >In this Experiment we created a class named Date and then under this class we declared data fields and member functions to check the validity of a given date.</p>

___

### Experiment No: 03
<h3 align = "justify"> Name of the Experiment: To write a C++ program to display the first n terms of the Fibonacci series using OOP concept.</h3>

### Theory: 
<p align = "justify" > The Fibonacci series is a series where the first and second terms are respectively zero and one, and then any next term is the sum previous two terms. For solving this problem we can use a for loop which will add the previous two terms and print the sum as a new term. </p>

### Code:
```cpp
#include <iostream>
#include <conio.h>
using namespace std;

class Fibonacci
{
private:
    int termNumber;

public:
    Fibonacci(int x)
    {
        termNumber = x;
    }

    void fibonacciSeries()
    {
        int firstTerm = 0, secondTerm = 1, nextTerm;
        cout << "\nFibonacci series up to " << termNumber << " terms: ";
        for (int i = 0; i < termNumber; i++)
        {
            if (i == 0)
            {
                cout << firstTerm << "\t";
                continue;
            }
            if (i == 1)
            {
                cout << secondTerm << "\t";
                continue;
            }
            nextTerm = firstTerm + secondTerm;
            firstTerm = secondTerm;
            secondTerm = nextTerm;
            cout << nextTerm << "\t";
        }
    }
};

int main()
{
    int x;
    cout << "Enter the number of terms: ";
    cin >> x;

    Fibonacci fib(x);

    fib.fibonacciSeries();

    getch();
}

```

### Output:
![Screenshot 2024-09-29 233206](https://github.com/user-attachments/assets/3c8e72ac-e135-4038-982f-b4af5931cfce)
### Discussion and Conclusion:
<p align = "justify" >In this Experiment we created a class named Fibonacci. We took the input from the user for the number of terms and then using a for loop under the fibonacciSeries function we printed the terms of the series.</p>

____

### Experiment No: 04
<h3 align = "justify"> Name of the Experiment: To write a program in C++ to display the pattern like right angle triangle with number. <br>
Sample Output: <br>
Input number of rows: 5 <br>
1 <br>
12<br>
123<br>
1234<br>
12345.</h3>

### Theory: 
<p align = "justify" >In this problem there is a specific number of rows provided as an input from the user. But as the the number of rows increases, the number of columns also increases. This problem can be solved using the concept of nested for loop.</p>

### Code:
```cpp
#include <iostream>
#include <conio.h>
using namespace std;

int main ()
{
    int row;
    cout << "Enter number of rows: ";
    cin >> row;

    for (int i = 1; i <= row; ++i)
    {
        for (int j = 1; j <= i; ++j)
        {
            cout << j << " ";
        }
        cout << endl;
    }

    getch();
}

```

### Output:
![Screenshot 2024-09-29 235706](https://github.com/user-attachments/assets/739b10d5-6efe-4d8a-9c79-749856ecc0ca)
### Discussion and Conclusion:
<p align = "justify" >In this Experiment we took the number of rows as input from the user. Then the pattern was implemented by nested for loop. In the code a for loop was used to create new rows and the inner for loop was used to print the numbers of that row. </p>


