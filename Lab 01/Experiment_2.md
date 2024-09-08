
## Experiment No: 02
### Date of Submission: 09 September 2024
### Name of the Experiment: Write a Java program to display the details of a university student, including department, roll number, name, series, and age.
### Theory: 
In C++ language, different classes and objects can be created and different problems can be solved easily reducing the length of the code. For declaring class the following syntax is followed:
```cpp
class ClassName
{
};
```
Creating an object of the class we take input data for the different fields of the object using cin and getline functions.
### Code:
```cpp
#include <iostream>
#include <string>
#include <conio.h>
using namespace std;

class student
{
public:
    string dept;
    int roll;
    string name;
    int series;
    int age;

    void display()
    {
        cout << "\n" << "Name: " << name << endl;
        cout << "Roll: " << roll << endl;
        cout << "Department: " << dept << endl;
        cout << "Series: " << series << endl;
        cout << "Age: " << age << endl;
    }
};

int main()
{
    student s1;
    cout << "Enter info:\nName:";
    getline(cin, s1.name);
    cout << "Department :";
    getline (cin, s1.dept);
    cout << "ROll:";
    cin >> s1.roll;
    cout << "Series :";
    cin >> s1.series;
    cout << "Age :";
    cin >> s1.age;

    s1.display();

    getch();
}

```
### OutPut:
![Screenshot 2024-09-09 023041](https://github.com/user-attachments/assets/c3c6cc0a-c92b-4a0d-9efe-41389c2fbffb)

### Discussion and Conclusion:
From the experiment, we can learn to create classes and objects in C++ language. We learned to access public the fields of a class from the main function. This concept reduces the length of our code and makes the code easy to understand.

