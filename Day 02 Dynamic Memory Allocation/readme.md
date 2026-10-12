
# 💻 Dynamic Memory Allocation in C++

Welcome to **Dynamic Memory Allocation in C++** 🎉  
This guide is made for **beginners** who want to clearly understand **how memory works in C++**, especially **Heap memory**, **pointers**, and the **new / delete keywords**.

If you ever wondered:
- ❓ What is heap memory?
- ❓ Why do we use `new` and `delete`?
- ❓ How do dynamic arrays work?

You’ll find all answers here 😊

---

## 🧠 Memory in C++ (Very Important Concept)

C++ mainly uses **two types of memory**:

### 📦 Stack Memory
- Used for **normal variables**
- Automatically destroyed when a function ends
- Fast but limited size

### 🏗️ Heap Memory
- Used for **dynamic memory**
- Created using `new`
- Must be manually freed using `delete`
- Bigger and flexible

---

## 📌 Topics Covered

- Dynamic variables
- Dynamic arrays
- Increasing dynamic array size
- Returning dynamic arrays from functions
- Memory cleanup (`delete`, `delete[]`)

---

## 🔢 Dynamic_variable.cpp — Dynamic Variable

This program shows the **difference between stack and heap variables**.

```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{
    // Normal variable (Stack memory)
    int x = 100;
    cout << x << endl;

    // Dynamic variable (Heap memory)
    int *p = new int;  // Allocate memory in heap
    *p = 10;

    cout << p << endl;   // Address
    cout << *p << endl;  // Value

    // Free heap memory
    delete p;

    return 0;
}
````

🧠 **Explanation:**

* `new int` creates memory in **heap**
* `p` stores the **address**
* `*p` accesses the value
* `delete` frees memory (VERY IMPORTANT)

---

## 📊 Dynamic_array.cpp — Dynamic Array

This program creates an array whose size is **decided at runtime**.

```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{
    int n;
    cout << "Enter array size: ";
    cin >> n;

    // Dynamic array in heap
    int *arr = new int[n];

    cout << "Enter " << n << " numbers:\n";
    for (int i = 0; i < n; i++)
    {
        cin >> arr[i];
    }

    cout << "You entered:\n";
    for (int i = 0; i < n; i++)
    {
        cout << arr[i] << " ";
    }
    cout << endl;

    // Free memory
    delete[] arr;

    return 0;
}
```

🧠 **Explanation:**

* `new int[n]` creates an array in heap
* `arr[i]` works like normal arrays
* `delete[]` is used for arrays

---

## 📈 Dynamic_array_size_increase.cpp — Increasing Array Size

C++ arrays **cannot resize automatically**, so we do it manually.

```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{
    int n;
    cout << "Enter initial size: ";
    cin >> n;

    int *arr = new int[n];

    cout << "Enter " << n << " values:\n";
    for (int i = 0; i < n; i++)
    {
        cin >> arr[i];
    }

    int newSize;
    cout << "Enter new size: ";
    cin >> newSize;

    // Step 1: Create bigger array
    int *newArr = new int[newSize];

    // Step 2: Copy old values
    for (int i = 0; i < n; i++)
    {
        newArr[i] = arr[i];
    }

    // Step 3: Delete old array
    delete[] arr;

    // Step 4: Point to new array
    arr = newArr;

    // Step 5: Fill new space
    for (int i = n; i < newSize; i++)
    {
        arr[i] = 0;
    }

    cout << "Array after resizing:\n";
    for (int i = 0; i < newSize; i++)
    {
        cout << arr[i] << " ";
    }
    cout << endl;

    delete[] arr;

    return 0;
}
```

🧠 **Key Steps to Resize Array:**

1. Create new bigger array
2. Copy old values
3. Delete old array
4. Reassign pointer

---

## 🔁 return_dynamic_array_from_function.cpp — Returning Dynamic Array

This program shows **how a function can return a dynamic array**.

```cpp
#include <bits/stdc++.h>
using namespace std;

int* createArray(int n)
{
    int *arr = new int[n];

    for (int i = 0; i < n; i++)
    {
        arr[i] = i + 1;
    }

    return arr; // Return heap memory
}

int main()
{
    int n;
    cout << "Enter size: ";
    cin >> n;

    int *result = createArray(n);

    cout << "Array from function:\n";
    for (int i = 0; i < n; i++)
    {
        cout << result[i] << " ";
    }
    cout << endl;

    delete[] result;

    return 0;
}
```

🧠 **Why this works:**

* Stack memory dies after function ends
* Heap memory **stays alive**
* Caller must delete it

---

## ⚠️ Common Mistakes to Avoid

❌ Forgetting `delete`  
❌ Using `delete` instead of `delete[]`  
❌ Accessing memory after deletion  
❌ Memory leaks

---

## ⚙️ How to Run

```bash
g++ filename.cpp -o output
./output
```

---

## 🎯 Who Should Learn This?

* Beginners learning C++
* Competitive programming students
* Data structures learners
* Anyone learning pointers

---




# Author

## **Engr. Md Monjur Bakth Mazumder**

🎓 **Secondary School Certificate (SSC) from [Shah Helal High School](https://www.shahhelalhs.edu.bd/)**

🎓 **Diploma in Computer Science and Technology from [Moulvibazar Polytechnic Institute (MPI)](https://mpi.moulvibazar.gov.bd/)**

🎓 **BSc in Computer Science & Engineering (CSE)** _(Ongoing)_ **at [Sylhet International University (SIU)](https://siu.edu.bd/)**

---

## Support the Project

If you found this repository helpful, please consider giving it a **⭐ Star**. It helps others discover the project and motivates future development.

---


## Connect with Me

### Professional Profiles

| Platform | Link |
|:---|:---|
| Portfolio | [monjurmbm404.github.io](https://monjurmbm404.github.io) |
| GitHub | [monjurmbm404](https://github.com/monjurmbm404) |
| LinkedIn | [monjurmbm404](https://www.linkedin.com/in/monjurmbm404) |
| Medium | [@monjurmbm404](https://medium.com/@monjurmbm404) |

### Competitive Programming

| Platform | Link |
|:---|:---|
| Codeforces | [monjurmbm404](https://codeforces.com/profile/monjurmbm404) |
| CodeChef | [monjurmbm404](https://www.codechef.com/users/monjurmbm404) |
| LeetCode | [monjurmbm404](https://leetcode.com/u/monjurmbm404) |
| VJudge | [monjurmbm404](https://vjudge.net/user/monjurmbm404) |

### Social Media

| Platform | Link |
|:---|:---|
| Facebook | [monjurmbm404](https://www.facebook.com/monjurmbm404) |
| X (Twitter) | [@monjurmbm404](https://x.com/monjurmbm404) |
| YouTube | [@monjurmbm404](https://youtube.com/@monjurmbm404) |

### Contact Information

| Type | Email |
|:---|:---|
| Professional | [monjurmbm404@gmail.com](mailto:monjurmbm404@gmail.com) |
