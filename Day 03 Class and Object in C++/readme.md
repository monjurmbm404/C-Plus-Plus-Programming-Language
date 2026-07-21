# 📘 Class and Object in C++

This repository explains **Class, Object, Constructor, Dynamic Object, `this` pointer, Object Returning, and Sorting** in C++ using **simple language and real examples**.

Each example is written in a **professional learning sequence**, so beginners can understand **why**, **how**, and **when** to use each concept.

---

## 🧠 What You Will Learn

- What is a **Class** and **Object**
- How to **store data inside objects**
- How to **take input (cin & getline)**
- What is a **Constructor**
- What is the **`this` pointer**
- **Dynamic objects (Heap memory)**
- Returning **object vs pointer from function**
- Why **dynamic memory is needed**
- How **sorting works** in C++

---

## 🧱 1. Basic Class and Object

📄 **File:** `class_and_object.cpp`

### 🔍 Concept

- A **class** is a blueprint.
- An **object** is a real thing created from that blueprint.
- Strings are stored using **character arrays**, so `strcpy()` is required.

### ✅ Code

```cpp
#include <bits/stdc++.h>
using namespace std;

// 1. THE BLUEPRINT
class Student
{
public:
    char name[100];
    int roll;
    double gpa;
};

int main()
{
    Student a;

    a.roll = 10;
    a.gpa = 4.50;

    char temp[100] = "Monjur";
    strcpy(a.name, temp);

    cout << a.name << " " << a.roll << " " << a.gpa << endl;
    return 0;
}
```

---

## 🧱 2. Object Input Using `cin`

📄 **File:** `class_and_object_input.cpp`

### 🔍 Concept

- Access class members using **dot (`.`) operator**
- `cin` **stops at space**, so full names are not captured

### ✅ Code

```cpp
#include <bits/stdc++.h>
using namespace std;

class Student
{
public:
    char name[100];
    int roll;
    double gpa;
};

int main()
{
    Student a1, a2;

    cin >> a1.name >> a1.roll >> a1.gpa;
    cin >> a2.name >> a2.roll >> a2.gpa;

    cout << a1.name << " " << a1.roll << " " << a1.gpa << endl;
    cout << a2.name << " " << a2.roll << " " << a2.gpa << endl;

    return 0;
}
```

---

## 🧱 3. Input with `getline()` and Buffer Fix

📄 **File:** `class_and_object_input_with_getline.cpp`

### 🔍 Concept

- `getline()` reads **full line including spaces**
- `cin.ignore()` or `getchar()` clears **input buffer**

### ✅ Code

```cpp
#include <bits/stdc++.h>
using namespace std;

class Student
{
public:
    char name[100];
    int roll;
    double gpa;
};

int main()
{
    Student a;
    cin.getline(a.name, 100);
    cin >> a.roll >> a.gpa;
    cout << a.name << " " << a.roll << " " << a.gpa << endl;

    Student b;
    cin.ignore();
    cin.getline(b.name, 100);
    cin >> b.roll >> b.gpa;
    cout << b.name << " " << b.roll << " " << b.gpa << endl;

    Student c;
    getchar();
    cin.getline(c.name, 100);
    cin >> c.roll >> c.gpa;
    cout << c.name << " " << c.roll << " " << c.gpa << endl;

    return 0;
}
```

---

## 🧱 4. Constructor (Automatic Initialization)

📄 **File:** `constructor.cpp`

### 🔍 Concept

- Constructor name = **Class name**
- Runs **automatically**
- No return type

### ✅ Code

```cpp
#include <bits/stdc++.h>
using namespace std;

class Student
{
public:
    int roll;
    int cls;
    double gpa;

    Student(int r, int c, double g)
    {
        roll = r;
        cls = c;
        gpa = g;
    }
};

int main()
{
    Student a(45, 5, 4.45);
    cout << a.roll << " " << a.cls << " " << a.gpa << endl;
    return 0;
}
```

---

## 🧱 5. Constructor with User Input

📄 **File:** `constructor_with_input.cpp`

