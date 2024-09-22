# Lab Report: 02
### Date of Submission: 22 September 2024
____

### Experiment No: 01
<h3 align = "justify"> Name of the Experiment: To Write a C++ program to access the private members of a class using friend class and friend function.</h3>

### Theory: 
<p align = "justify" >In C++ language, the private members of a class can not be accessed from outside the class. The private members can be accessed using friend function or friend class. The syntax for declaring friend function: </p>

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
### Code:
```cpp
#include <iostream>
}
```
### OutPut:
![Screenshot 2024-09-09 023041](https://github.com/user-attachments/assets/c3c6cc0a-c92b-4a0d-9efe-41389c2fbffb)

### Discussion and Conclusion:
<p align = "justify" >From the experiment, we can learn to create classes and objects in C++ language. We learnt to access public the fields of a class from the main function. This concept reduces the length of our code and makes the code easy to understand.</p>


