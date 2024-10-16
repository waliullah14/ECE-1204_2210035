# Extra Lab Report
### Date of Submission: 17 October 2024
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
<h3 align = "justify"> Name of the Experiment: To write a C++ program to find the third largest string in a given array of strings using OOP concept</h3>

### Theory: 
<p align = "justify" >?In this experiment we will have to find the third largest string from a string type array. To find out the string we will have to compare the string and find the desire string.</p>

### Code:
```cpp
#include <iostream>
#include <string>
#include <conio.h>
using namespace std;

class NewStringArray
{
private:
    string* strArr;
    int arrSize;
public:
    void setValue(string a[], int s)
    {
        strArr = a;
        arrSize = s;
    }

    void thirdLargest()
    {
        int largestLenght, secLength, thirdLength, index1, index2, index3;
        largestLenght = secLength = thirdLength = 0;

        for (int i = 0; i < arrSize; i++)
        {
            if (strArr[i].length() > largestLenght)
            {
                largestLenght = strArr[i].length();
                index1 = i;
            }
        }

        for (int i = 0; i < arrSize; i++)
        {
            if (strArr[i].length() >= secLength && i != index1)
            {
                secLength = strArr[i].length();
                index2 = i;
            }
        }

        for (int i = 0; i < arrSize; i++)
        {
            if (strArr[i].length() >= thirdLength && i != index1 && i != index2)
            {
                thirdLength = strArr[i].length();
                index3 = i;
            }
        }

        if (secLength == thirdLength)
        {
            cout << "Third largest string is: " << strArr[index2] << endl;
        }
        else
        {
            cout << "Third largest string is: " << strArr[index3] << endl;
        }

    }

};

int main ()
{
    int num;
    cout << "Enter the number of string in the array: ";
    cin >> num;
    string a[num];
    cout << "Enter the element of the array:" << endl;
    for (int i = 0; i < num; i++)
    {
        cin >> a[i];
    }

    NewStringArray array1;
    array1.setValue(a, num);
    array1.thirdLargest();

    getch();

}

```

### Output:
![Screenshot 2024-10-06 200437](https://github.com/user-attachments/assets/d52a6620-0deb-4748-a80d-e2d861cbb336)
### Discussion and Conclusion:
<p align = "justify" >In this experiment, we took different string as input from user. Then we found the length of each string. Then comparing the length, the third largest string was found and printed.</p>
