---
title: COMP1011 Programming Fundamentals
date: 2023-05-10
updated: 2023-06-14
tags: [2023, Course Notes, Computer Science] 
categories: "Course Notes"
keywords:
description: The overview of course COMP1011 Programming Fundamentals.
top_img: 
comments: true
cover:
toc:
toc_number:
toc_style_simple:
copyright:
copyright_author:
copyright_author_href:
copyright_url:
copyright_info:
mathjax: true
katex:
aplayer:
highlight_shrink:
aside:
abcjs:
---


<span style = 'font-family: Times New Roman'>

> 📢 Disclaimer
> Copyright © [The Hong Kong Polytechnic University, Faculty of Engineering, Department of Computing](https://www.polyu.edu.hk/comp/)
> The lecture notes is for reference only, permission is hereby granted, free of charge, to any person obtaining a copy of this documentation file, to deal in the Page without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Page is furnished to do so.
> The authors or copyright holders are not be liable for any claim, damages or other liabillty, whether in an action of contract, tort or otherwise, arising from, out of or in connection with or the use or other dealings in the Page.



<!-- <span style="font-family: Times New Roman;">


TABLE OF CONTENT

- [Lecture 1: INTRODUCTION TO COMPUTERS AND C++](#lecture-1-introduction-to-computers-and-c)
  - [1.1 Moore's Law](#11-moores-law)
  - [1.2 Computer Organization](#12-computer-organization)
    - [1.2.1 Two major components](#121-two-major-components)
    - [1.2.2 Input/Output (I/O) Model](#122-inputoutput-io-model)
  - [1.3 Data Hierarchy](#13-data-hierarchy)
  - [1.4 Computer Languages](#14-computer-languages)
  - [1.5 C++](#15-c)
  - [1.6 Operating Systems](#16-operating-systems)
    - [1.6.1 Windows](#161-windows)
    - [1.6.2 Linux](#162-linux)
    - [1.6.3 Mac OS X](#163-mac-os-x)
- [Lecture 1: INTRODUCTION TO C++ PROGRAMMING, INPUT/OUTPUT AND OPERATORS](#lecture-1-introduction-to-c-programming-inputoutput-and-operators)
  - [2.1 Your First Program in C++](#21-your-first-program-in-c)
  - [2.2 Variables and Operators](#22-variables-and-operators)
    - [2.2.1 boolean](#221-boolean)
    - [2.2.2 constant](#222-constant)
  - [2.3 Debugging the env](#23-debugging-the-env)
  - [2.4 The std Namespace](#24-the-std-namespace)
  - [2.5 Escape sequences](#25-escape-sequences)
  - [2.6 Precedence and Arithmetic Operator](#26-precedence-and-arithmetic-operator)
  - [2.7 Equality and Relational Operators](#27-equality-and-relational-operators)
  - [2.8 Operator Precedence](#28-operator-precedence)
  - [2.9 class](#29-class)
- [Lecture 2 CONTROL STRUCTURES: SELECTION STRUCTURES](#lecture-2-control-structures-selection-structures)
  - [2.1 Algorithm](#21-algorithm)
  - [2.2 Pseudocode](#22-pseudocode)
  - [2.3 if: single-selection statement](#23-if-single-selection-statement)
  - [2.4 if-else: double-selection statement](#24-if-else-double-selection-statement)
  - [2.5 switch: multiple-selection statement](#25-switch-multiple-selection-statement)
  - [2.6 Properties of ASCII code](#26-properties-of-ascii-code)
  - [2.7 C++ keywords](#27-c-keywords)
  - [2.8 Increment and Decrement Operators](#28-increment-and-decrement-operators)
  - [2.9 Assignment Operators](#29-assignment-operators)
  - [2.91 Ternary conditional operator](#291-ternary-conditional-operator)
  - [Exercise](#exercise)
- [Lecture 3 CONTROL STRUCTURES: REPETITION STRUCTURES](#lecture-3-control-structures-repetition-structures)
  - [3.1 while: repetition statement](#31-while-repetition-statement)
  - [3.2 for: repetition statement](#32-for-repetition-statement)
  - [3.3 do...while: repetition statement](#33-dowhile-repetition-statement)
  - [3.4 Formulating Algorithms: Counter-Controlled Repetition](#34-formulating-algorithms-counter-controlled-repetition)
  - [3.5 Formulating Algorithms: Sentinel-Controlled Repetition](#35-formulating-algorithms-sentinel-controlled-repetition)
  - [3.6 Formulating Algorithms: Nested Control Statements](#36-formulating-algorithms-nested-control-statements)
    - [3.6.1 goto](#361-goto)
  - [3.7 break and continue Statements](#37-break-and-continue-statements)
    - [3.7.1 break in the inner loop](#371-break-in-the-inner-loop)
    - [3.7.2 continue in a inner loop](#372-continue-in-a-inner-loop)
- [Lecture 4 CONTROL](#lecture-4-control)
    - [4.1 Formatting Decimal Numbers](#41-formatting-decimal-numbers)
    - [4.2 Random Number Generator](#42-random-number-generator)
    - [4.3 Mod()](#43-mod)
- [Lecture 5 ARRAYS](#lecture-5-arrays)
  - [5.1 Single Dimensional Array](#51-single-dimensional-array)
    - [5.1.1 Initializing Arrays](#511-initializing-arrays)
    - [5.1.2 Compilation](#512-compilation)
    - [5.1.3 setw()](#513-setw)
  - [5.2 Multidimensional Array](#52-multidimensional-array)
- [Lecture 6 FUNCTION](#lecture-6-function)
  - [6.1 Function](#61-function)
    - [6.1.1 Functions Libraries](#611-functions-libraries)
    - [6.1.2 Function Prototype](#612-function-prototype)
    - [6.1.3 Function Signatures](#613-function-signatures)
  - [6.2 Argument Coercion](#62-argument-coercion)
  - [6.3 Passing Array to Function](#63-passing-array-to-function)
  - [6.4 Passing 2D Array to Function](#64-passing-2d-array-to-function)
- [Lecture 7 MORE ON FUNCTIONS](#lecture-7-more-on-functions)
  - [7.1 call-by-value](#71-call-by-value)
  - [7.2 call-by-reference](#72-call-by-reference)
    - [7.2.1 bubbleSort](#721-bubblesort)
  - [7.3 Scope of Variables](#73-scope-of-variables)
- [Lecture 8 MEMORY ADDRESSES AND POINTERS](#lecture-8-memory-addresses-and-pointers)
  - [8.1 Storage Classes](#81-storage-classes)
    - [8.1.1 auto](#811-auto)
    - [8.1.2 register](#812-register)
    - [8.1.3 static](#813-static)
    - [8.1.4 extern](#814-extern)
  - [8.2 string](#82-string)
  - [8.3 Array of strings](#83-array-of-strings)
  - [8.4 Pointer and array](#84-pointer-and-array)
    - [8.4..1 Usage of pointer](#841-usage-of-pointer)
    - [8.4.2 Declaring a pointer](#842-declaring-a-pointer)
    - [8.4.3 Pointer Example](#843-pointer-example)
  - [8.5 Using const with Pointers: Four ways to pass pointer to function](#85-using-const-with-pointers-four-ways-to-pass-pointer-to-function)
  - [8.6 Relationship Between Pointers and Arrays](#86-relationship-between-pointers-and-arrays)
  - [8.7 sizeof() operator in C++](#87-sizeof-operator-in-c)
    - [8.7.1 Operated in data type](#871-operated-in-data-type)
    - [8.7.2 Operated in class type](#872-operated-in-class-type)
    - [8.7.3 Operated in array type](#873-operated-in-array-type)
    - [8.7.4 Operated in pointer type](#874-operated-in-pointer-type)
    - [8.7.5 Operated in expression type](#875-operated-in-expression-type)
  - [8.8 Array of Pointers](#88-array-of-pointers)
    - [8.8.1 Array of pointers to an integer](#881-array-of-pointers-to-an-integer)
    - [8.8.2 Array of Pointer to Strings](#882-array-of-pointer-to-strings)
    - [8.8.3  Void Pointer](#883--void-pointer)
  - [8.9 C++ References](#89-c-references)
    - [8.9.1 References to non-const values](#891-references-to-non-const-values)
    - [8.9.2 References as aliases](#892-references-as-aliases)
    - [8.9.3 Properties of References](#893-properties-of-references)
- [Lecture 9: MORE ON POINTERS AND STRUCTURES](#lecture-9-more-on-pointers-and-structures)
  - [9.1 Function Parameters](#91-function-parameters)
  - [9.2 References V.S. Pointers](#92-references-vs-pointers)
  - [9.3 Function Pointer in C++](#93-function-pointer-in-c)
  - [9.4 Memory Management](#94-memory-management)
    - [9.4.1 Memory Management Operators](#941-memory-management-operators)
    - [9.4.2 Assigning a value to the newly created object](#942-assigning-a-value-to-the-newly-created-object)
    - [9.4.3 How to create a single dimensional array](#943-how-to-create-a-single-dimensional-array)
    - [9.4.4 Delete operator](#944-delete-operator)
  - [9.5 malloc() vs new in C++](#95-malloc-vs-new-in-c)
- [Lecture 10: LINKED LISTS AND SEARCHING ALGORITHMS](#lecture-10-linked-lists-and-searching-algorithms)
  - [10.1 Operations on Linkedlist](#101-operations-on-linkedlist)
    - [10.1.1 Adding a node to the beginning or the end of a list](#1011-adding-a-node-to-the-beginning-or-the-end-of-a-list)
    - [10.1.2 Searching](#1012-searching)
    - [10.1.3 Deleting](#1013-deleting)
    - [10.1.4 Inserting](#1014-inserting)
  - [10.2 Double Linkedlist](#102-double-linkedlist)
  - [10.3 Linear Search](#103-linear-search)
- [Lecture 11: RECURSION AND DATA STRUCUTRES](#lecture-11-recursion-and-data-strucutres)
  - [11.1 Recursion VS Iteration](#111-recursion-vs-iteration)
  - [11.2 Sorting Algorithms](#112-sorting-algorithms)
    - [11.1.1 Selection Sort](#1111-selection-sort)
    - [11.1.2 Insertion Sort](#1112-insertion-sort)
    - [11.1.3 Bubble Sort](#1113-bubble-sort)
- [Lecture 12: C++ OOPS CONCEPTS](#lecture-12-c-oops-concepts)
  - [12.1 Object Class](#121-object-class)
  - [12.2 Constructor](#122-constructor)
    - [12.2.1 Default Constructor](#1221-default-constructor)
    - [12.2.2 Parameterized Constructor](#1222-parameterized-constructor)
    - [12.2.3 C++ Destructor](#1223-c-destructor)
    - [12.2.4 this Pointer](#1224-this-pointer)
    - [12.2.5 C++ static](#1225-c-static)
    - [12.2.6 C++ Structs](#1226-c-structs)
    - [12.2.7 Friend function](#1227-friend-function)
  - [12.3 C++ Enumeration](#123-c-enumeration)
  - [12.4 C++ Inheritance](#124-c-inheritance)
    - [12.4.1 Types Of Inheritance](#1241-types-of-inheritance)
    - [12.4.2 C++ Single Inheritance](#1242-c-single-inheritance)
      - [12.4.2.1 Inheriting Fields](#12421-inheriting-fields)
      - [12.4.2.2 Inheriting Methods](#12422-inheriting-methods)
    - [12.4.3 Three visibility modes](#1243-three-visibility-modes)
    - [12.4.4 C++ Multilevel Inheritance](#1244-c-multilevel-inheritance)
    - [12.5.5 C++ Multiple Inheritance](#1255-c-multiple-inheritance)
      - [12.5.5.1 C++ Multiple Inheritance](#12551-c-multiple-inheritance)
      - [12.5.5.2 Single inheritance](#12552-single-inheritance)
    - [12.5.6 Hybrid Inheritance](#1256-hybrid-inheritance)
    - [12.5.7 Hierarchical Inheritance](#1257-hierarchical-inheritance)
    - [12.5.8 Aggregation](#1258-aggregation)
  - [12.6 C++ Polymorphism](#126-c-polymorphism)
  - [12.7 Abstraction](#127-abstraction)
  - [12.8 C++ STL (Standard Tag Library)](#128-c-stl-standard-tag-library)
- [Reference](#reference)
 -->


---

# Lecture 1 INTRODUCTION TO COMPUTERS AND C++


## 1.1 Moore's Law
For many decades, hardware costs have fallen rapidly. Every year or two, the capacities of computers have approximately doubled inexpensively. This remarkable trend often is called Moore’s Law,
named for the person who identified it in the 1960s, Gordon Moore, co-founder of Intel—the leading manufacturer of the processors in today’s computers and embedded systems.


## 1.2 Computer Organization

1. Computations 
2. Making logical decisions

### 1.2.1 Two major components
1. Hardware
- Various devices comprising
- computer monitor, keyboard, mouse, speaker, camera microphone, memory modules, CPU, etc.
2. Software
- Programs that run on computer, i.e., sets of instructions to command computer to perform actions and make decisions 
- Computer programs are “subset” of software

ENIAC (Electronic Numerical Integrator and Computer) was the world’s first general-purpose electronic digital computer

### 1.2.2 Input/Output (I/O) Model
1. Input: obtain information form input devices 
2. Output: takes infomation processed by computer, places infromation on output devices
3. Memory: Rapid access to information; retain information from input unit; retain processed information e.g., RAM
4. Arithmetic and logic unit (ALU): Performs arithmetic and logical operations on data
5. Central processing unit (CPU): supervises and corrdinates other sections of computer. A multi-core processor implements multiple processors on a single integrated-circuit chip—a dual-core processor has two CPUs and a quad-core processor has four CPUs. Today’s desktop computers have processors that can execute billions of instructions per second.
6. Secondary storage unit: stores information for long term storage e.g., hard disk

<center><img src = '/img/CN_COMP1011/physicalStructure.png'></center>

## 1.3 Data Hierarchy

$ \text { Bits } \rightarrow \text { Characters }\rightarrow \text { Fields } \rightarrow \text { Records } \rightarrow \text { Files } \rightarrow \text { Database } $
<center><img src = '/img/CN_COMP1011/dataHierarchy.png'></center>

## 1.4 Computer Languages
1. Machine Language
<center><img src = '/img/CN_COMP1011/ML.png'></center>

2. Assembly Language 
Require a translator (essentially a program), called assembler, to convert it to machine language

LOAD BASEPAY
ADD OVERTIMEPAY

3. High-level language
- Translator programs (compilers): convert to machine language
- Interpreter programs: directly execute high-level language programs
  
## 1.5 C++ 
1. Edit 
2. Preprocess
3. Compile 
4. Link
5. Load
6. Execute

There are several versions of the C++ standard library, so we need to know which version of the STL we are using in order to know how the corresponding stacks and queues are implemented.

1. HP STL Other versions of C++ STL are generally implemented based on HP STL, which is the first implementation of C++ STL and is open source.

2. P.J. Plauger STL is implemented by P.J. Plauger with reference to HP STL, adopted by Visual C++ compiler, and is not open source.

3. SGI STL is implemented by Silicon Graphics Computer Systems with reference to HP STL and adopted by GCC, a C++ compiler for Linux. SGI STL is open source software and the source code is highly readable.


**Top-down design model**
Extension of C 
Early 1980s: Bjarne Stroustrup (Bell Laboratories)
“Spruces up” C
Provides capabilities for object-oriented programming(OOP)
Hybrid language
C-like style
Object-oriented style

## 1.6 Operating Systems

The software that contains the core components of the operating system is called the kernel. Popular desktop operating systems include Linux, Windows and OS X (formerly called Mac OS X)—we used all three in developing this book. Popular mobile operating systems used in smartphones and tablets include Google’s Android, Apple’s iOS (for iPhone, iPad and iPod Touch devices), BlackBerry OS and Windows Phone. You can develop applications in C++ for all of the following key operating systems, including several of the latest mobile operating systems.

### 1.6.1 Windows

Windows is a proprietary operating system—it’s controlled by Microsoft exclusively.
Windows is by far the world’s most widely used desktop operating system.

### 1.6.2 Linux

Linux is an open-source operating system, which means that anyone can download the source code and modify it as they wish. Linux is a popular operating system for servers and embedded systems, and it’s also widely used on desktop computers.

### 1.6.3 Mac OS X
Apple, founded in 1976 by Steve Jobs and Steve Wozniak, quickly became a leader in personal
computing. In 1979, Jobs and several Apple employees visited Xerox PARC (Palo Alto Research Center) to learn about Xerox’s desktop computer that featured a graphical user interface (GUI). That GUI served as the inspiration for the Apple Macintosh, launched with much fanfare in a memorable Super Bowl ad in 1984.

<center><img src = '/img/CN_COMP1011/cpp.png'></center>

---

# Lecture 1.2 INTRODUCTION TO C++ PROGRAMMING, INPUT/OUTPUT AND OPERATORS

## 2.1 Your First Program in C++ 
```cpp
#include <iostream>
```
- means to add the content of the library file, filename to the source program during preparation
- < > means to find the library file in the default location

```cpp
int main(){
}
```
- main() is the name of the function
- int means that the function returns an integer value


## 2.2 Variables and Operators

<center><img src = '/img/CN_COMP1011/cin.png'></center>

EXAM:
<center><img src = '/img/CN_COMP1011/sequence.png'></center>

**Common data types**
– int – integer numbers (e.g., -3, 0, 8)
– char – characters and symbols (e.g., H, d, ?, %)
– double – floating point numbers (e.g., 3.14, 1.618) 

**Arithmetic operators**
<center><img src = '/img/CN_COMP1011/arithmetic.png'></center>

**[Example]**
```cpp
#include <iostream>
using namespace std;
int main(){
    int  a = 7;
    int  b = 3;
    double c;

    c = a / b;
    cout << c << endl;
    return 0;
}
/*
2
*/
```
> a/b = 2
> a%b = 1
> 1.0*a/b = 2.33333
> From left to right

**Operator Precedence**
– Operators in parentheses evaluated first
› Nested/embedded parentheses
– Operators in innermost pair first
– Multiplication,  division,  modulus applied next
› Operators applied from left to right – Addition,  subtraction applied last
› Operators applied from left to right

2023-1-11




### 2.2.1 boolean
› Recall that the condition checking part of control structures will result in either a true or false value 
› In C++, true is represented as a non-zero value and false as 0 in computer memory 
› Such two values can be stored in a variable of data type bool. E.g.,

```cpp
bool done = false; 
if(done) {
    cout << "Finished" << endl; }
```

› Sometimes we have to save the condition checking result
– or, the evaluation of a function will return a bool value for further processing
› Read the following program that makes use of a function to make a decision based on input
– The return value is directly used in the condition checking part of an if/else selection structure

Logical Operators
```cpp
if (!(grade == 'A')){
}
```
equivalent to
```cpp
if (grade != 'A'){
}
```

| Operator | Meaning |
| :------: | :-----: |
|    !     |   not   |
|    &&    |   and   |
|       |   or    |




› Recall that the condition checking part of control structures will result in either a true or false value 
› In C++, true is represented as a non-zero value and false as 0 in computer memory 
› Such two values can be stored in a variable of data type bool. E.g.,

```cpp
bool done = false; 
    if(done) {
    cout << "Finished" << endl; 
}
```

**[Example]**
```cpp
#include <iostream> 
using namespace std; 
bool isPutInDeanList(double g, int n) {
    if (g >= 4.0 && n >= 3) {
    return true; 
    } 
    return false;
}

int main() {
    double gpa;
    int noOfSubjects;
    cout << "What is your GPA: ";
    cin >> gpa;
    cout << "How many subjects did you take in the last semester? ";
    cin >> noOfSubjects;
    
    if (isPutInDeanList(gpa, noOfSubjects)) {
    cout << "You are put in the Dean's list." << endl;
    } else {cout << "Study Harder!" << endl;
    } 
    return 0;
}
```



### 2.2.2 constant 
We use `CAPTIAL` for constant varibles.

```cpp
const int BRANCH_COUNT = 10;
const int WINDOW_COUNT = 10;
```
or
```cpp
const int BRANCH_COUNT = 10, WINDOW_COUNT = 10;
```



```cpp
// Demonstrating how constant works #include <iostream>
using namespace std;
int main() {
const double PI = 3.14159; 
double r;
cout << "Please enter the radius: ";
cin >> r;
cout << "Area of Circle is " << PI * r * r << endl;
return 0;
}

```

```cpp
/*
A class has a list of 1 = PASS and 2 = FAIL for 10 students, 'Very good' should be printed if more than 8 students PASS
*/

#include <iostream>
using namespace std;
int main(){
    const int PASS = 1;
    const int FAIL = 2;
    // int counter = 0;
    int result;
    int numberOfPASS = 0;
    int numberOfFAIL = 0;

    for (int i = 0; i < 10; i++){
        cout << "Enter result: 1 for PASS and 2 for FAIL" << endl;
        cin >> result;
        if (result == 1){
            // counter++;
            numberOfPASS++;
        }
        else {
            // counter++;
            numberOfFAIL++;
        }
    }
    cout << "Number of PASS: " << numberOfPASS << endl;
    cout << "Number of FAIL: " << numberOfFAIL << endl;
    
    if (numberOfPASS > 8 ? cout << "Very good" << endl : cout << "Very bad" << endl)
    return 0;

}
```

Using while loop
```cpp
while (studentCounter <= 10) {
studentCounter = studentCounter + 1;
}
```


---


## 2.3 Debugging the env
<center><img src = '/img/CN_COMP1011/clang.png'></center>

If `clang` is not installed:
```shell
xcode-select --install
```
argc means argument counts 
argv means argument value

**[Example]**
`control + shift + ` will open the terminal in the VSC, 
`control + a` back to the front line
`control + e` back to the end line
`control + u` delete the front line
`control + k` delete the end line
`control + l` clear the terminal
`control + c` stop the program
`control + d` exit the terminal
  
Compile:
```shell
(base) haleyk@Hin-Chis-MacBook-Pro Cpp_Practice % clang++ helloworld/helloworld.cpp -std=c++17 # Enter the Cpp_Practice folder
(base) haleyk@Hin-Chis-MacBook-Pro Cpp_Practice % ./a.out # compiled new files
Hello C++ World from VS Code and the C++ extension! 
```

If you adjust the `program` in `launch.json` as follows,
<center><img src = '/img/CN_COMP1011/launch.png'></center>

the compiled file would be `print_args`
<center><img src = '/img/CN_COMP1011/C.png'></center>

## 2.4 The std Namespace
Namespaces in C++ are used to organize too many classes so that it can be easy to handle the application.
`namespacename::classname` is used to call the class in the namespace.

```cpp
#include <iostream>  
using namespace std;  
namespace First {    
    void sayHello() {   
        cout<<"Hello First Namespace"<<endl;          
    }    
}    
namespace Second  {    
       void sayHello() {   
           cout<<"Hello Second Namespace"<<endl;   
       }    
}   
int main()  
{  
 First::sayHello();  
 Second::sayHello();  
return 0;  
}  
/*
Hello First Namespace
Hello Second Namespace
*/
```

## 2.5 Escape sequences 

<center><img src = '/img/CN_COMP1011/L2sequence.png'></center>


## 2.6 Precedence and Arithmetic Operator

<center><img src = '/img/CN_COMP1011/arithmetic.png'></center>
<center><img src = '/img/CN_COMP1011/precedence.png'></center>

## 2.7 Equality and Relational Operators


and &&：
```cpp
if ((score > 0) && (score < 10))
	cout << "score is between 0 and 10.\n";
else 
	cout << "score is not between 0 and 10.\n";
```

or ||：
```cpp
if ((x == 1) || (x == y))
	cout << "x is 1 or x equals y.\n";
else 
	cout << "x is neither 1 nor equal to y.\n";
```

<center><img src = '/img/CN_COMP1011/L2associativity.png'></center>

> ATTENTION: 
```cpp
if (x < y < z) // incorrect meaning: x < y is 1 or 0, and 1 < z is true
if ((x < y) && (y < z)) // correct: x < y is true or false, then compare true/false with z
```


= 和 == 的注意事项：

```cpp
x == y //逻辑表达式
x = y //赋值
```

<center><img src = '/img/CN_COMP1011/L2equality.png'></center>

## 2.8 Operator Precedence

<center><img src = '/img/CN_COMP1011/L2associativity.png'></center>

<center><img src = '/img/CN_COMP1011/L2operator.png'></center>


## 2.9 class

```cpp
class GradeBook {
public:
    void displayMessage(string courseName) const {
        cout << "Welcome to the Grade Book!" << courseName << endl;
    }
};

int main() {
    string nameOfCourse;
    GradeBook myGradeBook;
    cout << "Please enter the course name: " << endl;
    cin >> nameOfCourse; //getline(cin, nameOfCourse);
    cout << endl;

    myGradeBook.displayMessage(nameOfCourse);
}

```

Private courseName attribute and public operations setCourseName, getCourseName and displayMessage.
<center><img src = '/img/CN_COMP1011/UML.png'></center>



Compilation and linking process that produces an executable application
<center><img src = '/img/CN_COMP1011/UML1.png'></center>








---



# Lecture 2 CONTROL STRUCTURES: SELECTION STRUCTURES

## 2.1 Algorithm
Input -> Processing -> Output

## 2.2 Pseudocode
Prompt user to input xxx
Calculate sum = xxx + xxx
Print sum to the screen

## 2.3 if: single-selection statement
```cpp
if ( grade >= 60 )
cout << "Passed";
```

## 2.4 if-else: double-selection statement

```cpp
#include <iostream>
using namespace std;
int main(){
	int hours;
	double grossPay, rate;
	cout << "Enter the hourly rate of pay: $"
	cin >> rate;
	cout << "Enter the number of hours worked,\n" << "rounded to a whole number of hours: ";
	cin >> hours;
	if (hours > 40) // selection 1
		grossPay = rate*40 + 1.5*rate*(hours - 40);
	else // selection 2
		grossPay = rate*hours;
	cout.setf(ios::fixed);
	cout.setf(ios::showpoint);
	cout.precision(2);	

	cout << "Hours = " << hours << endl;
	cout << “Gross pay = $” << grossPay << endl;
	return 0;
}
```

```cpp
#include <iostream>
using namespace std; 

int main(){
	int netIncome;
	double taxBill;
	double fivePercentTax, tenPercentTax;
	
	cout << "Enter net income $";
	cin >> netIncome;
	
	if (netIncome <= 15000)
		taxBill = 0;
	else if ((netIncome > 15000) && (netIncome <= 25000))
		taxBill = (0.05*(netIncome-15000));
	else // more than $25,000
	{
		fivePercentTax = 0.05*10000;
		TenPercentTax = 0.10*(netIncome-25000);
		taxBill = (fivePercentTax + TenPercentTax);
	}
	
	cout.setf(ios::fixed);
	cout.setf(ios::showpoint);
	cout.precision(2); 
	cout << "Net Income=$" << netIncome << endl
	     << "TaxBill=$" << taxBill << endl;
	
	return 0;
}
```


The `if selection statement` expects only one statement in its body. Similarly, the if and else parts of an `if…else statement` each expect only one body statement. To include several statements in the body of an `if` or in either part of an `if…else`, enclose the statements in braces `({ and })`. A set of statements contained within a pair of braces is called a compound statement or a block. We use the term “block” from this point forward.

```cpp
if ( studentGrade >= 60 )
    cout << "Passed.\n";
else
    {
    cout << "Failed.\n";
    cout << "You must take this course again.\n";
    }
``` 


## 2.5 switch: multiple-selection statement
because it selects among many different actions (or groups of actions)

```cpp
int main()
{
	char grade;
	cout << "Enter your grade:"
	cin >> grade;

	switch (grade)
	{
        case 'a': // lowercase 
		case 'A': // uppercase
			cout << "Excellent. "
		         << "You need not take the final.\n";
			break; // Terminate the switch statement
		case 'B':
			cout << "Very good. ";
			break;
		case 'C':
			cout << "Pass. ";
			break;
		case 'D':
		case 'F':
			cout << "Not good. ";
				 << "Go study. \n";
			break;
		default: // catch-all
			cout << "That is not a possible grade.\n";
	}
	return 0;
}

```
## 2.6 Properties of ASCII code 
<center><img src = '/img/CN_COMP1011/ASCII.png'></center>

• Space (32) comes before all the printable characters 
• Numbers (48 – 57) come before (less than) letters 
• Uppercase letters (65 – 90) always come before than lowercase letter (97 – 122)

```cpp
#include <iostream>
using namespace std;
int main(){
    char c;
    c = 'A'; // A 
    int i;
    i = c; // 65
    cout << "The ASCII value of " << c << " is " << i << endl; 
    return 0;
}
/*
The ASCII value of A is 65
*/
```
```cpp
#include <iostream>
using namespace std;
int main(){
    char c;
    c = 'A';
    int i;
    i = c;
    c = c + 32;
    cout << "The ASCII value of " << (int)c << " is " << i << endl; // type of c is changed from char to int
    return 0;
}
/*
The ASCII value of 97 is 65
*/
```



## 2.7 C++ keywords

<center><img src = '/img/CN_COMP1011/keywords.png'></center>



## 2.8 Increment and Decrement Operators 
Increment operator  ++ can be used instead of c += 1 
Decrement operator -- can be used instead of c -= 1

– Pre-increment
› When the operator is placed before the variable (++c or --c), the variable value is changed, then the entire expression is evaluated. 
– Post-increment
› When the operator is placed after the variable (c++ or c--), the entire expression is evaluated, then the variable value is changed.

```cpp
// Demonstrating pre-increment and post-increment operators increment.cpp
#include <iostream>
using namespace std;
int main() {
int counter1 = 10; 
int counter2 = 10;

cout << "Original counter1: " << ++counter1 << endl;
// pre-increment cout << ++counter1 << endl;
cout << "Original counter2: " << counter2++ << endl;
// post-increment cout << counter2++ << endl;
return 0;
}
/*
Original counter1: 10
11
Original counter2: 10
10
*/
```

```cpp
#include <iostream>
using namespace std;
int main(){
    int a, b, c;
    a = 5;
    c = a++;
    cout << "a = " << a << endl; // 6
    cout << "c = " << c << endl; // 5
}
```
```cpp
int main(){
    int a, b, c;
    a = 5;
    c = ++a;
    cout << "a = " << a << endl; // 6
    cout << "c = " << c << endl; // 6
}
```

```cpp
int a, b, c;
a = 10;
b = 20;
c = a++ + b;
cout << c << endl; // 30
cout << a << endl; // 11
```

```cpp
int a, b, c;
a = 10;
b = 20;
c = a++ + a++; // a++ + a++ = 10 + 11 = 21
cout << c << endl; //21
cout << a << endl; //12
```

```cpp
a = 10;

```

When the variable is not in expression,
– pre-incrementing and post-incrementing have the same effect 


<center><img src = '/img/CN_COMP1011/operatorin.png'></center>
<center><img src = '/img/CN_COMP1011/operatorde.png'></center>


## 2.9 Assignment Operators 

<center><img src = '/img/CN_COMP1011/assignmentoperator.png'></center>

Comparsion `==`
V.S.
Assignment `=`

If paycode is 4, bonus given"
```cpp
if (payCode == 4) {
    cout << "You get a bonus!" << endl;
}
```
Paycode set to 4, and the statement is ALWAYS true (since 4 is non-zero) and given in every case
```cpp
if (payCode = 4) { 
    cout << "You get a bonus!" << endl;
}
```

## 2.91 Ternary conditional operator 

> (condition ? if true then : if false then) 

```cpp
cout << (grade >= 60 ? "Passed" : "Failed");
```
equal to 
```cpp
if (grade >= 60) {
    cout << "Passed."; } 
else {
    cout << "Failed."; }
```






## Exercise

<center><img src = '/img/CN_COMP1011/Exercise424.png'></center>

---


# Lecture 3 CONTROL STRUCTURES: REPETITION STRUCTURES

## 3.1 while: repetition statement

```cpp
int product = 3;
while ( product <= 100 )
    product = 3 * product;
```

```cpp
#include <iostream>
using namespace std;
int main()
{
	int countDown;
	cout << "How many greetings do you want? ";
	cin >> countDown;
	
	while (countDown > 0) 
	{	
		cout << "Hello ";
		countDown = countDown - 1;
	}
	cout << endl;
	cout << "That's all!\n";
	return 0;
}
```


## 3.2 for: repetition statement 

> for ( initialization; loopContinuationCondition; increment )
    statement
equal to
> initialization;
while ( loopContinuationCondition )
    {
    statement
    increment;
    }

<center><img src = '/img/CN_COMP1011/forStatement.png'></center>

How it works:

<center><img src = '/img/CN_COMP1011/forStatement1.png'></center>

## 3.3 do...while: repetition statement

Similar to while structure
– Makes loop continuation test at the end, not at the beginning
– Loop body executes at least onc

> do
    statement
while ( condition );

<center><img src = '/img/CN_COMP1011/dowhile.png'></center>



**[Example]**
```cpp
#include <iostream>  
using namespace std;  
int main() {  
     int i = 1;    
          do{    
              cout<<i<<"\n";    
              i++;    
          } while (i <= 10) ;    
}  
/*
1
2
3
4
5
6
7
8
9
10
*/
```



```cpp
#include <iostream>  
using namespace std;  
int main() {  
     int i = 1;    
         do{    
              int j = 1;          
              do{    
                cout<<i<<"\n";        
                  j++;    
              } while (j <= 3) ;    
              i++;    
          } while (i <= 3) ;     
}  
/*
1 1
1 2
1 3
2 1
2 2 
2 3
3 1
3 2
3 3
?*
```

```cpp
// Demonstrating do-while Repetition Structure // An input validation example #include <iostream>
using namespace std;
int main() {
char input;
do {
cout << "Do you want to quit?" << endl; 
cin >> input;
} while (!(input == 'Y' || input == 'y' || input == 'N' || input == 'n'));

if (input == 'Y' || input == 'y') {
cout << "Bye!" << endl;
} else {
cout << "The program continues." << endl;
}
return 0;
}
```


## 3.4 Formulating Algorithms: Counter-Controlled Repetition

> 3 phases
– Initialization
› Initializes the program variables 
```cpp
int minimumNumber = 3;
double rate = 0.07, time, balance = 0.0;
```
or 
```cpp
int minimumNumber(3);
double rate(0.07), time, balance(0.0);
```
– Processing
› Input data, adjusts program variables 
– Termination
› Calculate and print the final results
› Helps break down programs for top-down refinement


```cpp
// Fig. 4.8: GradeBook.h
// Definition of class GradeBook that determines a class average.
// Member functions are defined in GradeBook.cpp
#include <string> // program uses C++ standard string class
// GradeBook class definition
class GradeBook
{
public:
    explicit GradeBook( std::string ); // initializes course name
    void setCourseName( std::string ); // set the course name
    std::string getCourseName() const; // retrieve the course name
    void displayMessage() const; // display a welcome message
    void determineClassAverage() const; // averages user-entered grades
private:
    std::string courseName; // course name for this GradeBook
}; // end class GradeBook
```

```cpp
// Fig. 4.9: GradeBook.cpp
// Member-function definitions for class GradeBook that solves the
// class average program with counter-controlled repetition.
#include <iostream>
#include "GradeBook.h" // include definition of class GradeBook
using namespace std;

// constructor initializes courseName with string supplied as argument
GradeBook::GradeBook( string name )
{
setCourseName( name ); // validate and store courseName
} // end GradeBook constructor
// function to set the course name;
// ensures that the course name has at most 25 characters
void GradeBook::setCourseName( string name )
{
if ( name.size() <= 25 ) // if name has 25 or fewer characters
courseName = name; // store the course name in the object
{ // set courseName to first 25 characters of parameter name
courseName = name.substr( 0, 25 ); // select first 25 characters
cerr << "Name \"" << name << "\" exceeds maximum length (25).\n" << "Limiting courseName to first 25 characters.\n" << endl;
} // end if...else
} // end function setCourseName
// function to retrieve the course name
string GradeBook::getCourseName() const
{
return courseName;
} // end function getCourseName
// display a welcome message to the GradeBook user
void GradeBook::displayMessage() const
{
cout << "Welcome to the grade book for\n" << getCourseName() << "!\n" << endl;
} // end function displayMessage

// determine class average based on 10 grades entered by user
{
// initialization phase
int total = 0; // sum of grades entered by user

// processing phase
while ( ) // loop 10 times
{
cout << "Enter grade: "; // prompt for input
int grade = 0; // grade value entered by user
cin >> grade; // input next grade
total = total + grade; // add grade to total
} // end while

// termination phase
int average = total / 10; // ok to mix declaration and calculation
// display total and average of grades
cout << "\nTotal of all 10 grades is " << total << endl;
cout << "Class average is " << average << endl;
} // end function determineClassAverage
```


## 3.5 Formulating Algorithms: Sentinel-Controlled Repetition





## 3.6 Formulating Algorithms: Nested Control Statements


> if (){
> }
> else if (){
> }
> else{
> }


**[Example]**
```cpp
int main ()
using namespace std;
int main(){
    string grade;
    if (grade >= 'A'){
        cout << "Excellent. "
             << "You need not take the final.\n";
    }
    else if (grade >= 'B'){
        cout << "Very good. ";
    }
    else if (grade >= 'C'){
        cout << "Pass. ";
    }
    else if (grade >= 'D'){
        cout << "Not good. ";
             << "Go study. \n";
    }
    else if (grade >= 'F'){
        cout << "Not good. ";
             << "Go study. \n";
    }
    else {
        cout << "That is not a possible grade.\n";
    }
    return 0;
}
```



### 3.6.1 goto
The C++ goto statement is also known as jump statement. It is used to transfer control to the other part of the program. It unconditionally jumps to the specified label.

It can be used to transfer control from deeply nested loop or switch case label.

```cpp
#include <iostream>  
using namespace std;  
int main()  
{  
ineligible:    
    cout<<"You are not eligible to vote!\n";    
    cout<<"Enter your age:\n";    
    int age;  
    cin>>age;  
    if (age < 18){    
        goto ineligible;    
    }    
    else    
    {    
        cout<<"You are eligible to vote!";     
    }         
}  
/*
You are not eligible to vote!
Enter your age:
16
You are not eligible to vote!
Enter your age:
7
You are not eligible to vote!
Enter your age:
22
You are eligible to vote!
*/
```

## 3.7 break and continue Statements

break Statement
The break statement, when executed in a while, for, do…while or switch statement,
causes immediate exit from that statement. Program execution continues with the next
statement.

> Immediate exit from current switch,  while, for, or do-while control structures 


```cpp
#include <iostream>  
using namespace std;  
int main() {  
      for (int i = 1; i <= 10; i++)    
          {    
              if (i == 5)    
              {    
                  break;    
              }    
        cout<<i<<"\n";    
          }    
}  
/*
1
2
3
4
*/
```
### 3.7.1 break in the inner loop

```cpp
#include <iostream>  
using namespace std;  
int main()  
{  
    for(int i=1;i<=3;i++){        
            for(int j=1;j<=3;j++){        
                if(i==2&&j==2){        
                    break;        
                        }        
                    cout<<i<<" "<<j<<"\n";             
                    }        
          }    
}  
/*
1 2
1 3
2 1
3 1
3 2
3 3
*/
```



continue Statement
The continue statement, when executed in a while, for or do…while statement, skips
the remaining statements in the body of that statement and proceeds with the next iteration
of the loop.

> Used in while,  for, or do-while control structures Used in while, for, or do-while control structures 
You will skip the number in `==`

```cpp
#include <iostream>
using namespace std;
int main(){
    for(int i=1,i<=10,i++>){
        if(i==5){
            continue;
        }
        cout<<i<<'\n';
    }
}
/*
1
2
3
4
6
7
8
9
10
*/
```

### 3.7.2 continue in a inner loop
```cpp
#include <iostream>  
using namespace std;  
int main()  
{  
 for(int i=1;i<=3;i++){        
            for(int j=1;j<=3;j++){        
             if(i==2&&j==2){        
                continue;        
                        }        
                cout<<i<<" "<<j<<"\n";                  
                    }        
            }            
}  
/*
1 1
1 2
1 3
2 1
2 3
3 1
3 2
3 3
*/
```




---
# Lecture 4 CONTROL 

### 4.1 Formatting Decimal Numbers

```cpp
#include <iomanip>
cout.setf(ios::fixed);
cout.setf(ios::showpoint);
cout.precision(2); //两位小数
```


### 4.2 Random Number Generator

| Function | Features                                                    |
| :------- | :---------------------------------------------------------- |
| rand()   | Generates an integer between 0 and RAND_MAX (usually 32767) |
| srand()  | Sets the seed for the random number generator               |

So, we need **Scaling and Shifting**
› Modulus (remainder) operator: %
– 10 % 3 is 1
– x % y falls between 0 and y – 1 
› Example
i = rand() % 6 + 1; 
– rand() % 6 generates a number between 0 and 5 (scaling)
– +1 makes the range 1 to 6 (shifting)



```cpp
#include <iostream> 
#include <time.h>
using namespace std;
int main() {
    srand(time(0)); // seed the random number generator
    unsigned int i = rand(); 
    cout << "The random number is: " << i << endl;

    i = rand(); 
    cout << "The next random number is: " << i << endl;
    return 0; 
}
/*
The random number is: 2147483648
The next random number is: 2147483648
*/
```


Multiple initialization and update actions can be separated by commas:
```cpp
for (int i = 0, j = 0; j + i <= 10; i++, j++) {
cout << 2 * j + i << endl; }
```

**[Example]**
```cpp
#include <iostream>
using namespace std;
int main(){
    int n;
    int sum = 0;
    cin >> n;

    for (int i = 0; i <= n; i++){
        sum += i*i; // sum = sum + i*i
        cout << sum << endl;
    }

    return 0;
}
/*
5
0
1
5
14
30
55
*/
```

<center><img src = '/img/CN_COMP1011/dryRun.png'></center>


### 4.3 Mod()
Modulus (remainder) operator: `%`

> rand() function: 
```cpp
unsigned int i = rand();
```
Generates an integer **between 0 and RAND_MAX (usually 32767)**, but likely we need a random number that does not
fall in this range.

We need **Scaling** and **Shifting**, where

`10 % 3` is `1`
`x % y` falls between `0 and y – 1` 

>  srand(seed);
seed is an unsigned integer
Used before `rand()` to set the seed 
Using ONCE is enough throughout the program


**[Example]**
```cpp
i = rand() % 6 + 1; 
// rand() % 6 generates a number between 0 and 5 (scaling), +1 makes the range 1 to 6 (shifting)
```

```cpp
#include <iostream> 
#include <time.h> 
using namespace std; 
int main() {
srand(time(0)); // seed the random number generator 
unsigned int i = rand(); 
cout << "The random number is: " << i << endl;
i = rand(); 
cout << "The next random number is: " << i << endl;
return 0; 
}
/*
The random number is: 304307084
The next random number is: 1330597281
*/
```




---

# Lecture 5 ARRAYS 

> data-type arrayname[array-size];

Arrays start with `[0]`
`number[5 – 2] same as number[3]`, such as `number[3] = 'A'` , where `A` would be stored in position 3 of the array, i.e., `[0,0,0,A,0,0...]`

Initialization: he value in the allocated memory location is not reset (to 0) by default.


**[Example]**

```cpp
// Initializing an array with a declaration. #include <iostream> #include <iomanip>
#include <iostream> 
#include <iomanip>
using namespace std;
int main() {
    // use initializer list to initialize array n
    int n[10] = {32, 27, 64, 18, 95, 14, 90, 70, 60, 37};
    cout << "Element" << setw(13) << "Value" << endl;
    // output each array element's value
    for (int i = 0; i < 10; i++) {
        cout << setw(7) << i << setw(13) << n[i] << endl;
    }
    return 0;
}
/*
Element        Value
      0           32
      1           27
      2           64
      3           18
      4           95
      5           14
      6           90
      7           70
      8           60
      9           37
*/
```

› Suppose we have two arrays:
const int SIZE = 5; int squares[SIZE] = {0, 1, 4, 9, 16}; int lucky_numbers[SIZE];
› We would like to copy the values from squares to lucky_numbers. How to do it?

```cpp
const int SIZE = 5;
int squares[SIZE] = {0, 1, 4, 9, 16};
int lucky_numbers[SIZE];

for (int i = 0; i < SIZE; i++) {
    lucky_numbers[i] = squares[i];
}
```

---

## 5.1 Single Dimensional Array

> › General Format 
– Declaration
data-type array-name[array-size]
› E.g., char letter[15];
– Usage
array-name[index]
› E.g., letter[3] = 'A';


```cpp
#include <iostream>  
using namespace std;  
int main()  
{  
 int arr[5] = {10, 0, 20, 0, 30};  //creating and initializing array    
        //traversing array    
        for (int i = 0; i < 5; i++)    
        {    
            cout<< arr[i] <<"\n";    
        }    
}  

/*
10
0
20
0
30
*/
```

**[Example]**
Traversal using foreach loop

```cpp
#include <iostream>
using namespace std;
int main(){
	int arr[5] = {10, 0, 20, 0, 30};
	for (int x : arr){
		cout << x << endl;
	}
}

/*
10
0
20
0
30
*/
```

### 5.1.1 Initializing Arrays

For char, set to `'\0' (called a NULL value)`, which represents all
ZEROs to be stored in the memory location for that variable 

```cpp
char c = '\0'   
cout << c << endl; // NULL
cout << (int)c << endl; // 0
```

```cpp
char arrayC[10] = {"H", "e", "l", "l", "o"};
for (int i = 0; i < 10; i++){
    cout << (int)arrayC[i] << endl;
}
cout << endl;
cout << "Finish" << endl;
return 0;
```

```cpp
    char c = '0' 
    cout << int(c) << endl; // ASCII 48
    cout << c << endl; // 0
    char c = '\0'; 
    cout << c << endl; // NULL value
    cout << int(c) << endl; // 0
    char arrayC[5] = {'\0'}
    for (int i = 0; i < 5; i++){
        cout << (int)arrayC[i] << endl;
    } // 0 0 0 0 0
```

输入9/2， 只会返回totalCandy = 4，而非4.5

```cpp
int totalCandy, numberOfPeople;
double candyPerPerson;
candyPerPerson = totalCandy/numberOfPeople;
```
输入9/2， 强制返回返回含浮数点的totalCandy = 4.5

```cpp
int totalCandy, numberOfPeople;
double candyPerPerson;
candyPerPerson = static_cast<double>(totalCandy)/numberOfPeople;
```




### 5.1.2 Compilation

For all arrays that you are currently using, you must specify the size of an array in your source code BEFORE compilation.
If the array is created DURING program execution, dynamic memory allocation is required.


```cpp
const int n = 10; int abc[n];
/* OK */

int n; cin >> n; int abc[n];
/* Wrong! */
```
### 5.1.3 setw() 

```cpp
#include <iostream>
#include <iomanip>
using namespace std;

int main(){

    int array2[10] = {31, 54, 77, 52, 93, 17, 77, 31, 44, 55};

    cout << "Element" << setw (10) << "Value" << endl; // setw() is used to set the width of the output, for example, setw(10) means the width of the output is 10

    for (int i = 0; i<10 ; i++){
        cout << setw(7) << i << setw(4) << array2[i] << endl;
    }


    return 0;
}
/*
Element     Value
      0      31
      1      54
      2      77
      3      52
      4      93
      5      17
      6      77
      7      31
      8      44
      9      55
*/
```

```cpp
#include <iostream>
#include <iomanip>
using namespace std;
int main(){
    int a[10] = {31, 54, 77, 52, 93, 17, 77, 31, 44, 55};
    int total;

    for (int i = 0; i < 10; i++){
        total += a[i];
    }

    cout << "Total of array elements: " << total << endl;

}
/*
Total of array elements: 531
*/
```




## 5.2 Multidimensional Array

<center><img src = '/img/CN_COMP1011/multidimensional.png'></center>

```cpp
int num[2][3] = {{1, 6, 7}, {9, 3, 4}};
1 6 7 
9 3 4
```
When insufficient values are given during the declaration, 0 will be assigned to empty slot(s)

```cpp
int num[2][3] = {{1, 2}, {4}};
1 2 0
4 0 0
```

```cpp
#include <iostream>  
using namespace std;  
int main()  
{  
  int test[3][3];  //declaration of 2D array 	
    test[0][0]=5;  //initialization   
    test[0][1]=10;   
    test[1][1]=15;  
    test[1][2]=20;  
    test[2][0]=30;  
    test[2][2]=10;  
    //traversal    
    for(int i = 0; i < 3; ++i)  
    {  
        for(int j = 0; j < 3; ++j)  
        {  
            cout<< test[i][j]<<" ";  
        }  
        cout<<"\n"; //new line at each row   
    }  
    return 0;  
}  
/*
5 10 0 
0 15 20 
30 0 10 
*/
```

```cpp
#include <iostream>
using namespace std;
int main(){
    int a[3][3] = {{1,2,3},{4,5,6},{7,8,9}};
    int b[2][3] = {{1,},{4,5,6}};
    int c[3][3] = {{1,2,3},{4,5,6},{7,8,9}};


    for(int i=0;i<3;i++){
        for(int j=0;j<3;j++){
            cout<<a[i][j]<<" ";
        }
        cout<<endl;
    }
cout << "--------------" << endl;

    for (int i=0; i<2; i++){ // {1,}, return 1 0 0 
        for (int j=0; j<3; j++){
            cout<<b[i][j]<<" ";
        }
        cout<<endl;
    }
cout << "--------------" << endl;

    for (int i=2; i>=0; i--){ // reverse row i = 2,1,0
        for (int j=0; j<3; j++){
            cout<<c[i][j]<<" ";
        }
        cout<<endl;
    }
    return 0;
}
/*
1 2 3
4 5 6
7 8 9
--------------
1 0 0
4 5 6
--------------
7 8 9
4 5 6
1 2 3
*/
```

**[Example]**
Declaration and initialization at same time
```cpp
#include <iostream>  
using namespace std;  
int main()  
{  
  int test[3][3] =  
    {  
        {2, 5, 5},  
        {4, 0, 3},  
        {9, 1, 8}  };  //declaration and initialization    
    //traversal    
    for(int i = 0; i < 3; ++i)  
    {  
        for(int j = 0; j < 3; ++j)  
        {  
            cout<< test[i][j]<<" ";  
        }  
        cout<<"\n"; //new line at each row   
    }  
    return 0;  
}  
/*
2 5 5 
4 0 3 
9 1 8
*/
```

```cpp
#include <iostream>

using namespace std;

void printArray(int[][3], int); 

int main() {
    int row = 2; 
    int col = 3; 
    int num[row][col] = { { 1, 2, 3 }, { 4, 5, 6 } }; // 2D array
    cout << "Values in num are:" << endl; 
    printArray(num, row);
    return 0;
}

// Function definition of printArray 
void printArray(int a[][3], int size) { // size is the number of rows so we don't specify the number in rows
    for (int i = 0; i < size; i++) {
        for (int j = 0; j < 3; j++) {
            cout << a[i][j] << ' ';
        } 
        cout << endl;
    }
}
/*
Values in num are:
1 2 3
4 5 6
*/
```



---

# Lecture 6 FUNCTION

## 6.1 Function 

> return-value-type  function-name(parameter-list){
declarations and statements }

– parameter list
› Comma separated list of arguments
– Data type needed for each argument 
› If no arguments, use void or leave blank
– return-value-type
› Data type of result returned (use void if nothing returned)
› If no data to return, no need to add this keyword, OR 
› use return;

Function arguments can be
– Constants
sqrt(4); 
– Variables
sqrt(x); 
– Expressions
sqrt(sqrt(x));
sqrt(3 – 6 * x);


<center><img src = '/img/CN_COMP1011/function.png'></center>


### 6.1.1 Functions Libraries

<center><img src = '/img/CN_COMP1011/functionLibraries.png'></center>

```cpp
#include <iostream>
#include <cmath>
using namespace std;

int math(){
	const double COST_PER-SQ_FT = 10.50; 
	double budget, area, lengthSide;
	...
	
	lengthSide = sqrt(area); //function call
	...
}
```

```cpp
#include <iostream> 
using namespace std; 
int sum(int a, int b) {
    int answer;
    answer = a + b;
    return answer; 
    } 

int main() {
    int number1, number2;
    cin >> number1 >> number2;
    cout << "The sum is " << sum(number1, number2) << endl;
    return 0; }
```

### 6.1.2 Function Prototype

Function prototypes provide a concise description of the
function at the beginning of the program
– Imagine we have a number of functions defined in a program. Function prototypes serve as a “table of contents” of the program, and it is **optional**

**[Example]**

```cpp
#include <iostream> 
using namespace std; 
void printARange(int, int); // function prototype 
void printARange(int lower, int higher) {
    if (lower > higher) {
        cout << "Wrong Inputs" << endl;
    } 
    else {
        for (int i = lower; i <= higher; i++) {
        cout << i << endl;
    } 
    
int main() {
    int number1, number2;
    cin >> number1 >> number2;
    printARange(number1, number2);
    return 0; } 
}
}
```


**[Example]**

```cpp
double totalCost(int numberPar, double pricePar); //函数声明需要分号；

int main(){
	...
	return 0;
}

double totalCost(int numberPar, double pricePar) //调用函数，不需要分号；
{
	const double TAX_RATE = 0.05;
	double subtotal;
	subtotal = pricePar * numberPar;
	return (subtotal + subtotal * TAX_RATE);
}
```

### 6.1.3 Function Signatures

There exist **NO** functions having the same signature in the same program

```cpp
double maximum(double, double, double);
```

– Same signature with different return data types is also invalid.

<center><img src = '/img/CN_COMP1011/signature.png'></center>


## 6.2 Argument Coercion

<center><img src = '/img/CN_COMP1011/argument.png'></center>

› Force arguments to be of proper type
– Converting int (4) to double (4.0) cout << sqrt(4);
› Conversion rules
– Arguments usually converted automatically
– Changing from double to int can truncate data 
› 3.4 to 3
› Mixed type goes to highest type (promotion)
– int * double


```cpp
// ArgumentCoercion.cpp
#include <iostream>
using namespace std;
int main(){
    int a = 10;
    double b = 20.1;
    cout << a << endl;
    cout << b << endl;
    cout << (int)b << endl;
    cout << (double)a << endl;
}
/*
10
20.1
20
10
*/
```


## 6.3 Passing Array to Function

**[Example]**
Print array elements in arr1 and arr2 into function

```cpp
#include <iostream>  
using namespace std;  
void printArray(int arr[5]);  
int main()  
{  
    int arr1[5] = { 10, 20, 30, 40, 50 };    
    int arr2[5] = { 5, 15, 25, 35, 45 };    
    printArray(arr1); //passing array to function    
    printArray(arr2);  
}  
void printArray(int arr[5])  
{  
    cout << "Printing array elements:"<< endl;  
    for (int i = 0; i < 5; i++)  
    {  
    cout<<arr[i]<<"\n";    
    }  
}  
/*
Printing array elements: 
10
20
30
40
50                                                          
Printing array elements:  
5
15
25
35
45                                                            
*/
```

**[Example]**
Print minimum number
```cpp
#include <iostream>  
using namespace std;  
void  printMin(int arr[5]);  
int main()  
{  
	int arr1[5] = { 30, 10, 20, 40, 50 };    
	int arr2[5] = { 5, 15, 25, 35, 45 };    
    printMin(arr1);//passing array to function    
    printMin(arr2);  
}  
void  printMin(int arr[5])  
{  
    int min = arr[0];    
        for (int i = 0; i > 5; i++)    
        {    
            if (min > arr[i])    
            {    
                min = arr[i];    
            }    
        }    
        cout<< "Minimum element is: "<< min <<"\n";    
}  
/*
Minimum element is: 10                                                                
Minimum element is:  5  
*/
```

**[Example]**
Print maximum number
```cpp
#include <iostream>  
using namespace std;  
void  printMax(int arr[5]);  
int main()  
{  
        int arr1[5] = { 25, 10, 54, 15, 40 };    
        int arr2[5] = { 12, 23, 44, 67, 54 };    
        printMax(arr1); //Passing array to function  
        printMax(arr2);   
}  
void  printMax(int arr[5])  
{  
    int max = arr[0];    
        for (int i = 0; i < 5; i++)    
        {    
            if (max < arr[i])    
            {    
                max = arr[i];    
            }    
        }    
        cout<< "Maximum element is: "<< max <<"\n";    
}  
/*
Maximum element is: 54
Maximum element is: 67
*/
```

## 6.4 Passing 2D Array to Function

```cpp
#include <iostream>
using namespace std;
void printArray(int[][3], int);
int main() {
int row = 2; int col = 3; 
int num[row][col] = { { 1, 2, 3 }, { 4, 5, 6 } };
cout << "Values in num are:" << endl; 
printArray(num, 2);
return 0;
}

// function definition of printArray 
void printArray(int a[][3], int size) {
for (int i = 0; i < size; i++) {
for (int j = 0; j < 3; j++) {
cout << a[i][j] << ' ';
} cout << endl;
}
}
```



---




# Lecture 7 MORE ON FUNCTIONS 

## 7.1 call-by-value

In call by value, original value is not modified.

In call by value, value being passed to the function is locally stored by the function parameter in stack memory location. **If you change the value of function parameter, it is changed for the current function only**. It will not change the value of variable inside the caller method such as main().

> return-value-type function-name(parameter-list){
declarations and statements }

Args: 
return-value-type: use void if nothing returned 
parameter-list: use void or leave blank

**[Example]**
```cpp
#include <iostream>  
using namespace std;  
void change(int data);  
int main(){  
    int data = 3;  
    change(data);  
    cout << "Value of the data is: " << data<< endl;  
    return 0;
}  

void change(int data){  
data = 5;}  
/*
Value of the data is: 3
*/
```

**[Example]**


```cpp
#include <iostream> 
using namespace std;
    int sum(int a, int b) {
    int answer; // An illustration of call-by-value only 
    answer = a + b; // Meaningless regarding the aim of this function
    a = 100;
    b = 60;
    return answer;
}
int main() {
    int number1, number2; 
    cin >> number1 >> number2;  // Suppose the input are 10 and 20
    cout << "number1 is " << number1 << endl; 
    cout << "number2 is " << number2 << endl; 
    cout << "The sum is " << sum(number1, number2) << endl; 
    cout << "number1 is " << number1 << endl; 
    cout << "number2 is " << number2 << endl;
    return 0;
}
/*
number1 is 10
number2 is 20
The sum is 30
number1 is 10
number2 is 20
*/
```

<center><img src = '/img/CN_COMP1011/callByValue.png'></center>

<center><img src = '/img/CN_COMP1011/callbyvalue1.png'></center>

## 7.2 call-by-reference

第一种代入机制为传值调用（call-by-value）：实参在函数定义中形参位置“代入“
第二种代入机制为传引用函数（call-by-reference）：进行参数”替换”，更改变量的值，类型以符号&标记

In call by reference, original value is modified because we pass reference (address).

Here, address of the value is passed in the function, so actual and formal arguments **share the same address space**. Hence, **value changed inside the function, is reflected inside as well as outside the function.**

Note: To understand the call by reference, you must have the basic knowledge of pointers.


Alias for argument in function call 
Use `&` after data type
– Better to type it close to the variable name
int sum(int &a, int &b) {…}
Prototype
int sum(int&, int&);


```cpp
#include <iostream> 
using namespace std;
    int sum(int& a, int& b) {
    int answer; 
    answer = a + b; // An illustration of call-by-reference only 
    // Meaningless regarding the aim of this function 
    a = 100; 
    b = 60; 
    return answer;
    }
int main() {
    int number1, number2; 
    cin >> number1 >> number2;  // Suppose the input are 10 and 20
    cout << "number1 is " << number1 << endl; 
    cout << "number2 is " << number2 << endl; 
    cout << "The sum is " << sum(number1, number2) << endl; // The value of number1 and number2 is changed
    cout << "number1 is " << number1 << endl; // The value of number1 is changed
    cout << "number2 is " << number2 << endl; // The value of number2 is changed
    return 0;
}
/*
number1 is 10
number2 is 20
The sum is 30
number1 is 100
number2 is 60
*/
```

<center><img src = '/img/CN_COMP1011/callByReference.png'></center>

<center><img src = '/img/CN_COMP1011/callbyreference1.png'></center>


### 7.2.1 bubbleSort


```cpp
void swapNums(int &x, int &y) {
    int z = x;
    x = y;
    y = z;
}

int main() {
    int firstNum = 10;
    int secondNum = 20;

    cout << "Before swap: " << "\n";
    cout << firstNum << secondNum << "\n";

    // Call the function, which will change the values of firstNum and secondNum
    swapNums(firstNum, secondNum);

    cout << "After swap: " << "\n";
    cout << firstNum << secondNum << "\n";

    return 0;
}
/*
Before swap:
1020
After swap:
2010
*/
```

```cpp
#include<iostream>  
using namespace std;    
void swap(int *x, int *y)  
{  
    int swap;  
    swap=*x;  
    *x=*y;  
    *y=swap;  
}  
int main()   
{    
    int x=500, y=100;    
    swap(&x, &y);  // passing value to function  
    cout<<"Value of x is: "<<x<<endl;  
    cout<<"Value of y is: "<<y<<endl;  
    return 0;  
}    
/*
Value of x is: 100
Value of y is: 500 
*/
```



| No. | Call by value                                                            | Call by reference                                                       |
| --- | ------------------------------------------------------------------------ | ----------------------------------------------------------------------- |
| 1   | A copy of value is passed to the function                                | An address of value is passed to the function                           |
| 2   | Changes made inside the function is not reflected on other functions     | Changes made inside the function is reflected outside the function also |
| 3   | Actual and formal arguments will be created in different memory location | Actual and formal arguments will be created in same memory location     |




```cpp
#include <iostream>
using namespace std;
int main(){
    int arr[5] = {5, 4, 3, 2, 1};
    int temp;
    for(int i = 0; i < 5; i++){
        bool completed = true; // if no swap is done, then the array is sorted
        for(int j = 0; j < 5; j++){
            if(arr[j] > arr[j+1]){
                completed = false; // if swap is done, then the array is not sorted
                temp = arr[j];
                arr[j] = arr[j+1];
                arr[j+1] = temp;
            }
        }
        if(completed){ // if no swap is done, then the array is sorted
            break;
        }
    }
    for(int i = 0; i < 5; i++){
        cout << arr[i] << " ";
    }
    return 0;
}
/*
1 2 3 4 5
*/
```


---

形参和实参的区别：


1/ 值传递（call-by-value）
实参是变量，表达式等值
在值传递过程中，实参和形参位于内存中*两个不同的地址*中，实参先自己复制一次拷贝，再把拷贝复制给形参。所以，在值传递过程中，形参的变化不会对实参有任何的影响
z是实参，x是形参，x变z不变

```cpp
find（int x）{
}
y = find(z)；
```


2/ 地址传递/引用传递（call-by-reference）
实参是指针
在函数调用的时候，实参传递给你的是*指针地址*，地址一样也就意味着实参和形参是一样的，当你的形参发生改变时，实参也会发生改变
z是实参，x是形参。z随x而改变

```cpp
find（int &x）{
}
y = find(z)；
```

3/ const引用传递
与值传递不一样的是在值传递中要进行两次拷贝，const的出现只需拷贝一次就够了，节省内存
z是实参，x是形参。z不随x而改变。
```cpp
find（const int &x）{
}
y = find(z)；
```


## 7.3 Scope of Variables


Scope rules of Variables 
› File scope
– Declared outside all functions, known in all functions 
– a.k.a. global variables
› Function scope
– Can only be referenced inside the function being contained 
– E.g., Local variables and function parameters
› Block scope
– Begins at declaration after an opening brace { and ends at the corresponding ending brace }
– Can only be referenced in this range – static variables still have block scope



| Scope                 | Functions                                                                                                                     |
| --------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| Global/ File scope    | Variables declared outside all functions                                                                                      |
| Local/ Function scope | Variables declared inside a function                                                                                          |
| Block                 | Variables declared inside a block `{ and ends at the corresponding ending brace }`; `static` variables still have block scope |

**[Example]**

```cpp
#include <iostream>
using namespace std; 
int num = 123;  // global variable
void testingLocal() {
int num = 50;  // local variable in testingLocal() 
cout << "num in testingLocal() is " << num << endl;
}
int main() {
cout << "num here is global variable: " << num << endl; 
int num = 888;  // local variable in main() 
cout << "num in main() is " << num << endl;
{
int num = 246;  // local variable in a block in main() 
cout << "num in a block within main() is " << num << endl;
}
cout << "num in main() is " << num << endl; 
testingLocal();
return 0;
}
/*
num in testingLocal() is 50
num here is global variable: 123
num in main() is 888
num in a block within main() is 246
num in main() is 888
*/
```

---

# Lecture 8 MEMORY ADDRESSES AND POINTERS


## 8.1 Storage Classes

Storage class is used to define the lifetime and visibility of a variable and/or function within a C++ program.

Lifetime refers to the period during which the variable remains active and visibility refers to the module of a program in which the variable is accessible.

There are five types of storage classes, which can be used in a C++ program

| Storage Class | Keyword  | Lifetime                     | Visibility | Initial Value |
| ------------- | -------- | ---------------------------- | ---------- | ------------- |
| Automatic     | auto     | Function block               | Local      | Garbage       |
| Register      | register | Function block               | Local      | Garbage       |
| Static        | static   | Program block/ Whole Program | Local      | 0             |
| External      | extern   | Program block/ Whole Program | Global     | Garbage       |
| Mutable       | mutable  | Class block                  | Local      | Garbage       |



### 8.1.1 auto
It is the default storage class for all local variables. The `auto` keyword is applied to all local variables automatically.

```cpp
{   
auto int y;  
float y = 3.45;  
}  
```
The above example defines two variables with a same storage class, auto can only be used within functions.


### 8.1.2 register
It is used to define local variables that should be stored in a `register` instead of RAM. This means that the variable has a maximum size equal to the register size (usually one word) and can't have the unary `'&'` operator applied to it (as it does not have a memory location).

```cpp
register int counter=0;    
```

### 8.1.3 static
The `static` variable is initialized only once and exists till the end of a program. It retains its value between multiple functions call.

The static variable has the default value 0 which is provided by compiler.

**[Example]**
```cpp
#include <iostream>  
using namespace std;  
void func() {    
   static int i=0; //static variable    
   int j=0; //local variable    
   i++;    
   j++;    
   cout<<"i=" << i<<" and j=" <<j<<endl;    
}    
int main()  
{  
    func();    
    func();    
    func();    
}  
/*
i= 1 and j= 1
i= 2 and j= 1
i= 3 and j= 1
/*
```

```cpp
#include <iostream>
using namespace std;
void testingStaticVariable() {
// initialize only in the first call 
static int num = 0; cout << num++ << endl;
}
int main() {
testingStaticVariable(); 
testingStaticVariable(); 
testingStaticVariable();
return 0;
};
/*
0
1
2
*/
```


### 8.1.4 extern
The `extern` storage class is used to give a reference of a global variable that is visible to ALL the program files. When you have multiple files and you define a global variable or function, which will be used in other files also, then extern will be used in another file to provide the reference of defined variable or function.

```cpp
extern int counter = 0;  
```

## 8.2 string 
C++缺少原生数据类型，无法直接操作字符串，需要使用string类
In C++, string is an object of `std::string` class that represents sequence of characters. We can perform many operations on strings such as concatenation, comparison, conversion etc.

<cstring> library


› cin.getline
– Read line of text
– cin.getline(array, size, delimiter);
– Copies input into specified array until either
› the input size is reached › delimiter character is countered
› Example
char sentence[80]; cin.getline(sentence, 80, '\n');
› Only at most 79 characters are to be read from keyboard
– The reason why only at most 79 characters are to be read from the keyboard in the example given is that the last character in the sentence array must be reserved for the null character ('\0'), which marks the end of the string. The sentence array has a size of 80, which means it can store up to 79 characters plus the null character. Therefore, the getline() function is specified to read at most 79 characters from the keyboard to ensure that there is enough space for the null character.



```cpp
#include <iostream>
#include <string>
using namespace std;

int main(){
	string middleName, petName;
	string alterEgoName;
	cout << "Enter your middle name and the name of your pet.\n";
	cin >> middleName;
	cin >> petName;
	
	alterEgoName = petName + ' ' + middleName;
	
	cout << "The name of your alter ego is ";
	cout << alterEgoName << "." << endl;
	 
	return 0;
}
```

**[Example]**
```cpp
#include <iostream>  
using namespace std;  
int main( ) {  
    string s1 = "Hello";    
        char ch[] = { 'C', '+', '+'};    
        string s2 = string(ch);    
        cout<<s1<<endl;    
        cout<<s2<<endl;    
}  
/*
Hello
C++
*/
```
<center><img src = '/img/CN_COMP1011/string.png'></center>

**[Example]**
String compare:
```cpp
#include <iostream>  
#include <cstring>  // for strcmp
using namespace std;  
int main ()  
{  
  char key[] = "mango";  // key to be guessed
  char buffer[50];  // buffer for user input
  do {  
    cout<<"What is my favourite fruit? ";  
    cin>>buffer;  // read user input into buffer
  } while (strcmp (key,buffer) != 0);  // compare strings
    cout<<"Answer is correct!!"<<endl;  
  return 0;  
}  
/*
What is my favourite fruit? apple
What is my favourite fruit? banana
What is my favourite fruit? mango
Answer is correct!!
*/
```

**[Example]**
String concat:
```cpp
#include <iostream>  
#include <cstring>  
using namespace std;  
int main()  
{  
    char key[25], buffer[25];  
    cout << "Enter the key string: ";  
    cin.getline(key, 25);  
    cout << "Enter the buffer string: ";  
    cin.getline(buffer, 25);  
    strcat(key, buffer);   
    cout << "Key = " << key << endl;  
    cout << "Buffer = " << buffer<<endl;  
    return 0;  
}  
/*
Enter the key string: Welcome to
Enter the buffer string:  C++ Programming.
Key = Welcome to C++ Programming.
Buffer =  C++ Programming.
*/
```

**[Example]**
String copy:
```cpp
#include <iostream>  
#include <cstring>  
using namespace std;  
int main()  
{  
    char key[25], buffer[25];  
    cout << "Enter the key string: ";  
    cin.getline(key, 25);  
    strcpy(buffer, key);  
    cout << "Key = "<< key << endl;  
    cout << "Buffer = "<< buffer<<endl;  
    return 0;  
}  
/*
Enter the key string: C++ Tutorial
Key = C++ Tutorial
Buffer = C++ Tutorial
*/
```


**[Example]**
```cpp
#include <iostream>  
#include <cstring>  
using namespace std;  
int main()  
{  
    char ary[] = "Welcome to C++ Programming";  
    cout << "Length of String = " << strlen(ary)<<endl;  
    return 0;  
}  
/*
Length of String = 27
*/
```

**[Example]**
```cpp
#include <iostream> 
#include <iomanip> 
#include <cstring>
using namespace std;
int main() {
char s1[] = "Happy New Year"; 
char s2[] = "Happy New Year"; 
char s3[] = "Happy Holidays";
cout << "s1 = " << s1 << endl; 
cout << "s2 = " << s2 << endl; 
cout << "s3 = " << s3 << endl << endl;
cout << "strcmp(s1, s2) = " << setw(2) << strcmp(s1, s2) << endl; 
cout << "strcmp(s1, s3) = " << setw(2) << strcmp(s1, s3) << endl; 
cout << "strcmp(s3, s1) = " << setw(2) << strcmp(s3, s1) << endl << endl;
cout << "strncmp(s1, s2, 6) = " << setw(2) << strncmp(s1, s2, 6) << endl; 
cout << "strncmp(s1, s3, 7) = " << setw(2) << strncmp(s1, s3, 7) << endl; 
cout << "strncmp(s3, s1, 7) = " << setw(2) << strncmp(s3, s1, 7) << endl;
return 0;
}

/*
s1 = Happy New Year
s2 = Happy New Year
s3 = Happy Holidays

strcmp(s1, s2) = 0
strcmp(s1, s3) = 1
strcmp(s3, s1) = -1

strncmp(s1, s2, 6) = 0
strncmp(s1, s3, 7) = 1
strncmp(s3, s1, 7) = -1

In the first comparison strcmp(s1, s2), both strings are identical, so the result is 0.

In the second comparison strcmp(s1, s3), the strings differ starting from the seventh character ('N' vs 'H'), so the result is 1. 78 VS 72

In the third comparison strcmp(s3, s1), the strings differ starting from the seventh character ('H' vs 'N'), so the result is -1.

Similarly, the strncmp function compares at most the first n characters of two null-terminated strings lexicographically. In the first comparison strncmp(s1, s2, 6), the first six characters of both strings are identical, so the result is 0. In the second comparison strncmp(s1, s3, 7), the first seven characters of both strings are identical, so the result is 1. In the third comparison strncmp(s3, s1, 7), the first seven characters of both strings are different ("Happy H" vs "Happy N"), so the result is -1.
*/
```


```cpp
#include <iostream> 
#include <cstring>
using namespace std;
int main() {
char string1[] = "abcdefghijklmnopqrstuvwxyz"; 
char string2[] = "four"; char string3[] = "Boston";
cout << "The length of \"" << string1; 
cout << "\" is " << strlen(string1) << endl; 
cout << "The length of \"" << string2; 
cout << "\" is " << strlen(string2) << endl; 
cout << "The length of \"" << string3; 
cout << "\" is " << strlen(string3) << endl;
return 0; 
}
/*
The length of "abcdefghijklmnopqrstuvwxyz" is 26 
The length of "four" is 4 
The length of "Boston" is 6
*/
```



<center><img src = '/img/CN_COMP1011/pointers.png'></center>

|       Symbol       |         Name         |             Description             |
| :----------------: | :------------------: | :---------------------------------: |
| & (ampersand sign) |   Address operator   | Determine the address of a variable |
| ∗ (asterisk sign)  | Indirection operator |   Access the value of an address    |


## 8.3 Array of strings

cin.fail() returns true when a format error occurs
cin.clear() restore the state from fail to not fail
cin.peek() check the next character in the stream buffer that has nit be extracted yet
cin.ignore() discard the next character in the stream buffer if it is not a ‘\n’
cin.ignore() discard the next n characters in the stream buffer until delimiter is found; delimiter is also discarded

<center><img src = '/img/CN_COMP1011/arrayOfStrings.png'></center>

```cpp
#include <iostream> 
#include <cstring>
using namespace std;
int main() {
// List of 5 names and each has a maximum 10 characters 
char nameList[5][11];
// Ask for name input for (int i = 0; i < 5; i++) {
cout << "Please enter name " << i + 1 << ": "; 
cin.getline(nameList[i], 11, '\n'); // This segment of code discards extra characters entered 
if (cin.fail()) {
cin.clear(); while (!(cin.peek() == '\n')) {
cin.ignore();
} if (cin.peek() == '\n') {
cin.ignore(1, '\n');
}
}
}
cout << endl;
// Print all names 
cout << nameList[0]; 
for (int i = 1; i < 5; i++) {
cout << ", " << nameList[i];
} 
cout << endl << endl;
// Print the third letter of the second name 
cout << "The third letter of the second name: "; 
cout << nameList[1][2] << endl;
char name[11]; // copy the third name 
strcpy(name, nameList[2]); 
cout << "The third name is copied: " << name << endl;
return 0;

/*
Please enter name 1: John Smith
Please enter name 2: Mary Ann
Please enter name 3: Peter
Please enter name 4: Tom
Please enter name 5: Jerry
John Smith, Mary Ann, Peter, Tom, Jerry
The third letter of the second name: r
The third name is copied: Peter
*/
```

## 8.4 Pointer and array

› Either data or instruction 
Each location can hold 8 bits
– Each address is 32-bit long, representing a memory location
– Each memory location can store 8 bits of information

Notice that the asterisk * has TWO roles in pointers
```cpp
int *yPtr = &y;
*yPtr = 9;
```
› * and & are inverses of each other 
– Examine the example in the next slide
– Used during **declaration** of a pointer variable 
– Used during **dereferencing** a pointer
› It refers to the memory location of y and stores 9 into it


```cpp
int abc = 888;
```
– it occupies 4 contiguous memory locations
– say, 0x6000 – 0x6003
The address of abc is the smallest address among the four. Thus, it is 0x6000

We can get the address of a variable by using the ampersand “&” operator
```cpp
int abc = 888; 
cout << &abc << endl;
```
– The output will be 0x6000
```cpp
int abc = 888; 
cout << abc << endl;
```
– The output will be 888




### 8.4..1 Usage of pointer

1) Dynamic memory allocation
In c language, we can dynamically allocate memory using malloc() and calloc() functions where pointer is used.

2) Arrays, Functions and Structures
Pointers in c language are widely used in arrays, functions and structures. It reduces the code and improves the performance.

### 8.4.2 Declaring a pointer

```cpp
int ∗ a; //pointer to int    
char ∗ c; //pointer to char    
```

### 8.4.3 Pointer Example

**[Example]**
Using pointer to print the address and value.

```cpp
#include <iostream>  
using namespace std;  
int main()  
{  
int number=30;    
int ∗p;      
p=&number;//stores the address of number variable    
cout<<"Address of number variable is:"<<&number<<endl;    
cout<<"Address of p variable is:"<<p<<endl;    
cout<<"Value of p variable is:"<<*p<<endl;    
return 0;  
}  
/*
Address of number variable is:0x7fff5fbff7f4
Address of p variable is:0x7fff5fbff7f4
Value of p variable is:30 
*/
```

```cpp
#include <iostream>
using namespace std;
int main() {
int a;      // a is an integer int* aPtr;  // aPtr is a pointer to an integer
a = 7; 
aPtr = &a;  // aPtr assigned address of a
cout << "The address of a is " << &a << endl << "The value of aPtr is " << aPtr << endl;
cout << "The value of a is " << a << endl << "The value of *aPtr is " << *aPtr << endl;
cout << "Showing that * and & are inverses of " << "each other.\n&*aPtr = " << &*aPtr << endl << "*&aPtr = " << *&aPtr << endl;
return 0;
}
/*
The address of a is 0x7fff5fbff7f4
The value of aPtr is 0x7fff5fbff7f4
The value of a is 7
The value of *aPtr is 7
Showing that * and & are inverses of each other.
&*aPtr = 0x7fff5fbff7f4
*&aPtr = 0x7fff5fbff7f4
*/
```


**[Example]**
Pointer Program to swap 2 numbers without using 3rd variable.
P1 = P2

```cpp
#include <iostream>  
using namespace std;  
int main()  
{  
int a=20,b=10,∗p1=&a,∗p2=&b;    
cout<<"Before swap: ∗p1="<<∗p1<<" ∗p2="<<∗p2<<endl;    
∗p1=∗p1+∗p2;  
∗p2=∗p1-∗p2;    
∗p1=∗p1-∗p2;    
cout<<"After swap: ∗p1="<<∗p1<<" ∗p2="<<∗p2<<endl;    
return 0;  
}  
/*
Before swap: ∗p1=20 ∗p2=10
After swap: ∗p1=10 ∗p2=20
*/
```

## 8.5 Using const with Pointers: Four ways to pass pointer to function
– Non-constant pointer to non-constant data › Highest amount of access 
data—the data can be modified through the dereferenced pointer, and the pointer can be modified to point to other data. Such a pointer’s declaration (e.g., int *countPtr) does not include const.

– Non-constant pointer to constant data 
A nonconstant pointer to constant data is a pointer that can be modified to point to any data item of the appropriate type, but the data to which it points cannot be modified through that pointer.

```cpp
void f( const int * ); // prototype
int main() {
    int y = 0;
    f( &y ); // f cannot modify the value of y

    void f( const int *xPtr ) { // xPtr cannot be used to modify the value of the variable to which it points
    *xPtr = 100; // error: cannot modify a const object
    } // end function f
    return 0;
}
```


```cpp
#include <iostream>
using namespace std;
int main()
{
    // non-constant pointer to constant data
    int a = 10;
    int b = 20;
    int *ptr = &a;
    ptr = &b;
    *ptr = 30; 
    cout << *ptr << endl;
    cout << b << endl;

    // 30 30
}
```
– Constant pointer to non-constant data 
A constant pointer to nonconstant data is a pointer that always points to the same memory location, and the data at that location can be modified through the pointer. Pointers that are declared const must be initialized when they’re declared, but if the pointer is a function parameter, it’s initialized with the pointer that’s passed to the function.
```cpp
int main(){
int x, y;
int * const ptr = &x; // const pointer must be initialized
*ptr = 7; // allowed: *ptr is not const
ptr = &y; // error: ptr is const; cannot assign to it a new address
return 0;
}
```


This code will not compile due to an error in the line *ptr = 7;. Since ptr is a pointer to a constant integer, it is not allowed to modify the value of the integer that it points to. Therefore, attempting to assign a new value to the pointed integer will result in a compilation error. The correct way to use a pointer to a constant integer is to only read the value of the integer using the pointer.

```cpp
int main(){
    int x = 5, y;
    const int *ptr = &x; // ptr points to constant integer
    cout << *ptr << endl; // allowed: reading constant integer
    *ptr = 7; // error: modifying constant integer
    ptr = &y; // allowed: pointer not constant
    return 0;
}
```


– Constant pointer to constant data › Least amount of access
The minimum access privilege is granted by a constant pointer to constant data. Such a pointer always points to the same memory location, and the data at that location cannot be modified via the pointer.

The code will not compile successfully because of the following reasons:

ptr is declared as a constant pointer to constant data, which means that the address pointed to by ptr cannot be changed and the data pointed to by ptr cannot be modified.

In the line ptr = &b;, an attempt is being made to modify the address pointed to by ptr, which is not allowed because ptr is declared as a constant pointer.

In the line *ptr = 30;, an attempt is being made to modify the data pointed to by ptr, which is not allowed because the data is declared as constant.

In the line a = 30;, the value of a is being changed, but it is not related to the ptr pointer.

```cpp
int main(){
    // constant pointer to constant data
    int a = 10;
    int b = 20;
    const int * const ptr = &a;
    ptr = &b; // error: assignment of read-only variable 'ptr'
    *ptr = 30; // error: assignment of read-only location '*ptr'
    a = 30; // allowed
    cout << *ptr << endl;
    cout << b << endl;
}
```

## 8.6 Relationship Between Pointers and Arrays 
› Accessing array elements with pointers
– Element b[n] can be accessed by *(bPtr + n)
› Called pointer/offset notation
– Addresses
› &b[3] same as bPtr + 3
– Array name can be treated as pointer
› b[3] same as *(b + 3) 
– Pointers can be subscripted (pointer/subscript notation)
› bPtr[3] same as b[3]


char blocks[3] = {'A', 'F', 'X'};: This declares an array of three characters with the values 'A', 'F', and 'X'.

char *ptr = blocks;: This declares a pointer ptr that points to the first element of the blocks array.

ptr = blocks + 1;: This updates the ptr pointer to point to the second element of the blocks array (i.e., 'F').

temp = *ptr;: This assigns the value of the second element of the blocks array (i.e., 'F') to the variable temp.

temp = *(ptr + 1);: This assigns the value of the third element of the blocks array (i.e., 'X') to the variable temp.

ptr = blocks;: This updates the ptr pointer to point to the first element of the blocks array again (i.e., 'A').

temp = *++ptr;: This first increments the ptr pointer to point to the second element of the blocks array (i.e., 'F'), and then assigns the value of the second element (i.e., 'F') to the variable temp.

temp = ++*ptr;: This first dereferences the ptr pointer to get the value of the second element (i.e., 'F'), then increments that value to 'G', and finally assigns the updated value ('G') to the variable temp.

temp = *ptr++;: This first assigns the value of the second element of the blocks array (i.e., 'G') to the variable temp, and then increments the ptr pointer to point to the third element of the blocks array (i.e., 'X').

temp = *ptr;: This assigns the value of the third element of the blocks array (i.e., 'X') to the variable temp.

```cpp
char blocks[3] = {'A', 'F', 'X'}; 
char *ptr = blocks; 
char temp;
ptr = blocks + 1; 
temp = *ptr; // temp = 'F'
temp = *(ptr + 1); // temp = 'X'
ptr = blocks; // ptr = &blocks[0]
temp = *++ptr; // ++ptr = &blocks[1]
temp = ++*ptr; // *ptr = 'F' -> ++*ptr = 'G'
temp = *ptr++; // *ptr = 'G' -> ptr = &blocks[2]
temp = *ptr; // *ptr = 'X'
```





## 8.7 sizeof() operator in C++

The sizeof() is an operator that evaluates the size of data type, constants, variable. It is a compile-time operator as it returns the size of any variable or a constant at the compilation time.

The size, which is calculated by the sizeof() operator, is the amount of RAM occupied in the computer.


```cpp
sizeof(data_type); 
```


### 8.7.1 Operated in data type
When an operand is of pointer type
**[Example]**
```cpp
#include <iostream>  
using namespace std;  
int main()  
{  
  // Determining the space in bytes occupied by each data type.  
  std::cout << "Size of integer data type : " <<sizeof(int)<< std::endl;  
  std::cout << "Size of float data type : " <<sizeof(float)<< std::endl;  
  std::cout << "Size of double data type : " <<sizeof(double)<< std::endl;  
  std::cout << "Size of char data type : " <<sizeof(char)<< std::endl;  
  return 0;  
}  
/*
Size of integer data type : 4
Size of float data type : 4
Size of double data type : 8
Size of char data type : 1
*/

```


### 8.7.2 Operated in class type

**[Example]**
```cpp
#include <iostream>  
using namespace std;  
class Base  
{  
int a;  
};  
int main()  
{  
Base b;  
std::cout << "Size of class base is : "<<sizeof(b) << std::endl;  
return 0;  
}  
/*
Size of class base is : 4
*/
```
In the above program, we have evaluated the size of the class, which is having a single integer variable. The output would be 4 bytes as int variable occupies 4 bytes.


```cpp
#include <iostream>  
using namespace std;  
class Base  
{  
    int a;  
    int d;  
};  
int main()  
{  
  Base b;  
  std::cout << "Size of class base is : "<<sizeof(b) << std::endl;  
  return 0;  
}  
/*
Size of class base is : 8
*/
```


```cpp
#include <iostream>  
  
using namespace std;  
  
class Base  
{  
    int a;  
    int d;  
    char ch;  
};  
int main()  
{  
  Base b;  
  std::cout << "Size of class base is : "<<sizeof(b) << std::endl;  
    return 0;  
} 
/*
Size of class base is : 12
*/ 
```

In the above code, the class has two integer variables, and one char variable. According to our calculation, the size of the class would be equal to 9 bytes (int+int+char), but this is wrong due to the concept of structure padding.




### 8.7.3 Operated in array type
**[Example]**
```cpp
#include <iostream>  
using namespace std;  
 int main()  
{  
  int arr[]={10,20,30,40,50};  
  std::cout << "Size of the array 'arr' is : "<<sizeof(arr) << std::endl;  
  return 0;  
}  
/*
Size of the array 'arr' is : 20
*/
```

```cpp
#include <iostream>  
using namespace std;  
void fun(int arr[])  
{  
    std::cout << "Size of array is : " <<sizeof(arr)<< std::endl;  
}  
int main()  
{  
  int arr[]={10,20,30,40,50};  
  fun(arr);  
  return 0;  
}  
/*
Size of array is : 8
*/
```
In the above program, we have tried to print the size of the array using the function. In this case, we have created an array of type integer, and we pass the 'arr' to the function fun(). The fun() would return the size of the integer pointer, i.e., int*, and the size of the int* is 8 bytes in the 64-bit operating system.


### 8.7.4 Operated in pointer type
**[Example]**
```cpp
#include <iostream>  
using namespace std;  
int main()  
{  
	int *ptr1=new int(10);  
	std::cout << "size of ptr1 : " <<sizeof(ptr1)<< std::endl;  
	std::cout << "size of *ptr1 : " <<sizeof(*ptr1)<< std::endl
	char *ptr2=new char('a');
	std::cout <<"size of ptr2 : " <<sizeof(ptr2)<< std::endl;  
	std::cout <<"size of *ptr2 : "<<sizeof(*ptr2)<< std::endl;  
	double *ptr3=new double(12.78);
	std::cout <<"size of ptr3 : " <<sizeof(ptr3)<< std::endl;  
	std::cout <<"size of *ptr3 : "<<sizeof(*ptr3)<< std::endl; 
	return 0;  
}  
/*
size of ptr1 : 8
size of *ptr1 : 4
size of ptr2 : 8
size of *ptr2 : 1
size of ptr3 : 8
size of *ptr3 : 8
*/
```

In the above program, we have determined the size of pointers. The size of pointers would remain same for all the data types. If the computer has 32bit operating system, then the size of the pointer would be 4 bytes. If the computer has 64-bit operating system, then the size of the pointer would be 8 bytes. I am running this program on 64-bit, so the output would be 8 bytes. Now, **if we provide the '*' symbol to the pointer, then the output depends on the data type**, for example, *ptr1 is of integer type means the sizeof() operator will return 4 bytes as int data type occupies 4 bytes.


### 8.7.5 Operated in expression type
**[Example]**
```cpp
#include <iostream>  
using namespace std;  
   
int main()  
{  
   int num1;  
   double num2;  
   cout << sizeof(num1+num2);  
     return 0;  
}  
/*
8
*/
```
In the above program, we have declared two variables num1 and num2 of type int and double, respectively. The size of the int is 4 bytes, while the size of double is 8 bytes. The result would be the variable, which is of double type occupying 8 bytes.

---
## 8.8 Array of Pointers

### 8.8.1 Array of pointers to an integer
1 pointer
**[Example]**
```cpp
#include <iostream>  
using namespace std;  
int main()  
{  
    int *ptr;  // integer pointer declaration, which can store the address of an integer variable.
    int marks[10]; // marks array declaration, which can store 10 integer values.
    std::cout << "Enter the elements of an array :" << std::endl;  
    for(int i=0;i<10;i++)  
    {  
        cin>>marks[i]; // input the elements of an array. 
    }  
    ptr=marks; // both marks and ptr pointing to the same element.
    std::cout << "The value of *ptr is :" <<*ptr<< std::endl;  
    std::cout << "The value of *marks is :" <<*marks<<std::endl;  
}  
/*
Enter the elements of an array :
1
2
3
4
5
6
7
8
9
10
The value of *ptr is :1
The value of *marks is :1
*/
```

**[Example]**
More than 1 pointer

We declare an array of pointer named as ptr, and it allocates 5 integer pointers in memory.
```cpp
int *ptr[5];         // array of 5 integer pointer.   
```

The element of an array of a pointer can also be initialized by assigning the address of some other element. We are assigning the address of 'a' variable to the third element of an array 'ptr'.
```cpp
int a; // variable declaration.  
ptr[2] = &a;    
```

We can also retrieve the value of 'a' be dereferencing the pointer.
```cpp
*ptr[2];  
```

We declare an array of integer type and an array of integer pointers. We have defined the 'for' loop, which iterates through the elements of an array 'ptr1', and on each iteration, the address of element of ptr1 at index 'i' gets stored in the ptr2 at index 'i'.
```cpp
#include <iostream>  
using namespace std;  
int main()  
{  
    int ptr1[5]; // integer array declaration, which can store 5 integer values.  
    int *ptr2[5]; // integer array of pointer declaration, which can store 5 integer pointers.  
    std::cout << "Enter five numbers :" << std::endl;  
    for(int i=0;i<5;i++)  
    {  
        std::cin >> ptr1[i];  // input the elements of an array.
    }  
    for(int i=0;i<5;i++)  
    {  
        ptr2[i]=&ptr1[i]; // storing the address of ptr1 array in ptr2 array.  
    }  
    // printing the values of ptr1 array  
    std::cout << "The values are" << std::endl;  
    for(int i=0;i<5;i++)  
    {  
        std::cout << *ptr2[i] << std::endl;  
    }  
}  
/*
Enter five numbers :
4
5
1
2
3
The values are
4
5
1
2
3
*/
```
### 8.8.2 Array of Pointer to Strings
An array of pointer to strings is an array of character pointers that holds the address of the first character of a string or we can say the base address of a string.

- more efficient than the two-dimensional array of characters in case of memory consumption because an array of pointer to strings consumes less memory than the two-dimensional array of characters to store the strings.
- the manipulation of strings is comparatively easier than in the case of 2d array. 
- We can also easily change the position of the strings by using the pointers

**[Example]**
Declared an array of pointer names as 'names' of size 5 and did the initialization at the time of declaration.
```cpp
char *names[5] = {"john",  
                  "Peter",  
                  "Marco",  
                  "Devin",  
                  "Ronan"};  
```
Each element of the 'names' array is a string literal, and each string literal would hold the base address of the first character of a string. For example, names[0] contains the base address of "john", names[1] contains the base address of "Peter", and so on. It is not guaranteed that all the string literals will be stored in the contiguous memory location, but the characters of a string literal are stored in a contiguous memory location.
```cpp
char *names[ ] = {"john",  
                  "Peter",  
                  "Marco",  
                  "Devin",  
                  "Ronan"};  
```

**[Example]**
```cpp
#include <iostream>  
using namespace std;  
int main()  
{  
  char *names[5] = {"john",  
                    "Peter",  
                    "Marco",  
                    "Devin",  
                    "Ronan"};  
for(int i=0;i<5;i++)  
    {  
        std::cout << names[i] << std::endl;  
    }  
    return 0;  
}  
/*
john
Peter
Marco
Devin
Ronan
*/
```

---

### 8.8.3  Void Pointer
A void pointer is a pointer that has no associated data type with it. It means that a void pointer can be used to point the memory location of any data type. A void pointer can be typecasted to any data type.

Syntax of void pointer
```cpp
void *ptr;  
```

Cannot assign the address of a variable to the variable of a different data type. We declare a pointer of type **integer**, i.e., ptr and a **float** variable, i.e., 'a'. After declaration, we try to store the address of 'a' variable in 'ptr', but this is not possible in C++ as the variable cannot hold the address of different data types.

**[Example]**
```cpp
int *ptr;  // integer pointer declaration  
float a=10.2; // floating variable initialization  
ptr= &a;  // This statement throws an error.  
```

**[Example]**
```cpp
#include <iostream.h>  
using namespace std;  
int main()  
{  
    int *ptr;  
    float f=10.3;  
    ptr = &f; // error  
    std::cout << "The value of *ptr is : " <<*ptr<< std::endl;  
    return 0;  
}  
/*
error: invalid conversion from ‘float*’ to ‘int*’ [-fpermissive]
*/
```

C++ has overcome the above problem by using the C++ **void pointer** as a void pointer can hold the address of any data type.
```cpp
#include <iostream>  
using namespace std;  
int main()  
{  
  void *ptr;   // void pointer declaration  
  int a=9;   // integer variable initialization  
  ptr=&a;   // storing the address of 'a' variable in a void pointer variable.  
  std::cout << &a << std::endl;  
  std::cout << ptr << std::endl;  
  return 0;  
} 
/*
0x7fff5b0b9bfc
0x7fff5b0b9bfc
*/ 
```

In C, we can assign the address of a variable to the variable of a different data type by using the typecasting. 
```c
#include <stdio.h>  
int main()  
{  
   void *ptr; // void pointer declaration  
   int *ptr1;  // integer pointer declaration  
   int a =90;  // integer variable initialization  
   ptr=&a; // storing the address of 'a' in ptr  
   ptr1=ptr; // assigning void pointer to integer pointer type.  
   printf("The value of *ptr1 : %d",*ptr1);  
   return 0;  
}  
```
In C++, we can do the same by using the void pointer. We can assign the address of a variable to the variable of a different data type by using the void pointer.
typecast <-> void pointer to integer pointer by `(int *)ptr`

```cpp
#include <iostream>  
using namespace std;  
int main()  
{  
  void *ptr; // void pointer declaration  
  int *ptr1; // integer pointer declaration  
  int data=10; // integer variable initialization  
  ptr=&data;  // storing the address of data variable in void pointer variable  
  ptr1=(int *)ptr; // assigning void pointer to integer pointer  
  std::cout << "The value of *ptr1 is : " <<*ptr1<< std::endl;  
  return 0;  
}  
/*
The value of *ptr1 is : 10
*/
```
---

## 8.9 C++ References

```cpp
int a=10;  
int &ref=a;  
```
'ref' is a reference variable of 'a', i.e., we can use the 'ref' variable in place of 'a' variable.

### 8.9.1 References to non-const values

```cpp
#include <iostream>  
using namespace std;  
int main()  
{  
int a=10;  
int &value=a;  
std::cout << value << std::endl;  
return 0;  
}  
/*
10
*/
```


### 8.9.2 References as aliases



```cpp
int a=10;   // 'a' is a variable.  
int &b=a; // 'b' reference to a.  
int &c=a; // 'c' reference to a.  
```

**[Example]**
```cpp
#include <iostream>  
using namespace std;  
int main()  
{  
    int a=70; // variable initialization  
    int &b=a;  
    int &c=a;  
    std::cout << "Value of a is :" <<a<< std::endl;  
    std::cout << "Value of b is :" <<b<< std::endl;  
    std::cout << "Value of c is :" <<c<< std::endl;  
    return 0;} 
/*
Value of a is :70
Value of b is :70
Value of c is :70
*/
```

### 8.9.3 Properties of References

**Initializátion**

It must be initialized at the time of the declaration.

```cpp
#include <iostream>  
using namespace std;  
int main()  
{  
int a=10; // variable initialization  
int &b=a; // b reference to a  
std::cout << "value of a is " <<b<< std::endl;  
return 0;  
}  
```

**[Example]**

At the time of declaration, 'a' variable is assigned to 'b'. If we do not assign at the time of declaration, then the code would look like and report an compile time error.

```cpp
int &b;  
&b=a; 
```

'y' reference variable is referring to 'x' variable, and then 'z' is assigned to 'y'. But this reassignment is not possible with the reference variable, so it throws a compile-time error.

**[Example]**
```cpp
#include <iostream>  
using namespace std;  
int main()  
{  
int x=11; // variable initialization  
int z=67;  
int &y=x; // y reference to x  
int &y=z; // y reference to z, but throws a compile-time error.  
return 0;}  
/*
main.cpp: In function ‘int main()’:
main.cpp:8:7: error: redefinition of ‘int& y’
 int &y=z; // y reference to z, but throws a compile-time error.
       ^
main.cpp:6:7: note: ‘int& y’ previously declared here
    int &y=x; // y reference to x
        ^
    */
```

# Lecture 9: MORE ON POINTERS AND STRUCTURES


In C++, classes and structs are blueprints that are used to create the instance of a class. Structs are used for lightweight objects such as Rectangle, color, Point, etc.

|                                                  | Structure                                          | Class                                    |
| :----------------------------------------------- | :------------------------------------------------- | :--------------------------------------- |
| **Access specifier when not declared explictly** | default: public                                    | default: private                         |
| **Syntax**                                       | struct structure_name {// body of the structure. } | class class_name {// body of the class.} |
| **Instance**                                     | structure variable                                 | object of the class                      |



Syntax:
```cpp
struct structure_name  
{  
     // member declarations.  
}   
```
```cpp
struct Student  
{  
    char name[20];  
     int id;  
     int age;  
}  
```

**[Example]**

```cpp
#include <iostream>    
using namespace std;    
 struct Rectangle      
{      
   int width, height;      
      
 };      
int main(void) {    
    struct Rectangle rec;    
    rec.width=8;    
    rec.height=5;    
   cout<<"Area of Rectangle is: "<<(rec.width * rec.height)<<endl;    
 return 0;    
}    
/*
Area of Rectangle is: 40
*/
```

**[Example]**
  
```cpp
#include <iostream>
using namespace std;
struct Rectangle {
int width, height;
Rectangle (int w, int h){
    width = w;
    height = h;
};
void areaOfRectangle(){
    cout << "Area of Rectangle is: " << width * height << endl;
};
};

int main(void){
    struct Rectangle r1 = Rectangle(10, 5);
    r1.areaOfRectangle();
    return 0;
};
/*
Area of Rectangle is: 50
*/
```


## 9.1 Function Parameters

we are swapping the values of 'a' and 'b'. We have passed the variables 'a' and 'b' to the swap() function. 

In swap() function, 'p' is referring to 'a' and 'q' is referring to 'b'. When we swap the values of 'p' and 'q' means that the values of 'a' and 'b' are also swapped.

**[Example]**

```cpp
#include <iostream>  
using namespace std;  
int main()  
{  
int a=9; // variable initialization  
int b=10; // variable initialization  
swap(a, b); // function calling  
std::cout << "value of a is :" <<a<< std::endl;  
std::cout << "value of b is :" <<b<< std::endl;  
return 0;  
}  
// without using the swap() function
// void swap(int &p, int &q) // function definition  
// {  
// int temp; // variable declaration  
// temp=p;  
// p=q;  
// q=temp;  
// }  
/*
value of a is :10
value of b is :9
*/
```

Access the 'id' of the profile struct of the employee. We generally access this member by using the statement `e.p.id`, but this would be a tedious task if **we have multiple access to this member**. To avoid this situation, we create a reference variable, i.e., ref, which is another name of `'e.p.id'`.

**[Example]**
```cpp
#include <iostream>  
using namespace std;  
struct profile  
{  
int id;  
};  
struct employee  
{  
profile p;  
};  
int main()  
{  
employee e;  
int &ref=e.p.id;  
ref=34;  
std::cout << e.p.id << std::endl;  
}  
/*
34
*/
```


**[Example]**

```cpp
#include <iostream> 
#include <cstring>
using namespace std;
struct BankAccount {
    int accountNo;
    double balance; };
struct BankCustomer {
    char name[51];
    int age;
    char gender;
    char address[101];
    BankAccount accounts[3]; };

void deposit(BankCustomer&, int, double); 
void print(const BankCustomer&);

int main() {
BankCustomer bc;
// initialize the bank customer values 
strcpy(bc.name, "Dennis Liu"); 
bc.age = 20; 
bc.gender = 'M'; 
strcpy(bc.address, "PQ730, Mong Man Wai Building, PolyU"); 
bc.accounts[0].accountNo = 1234; 
bc.accounts[0].balance = 1000; 
bc.accounts[1].accountNo = 0; 
bc.accounts[2].accountNo = 0;

cout << "Before deposit:" << endl; 
print(bc);
deposit(bc, 1234, 888); 
cout << endl;
cout << "After deposit:" << endl; 
print(bc);
return 0;
}

void deposit(BankCustomer &bc, int depositAcc, double amount) {
if (amount > 0) {
for (int i = 0; i < 3; i++) {
if (bc.accounts[i].accountNo == depositAcc) {
bc.accounts[i].balance += amount; }
} 
}
}

void print(const BankCustomer &bc) {
cout << "Name: " << bc.name << endl;
cout << "Age: " << bc.age << endl;
cout << "Gender: " << bc.gender << endl;
cout << "Address: " << bc.address << endl;

for (int i = 0; i < 3; i++) {
if (bc.accounts[i].accountNo != 0) {
cout << "Account No: " << bc.accounts[i].accountNo << " || Balance: " << bc.accounts[i].balance << endl; }
}
}
```




## 9.2 References V.S. Pointers 

A reference is a variable that is referred to as another name for an already existing variable. The reference of a variable is created by storing the address of another variable.

```cpp
int &a = i;  
```

```cpp
#include <iostream>  
using namespace std;  
int main()  
{    
   int i=8;    // variable initialization  
   int &a=i; // creating a reference variable  
   cout<<"The value of 'i' variable is :"<<a;  
   return 0;  
}  
```

A pointer is a variable that contains the address of another variable. It can be dereferenced with the help of (*) operator to access the memory location to which the pointer points.

**Definition**

Pass by reference 

```cpp
#include <iostream>  
using namespace std;  
void func(int &);  
int main()  
{  
   int a=10;  
   std::cout <<"Value of 'a' is :" <<a<< std::endl;  
  func(a);   
  std::cout << "Now value of 'a' is :" <<a<< std::endl;  
  return 0;  
}  
void func(int &m)  
{  
   m=8;  
}  
```

**Declaration**
| Variable  | Example     |
| :-------- | :---------- |
| Reference | `int &a=?;` |
| Pointer   | `int *p=?;` |


**Reassignment**

The code shows the error that multiple declarations of `int &a` are not allowed. 
```cpp
#include <iostream>  
using namespace std;  
void func(int &);  
int main()  
{  
  int i;    // variable declaration  
  int k;    // variable declaration  
  int &a=i;  
  int &a=k; // error  
  return 0;  
}  
```

**Memory Address**


reference variable = the actual variable
pointer variable =\\= the actual variable



**[Example]**

```cpp
#include <iostream>  
using namespace std;  
void func(int &);  
int main()  
{  
  int i;  
  int &a=i;  
  std::cout << "The address of 'a' variable is : " <<&a<< std::endl;  
  std::cout << "The address of 'i' variable is : " <<&i<< std::endl;  
  return 0;  
}  
/*
The address of 'a' variable is : 0x7fff078e7e44
The address of 'i' variable is : 0x7fff078e7e44
*/

```

The new variable will not be assigned to the reference variable until the actual variable is either deleted or goes out of the scope.

**[Example]**

```cpp
#include <iostream>  
using namespace std;  
int main()  
{  
    int k;  
    int *p;  
    p=&k;  
    cout<<"The memory address of p variable is :"<<&p;  
    cout<<"\nThe memory address of k variable is :"<<&k;  
    return 0;  
}  
/*
The memory address of p variable is :0x7fff5b9e7e48
The memory address of k variable is :0x7fff5b9e7e44
*/
```

**NULL Value**

| Variable  | NULL value         |
| :-------- | :----------------- |
| Reference | cannot be assigned |
| Pointer   | can be assigned    |



**Indirection**

| Variable  | Indirection                                                             |
| :-------- | :---------------------------------------------------------------------- |
| Reference | cannot                                                                  |
| Pointer   | can have pointer to pointer offering more than one level of indirection |


**[Example]**
    
```cpp
#include <iostream>  
using namespace std;  
int main()  
{  
  int a=8; // variable initialization  
 int &p=a; // creating a reference variable for ?a? variable.  
 int &&q=p;  // reference to reference is not valid, it throws an error.  
 return 0;  
}  
/*
main.cpp: In function 'int main()':
main.cpp:18:10: error: cannot bind 'int' lvalue to 'int&&'
int &&q=p;
*/
```


The pointer 'p' is pointing to variable 'a' while 'q' is a double pointer which is pointing to 'p'. Therefore, we can say that the value of 'p' would be the address of 'a' variable and the value of 'q' variable would be the address of 'p' variable.

**[Example]**

```cpp
#include <iostream>  
using namespace std;  
int main()  
{  
 int *p;  
 int a=8;  
 int **q;  
 p=&a;  
 q=&p;  
std::cout << "The value of q is : " <<*q<< std::endl;  

return 0;  
}  
/*
The value of q is : 0x7fff5b9e7e44
*/
```

**Arithmetic Operations**


| Variable  | Arithemetic Operations                                       |
| :-------- | :----------------------------------------------------------- |
| Reference | cannot be applied                                            |
| Pointer   | can be applied to the pointers named as "Pointer Arithmetic" |

**[Example]**

```cpp
#include <iostream>  
using namespace std;  
int main()  
{  
   
 int value=90;  // variable declaration  
 int &a=value;   // assigning value to the reference  
 &a=&a+5 // arithmetic operation is not possible with reference variable, it throws an error.  
 return 0;  
}  
/*
main.cpp: In function 'int main()':
main.cpp:18:5: error: lvalue required as unary '&' operand
&a=&a+5;
*/
```


**[Example]**

```cpp
#include <iostream>  
using namespace std;  
int main()  
{  
 int a[]={1,2,3,4,5}; // array initialization  
  int *ptr;  // pointer declaration  
  ptr=a; assigning base address to pointer ptr.  
  cout<<"The value of *ptr is :"<<*ptr;  
  ptr=ptr+1;  // incrementing the value of ptr by 1.  
  std::cout << "\nThe value of *ptr is: " <<*ptr<< std::endl;  
  return 0;  
}  
/*
The value of *ptr is :1
The value of *ptr is: 2
*/
```



## 9.3 Function Pointer in C++

<center><img src = '/img/CN_COMP1011/functionPointer.png'></center>

Computer only understands the low-level language, i.e., binary form. The program we write in C++ is always in high-level language, so to convert the program into binary form, we use compiler. Compiler is a program that converts source code into an executable file. This executable file gets stored in RAM. The CPU starts the execution from the main() method, and it reads the copy in RAM but not the original file.

All the functions and machine code instructions are data. This data is a bunch of bytes, and all these bytes have some address in RAM. The function pointer contains RAM address of the first instruction of a function.



**Syntax for Declaration**

```cpp
int (*FuncPtr) (int,int);  
```

```cpp
#include <iostream>  
using namespace std;  
int main()  
{  
  std::cout << "Address of a main() function is : " <<&main<< std::endl;  
  return 0;  
}  
```

**Calling a function indirectly**

We declare the function pointer, i.e., `int (*funcptr)(int,int)` and then we store the address of add() function in funcptr. This implies that funcptr contains the address of add() function. Now, we can call the add() function by using funcptr. The statement funcptr(5,5) calls the add() function, and the result of add() function gets stored in sum variable.

**[Example]**

```cpp
#include <iostream>  
using namespace std;  
int add(int a , int b)  
{  
    return a+b;  
}  
int main()  
{  
int (*funcptr)(int,int);  // function pointer declaration  
    funcptr=add; // funcptr is pointing to the add function  
int sum=funcptr(5,5);  
    std::cout << "value of sum is :" <<sum<< std::endl;  
    return 0;  
}  
/*
value of sum is : 10
*/
```

**[Example]**

We define the function printname() which contains the char pointer as a parameter. We declare the function pointer, i.e., void (*ptr)(char*). The statement ptr=printname means that we are assigning the address of printname() function to ptr. Now, we can call the printname() function by using the statement ptr(s).

```cpp
#include <iostream>  
using namespace std;  
void printname(char *name)  
{  
    std::cout << "Name is :" <<name<< std::endl;  
}  
  
int main()  
{  
    char s[20];  // array declaration  
    void (*ptr)(char*);  // function pointer declaration  
    ptr=printname;  // storing the address of printname in ptr.  
    std::cout << "Enter the name of the person: " << std::endl;  
    cin>>s;  
    cout<<s;  
    ptr(s);  // calling printname() function  
   return 0;  
}  
/*
Enter the name of the person:
Rahul
Rahul
Name is : Rahul
*/
```

**Passing a function pointer as a parameter**

The func2() function takes the function pointer as a parameter. The main() method calls the func2() function in which the address of func1() is passed. In this way, the func2() function is calling the func1() indirectly.


**[Example]**


```cpp
#include <iostream>  
using namespace std;  
void func1()   // function definition
{  
    cout<<"func1 is called";  
}  
void func2(void (*funcptr)())  // function definition
{  
    funcptr();  // calling func1() function
}  
int main()  
{  
  func2(func1);   // calling func2() function
  return 0;  
}  
/*
func1 is called
*/
```

## 9.4 Memory Management

We declare an array with a maximum size to avoid insufficient size until the declaration time, but some memory will be unused. To avoid the wastage of memory, we use the new operator to allocate the memory dynamically at the run time.


### 9.4.1 Memory Management Operators

Syntax
```cpp
pointer_variable = new data-type
```
The above syntax is used to create the object using the new operator. In the above syntax, **'pointer_variable'** is the name of the pointer variable, **'new'** is the operator, and **'data-type'** defines the type of the data.

**[Example]**
  
```cpp
int *p;  
p = new int;  
```
can be changed to 

```cpp
int *p = new int;
```

**[Example]**

```cpp
float *q;
q = new float;
```
can be changed to
```cpp
float *q = new float;
```

### 9.4.2 Assigning a value to the newly created object
**[Example]**

To assign the value:
```cpp
*p = 45;  
*q = 9.8;  
```

```cpp
pointer_variable = new data-type(value);  
```

Now:
```cpp
int *p = new int(45);  
float *p = new float(9.8);  
```
### 9.4.3 How to create a single dimensional array
As we know that new operator is used to create memory space for any data-type or even user-defined data type such as an array, structures, unions, etc., so the syntax for creating a one-dimensional array is given below:

```cpp
pointer-variable = new data-type[size];  
```

**[Example]**
```cpp
int *a1 = new int[8];  
```

### 9.4.4 Delete operator
In the above statement, 'delete' is the operator used to delete the existing object, and 'pointer_variable' is the name of the pointer variable.

```cpp
delete pointer_variable;   
```

**[Example]**
```cpp
delete p;  
delete q; 
```

```cpp
delete [ ] pointer_variable;   
```
**[Example]**

```cpp
#include <iostream>  
using namespace std;
int main()  
{
    int size; // variable declaration
    int *arr = new int[size]; // Dynamically allocate memory for the array
    cout << "Enter the size of the array: ";
    cin >> size;
    cout << "Enter the elements of the array: ";
    for (int i = 0; i < size; i++)
    {
        cin >> arr[i];
    }
    cout << "The elements of the array are: ";
    for (int i = 0; i < size; i++)
    {
        cout << arr[i] << ", ";
    }
    delete[] arr; // Deallocate the memory
    return 0;
}
/*
Enter the size of the array: 5
Enter the elements of the array: 1 2 3 4 5
The elements of the array are: 1, 2, 3, 4, 5,
*/
```

## 9.5 malloc() vs new in C++
Both the malloc() and new in C++ are used for the same purpose. They are used for allocating memory at the runtime. But, malloc() and new have different syntax.

| malloc()                      | new                       |
| :---------------------------- | :------------------------ |
| malloc() is a function in C++ | new is an operator in C++ |

```cpp
type variable = new type(parameter_list);  
```
**type**: It defines the datatype of the variable for which the memory is allocated by the new operator.
**variable**: It is the name of the variable that points to the memory.
**parameter_list**: It is the list of values that are initialized to a variable.

**[Example]**
```cpp
#include <iostream>  
using namespace std;  
int main()  
{  
 int *ptr;  // integer pointer variable declaration  
 ptr=new int; // allocating memory to the pointer variable ptr.  
 std::cout << "Enter the number : " << std::endl;  
 std::cin >>*ptr;  
 std::cout << "Entered number is " <<*ptr<< std::endl;  
return 0;  
}  
/*
Enter the number: 
5
Entered number is 5
*/
```

**[Example]**
```cpp
type variable_name = (type *)malloc(sizeof(type));   
```

```cpp
#include <iostream>  
#include<stdlib.h>  
using namespace std;  
  
int main()  
{  
     
  int len;   // variable declaration  
  std::cout << "Enter the count of numbers :" << std::endl;  
  std::cin >> len;  
  int *ptr; // pointer variable declaration  
  ptr=(int*) malloc(sizeof(int)*len);  // allocating memory to  the poiner variable  
  for(int i=0;i<len;i++)  
  {  
      std::cout << "Enter a number : " << std::endl;  
      std::cin >> *(ptr+i);  
  }  
  std::cout << "Entered elements are : " << std::endl;  
   for(int i=0;i<len;i++)  
  {  
     std::cout << *(ptr+i) << std::endl;  
  }  
free(ptr);  
    return 0;  
}  
```

---

# Lecture 10: LINKED LISTS AND SEARCHING ALGORITHMS 

## 10.1 Operations on Linkedlist 

<center><img src = linkedlist.png></center>

```cpp
struct Node {
int data;
Node *next; };

Node a, b, c; 
a.next = &b; 
b.next = &c; 
(*a.next).data; 
a.next->data;
```

<center><img src = linkedlist2.png></center>


### 10.1.1 Adding a node to the beginning or the end of a list

<center><img src = linkedlist3.png></center>


At the beginning approach 1:
```cpp
void push(Node **ptr, int val){
Node *newNode = new Node;
newNode->data = val;
newNode->next = *ptr;
*ptr = newNode; 
}; 
push(&head, 4);
```

At the beginning appraoch 2:
```cpp
Node* push(Node *ptr, int val){
Node *newNode = new Node();
newNode->data = val;
newNode->next = ptr;
return newNode; 
}; 
head = push(head, 4);
```



At the end: 
```cpp
Node *current = head; 
while (current->next != NULL){
current = current->next; 
}; 
Node newNode; // What about Node *newNode = new Node? 
current->next = &newNode; c
urrent->next->next = NULL;
```



### 10.1.2 Searching

We use a pointer `cur` to represent the current node
```cpp
// Assume head is the head pointer of a list 
Node *cur = head; 
bool found = false; 
// Search until target value is found or end of the list is reached 
while (cur && cur->data != target) {
cur = cur->next; 
} 
// Determine if the target is found or ran off the end of the list 
found = (cur != NULL);
```


### 10.1.3 Deleting

1. We need to search the node
2. Also, we need to maintain one more pointer, `pre`, to represent a previous node of `cur`.
3. Consider 2 cases 
– deleting the first node and
– deleting any other node

```cpp
Node *cur = head; 
Node *pre = NULL; 
bool found = false; 
//search until target value is found or end of the list is reached 
while (cur && cur -> data != target) {
pre = cur;
cur = cur->next; } 
//determine if the target is found or ran off the end of the list 
found = (cur != NULL);
```

```cpp
// Given the head pointer, the node to be deleted (cur), and its predecessor (pre) 
if (pre == NULL) {
// deletion is on the first node of the list
head = cur->next; 
} else {
// deleting a node other than the first node of the list
pre->next = cur->next; }
```


### 10.1.4 Inserting 

1. Inserting a node in the middle of the list
2. Inserting a node in the empty list
```cpp
// Given the head pointer, the predecessor (pre) and the data to be inserted (item) 
Node *newNode = new Node; 
newNode->data = item; 
if (pre == NULL) { 
    // add before first node or to an empty list
newNode->next = head;
list = newNode; } else { 
    // add in the middle or at the end
newNode->next = pre->next;
pre->next = newNode; }
```


## 10.2 Double Linkedlist



In singly linked list, we cannot delete a node unless we have reference to its predecessor.
Add a second pointer that points to the previous node.

```cpp
struct Node {
int data;
Node *next;
Node *prev; };
```

```cpp
int main() {
// For testing
int size = 10;
int *arr = new int[size];
arr = resize(arr, size); 
} 
int* resize(int *arr, int &size) {
int newSize = size * 2;
int* newArr = new int[newSize];
for(int i = 0; i < size; i++) {
}
newArr[i] = arr[i]; 
} 
delete arr; 
size = newSize; 
return newArr;

```

## 10.3 Linear Search

<center><img src = '/img/CN_COMP1011/linearSearch.png'></center>

Adavatnages: useful for unsorted arrays
Disadvantages: inefficient for large arrays since every arrays must be checked


```cpp
#include <iostream> 
using namespace std; 
int main() {
int num[10] = {2, 1, 9, 3, 7, 4, 8, 0, 6, 5};
int keyValue = 4;
int index = -1;
// Searching the array linearly
for(int i = 0; i < 10 && index == -1; i++) {
if(keyValue == num[i]) {
index = i; 
}
} 
if(index != -1) {
cout << keyValue << " is stored in index " << index << "." << endl;
} 
else {cout << keyValue << " is not found!" << endl;
} 
return 0;
}

```




---

# Lecture 11: RECURSION AND DATA STRUCUTRES

## 11.1 Recursion VS Iteration

$$
\begin{aligned}
&\text{factorial}(n) = n! = n \times (n-1) \times (n-2) \times \cdots \times 2 \times 1 \\
&\text{factorial}(n) = n \times \text{factorial}(n-1) \\
&\text{factorial}(0) = 1 \\
&\text{factorial}(1) = 1 \\
\end{aligned}
$$

› Repetition
– Iteration: explicit loop
– Recursion: repeated function calls 
› Termination
– Iteration: loop condition fails
– Recursion: base case reached 



<center><img src = '/img/CN_COMP1011/recursion.png'></center>

```cpp
#include<iostream>  
using namespace std;    
    int main(){  
    int factorial(int);  
    int fact,value;  
    cout<<"Enter any number: ";  
    cin>>value;  
    fact=factorial(value);  
    cout<<"Factorial of a number is: "<<fact<<endl;  
    return 0;  
}  
int factorial(int n){  
    if(n<0)  
    return(-1); /*Wrong value*/    
    if(n==0)  
    return(1);  /*Terminating condition*/  
    else{  
    return(n*factorial(n-1));      
    }}  
/*
Enter any number: 5
Factorial of a number is: 120
*/
```

```cpp
#include <iostream>
using namespace std;

int factorial(int n) {
    if (n == 0 || n == 1) { // base case
        return 1;
    } else {
        return n * factorial(n-1); // recursive case
    }
}

int main() {
    int num;
    cout << "Enter a non-negative integer: ";
    cin >> num;
    cout << "Factorial of " << num << " is " << factorial(num) << endl;
    return 0;
}
```


```cpp
int factorial(int n) {
    int result = 1;
    for (int i = 1; i <= n; i++) {
        result *= i;
    }
    return result;
}
```



## 11.2 Sorting Algorithms 




### 11.1.1 Selection Sort

In the i th iteration, “select” the smallest element in the unsorted part of the list (I), and place it at the end of the sorted part of the list (S).


Selection-Sort $(A, n)$
1. for integer $i \leftarrow 0$ to $n-2$
2. $\quad \min \leftarrow i$
3. for integer $j \leftarrow i+1$ to $n$ - 1
4. $\quad$ if $A[\mathrm{~min}]>A[j]$ then
5. $\quad \min \leftarrow j$
6. $\operatorname{swap} A[i]$ and $A[\mathrm{~min}]$
7. 
<center><img src = '/img/CN_COMP1011/selectionSort.png'></center>

```cpp
void selectionSort(int arr[], int n) {
int i, j, min_idx; 
for (i = 0; i < n - 1; i++) { // Find the minimum in unsorted array 
min_idx = i; for (j = i + 1; j < n; j++) {
if (arr[j] < arr[min_idx]) {
min_idx = j;
}
} swap(&arr[min_idx], &arr[i]);
}
}
```

```cpp
void swap(int *xp, int *yp) {
int temp = *xp; 
*xp = *yp; 
*yp = temp;
}
```

### 11.1.2 Insertion Sort

Find an appropriate location for A[i] among the sorted elements in A and put it there

$$A[0] \leq \cdots \leq A[j]<A[j+1] \leq \cdots \leq A[i-1] \mid A[i] \cdots A[n-1]$$

InsertionSort $(A[0 . . n-1])$
//Sorts a given array by insertion sort
//Input: An array $A[0 . n-1]$ of $n$ orderable elements
//Output: Array $A[0 . . n-1]$ sorted in nondecreasing order
for $i \leftarrow 1$ to $n-1$ do
$v \leftarrow A[i]$
$j \leftarrow i-1$
while $j \geq 0$ and $A[j]>v$ do
$A[j+1] \leftarrow A[j]$
$j \leftarrow j-1$
$A[j+1] \leftarrow-v$

<center><img src = '/img/CN_COMP1011/insertSort.png'></center>

```cpp
void insertionSort(int a[], int n) { 
    for(int i = 1; i < n; i++) {
        int v = a[i]; 
        int j = i - 1; 
        while(j >= 0 && a[j] > v) {
            a[j + 1] = a[j];
            j = j - 1;
}       a[j + 1] = v;
}
}
```

### 11.1.3 Bubble Sort

Repeatedly swapping the adjacent elements if they are in wrong order

First Pass:
$(51428) \rightarrow(15428)$, Swap since $5>1$
$(15428) \rightarrow(14528)$, Swap since $5>4$
$(14528) \rightarrow(14258)$, Swap since $5>2$
$(14258) \rightarrow(14258)$, do not swap


Second Pass:
$(14258) \rightarrow(14258) $
$(14258) \rightarrow(12458)$, Swap since $4>2$
$(12458) \rightarrow(12458) $
$(12458) \rightarrow(12458)$

Now, the array is already sorted, but our algorithm does not know if it is completed. The algorithm needs one whole pass without any swap to know it is sorted

Third Pass:
$
\begin{aligned}
& (12458) \rightarrow(12458) \\
& (12458) \rightarrow(12458) \\
& (12458) \rightarrow(12458) \\
& (12458) \rightarrow(12458) \\
&
\end{aligned}
$

```cpp
#include <iostream>
using namespace std;
void swap(int&, int&); 
void bubbleSort(int[], int);

int main() {
int num[5] = { 7, 6, 5, 4, 3 }; 
bubbleSort(num, 5); 
cout << "The sorted array is"; 
for (int i = 0; i < 5; i++) {
cout << " " << num[i];
} 
cout << endl; 
return 0;
}

void swap(int& a, int& b) {// swapping two elements
int temp;
temp = a;
a = b;
b = temp; 
}

void bubbleSort(int numarray[], int n) {
bool swapped;
for (int i = 0; i < n - 1; i++) {
swapped = false;
for (int j = 0; j < n - 1; j++) {
if (numarray[j] > numarray[j + 1]) {
swap(numarray[j], numarray[j + 1]); 
swapped = true;
} 
} 
if (swapped == false)
break;
} 
}

```


---

# Lecture 12: C++ OOPS CONCEPTS

| Name          | Function                                                                                                                                                                                                                                                            |
| :------------ | :------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Object        | Any entity that has state and behavior is known as an object. For example: chair, pen, table, keyboard, bike etc. It can be physical and logical.                                                                                                                   |
| Class         | Collection of objects is called class. It is a logical entity.                                                                                                                                                                                                      |
| Inheritance   | When one object acquires all the properties and behaviours of parent object i.e. known as inheritance. It provides code reusability. It is used to achieve runtime polymorphism.                                                                                    |
| Polymorphism  | When one task is performed by different ways i.e. known as polymorphism. For example: to convince the customer differently, to draw something e.g. shape or rectangle etc. In C++, we use **Function overloading and Function overriding** to achieve polymorphism. |
| Abstraction   | Hiding internal details and showing functionality is known as abstraction. For example: phone call, we don't know the internal processing. In C++, we use **abstract class and interface** to achieve abstraction.                                                  |
| Encapsulation | Binding (or wrapping) code and data together into a single unit is known as encapsulation. For example: capsule, it is wrapped with different medicines.                                                                                                            |

## 12.1 Object Class
```cpp
class Student{
  public: 
  int id;
  float salary;
  string name;
}
```

**[Example]**

```cpp
#include <iostream>  
using namespace std;  
class Student {  
   public:  
      int id;//data member (also instance variable)      
      string name;//data member(also instance variable)      
};  
int main() {  
    Student s1; //creating an object of Student   
    s1.id = 201;    
    s1.name = "Sonoo Jaiswal";   
    cout<<s1.id<<endl;  
    cout<<s1.name<<endl;  
    return 0;  
}  
/*
200
Sonoo Jaiswal
*/
```

**[Example]**

```cpp
#include <iostream>
using namespace std;
class Student {
   public:
      int id;//data member (also instance variable)
      string name;//data member(also instance variable)
      float salary;
      void insert(int i, string n, float s) {
         id = i;
         name = n;
         salary = s;
      }
      void display() {
         cout<<id<<"  "<<name<<"  "<<salary<<endl;
      }
};
int main() {
    Student s1;
    s1.insert(201, "Sonoo", 890000);
    s1.display();
    Student s2;
    s2.insert(202, "Nakul", 590000);
    s2.display();
    return 0;
}
/*
201  Sonoo  890000
202  Nakul  590000
*/
```

```cpp
#include <iostream>  
using namespace std;  
class Employee {  
   public:  
       int id;//data member (also instance variable)      
       string name;//data member(also instance variable)  
       float salary;  
       void insert(int i, string n, float s)    
        {    
            id = i;    
            name = n;    
            salary = s;  
        }    
       void display()    
        {    
            cout<<id<<"  "<<name<<"  "<<salary<<endl;    
        }    
};  
int main(void) {  
    Employee e1; //creating an object of Employee   
    Employee e2; //creating an object of Employee  
    e1.insert(201, "Sonoo",990000);    
    e2.insert(202, "Nakul", 29000);    
    e1.display();    
    e2.display();    
    return 0;  
}  
/*
201  Sonoo  990000
202  Nakul  29000
*/
```
## 12.2 Constructor

There can be two types of constructors in C++.
1. Default constructor
2. Parameterized constructor

### 12.2.1 Default Constructor

```cpp
#include <iostream>  
using namespace std;  
class Employee  
 {  
   public:  
        Employee()    
        {    
            cout<<"Default Constructor Invoked"<<endl;    
        }    
};  
int main(void)   
{  
    Employee e1; //creating an object of Employee   
    Employee e2;   
    return 0;  
}  
/*
Default Constructor Invoked
Default Constructor Invoked
*/
```

### 12.2.2 Parameterized Constructor

```cpp
#include <iostream>
using namespace std;
class Employee {
   public:
       int id;//data member (also instance variable)    
       string name;//data member(also instance variable)
       float salary;
       Employee(int i, string n, float s)  
        {  
            id = i;  
            name = n;  
            salary = s;
        }  
       void display()  
        {  
            cout<<id<<"  "<<name<<"  "<<salary<<endl;  
        }  
};
int main(void) {
    Employee e1 = Employee(101, "Sonoo", 890000); //creating an object of Employee 
    Employee e2 = Employee(102, "Nakul", 59000); 
    e1.display();  
    e2.display();  
    return 0;
}
/*
101  Sonoo  890000
102  Nakul  59000
*/
```


### 12.2.3 C++ Destructor
A destructor is defined like constructor. It must have same name as class. But it is prefixed with a `tilde sign (~)`.

```cpp
#include <iostream>
using namespace std;
class Employee
{
  public:
    Employee()
    {
        cout << "Constructor Invoked" << endl;
    }
    ~Employee()
    {
        cout << "Destructor Invoked" << endl;
    }
};
int main(void)
{
    Employee e1; //creating an object of Employee
    Employee e2; //creating an object of Employee
    return 0;
}
/*
Constructor Invoked
Constructor Invoked
Destructor Invoked
Destructor Invoked
*/
```

### 12.2.4 this Pointer
In C++ programming, `this` is a keyword that refers to the current instance of the class. There can be 3 main usage of this keyword in C++.

- It can be used to pass current object as a parameter to another method.
- It can be used to refer current class instance variable.
- It can be used to declare indexers.

```cpp
#include <iostream>  
using namespace std;  
class Employee {  
   public:  
       int id; //data member (also instance variable)      
       string name; //data member(also instance variable)  
       float salary;  
       Employee(int id, string name, float salary)    
        {    
             this->id = id;    
            this->name = name;    
            this->salary = salary;   
        }    
       void display()    
        {    
            cout<<id<<"  "<<name<<"  "<<salary<<endl;    
        }    
};  
int main(void) {  
    Employee e1 =Employee(101, "Sonoo", 890000); //creating an object of Employee   
    Employee e2=Employee(102, "Nakul", 59000); //creating an object of Employee  
    e1.display();    
    e2.display();    
    return 0;  
}  
/*
101  Sonoo  890000
102  Nakul  59000
*/
```


### 12.2.5 C++ static
In C++, static is a keyword or modifier that belongs to the type not instance. So instance is not required to access the static members. In C++, static can be field, method, constructor, class, properties, operator and event.

**[Example]**

```cpp
#include <iostream>  
using namespace std;  
class Account {  
   public:  
       int accno; //data member (also instance variable)      
       string name; //data member(also instance variable)  
       static float rateOfInterest;   
       Account(int accno, string name)   
        {    
             this->accno = accno;    
            this->name = name;    
        }    
       void display()    
        {    
            cout<<accno<< "" <<name<< ""<<rateOfInterest<<endl;   
        }    
};  
float Account::rateOfInterest=6.5; //static member initialization
int main(void) {  
    Account a1 =Account(201, "Sanjay"); //creating an object of Employee   
    Account a2=Account(202, "Nakul"); //creating an object of Employee  
    a1.display();    
    a2.display();    
    return 0;  
}  
/*
201  Sanjay  6.5
202  Nakul  6.5
*/
```

**[Example]**
```cpp
#include <iostream>
using namespace std;
class Account{
    public:
    int accountNumber;
    string name;
    static int count;

    Account(int accountNumber, string name){
        this->accountNumber = accountNumber;
        this->name = name;
        count++;
    }
    void display(){
        cout << "Account Number:" << " " << accountNumber << " " << "Name:" << "" << name << endl;
    }
};
int Account::count = 0;
int main (void){
    Account a1 = Account(101, "John");
    Account a2 = Account(102, "Mary");
    Account a3 = Account(103, "Peter");
    Account a4 = Account(104, "Jane");
    Account a5 = Account(105, "Bob");
    a1.display();
    a2.display();
    a3.display();
    a4.display();
    a5.display();
    cout << "Number of objects created:" << " " << Account::count << endl;
    return 0;
}
/*
Account Number: 101 Name: John
Account Number: 102 Name: Mary
Account Number: 103 Name: Peter
Account Number: 104 Name: Jane
Account Number: 105 Name: Bob
Number of objects created: 5
*/
```

### 12.2.6 C++ Structs 


In C++, classes and structs are blueprints that are used to create the instance of a class. Structs are used for lightweight objects such as Rectangle, color, Point, etc.

|                                                  | Structure                                          | Class                                    |
| :----------------------------------------------- | :------------------------------------------------- | :--------------------------------------- |
| **Access specifier when not declared explictly** | default: public                                    | default: private                         |
| **Syntax**                                       | struct structure_name {// body of the structure. } | class class_name {// body of the class.} |
| **Instance**                                     | structure variable                                 | object of the class                      |



Syntax:
```cpp
struct structure_name  
{  
     // member declarations.  
}   
```
```cpp
struct Student  
{  
    char name[20];  
     int id;  
     int age;  
}  
```

**[Example]**

```cpp
#include <iostream>    
using namespace std;    
 struct Rectangle      
{      
   int width, height;      
      
 };      
int main(void) {    
    struct Rectangle rec;    
    rec.width=8;    
    rec.height=5;    
   cout<<"Area of Rectangle is: "<<(rec.width * rec.height)<<endl;    
 return 0;    
}    
/*
Area of Rectangle is: 40
*/
```

**[Example]**
  
```cpp
#include <iostream>
using namespace std;
struct Rectangle {
int width, height;
Rectangle (int w, int h){
    width = w;
    height = h;
};
void areaOfRectangle(){
    cout << "Area of Rectangle is: " << width * height << endl;
};
};

int main(void){
    struct Rectangle r1 = Rectangle(10, 5);
    r1.areaOfRectangle();
    return 0;
};
/*
Area of Rectangle is: 50
*/
```


### 12.2.7 Friend function

If a function is defined as a friend function in C++, then the protected and private data of a class can be accessed using the function.

By using the keyword friend compiler knows the given function is a friend function.

For accessing the data, the declaration of a friend function should be done inside the body of a class starting with the keyword friend.

Syntax:
```cpp
class class_name    
{    
    friend data_type function_name(argument/s);            // syntax of friend function.  
};    
```
---

## 12.3 C++ Enumeration
Enum in C++ is a data type that contains fixed set of constants.

It can be used for days of the week (SUNDAY, MONDAY, TUESDAY, WEDNESDAY, THURSDAY, FRIDAY and SATURDAY) , directions (NORTH, SOUTH, EAST and WEST) etc. The C++ enum constants are static and final implicitly.

C++ Enums can be thought of as classes that have fixed set of constants.

**[Example]**
```cpp
#include <iostream>  
using namespace std;  
enum week { Monday, Tuesday, Wednesday, Thursday, Friday, Saturday, Sunday };  
int main()  
{  
    week day;  
    day = Friday;  
    cout << "Day: " << day+1<<endl;  
    return 0;  
}     
/*
Day: 6
*/
```


## 12.4 C++ Inheritance
Code reusability: Now you can reuse the members of your parent class. So, there is no need to define the member again. So less code is required in the class.


### 12.4.1 Types Of Inheritance
C++ supports five types of inheritance:

Single inheritance
Multiple inheritance
Hierarchical inheritance
Multilevel inheritance
Hybrid inheritance

Syntax:
```cpp
class derived_class_name :: visibility-mode base_class_name  
{  
    // body of the derived class.  
}  
```
> 1. derived_class_name: It is the name of the derived class
> 2. visibility mode: It can be public or private
> 3. base_class_name: It is the name of the base class.

When the base class is privately inherited by the derived class, public members of the base class becomes the private members of the derived class. Therefore, the public members of the base class are not accessible by the objects of the derived class only by the member functions of the derived class.

When the base class is publicly inherited by the derived class, public members of the base class also become the public members of the derived class. Therefore, the public members of the base class are accessible by the objects of the derived class as well as by the member functions of the base class.
Note:

In C++, the default mode of visibility is private.
The private members of the base class are never inherited.


### 12.4.2 C++ Single Inheritance

Single inheritance is defined as the inheritance in which a derived class is inherited from the only one base class.

A -> B, where A is the base class and B is the derived class.

#### 12.4.2.1 Inheriting Fields

**[Example]**

```cpp
#include <iostream>  
using namespace std;  
 class Account {  
   public:  
   float salary = 60000;   
 };  
   class Programmer: public Account {  
   public:  
   float bonus = 5000;    
   };       
int main(void) {  
     Programmer p1;  
     cout<<"Salary: "<<p1.salary<<endl;    
     cout<<"Bonus: "<<p1.bonus<<endl;    
    return 0;  
}  
/*
Salary: 60000
Bonus: 5000
*/
```
#### 12.4.2.2 Inheriting Methods

**[Example]**

```cpp
#include <iostream>
using namespace std;
class Animal {
    public:
    void eat(){
        cout << "eating..." << endl;

    }
};
class Dog: public Animal {
    public: 
    void bark(){
        cout << "barking..." << endl;
    }
};
int main(void){
    Dog d1;
    d1.eat();
    d1.bark();
    return 0;
}
/*
eating...
barking...
*/
```

**[Example]**

```cpp
#include <iostream>  
using namespace std;  
class A  
{  
    int a = 4;  
    int b = 5;  
    public:  
    int mul()  
    {  
        int c = a*b;  
        return c;  
    }     
};  
  
class B : private A  // private inheritance
{  
    public:  
    void display()  
    {  
        int result = mul(); // calling the function of class A
        std::cout <<"Multiplication of a and b is :"<<result<< std::endl;  
    }  
};  
int main()  
{  
  A a1; // object of class A
  B b1; // object of class B
  a1.mul(); // calling the function of class A, but it is not accessible because of private inheritance
  b1.display();  // calling the function of class B
  return 0;  
}  
/*
Multiplication of a and b is :20
*/
```

### 12.4.3 Three visibility modes 
Visibility modes can be classified into three categories:

| Base class visibility | Derived class visibilities |               |               |
| :-------------------: | :------------------------: | :-----------: | :-----------: |
|                       |         **Public**         |  **Private**  | **Protected** |
|      **Private**      |       Not inherited        | Not inherited | Not inherited |
|      **Public**       |           Public           |    Private    |   Protected   |
|     **Protected**     |         Protected          |    Private    |   Protected   |


C++ introduces a third visibility modifier, i.e., `protected`. The member which is declared as protected will be accessible to all the member functions within the class as well as the class immediately derived from it.

1. Public: When the member is declared as public, it is accessible to all the functions of the program.
2. Private: When the member is declared as private, it is accessible within the class only.
3. Protected: When the member is declared as protected, it is accessible within its own class as well as the class immediately derived from it.


### 12.4.4 C++ Multilevel Inheritance

Multiple inheritance is defined as the inheritance in which a derived class is inherited from more than one base class. Inheritance is **transitive** so the last derived class acquires all the members of all its base classes.

> A -> B -> C, where A is the base class and B and C are the derived class.

**[Example]**

```cpp
#include <iostream>
using namespace std;  
 class Animal {  
   public:  
 void eat() {   
    cout<<"Eating..."<<endl;   
 }    
   };  
   class Dog: public Animal   
   {    
       public:  
     void bark(){  
    cout<<"Barking..."<<endl;   
     }    
   };   
   class BabyDog: public Dog   
   {    
       public:  
     void weep() {  
    cout<<"Weeping...";   
     }    
   };   
int main(void) {  
    BabyDog d1;  
    d1.eat();  
    d1.bark();  
     d1.weep();  
     return 0;  
}  
/*
Eating...
Barking...
Weeping...
*/
```

### 12.5.5 C++ Multiple Inheritance
Multiple inheritance is the process of deriving a new class that inherits the attributes from two or more classes.

> A, B, C -> D, where A, B, C are the base classes and D is the derived class.


**[Example]**
Syntax of the Derived class:
```cpp
class D : visibility B-1, visibility B-2, ?  
{  
    // Body of the class;  
}   
```

```cpp
#include <iostream>  
using namespace std;  
class A  
{  
    protected:  // protected visibility mode
    int a;  // protected member
    public:  
    void get_a(int n)  
    {  
        a = n;  
    }  
};  
  
class B  
{  
    protected:  // protected visibility mode
    int b;  // protected member
    public:  
    void get_b(int n)  
    {  
        b = n;  
    }  
};  
class C : public A,public B  
{  
    public:  
    void display()  
    {  
        std::cout << "The value of a is : " <<a<< std::endl;  
        std::cout << "The value of b is : " <<b<< std::endl;  
        cout<<"Addition of a and b is : "<<a+b;  
    }  
};  
int main()  
{  
   C c;  
   c.get_a(10);  
   c.get_b(20);  
   c.display();  
  
    return 0;  
} 
/*
The value of a is : 10
The value of b is : 20
Addition of a and b is : 30
*/
```

#### 12.5.5.1 C++ Multiple Inheritance
Ambiguity can be occurred in using the multiple inheritance when a function with the same name occurs in more than one base class.

**[Example]**

```cpp
#include <iostream>  
using namespace std;  
class A  
{  
    public:  
    void display()  
    {  
        std::cout << "Class A" << std::endl;  
    }  
};  
class B  
{  
    public:  
    void display()  
    {  
        std::cout << "Class B" << std::endl;  
    }  
};  
// class C : public A, public B  
// {  
//     void view()  
//     {  
//         display();  
//     }  
// };  
class C : public A, public B  
{  
    void view()  
    {  
        A :: display();         // Calling the display() function of class A.  
        B :: display();         // Calling the display() function of class B.  
  
    }  
};  
int main()  
{  
    C c;  
    c.display();  
    return 0;  
}  
```
#### 12.5.5.2 Single inheritance

```cpp
class A  
{  
  public:  
void display()  
{  
   cout<<?Class A?;  
}   
} ;  
class B  
{   
  public:  
void display()  
{  
 cout<<?Class B?;  
}  
} ;
int main()  
{  
   B b;  
   b.display();               // Calling the display() function of B class.  
   b.B :: display();       // Calling the display() function defined in B class.  
}   
```
### 12.5.6 Hybrid Inheritance
Hybrid inheritance is a combination of more than one type of inheritance.
A -> B, C -> D
```cpp
#include <iostream>  
using namespace std;  
class A  
{  
    protected:  
    int a;  
    public:  
    void get_a()  
    {  
       std::cout << "Enter the value of 'a' : " << std::endl;  
       cin>>a;  
    }  
};  
  
class B : public A   
{  
    protected:  
    int b;  
    public:  
    void get_b()  
    {  
        std::cout << "Enter the value of 'b' : " << std::endl;  
       cin>>b;  
    }  
};  
class C   
{  
    protected:  
    int c;  
    public:  
    void get_c()  
    {  
        std::cout << "Enter the value of c is : " << std::endl;  
        cin>>c;  
    }  
};  
  
class D : public B, public C  
{  
    protected:  
    int d;  
    public:  
    void mul()  
    {  
         get_a();  
         get_b();  
         get_c();  
         std::cout << "Multiplication of a,b,c is : " <<a*b*c<< std::endl;  
    }  
};  
int main()  
{  
    D d;  
    d.mul();  
    return 0;  
}  
/*
Enter the value of 'a' :
1
Enter the value of 'b' :
2
Enter the value of c is :
3
Multiplication of a,b,c is : 6
*/
```
### 12.5.7 Hierarchical Inheritance
Hierarchical inheritance is defined as the process of deriving more than one class from a base class.
A -> B, C, D

Syntax:
```cpp
class A  
{  
    // body of the class A.  
}    
class B : public A   
{  
    // body of class B.  
}  
class C : public A  
{  
    // body of class C.  
}   
class D : public A  
{  
    // body of class D.  
}
```
```cpp
#include <iostream>  
using namespace std;  
class Shape                 // Declaration of base class.  
{  
    public:  
    int a;  
    int b;  
    void get_data(int n,int m)  
    {  
        a= n;  
        b = m;  
    }  
};  
class Rectangle : public Shape  // inheriting Shape class  
{  
    public:  
    int rect_area()  
    {  
        int result = a*b;  
        return result;  
    }  
};  
class Triangle : public Shape    // inheriting Shape class  
{  
    public:  
    int triangle_area()  
    {  
        float result = 0.5*a*b;  
        return result;  
    }  
};  
int main()  
{  
    Rectangle r;  
    Triangle t;  
    int length,breadth,base,height;  
    std::cout << "Enter the length and breadth of a rectangle: " << std::endl;  
    cin>>length>>breadth;  
    r.get_data(length,breadth); 
     
    int m = r.rect_area();  
    std::cout << "Area of the rectangle is : " <<m<< std::endl;  
    std::cout << "Enter the base and height of the triangle: " << std::endl;  
    cin>>base>>height;  
    t.get_data(base,height);  
    float n = t.triangle_area();  
    std::cout <<"Area of the triangle is : "  << n<<std::endl;  
    return 0;  
} 
/*
Enter the length and breadth of a rectangle:
23  
20  
Area of the rectangle is : 460          
Enter the base and height of the triangle:  
2   
5
Area of the triangle is : 5 
*/
```

### 12.5.8 Aggregation

```cpp
#include <iostream>  
using namespace std;  
class Address {  
    public:  
   string addressLine, city, state;    
     Address(string addressLine, string city, string state)    
    {    
        this->addressLine = addressLine;    
        this->city = city;    
        this->state = state;    
    }    
};  
class Employee    
    {    
        private:  
        Address* address;  //Employee HAS-A Address   
        public:  
        int id;    
        string name;    
        Employee(int id, string name, Address* address)    
       {    
           this->id = id;    
           this->name = name;    
           this->address = address;    
       }    
     void display()    
       {    
           cout<<id <<" "<<name<< " "<<     
             address->addressLine<< " "<< address->city<< " "<<address->state<<endl;    
       }    
   };   
int main(void) {  
    Address a1= Address("C-146, Sec-15","Noida","UP");    
    Employee e1 = Employee(101,"Nakul",&a1);    
            e1.display();   
   return 0;  
}  
/*
101 Nakul C-146, Sec-15 Noida UP
*/
```


---

## 12.6 C++ Polymorphism
```cpp
#include <iostream>    
using namespace std;    
class Shape {                                        //  base class  
    public:    
virtual void draw(){                             // virtual function  
cout<<"drawing..."<<endl;      
    }        
};     
class Rectangle: public Shape                  //  inheriting Shape class.  
{      
 public:    
 void draw()      
   {      
       cout<<"drawing rectangle..."<<endl;      
    }      
};    
class Circle: public Shape                        //  inheriting Shape class.  
  
{      
 public:    
 void draw()      
   {      
      cout<<"drawing circle..."<<endl;      
   }      
};    
int main(void) {    
    Shape *s;                               //  base class pointer.  
    Shape sh;                               // base class object.  
        Rectangle rec;    
        Circle cir;    
            s=&sh;    
            s->draw();     
            s=&rec;    
            s->draw();      
            s=?    
            s->draw();     
}    
// drawing...
// drawing rectangle...
// drawing circle...
```

---

## 12.7 Abstraction
```cpp
#include <iostream>    
using namespace std;    
 class Sum    
{    
private: int x, y, z; // private variables  
public:    
void add()    
{    
cout<<"Enter two numbers: ";    
cin>>x>>y;    
z= x+y;    
cout<<"Sum of two number is: "<<z<<endl;    
}    
};    
int main()    
{    
Sum sm;    
sm.add();    
return 0;    
}    
// Enter two numbers: 2 3
// Sum of two number is: 5
```


---

## 12.8 C++ STL (Standard Tag Library)

C++ STL Containers

|     Container      |                                                                  Description                                                                   |          Header          |        Iterator        |
| :----------------: | :--------------------------------------------------------------------------------------------------------------------------------------------: | :----------------------: | :--------------------: |
|       vector       | Vector is a dynamic array. It can grow and shrink dynamically. It is implemented as a dynamic array. It is also known as a sequence container. |    #include <vector>     | Random Access Iterator |
|        list        |               List is a doubly linked list. It is implemented as a doubly linked list. It is also known as a sequence container.               |     #include <list>      | Bidirectional Iterator |
|    forward_list    |           Forward list is a singly linked list. It is implemented as a singly linked list. It is also known as a sequence container.           | #include <forward_list>  |    Forward Iterator    |
|       deque        |                 Deque is a double ended queue. It is implemented as a dynamic array. It is also known as a sequence container.                 |     #include <deque>     | Random Access Iterator |
|       array        |                Array is a fixed size array. It is implemented as a fixed size array. It is also known as a sequence container.                 |     #include <array>     | Random Access Iterator |
|       stack        |       Stack is a LIFO(Last In First Out) data structure. It is implemented as a dynamic array. It is also known as a container adapter.        |     #include <stack>     | Random Access Iterator |
|       queue        |       Queue is a FIFO(First In First Out) data structure. It is implemented as a dynamic array. It is also known as a container adapter.       |     #include <queue>     | Random Access Iterator |
|   priority_queue   |         Priority queue is a heap based data structure. It is implemented as a dynamic array. It is also known as a container adapter.          |     #include <queue>     | Random Access Iterator |
|        set         |             Set is a sorted set. It is implemented as a balanced binary search tree. It is also known as a associative container.              |      #include <set>      | Bidirectional Iterator |
|      multiset      |           Multiset is a sorted set. It is implemented as a balanced binary search tree. It is also known as a associative container.           |      #include <set>      | Bidirectional Iterator |
|        map         |      Map is a sorted key-value pair set. It is implemented as a balanced binary search tree. It is also known as a associative container.      |      #include <map>      | Bidirectional Iterator |
|      multimap      |   Multimap is a sorted key-value pair set. It is implemented as a balanced binary search tree. It is also known as a associative container.    |      #include <map>      | Bidirectional Iterator |
|   unordered_set    |               Unordered set is an unordered set. It is implemented as a hash table. It is also known as a associative container.               | #include <unordered_set> | Random Access Iterator |
| unordered_multiset |            Unordered multiset is an unordered set. It is implemented as a hash table. It is also known as a associative container.             | #include <unordered_set> | Random Access Iterator |
|   unordered_map    |       Unordered map is an unordered key-value pair set. It is implemented as a hash table. It is also known as a associative container.        | #include <unordered_map> | Random Access Iterator |
| unordered_multimap |     Unordered multimap is an unordered key-value pair set. It is implemented as a hash table. It is also known as a associative container.     | #include <unordered_map> | Random Access Iterator |
|       stack        |                                        It is a container adapter. It is implemented as a dynamic array.                                        |     #include <stack>     | Random Access Iterator |
|       queue        |                                        It is a container adapter. It is implemented as a dynamic array.                                        |     #include <queue>     | Random Access Iterator |
|   priority_queue   |                                        It is a container adapter. It is implemented as a dynamic array.                                        |     #include <queue>     | Random Access Iterator |


Classification of containers:
Sequence: vector, list, forward_list, deque, array
Associative: set, multiset, map, multimap
Derived containers: stack, queue, priority_queue


---

# RERERENCES
C++入门经典(第10版)2017-11
<a src = 'www.runoob.com'>菜鸟教程</a>
<a src = 'https://blog.csdn.net/pepping798/article/details/45825075'> C++ 实参和形参 </a>
<a src = 'https://www.javatpoint.com/cpp-tutorial'> Javatpoint </a>
C++ How to Program by Paul Deitel and Harvey Dietel (ninth edition)

<center><iframe src="https://archive.org/embed/chowtoprogram0004deit" width="560" height="384" frameborder="0" webkitallowfullscreen="true" mozallowfullscreen="true" allowfullscreen></iframe></center>
