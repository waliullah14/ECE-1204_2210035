# Lab Report: 02
### Date of Submission: 22 September 2024
____

### Experiment No: 01
<h3 align = "justify"> Name of the Experiment: To Write a C++ program to access the private attributes of a class using friend class and friend function.</h3>

### Theory: 
<p align = "justify" >In C++ language, the private members of a class can not be accessed from outside the class. The private members can be accessed using friend function or friend class. Friend function or class can be declared using keyword "friend". <br><br> The syntax for declaring friend function: </p>

```cpp
class ClassName
{
private:
  dataType variableName;
public:
  //declaration of friend function
  friend returnType functionName(ClassName& object);
};

//defining friend function
friend returnType functionName(ClassName& object)
{
  //code here
}
```
<br>
<p align = "justify" >The syntax for declaring friend class: </p>

```cpp
class ClassName
{
private:
  dataType variableName;
public:
  //declaration of friend class
  friend class ClassName2;
};

//defining friend class
class ClassName2
{
  //code here
};
```
### Description of the Problem:
<p align = "justify" >A class named Student should be created. There will be three private members of the class such as roll, name and marks. Creating objects of the Student class different values should be assigned to them. Then the values should be accessed using a friend function or friend class named Teacher and finally, the highest and lowest marks should be printed along with the the roll of the students who got the highest and the lowest marks.</p>

### Code:
```cpp
#include <iostream>
#include <string>
#include <conio.h>
using namespace std;

class Student
{
    string name;
    int roll;
    float marks;
public:
    void setInfo()
    {

        cout << "Name: " << endl;
        cin >> name;
        cout << "Roll: " << endl;
        cin >> roll;
        cout << "Marks: " << endl;
        cin >> marks;
    }

    friend class Teacher;

};

class Teacher
{
public:
    string getName(Student& a)
    {
        return a.name;
    }
    int getRoll(Student& b)
    {
        return b.roll;
    }
    float getMarks(Student& c)
    {
        return c.marks;
    }

    void display(Student& a)
    {
        cout << "Name: " << a.name << "\n" << "Roll: " << a.roll << "\n" << "Mark: " << a.marks << "\n" << endl;
    }

};

int main()
{
    int  studentNumber;
    cout << "Enter Number of student: ";
    cin >> studentNumber;
    Student student[studentNumber];
    for (int i = 0; i < studentNumber; i++)
    {
        cout << "\nStudent " << i+1 << ": " << endl;
        student[i].setInfo();
    }

    cout << "\nStudent Info:" << endl;

    for (int i = 0; i < studentNumber; i++)
    {
        Teacher show;
        show.display(student[i]);
    }

    float highestMark = 0, lowestMark = 20;
    Teacher get;
    int highestIndex, lowestIndex;

    for (int i = 0; i < studentNumber; i++)
    {
        if (highestMark < get.getMarks(student[i]))
        {
            highestMark = get.getMarks(student[i]);
        }
    }
    for (int i = 0; i < studentNumber; i++)
    {
        if (lowestMark > get.getMarks(student[i]))
        {
            lowestMark = get.getMarks(student[i]);
        }
    }

    int highestRoll,lowestROll;

    for (int i = 0; i < studentNumber; i++)
    {
        if (lowestMark == get.getMarks(student[i]))
        {
            lowestROll = get.getRoll(student[i]);
        }
    }
    for (int i = 0; i < studentNumber; i++)
    {
        if (highestMark == get.getMarks(student[i]))
        {
            highestRoll = get.getRoll(student[i]);
        }
    }

    float sum = 0;

    for (int i = 0; i < studentNumber; i++)
    {
        sum += get.getMarks(student[i]);
    }

    cout << "Highest Mark: " << highestMark << "\n" << "Roll: " << highestRoll << "\n" << endl;
    cout << "Lowest Mark: " << lowestMark << "\n" << "Roll: " << lowestROll  << "\n" << endl;
    cout << "Average Mark:" << (sum/studentNumber) << endl;

    getch();
}

```

### Output:
**Scanning Data:** <br> <br>
![Screenshot 2024-09-22 141041](https://github.com/user-attachments/assets/e7e185d4-11dc-4c3b-b1e3-02dd6a137abc)

**Printed Output:** <br> <br>
![Screenshot 2024-09-22 141344](https://github.com/user-attachments/assets/f0fd5645-cb21-4c4b-8d5b-e1c137ab1aa6)

### Discussion and Conclusion:
<p align = "justify" >From the experiment, we can learn how to access the private attributes of a class using the friend function and friend class. For using the friend function we should remember that the friend function is not a member function of any base class. So, we can not call any friend function using the object of the base class though the friend function is declared inside the base class. Similarly, though the friend class is declared inside the base class, it does not automatically inherit the attributes of the base class.</p>


