# Lab Report: 02
### Date of Submission: 22 September 2024
____

### Experiment No: 01
<h3 align = "justify"> Name of the Experiment: To Write a C++ program to access the private members of a class using friend class and friend function.</h3>

### Theory: 
<p align = "justify" >In C++ language, the private members of a class can not be accessed from outside the class. The private members can be accessed using friend function or friend class. Friend function or class can be declared using keyword "friend" The syntax for declaring friend function: </p>

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
<p align = "justify" >Create a class named student Student. There will be three private members of the class such as roll, name and marks. creating objects of the Student class assign value to them. Then access those values using a friend function or friend class and finally print the highest and lowest marks and print the roll of the students who got the highest and the lowest marks.</p>

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
        cout << "\n";
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


### OutPut:
![Screenshot 2024-09-09 023041](https://github.com/user-attachments/assets/c3c6cc0a-c92b-4a0d-9efe-41389c2fbffb)

### Discussion and Conclusion:
<p align = "justify" >From the experiment, we can learn to create classes and objects in C++ language. We learnt to access public the fields of a class from the main function. This concept reduces the length of our code and makes the code easy to understand.</p>


