# Extra Lab Report
### Date of Submission: 17 October 2024
____

### Experiment No: 01
<h3 align = "justify"> Name of the Experiment: Create a class called Book with attributes such as title, author, and price. Include a method
to display the book's details. Write a program that instantiates a Book object and displays
its details.</h3>

### Theory: 
<p align = "justify" >Text</p>

### Code:
```cpp
#include <iostream>
#include <string>
#include <conio.h>
using namespace std;

class Book
{
private:
    string title;
    string author;
    double price;

public:
    void setValue()
    {
        cout << "Enter Title: ";
        getline (cin, title);
        cout << "Enter Author Name: ";
        getline (cin, author);
        cout << "Enter Price: ";
        cin >> price;
    }

    void display()
    {
        cout << "\nTitle :" << title << "\nAuthor: " << author << "\nPrice: " << price << "TK" << endl;
    }
};

int main()
{
    Book book1;
    book1.setValue();
    book1.display();

    getch();
}


```

### Output:
![Screenshot 2024-10-17 180751](https://github.com/user-attachments/assets/01ce36ca-03f4-4881-9690-8d6365c750a1)
### Discussion and Conclusion:
<p align = "justify" >Text.</p>

___

### Experiment No: 02
<h3 align = "justify"> Name of the Experiment: Develop a class Student that has attributes for student ID and name. Include a method
to display the student's information. Create an instance of the Student class and print its
details.</h3>

### Theory: 
<p align = "justify" >Text</p>

### Code:
```cpp
#include <iostream>
#include <conio.h>
#include <string>
using namespace std;

class Student
{
private:
    int ID;
    string name;

public:
    Student(int i, string n)
    {
        ID = i;
        name = n;
    }
    void display()
    {
        cout << "Studet ID: " << ID << "\nName: " << name << endl;
    }
};

int main()
{
    Student s1(2210035, "Waliullah");
    s1.display();

    getch();
}


```

### Output:
![Screenshot 2024-10-17 181351](https://github.com/user-attachments/assets/e0d81102-ada3-4a46-9395-2c17807c2bdc)
### Discussion and Conclusion:
<p align = "justify" >Text.</p>

___

### Experiment No: 03
<h3 align = "justify"> Name of the Experiment: Implement a class called Calculator with methods for basic arithmetic operations
(addition, subtraction, multiplication, division). Write a program that allows the user to
perform calculations using the Calculator class.</h3>

### Theory: 
<p align = "justify" >Text</p>

### Code:
```cpp
#include <iostream>
#include <string>
#include <conio.h>
using namespace std;

class Calculator
{
private:
    float num1, num2;

public:
    void setValue1()
    {
        cout << "Enter First Number: ";
        cin >> num1;
    }
    void setValue2()
    {
        cout << "Enter Second Number: ";
        cin >> num2;
    }


    void add()
    {
        cout << "Ans = " << num1 + num2 << endl;
    }
    void subtract()
    {
        cout << "Ans = " << num1 - num2 << endl;
    }
    void multiply()
    {
        cout << "Ans = " << num1 * num2 << endl;
    }
    void divide()
    {
        cout << "Ans = " << num1 / num2 << endl;
    }

};
int main()
{
    char symbol;
    Calculator calculate;

    calculate.setValue1();

    cout << "Enter the operator(+, -, *, /): ";
    cin >> symbol;

    calculate.setValue2();
    cout << endl;

    switch (symbol)
    {
    case '+':
        calculate.add();
        break;
    case '-':
        calculate.subtract();
        break;
    case '*':
        calculate.multiply();
        break;
    case '/':
        calculate.divide();
        break;
    default :
        cout << "Invalid Operator" << endl;
    }

    getch();

}


```

### Output:
![Screenshot 2024-10-17 181508](https://github.com/user-attachments/assets/c9138cf7-e726-4936-ac33-4bc7550c921c)
### Discussion and Conclusion:
<p align = "justify" >Text.</p>

___

### Experiment No: 04
<h3 align = "justify"> Name of the Experiment: Create a Person class with attributes for name and age. Implement a method to check if
the person is an adult (18 years or older). Instantiate a Person object and check if they
are an adult.</h3>

### Theory: 
<p align = "justify" >Text</p>

### Code:
```cpp
#include <iostream>
#include <string>
#include <conio.h>
using namespace std;

class Person
{
private:
    int age;
    string name;

public:
    Person()
    {
        cout << "Enter Name: ";
        getline (cin, name);
        cout << "Enter Age: ";
        cin >> age;
    }
    bool isAdult()
    {
        if (age >= 18)
            return 1;

        return 0;
    }

    void display()
    {
        cout << "Name: " << name << "\nAge: " << age << endl;
    }
};

int main()
{
    Person person1;

    person1.display();

    if (person1.isAdult())
    {
        cout << "The person is an adult." << endl;
    }
    else
        cout << "The person is not an adult." << endl;

    getch();
}


```

### Output:
![Screenshot 2024-10-17 181637](https://github.com/user-attachments/assets/c46aab80-864b-4278-b716-f4915849f61e)
### Discussion and Conclusion:
<p align = "justify" >Text.</p>

___

### Experiment No: 05
<h3 align = "justify"> Name of the Experiment: Design a class hierarchy with a base class Employee and subclasses Manager and
Intern. Implement methods to calculate and display the salary of each type of employee.
Write a program that demonstrates the use of inheritance and method overriding.</h3>

### Theory: 
<p align = "justify" >Text</p>

### Code:
```cpp
#include <iostream>
#include <string>
#include <conio.h>
using namespace std;

class Employee
{
private:
    string name;
    string role;

public:
    Employee(string n, string r)
    {
        name = n;
        role = r;
    }

    string getName()
    {
        return name;
    }
    string getRole()
    {
        return role;
    }
    int calculateSalary()
    {
        return 0;
    }
};

class Manager : public Employee
{
private:
    int baseSalary;
    int experience;

public:
    Manager(string n, int b, int e) : Employee(n, "Manager")
    {
        baseSalary = b;
        experience = e;
    }

    int calculateSalary()
    {
        return baseSalary + (baseSalary * experience * 0.05);
    }
};

class Intern : public Employee
{
private:
    int baseSalary;
    int bonus;

public:
    Intern(string n, int b, int bo) : Employee(n, "Intern")
    {
        baseSalary = b;
        bonus = bo;
    }

    int calculateSalary()
    {
        return baseSalary + bonus;
    }
};

int  main()
{
    Manager e1("Waliullah", 35000, 4);
    Intern e2("Hamim", 15000, 2000);

    cout << "Employee Name: " << e1.getName() << "\nRole: " << e1.getRole() << "\nSalary: " << e1.calculateSalary() << " Taka" << endl;
    cout << "\nEmployee Name: " << e2.getName() << "\nRole: " << e2.getRole() << "\nSalary: " << e2.calculateSalary() << " Taka" << endl;


    getch();
}


```

### Output:
![image](https://github.com/user-attachments/assets/3756b868-8bc1-4af0-a6d9-6cf2e2bbea21)
### Discussion and Conclusion:
<p align = "justify" >Text.</p>

___

### Experiment No: 06
<h3 align = "justify"> Name of the Experiment: Implement a class called Library that manages a collection of Book objects. Include
methods to add and remove books, as well as display all available books. Write a program
to test the functionality of the Library class.</h3>

### Theory: 
<p align = "justify" >Text</p>

### Code:
```cpp
#include <iostream>
#include <string>
#include <conio.h>
using namespace std;

class Book
{
private:
    string title;
    string author;

public:
    Book() {}

    Book(string t, string a)
    {
        title = t;
        author = a;
    }

    string getTitle() const
    {
        return title;
    }

    void setTitle(string t)
    {
        title = t;
    }

    string getAuthor() const
    {
        return author;
    }

    void setAuthor(string a)
    {
        author = a;
    }
};

class Library
{
private:
    Book books[10];
    int bookCount;

public:
    Library()
    {
        bookCount = 0;
    }

    void addBook(Book book)
    {
        if (bookCount < 10)
        {
            books[bookCount] = book;
            bookCount++;
        }
        else
        {
            cout << "Library is full, cannot add more books." << endl;
        }
    }

    void removeBook(string title)
    {
        bool found = false;
        for (int i = 0; i < bookCount; i++)
        {
            if (books[i].getTitle() == title)
            {
                for (int j = i; j < bookCount - 1; j++)
                {
                    books[j] = books[j + 1];
                }
                bookCount--;
                found = true;
                break;
            }
        }
        if (!found)
        {
            cout << "Book not found." << endl;
        }
    }

    void displayBooks() const
    {
        if (bookCount == 0)
        {
            cout << "No books in the library." << endl;
        }
        else
        {
            for (int i = 0; i < bookCount; i++)
            {
                cout << books[i].getTitle() << " by " << books[i].getAuthor() << endl;
            }
        }
    }
};

int main()
{
    Library library;

    Book book1("Bangla Essays", "Kazi Najrul Islam");
    Book book2("Bangla Language", "Munie Chowdhury");
    Book book3("Matheatics", "H K Das");
    Book book4("Geography", "Mahedi Jahan");

    library.addBook(book1);
    library.addBook(book2);
    library.addBook(book3);
    library.addBook(book4);

    cout << "Books in the library:" << endl;
    library.displayBooks();

    cout << "\nRemoving 'Bangla Language' from the library." << endl;
    library.removeBook("Bangla Language");

    cout << "\nBooks in the library after removal:" << endl;
    library.displayBooks();

    getch();
}



```

### Output:
![image](https://github.com/user-attachments/assets/893f0d28-5439-49a6-b3bb-4e64d4bb2f72)
### Discussion and Conclusion:
<p align = "justify" >Text.</p>

___

### Experiment No: 07
<h3 align = "justify"> Name of the Experiment: Create a class ShoppingCart that holds a list of Product objects. Implement methods
to add items to the cart, remove items, and calculate the total price. Write a program to test
the functionality of the ShoppingCart class.</h3>

### Theory: 
<p align = "justify" >Text</p>

### Code:
```cpp
#include <iostream>
#include <string>
#include <conio.h>
using namespace std;

class ShoppingCart
{
private:
    string products[100];
    int price[100];
    int productNumber;

public:
    ShoppingCart()
    {
        productNumber = 0;
    }

    void addProduct(const string& productName, int p)
    {
        if (productNumber < 100)
        {
            products[productNumber] = productName;
            price[productNumber] = p;
            productNumber++;
        }
        else
        {
            cout << "Cart is full. Cannot add more items." << endl;
        }
    }

    void removeProduct(const string& productName)
    {
        for (int i = 0; i < productNumber; i++)
        {
            if (products[i] == productName)
            {
                for (int j = i; j < productNumber - 1; j++)
                {
                    products[j] = products[j + 1];
                    price[j] = price[j + 1];
                }
                productNumber--;
                break;
            }
        }
    }

    int total() const
    {
        int total = 0;
        for (int i = 0; i < productNumber; i++)
        {
            total = total + price[i];
        }
        return total;
    }

    void display() const
    {
        for (int i = 0; i < productNumber; i++)
        {
            cout << products[i] << " - " << price[i] << endl;
        }
    }
};

int main()
{
    ShoppingCart cart;

    cart.addProduct("Rice", 700);
    cart.addProduct("Fish", 450);
    cart.addProduct("Vegetables", 150);

    cout << "Current Items in Cart:" << endl;
    cart.display();

    int totalPrice = cart.total();
    cout << "Total price: " << totalPrice << endl;

    cart.removeProduct("Vegetables");

    cout << "\nUpdated Items in Cart after removing Vegetables:" << endl;
    cart.display();

    totalPrice = cart.total();
    cout << "Total price: " << totalPrice << endl;

    getch();
}



```

### Output:
![image](https://github.com/user-attachments/assets/4a98dd3b-ae34-4a70-9003-f72f792e5850)
### Discussion and Conclusion:
<p align = "justify" >Text.</p>

___

### Experiment No: 08
<h3 align = "justify"> Name of the Experiment: Write an abstract class called Appliance with an abstract method turnOn(). Create
subclasses WashingMachine and Refrigerator that implement this method. Write
a program that demonstrates method overriding(function overriding).</h3>

### Theory: 
<p align = "justify" >Text</p>

### Code:
```cpp
#include <iostream>
#include <string>
#include <conio.h>
using namespace std;

class Appliance
{
public:
    void virtual turnOn() = 0;
};

class WashingMachine : public Appliance
{
public:
    void turnOn() override
    {
        cout << "Washing Machine is running" << endl;
    }
};
class Refrigerator : public Appliance
{
public:
    void turnOn() override
    {
        cout << "\nRefrigerator is running" << endl;
    }
};

int main()
{
    WashingMachine machine;
    Refrigerator fridge;

    machine.turnOn();
    fridge.turnOn();

    getch();
}


```

### Output:
![image](https://github.com/user-attachments/assets/47eac48c-38a1-45bf-8590-8b5f32fe6443)
### Discussion and Conclusion:
<p align = "justify" >Text.</p>

___

### Experiment No: 09
<h3 align = "justify"> Name of the Experiment: Design a class School that manages a collection of Student objects. Implement
methods to add, remove, and search for students by ID. Write a program to test the School
class.</h3>

### Theory: 
<p align = "justify" >Text</p>

### Code:
```cpp
#include <iostream>
#include <string>
#include <conio.h>
using namespace std;

class Student
{
private:
    int id;
    string name;

public:
    void setStudent(int student_id, const string& student_name)
    {
        id = student_id;
        name = student_name;
    }

    int getID() const
    {
        return id;
    }
    string getName() const
    {
        return name;
    }

};

class School
{
private:
    Student students[1000];
    int studentNumber;

public:
    School()
    {
        studentNumber = 0;
    }

    void add_student(int id, const string& name)
    {
        if (studentNumber < 1000)
        {
            students[studentNumber].setStudent(id, name);
            studentNumber++;
            cout << "New student added to the school." << endl;
        }
        else
        {
            cout << "School is full. Cannot add more students." << endl;
        }
    }
    void rmv(int id)
    {
        for (int i = 0; i < studentNumber; i++)
        {
            if (students[i].getID() == id)
            {
                for (int j = i; j < studentNumber - 1; j++)
                {
                    students[j] = students[j + 1];
                }
                studentNumber--;
                cout << "A student has been removed from the school." << endl;
                return;
            }
        }
        cout << "Student with ID " << id << " not found." << endl;
    }

    void searchStudent(int id) const
    {
        for (int i = 0; i < studentNumber; i++)
        {
            if (students[i].getID() == id)
            {
                cout << "Student Found: ID = " << students[i].getID() << ", Name = " << students[i].getName() << endl;
                return;
            }
        }
        cout << "Student with ID " << id << " not found." << endl;
    }

    void display() const
    {

        cout << "\nList of Students:" << endl;
        for (int i = 0; i < studentNumber; i++)
        {
            cout << "ID: " << students[i].getID() << ", Name: " << students[i].getName() << endl;
        }

    }
};

int main()
{
    School mySchool;

    mySchool.add_student(1, "Hamim");
    mySchool.add_student(2, "Fuad");
    mySchool.add_student(3, "Waliullah");

    mySchool.display();

    cout << "\nSearching for student with ID 2:" << endl;
    mySchool.searchStudent(2);

    cout << "\nRemoving student with ID 2:" << endl;
    mySchool.rmv(2);

    mySchool.display();

    cout << "\nSearching for student with ID 2 after removal:" << endl;
    mySchool.searchStudent(2);

    getch();
}



```

### Output:
![image](https://github.com/user-attachments/assets/99748ddc-9c4d-4506-8708-17d573399da6)
### Discussion and Conclusion:
<p align = "justify" >Text.</p>

___

### Experiment No: 10
<h3 align = "justify"> Name of the Experiment: Text.</h3>

### Theory: 
<p align = "justify" >Text</p>

### Code:
```cpp
#include <iostream>
#include <string>
#include <conio.h>
using namespace std;

class Game
{
private:
    string state;

public:
    Game()
    {
        state = "Not Started";
    }
    void start()
    {
        if (state == "Not Started")
        {
            state = "Running";
            cout << "Game has started." << endl;
        }
        else if (state == "Paused")
        {
            state = "Running";
            cout << "Game has started." << endl;
        }
        else if (state == "Running")
        {
            cout << "Game is already running." << endl;
        }
        else if (state == "Ended")
        {
            cout << "Game has started." << endl;
        }
    }

    void pause()
    {
        if (state == "Running")
        {
            state = "Paused";
            cout << "Game is paused." << endl;
        }
        else if (state == "Paused")
        {
            cout << "Game is already paused." << endl;
        }
        else if (state == "Ended")
        {
            cout << "Game has already ended. Can't pause." << endl;
        }
        else
        {
            cout << "Game hasn't started yet." << endl;
        }
    }

    void end()
    {
        if (state == "Running" || state == "Paused")
        {
            state = "Ended";
            cout << "Game has ended." << endl;
        }
        else if (state == "Ended")
        {
            cout << "Game has already ended." << endl;
        }
        else
        {
            cout << "Game hasn't started yet." << endl;
        }
    }

    void displayStatus() const
    {
        cout << "Current status of Game: " << state << endl;
    }
};

int main()
{
    Game myGame;

    myGame.displayStatus();

    myGame.start();
    myGame.displayStatus();

    myGame.pause();
    myGame.displayStatus();

    myGame.start();
    myGame.displayStatus();

    myGame.end();
    myGame.displayStatus();

    return 0;
}



```

### Output:
![image](https://github.com/user-attachments/assets/8a09fa4b-bcf4-4a2f-9228-58a0f1a26983)
### Discussion and Conclusion:
<p align = "justify" >Text.</p>

___

### Experiment No: 11
<h3 align = "justify"> Name of the Experiment: Text.</h3>

### Theory: 
<p align = "justify" >Text</p>

### Code:
```cpp
#include <iostream>
#include <conio.h>
using namespace std;

class Person
{
private:
    string name;
    int age;
    static int personCount;

public:
    Person(string n, int a)
    {
        name = n;
        age = a;
        personCount++;
    }

    static void displayCount()
    {
        cout << "\nTotal number of persons: " << personCount << endl;
    }

    void displayInfo() const
    {
        cout << "Name: " << name << "\nAge: " << age << endl;
    }
};

int Person::personCount = 0;

int main()
{
    Person p1("Hamim", 20);
    Person p2("Waliullah", 21);
    Person p3("Nadrima", 19);
    Person p4("Fuadd", 24);

    cout << "Person 1: " << endl;
    p1.displayInfo();
    cout << "\nPerson 2: " << endl;
    p2.displayInfo();
    cout << "\nPerson 3: " << endl;
    p3.displayInfo();
    cout << "\nPerson 4: " << endl;
    p4.displayInfo();

    Person::displayCount();

    getch();
}



```

### Output:
![image](https://github.com/user-attachments/assets/b68ccba6-6f63-411a-bc54-7397586831fa)

### Discussion and Conclusion:
<p align = "justify" >Text.</p>

___

### Experiment No: 12
<h3 align = "justify"> Name of the Experiment: Text.</h3>

### Theory: 
<p align = "justify" >Text</p>

### Code:
```cpp
#include <iostream>
#include <conio.h>
using namespace std;

class Complex
{
private:
    double real;
    double imaginary;

public:
    Complex(double r, double i)
    {
        real = r;
        imaginary= i;
    }

    Complex operator + (Complex other)
    {
        return Complex(real + other.real, imaginary + other.imaginary);
    }

    Complex operator - ( Complex other)
    {
        return Complex(real - other.real, imaginary - other.imaginary);
    }

    Complex operator * ( Complex& other)
    {
        return Complex(real * other.real - imaginary * other.imaginary, real * other.imaginary + imaginary * other.real);
    }

    Complex operator / ( Complex& other)
    {
        double denominator = other.real * other.real + other.imaginary * other.imaginary;
        return Complex((real * other.real + imaginary * other.imaginary) / denominator, (imaginary * other.real - real * other.imaginary) / denominator);
    }

    void display()
    {
        if (imaginary >= 0)
            cout << real << " + " << imaginary << "i" << endl;
        else
            cout << real << " - " << -imaginary << "i" << endl;
    }
};

int main()
{
    Complex c1(13.0, 44.0);
    Complex c2(7.0, 6.0);

    Complex sum = c1 + c2;
    cout << "Sum: ";
    sum.display();

    Complex diff = c1 - c2;
    cout << "Difference: ";
    diff.display();

    Complex product = c1 * c2;
    cout << "Product: ";
    product.display();

    Complex quotient = c1 / c2;
    cout << "Quotient: ";
    quotient.display();

    getch();
}



```

### Output:
![image](https://github.com/user-attachments/assets/340f1e7a-40d9-47f9-9b0f-8f8049ba31e2)
### Discussion and Conclusion:
<p align = "justify" >Text.</p>

___

### Experiment No: 13
<h3 align = "justify"> Name of the Experiment: Text.</h3>

### Theory: 
<p align = "justify" >Text</p>

### Code:
```cpp
#include <iostream>
#include <conio.h>
using namespace std;

class Rectangle
{
private:
    double length;
    double breadth;

public:
    Rectangle(double l, double b)
    {
        length = l;
        breadth = b;
    }

    double area()
    {
        return length * breadth;
    }

    bool operator==(Rectangle other)
    {
        return area() == other.area();
    }

    bool operator>( Rectangle other)
    {
        return area() > other.area();
    }

    bool operator<( Rectangle other)
    {
        return area() < other.area();
    }
};

int main()
{
    Rectangle rect1(4.0, 5.0);
    Rectangle rect2(4.0, 10.0);

    if (rect1 == rect2)
    {
        cout << "Rectangle 1 and Rectangle 2 have equal areas." << endl;
    }

    else if (rect1 > rect2)
    {
        cout << "Rectangle 1 is larger than rectangle 2." << endl;
    }

    else if (rect1 < rect2)
    {
        cout << "Rectangle 2 is larger than rectangle 1." << endl;
    }

    getch();
}



```

### Output:
![image](https://github.com/user-attachments/assets/b2b87fa5-08d5-46ea-b065-d2ef61cab2f3)
### Discussion and Conclusion:
<p align = "justify" >Text.</p>

___
