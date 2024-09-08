## Experiment No: 01
### Date of Submission: 09 September 2024
### Name of the Experiment: Write a Java program to store and display information for ten cars, including mileage, color, model, and brand.
### Theory: 
In C++ language, different classes and objects can be created and different problems can be solved easily reducing the length of the code. For declaring class the following syntax is followed:
```cpp
class ClassName
{
};
```
### Code:
```cpp
#include <iostream>
#include <string>
#include <conio.h>
using namespace std;

class Cars
{
public:
    string brand;
    string model;
    string color;
    float mileage;

    void setValue(string a, string b, string c, float d)
    {
        brand = a;
        model = b;
        color = c;
        mileage = d;
    }

    void display()
    {
        cout << "Brand: " << brand << "\n" << "Model: " << model << "\n" << "Color: " << color << "\n" << "Mileage: " << mileage << "\n" << endl;
    }
};

int main()
{
    Cars car[10];
    car[0].setValue("Prado", "B125", "Maroon", 25);
    car[1].setValue("Honda", "CZ125", "Black", 20);
    car[2].setValue("Prado", "B125H", "Blue", 25);
    car[3].setValue("Mercedes", "M125", "Maroon", 35);
    car[4].setValue("Mahindra", "B1d25", "White", 31);
    car[5].setValue("Prado", "B12B5", "Blue", 23);
    car[6].setValue("BMW", "B125353", "Black", 25);
    car[7].setValue("Prado", "B125H", "Red", 25);
    car[8].setValue("Honda", "B127", "Yellow", 27);
    car[9].setValue("Lamborghini", "L125", "Black", 20);

    for (int i = 0; i < 10; i++)
    {
        car[i].display();
    }

    getch();
}
```
### OutPut:
![Screenshot 2024-09-09 023041](https://github.com/user-attachments/assets/c3c6cc0a-c92b-4a0d-9efe-41389c2fbffb)

### Discussion and Conclusion:
From the experiment, we can learn to create classes and objects in C++ language. We learned to access public the fields of a class from the main function. This concept reduces the length of our code and makes the code easy to understand.