```cpp
#include <bits/stdc++.h>
using namespace std;

class Student
{
public:
    int roll, cls;
    double gpa;

    Student(int r, int c, double g)
    {
        roll = r;
        cls = c;
        gpa = g;
    }
};

int main()
{
    int r, c;
    double g;
    cin >> r >> c >> g;

    Student a(r, c, g);
    cout << a.roll << " " << a.cls << " " << a.gpa << endl;
    return 0;
}
```

---

## 🧱 6. `this` Pointer & Arrow Operator

📄 **File:** `this_and_arrow_sign.cpp`

### 🔍 Concept

- `this` = address of current object
- `this->variable` resolves name conflict

```cpp
#include <bits/stdc++.h>
using namespace std;

class Student
{
public:
    int roll, cls;
    double gpa;

    Student(int roll, int cls, double gpa)
    {
        this->roll = roll;
        (*this).cls = cls;
        this->gpa = gpa;
    }
};

int main()
{
    Student a(45, 5, 4.45);
    cout << a.roll << " " << a.cls << " " << a.gpa << endl;
    return 0;
}
```

---

## 🧱 7. Dynamic Object (Heap Memory)

📄 **File:** `Dynamic_object.cpp`

### 🔍 Concept

- `new` → Heap memory
- Pointer required
- Use `->` operator

```cpp
Student *a = new Student(45, 5, 4.45);
cout << a->roll << " " << a->cls << " " << a->gpa << endl;
```

---

## 🧱 8. Returning Object from Function

📄 **File:** `object_return_from_function.cpp`

### 🔍 Concept

- Object is **copied**
- Safe and clean

```cpp
Student fun()
{
    Student a(45, 5, 4.45);
    return a;
}
```

---

## 🧱 9. Returning Dynamic Object (Pointer)

📄 **File:** `Dynamic_object_return_from_function.cpp`

### 🔍 Concept

- Heap memory survives function scope
- Must return pointer

```cpp
Student *fun()
{
    Student *a = new Student(45, 5, 4.45);
    return a;
}
```

---

## ⚠️ 10. Why Dynamic Object Is Needed

📄 **File:** `why_we_need_dynamic_object.cpp`

### 🔍 Concept

- Stack object dies after function ends
- Returning its address causes **undefined behavior**

❌ **Wrong**

```cpp
Student a;
return &a;
```

✅ **Correct**

```cpp
Student *a = new Student(...);
return a;
```

---

## 🔢 11. Sorting in C++

📄 **File:** `sorting.cpp`

```cpp
sort(a, a + n);                  // Ascending
sort(a, a + n, greater<int>());  // Descending
```

---

## ✅ Final Notes

- Written for **absolute beginners**
- Uses **real memory explanation**
- Perfect for **exam + interview**
- Ideal as **GitHub reference repo**

---



# Author

## **Engr. Md Monjur Bakth Mazumder**

🎓 **Secondary School Certificate (SSC) from [Shah Helal High School](https://www.shahhelalhs.edu.bd/)**

🎓 **Diploma in Computer Science and Technology from [Moulvibazar Polytechnic Institute (MPI)](https://mpi.moulvibazar.gov.bd/)**

🎓 **BSc in Computer Science & Engineering (CSE)** _(Ongoing)_ **at [Sylhet International University (SIU)](https://siu.edu.bd/)**

📧 **Email:** monjurmbm404@gmail.com

---

## ⭐ Support the Project

If you found this repository helpful, please consider giving it a **⭐ Star**. It helps others discover the project and motivates future development.

---

## 🌐 Connect with Me

| Platform       | Link                                        |
| -------------- | ------------------------------------------- |
| 💻 GitHub      | https://github.com/monjurmbm404             |
| 💼 LinkedIn    | https://linkedin.com/in/monjurmbm404        |
| 🧩 LeetCode    | https://leetcode.com/u/monjurmbm404         |
| ⚔️ Codeforces  | https://codeforces.com/profile/monjurmbm404 |
| 🍽️ CodeChef    | https://www.codechef.com/users/monjurmbm404 |
| 🏆 VJudge      | https://vjudge.net/user/monjurmbm404        |
| 📘 Facebook    | https://www.facebook.com/monjurmbm404       |
| 🐦 X (Twitter) | https://x.com/monjurmbm404                  |
| ▶️ YouTube     | https://youtube.com/@monjurmbm404           |
| ✍️ Medium      | https://medium.com/@monjurmbm404            |
