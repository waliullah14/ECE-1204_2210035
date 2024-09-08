

## Experiment No: 02
### Date of Submission: 09 September 2024
### Name of the Experiment: To complete the following code and compare the speeds of the cars.
```cpp
#include<iostream>
#include<string>
using namespace std;

class Car1{
private:
  int speed = 100;
  string name = "a";
};
class Car2{
private:
  int speed = 200;
  string name = "b";
};
class Car3{
private:
  int speed = 300;
  string name = "c"'
};
```
### Theory: 
In C++ language, different classes and objects can be created and different problems can be solved easily reducing the length of the code. For declaring a class the following syntax is followed:
```cpp
class ClassName
{
};
```
There are two types of fields in a class private and public. Private fields can not be accessed from the main function directly. To access private fields from main function we need to use a public function or a friend function within that class.
### Code:
```cpp
#include<iostream>
#include<conio.h>
#include<string>
using namespace std;

class Car1
{
private:
    int speed = 100;
    string name = "a";
public:
    int getSpeed()
    {
        return speed;
    }
    string getName()
    {
        return name;
    }
};
class Car2
{
private:
    int speed = 200;
    string name = "b";
public:
    int getSpeed()
    {
        return speed;
    }
    string getName()
    {
        return name;
    }
};
class Car3
{
private:
    int speed = 300;
    string name = "c";
public:
    int getSpeed()
    {
        return speed;
    }
    string getName()
    {
        return name;
    }
};

int main()
{
    Car1 c1;
    Car2 c2;
    Car3 c3;

//    c1.getSpeed();
//    c1.getName();
//    c2.getSpeed();
//    c2.getName();
//    c3.getSpeed();
//    c3.getName();

    if(c1.getSpeed() > c2.getSpeed() && c1.getSpeed() > c3.getSpeed())
    {
        cout << c1.getName() << " is the fastest car." << endl;
    }
    else if(c2.getSpeed() > c1.getSpeed() && c2.getSpeed() > c3.getSpeed())
    {
        cout << c2.getName() << " is the fastest car." << endl;
    }
    else if(c3.getSpeed() > c1.getSpeed() && c3.getSpeed() > c2.getSpeed())
    {
        cout << c3.getName() << " is the fastest car." << endl;
    }
    if(c1.getSpeed() < c2.getSpeed() && c1.getSpeed() < c3.getSpeed())
    {
        cout << c1.getName() << " is the slowest car." << endl;
    }
    else if(c2.getSpeed() < c1.getSpeed() && c2.getSpeed() < c3.getSpeed())
    {
        cout << c2.getName() << " is the slowest car." << endl;
    }
    else if(c3.getSpeed() < c1.getSpeed() && c3.getSpeed() < c2.getSpeed())
    {
        cout << c3.getName() << " is the slowest car." << endl;
    }

    getch();
}
```
### OutPut:
![Screenshot 2024-09-09 023127](https://github.com/user-attachments/assets/9a3ff6ce-ddfa-4dcd-9957-0a5ffaf7b082)


### Discussion and Conclusion:
From the experiment, we can learn to create classes and objects in C++ language. We learnt to access public the fields of a class from the main function. We learnt to use the getline() function to read a whole line in a string. The concept of OOP reduces the length of our code and makes the code easy to understand.

