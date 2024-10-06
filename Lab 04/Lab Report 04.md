# Lab Report: 04
### Date of Submission: 06 October 2024
____

### Experiment No: 01
<h3 align = "justify"> Name of the Experiment: To write a C++ program to find the second lowest and second highest numbers in a given array using OOP concept.</h3>

### Theory: 
<p align = "justify" >In an int type array different inputs can be taken from users. Then comparing the integers among themselves the second highest and second lowest integers can be found. For comparing the values using for loop and nested for loop convenient.</p>

### Code:
```cpp
#include <iostream>
#include <conio.h>
using namespace std;

class NewArray
{
private:
    int* arr;
    int arrSize;
public:
    void setValue(int a[], int s)
    {
        arr = a;
        arrSize = s;
    }
    void sortArr()
    {
        for (int i = 0; i < arrSize - 1; i++)
        {
            for (int j = i + 1; j < arrSize; j++)
            {
                if (arr[j] <  arr[i])
                {
                    int temp = arr[j];
                    arr[j] = arr[i];
                    arr[i] = temp;
                }
            }
        }
    }

    void findNum()
    {
        int secLowest;
        int secHighest;

        for (int i = 1; i < arrSize; i++)
        {
            if (arr[0] < arr[i])
            {
                secLowest = arr[i];
                break;
            }

        }
        for (int i = 2; i < arrSize; i++)
        {
            if (arr[arrSize - 1]  > arr[arrSize - i])
            {
                secHighest = arr[arrSize - i];
                break;
            }

        }

        cout << "Second Highest Term: " << secHighest << endl;
        cout << "Second Lowest Term: " << secLowest << endl;
    }

};

int main ()
{
    int num;
    cout << "Enter array size: ";
    cin >> num;
    int a[num];
    cout << "Enter the element of the array:" << endl;
    for (int i = 0; i < num; i++)
    {
        cin >> a[i];
    }

    NewArray array1;
    array1.setValue(a, num);
    array1.sortArr();
    array1.findNum();

    getch();

}

```

### Output:
![Screenshot 2024-10-06 200526](https://github.com/user-attachments/assets/10c6cee5-608c-45d7-8954-b5c16139aa6a)
### Discussion and Conclusion:
<p align = "justify" >In this experiment we first took the elements as input from user. Then the array was sorted. After that, the second largest and second lowest was value was found and printed as output.</p>

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

