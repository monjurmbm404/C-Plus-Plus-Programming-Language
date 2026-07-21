
# 📘 String Class in C++ (Beginner to Intermediate Guide)

This repository explains the **C++ `string` class** step by step with **clear examples, real use cases, and beginner-friendly explanations**.

Unlike C-style character arrays (`char[]`), the **C++ String class is safer, smarter, and automatically manages memory**.

---

## 🧠 What You Will Learn

* What is the **String class**
* How to **create and reassign strings**
* How to **take input with spaces**
* **Element access methods**
* **String capacity & memory behavior**
* **Iterators** (professional way to traverse)
* **String modifiers** (append, erase, replace, insert)
* **StringStream** for word extraction

---

## 🧱 1. Introduction to String Class

📄 **File:** `string.cpp`

### 🔍 Concept

* `string` is a **dynamic container**
* Automatically resizes memory
* No fixed size like `char s[10]`

### ✅ Code

```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{
    string s = "monjur";
    s = "Md Monjur Bakth Mazumder";
    cout << s << endl;
    return 0;
}
```

---

## 🧱 2. Taking String Input with Spaces

📄 **File:** `string_input_with_space.cpp`

### 🔍 Concept

* `cin` stops at spaces
* `getline()` reads **entire line**
* `cin.ignore()` clears buffer

### ✅ Code

```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{
    int x;
    cin >> x;

    string s;
    cin.ignore();
    getline(cin, s);

    cout << x << endl;
    cout << s << endl;
    return 0;
}
```

---

## 🧱 3. Element Access in String

📄 **File:** `element_access.cpp`

### 🔍 Concept

Different ways to access characters in a string.

### ✅ Methods

* `s[index]`
* `s.at(index)` (safe)
* `s.front()`
* `s.back()`

### ✅ Code

```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{
    string s;
    cin >> s;

    cout << "Using []: " << s[2] << endl;
    cout << "Using at(): " << s.at(2) << endl;
    cout << "Last char: " << s.back() << endl;
    cout << "First char: " << s.front() << endl;

    return 0;
}
```

---

## 🧱 4. String Capacity & Memory

📄 **File:** `string_capacity.cpp`

### 🔍 Concept

* `size()` → actual characters
* `capacity()` → reserved memory
* `max_size()` → theoretical limit

### ✅ Code

```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{
    string s = "Md Monjur Bakth Mazumder";

    cout << "Size: " << s.size() << endl;
    cout << "Max Size: " << s.max_size() << endl;
    cout << "Capacity: " << s.capacity() << endl;

    cout << "Is Empty?: " << s.empty() << endl;

    s.resize(5);
    cout << "After resize(5): " << s << endl;

    s.clear();
    if(s.empty()) cout << "String is now empty!" << endl;

    return 0;
}
```

---

## 🧱 5. Iterators in String

📄 **File:** `string_Iterators.cpp`

### 🔍 Concept

* Iterator = pointer-like object
* Professional traversal method
* `auto` simplifies syntax

### ✅ Code

```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{
    string s = "Md Monjur Bakth Mazumder";

    cout << *s.begin() << endl;
    cout << *(s.end() - 1) << endl;

    for(int i = 0; i < s.size(); i++)
        cout << s[i] << " ";

    cout << endl;

    for(string::iterator j = s.begin(); j < s.end(); j++)
        cout << *j << " ";

    cout << endl;

    for(auto j = s.begin(); j < s.end(); j++)
        cout << *j << " ";

    return 0;
}
```

---

## 🧱 6. String Modifiers (Editing Text)

📄 **File:** `string_modifires.cpp`

### 🔍 Concept

Modify strings dynamically.

### ✅ Operations

* `append()`
* `push_back()`
* `pop_back()`
* `assign()`
* `erase()`
* `replace()`
* `insert()`

### ✅ Code

```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{
    string s = "monjur";
    string s2 = "mazumder";

    s.append(s2);
    s.push_back('A');
    s.pop_back();
    s.pop_back();

    s = "Monjur Bakth";
    s.assign("Monjur Bakth Mazumder");

    s.erase(7, 6);

    s.replace(7, 5, "Bangladesh");

    s.insert(18, "Bakth ");

    cout << s << endl;
    return 0;
}
```

---

## 🧱 7. StringStream (Word Extraction)

📄 **File:** `stringstream.cpp`

### 🔍 Concept

* Break sentence into words
* Useful for parsing input

### ✅ Code

```cpp
#include <bits/stdc++.h>
using namespace std;

int main()
{
    string s;
    getline(cin, s);

    stringstream ss(s);
    string word;

    while (ss >> word)
    {
        cout << word << endl;
    }

    return 0;
}
```

---

## 🧠 Summary Table

| Feature      | Method         |
| ------------ | -------------- |
| Length       | `size()`       |
| Empty check  | `empty()`      |
| Add text     | `append()`     |
| Remove text  | `erase()`      |
| Replace text | `replace()`    |
| Insert text  | `insert()`     |
| Access char  | `[]`, `at()`   |
| Split words  | `stringstream` |

---

## ✅ Final Notes

* Much safer than `char[]`
* Handles memory automatically
* Industry-standard C++ practice
* Perfect for **exams, interviews & real projects**

---
# String Built-in Functions in C++

This is a reference guide for commonly used string built-in functions in C++.

---

## Capacity Functions

| Function | Description |
|----------|-------------|
| `s.size()` | Returns the size (number of characters) of the string. |
| `s.max_size()` | Returns the maximum size that the string can hold. |
| `s.capacity()` | Returns the current allocated capacity of the string. |
| `s.clear()` | Clears the contents of the string. |
| `s.empty()` | Returns `true` if the string is empty, otherwise `false`. |
| `s.resize()` | Changes the size of the string. |

---

## Element Access Functions

| Function | Description |
|----------|-------------|
| `s[i]` | Access the character at the `i`-th index. |
| `s.at(i)` | Access the character at the `i`-th index with bounds checking. |
| `s.back()` | Access the last character of the string. |
| `s.front()` | Access the first character of the string. |

---

## Modifiers

| Function | Description |
|----------|-------------|
| `s +=` | Append another string. |
| `s.append()` | Append another string. |
| `s.push_back()` | Add a character to the end of the string. |
| `s.pop_back()` | Remove the last character of the string. |
| `s =` | Assign a new string. |
| `s.assign()` | Assign a new string. |
| `s.erase()` | Erase characters from the string. |
| `s.replace()` | Replace a portion of the string with another string. |
| `s.insert()` | Insert a string at a specific position. |

---

## Iterators

| Function | Description |
|----------|-------------|
| `s.begin()` | Returns an iterator to the first element of the string. |
| `s.end()` | Returns an iterator to the position after the last element of the string. |

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
