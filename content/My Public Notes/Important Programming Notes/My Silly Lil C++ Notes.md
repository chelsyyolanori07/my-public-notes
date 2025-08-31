
### Basic
- why c++ though?
![[Pasted image 20250831183714.png]]
- To make the output move to another row is just simply can using twi ways: first using << endl; or using \n (Both `\n` and `endl` are used to break lines. However, `\n` is most used)

``` cpp
#include <iostream>
using namespace std;

int main() {
  cout << "Hello world this is me trying to do better :)\n\n";
  cout << "Yesss" << endl;
  cout << "hellow";
  return 0;
}
```


```
Output:

Hello world this is me trying to do better :)

Yesss
hellow
```



```
Syntax Umum
input library.. iostream
matematika => #include <cmath> sqrt, pow, dkk
string => include <string>

fungsi-fungsinya
int main() {
=====================
}

\n = endl
\t = tab

fungsi

```
### Space Thingy
- A lil notes about new line thingy
![[Pasted image 20250831183745.png]]
- The compiler ignores white spaces. However, multiple lines makes the code more readable
- It is important that you end the statement with a semicolon ; after every stataments to avaoid errors
- The statements are executed, one by one, in the same order as they are written

### It can cout number as well and calculated real time
- Can write number like this for example
``` cpp
#include <iostream>
using namespace std;

int main() {
  cout << 3 + 5 << endl;
  cout << 10 - 7 << endl;
  cout << 5 * 8 << endl;
  cout << 30 / 5 << endl;
  return 0;
}
```

```
Output:
8
3
40
6
```
	
- Single-line comments start with two forward slashes (`//`)
- Multi-line comments start with `/*` and ends with `*/`
- Variables are containers for storing data values.
- In C++, there are different **types** of variables (defined with different keywords), for example:
	- `int` - stores integers (whole numbers), without decimals, such as 123 or -123
	- `double` - stores floating point numbers, with decimals, such as 19.99 or -19.99
	- `char` - stores single characters, such as 'a' or 'B'. Char values are surrounded by single quotes
	- `string` - stores text, such as "Hello World". String values are surrounded by double quotes
	- `bool` - stores values with two states: true or false
- Declaring variable syntax
``` cpp
type variableName = value;
```

- Contoh assign variable
``` cpp
#include <iostream>
using namespace std;

int main() {
  int n;
  int number = 7;
  n = 5;
  cout << number << endl;
  cout << n << endl;
  cout << number * n;
}
```

```
Output:
7
5
35
```
- Note that if you assign a new value to an existing variable, it will overwrite the previous value
- Buat nama variabel harus hati2 karena 
	- camel style => namaNama 
	- nama, hello
	- ga boleh angka duluan
	- nama1


``` cpp
int myNum = 5;               // Integer (whole number without decimals)  
double myFloatNum = 5.99;    // Floating point number (with decimals)  
char myLetter = 'D';         // Character  
string myText = "Hello";     // String (text)  
bool myBoolean = true;       // Boolean (true or false)
=================================================================
int myNum = 5;               // Integer (whole number)  
float myFloatNum = 5.99;     // Floating point number  
double myDoubleNum = 9.98;   // Floating point number  
char myLetter = 'D';         // Character  
bool myBoolean = true;       // Boolean  
string myText = "Hello";     // String
```

- To combine both text and a variable, separate them with the `<<` operator
- To declare more than one variable of the **same type**, use a comma-separated list
- The general rules for naming variables are:
	- Names can contain letters, digits and underscores
	- Names must begin with a letter or an underscore (_)
	- Names are case-sensitive (`myVar` and `myvar` are different variables)
	- Names cannot contain whitespaces or special characters like !, #, %, etc.
	- Reserved words (like C++ keywords, such as `int`) cannot be used as names
- When you do not want others (or yourself) to change existing variable values, use the `const` keyword (this will declare the variable as "constant", which means **unchangeable and read-only**)
- When you declare a constant variable, it must be assigned with a value:
```
**const** int myNum = 15;  // myNum will always be 15  
myNum = 10;  // error: assignment of read-only variable 'myNum'
```

- `cout` is pronounced "see-out". Used for **output**, and uses the insertion operator (`<<`)
- `cin` is pronounced "see-in". Used for **input**, and uses the extraction operator (`>>`)
``` cpp
#include <iostream>
using namespace std;

int main() {
  int x, y, z;
  int sum, kali;
  cout << "Type your x: ";
  cin >> x;
  cout << "Type your y: ";
  cin >> y;
  cout << "Type your z:";
  sum = x + y + z;
  kali = x * y * z;
  cout << "Sum is: " << sum;
  cout << "Multiplication is: " << kali;
  return 0;
}
```

- data type table
![[Pasted image 20250831184002.png]]

- `float` vs. `double`
	The **precision** of a floating point value indicates how many digits the value can have after the decimal point. The precision of `float` is only six or seven decimal digits, while `double` variables have a precision of about 15 digits. Therefore it is safer to use `double` for most calculations
- A boolean data type is declared with the `bool` keyword and can only take the values `true` or `false`. When the value is returned, `true` = `1` and `false` = `0`
- The `auto` keyword automatically detects the type of a variable based on the value you assign to it
``` cpp
auto x = 5; // x is automatically treated as int

// Creating auto variables  
auto myNum = 5; // int  
auto myFloatNum = 5.99; // float  
auto myDoubleNum = 9.98; // double  
auto myLetter = 'D'; // char  
auto myBoolean = true; // bool  
auto myString = string("Hello"); // std::string

==================================================================

auto x = 5; // x is now an int  
x = 10;     // OK - still an int  
x = 9.99;   // Error - can't assign a double to an int
```

- Arithmrtic operators
![[Pasted image 20250831183410.png]]
- Assignment Operators
![[Pasted image 20250831183433.png]]
- Comparison operators are used to compare two values (or variables). This is important in programming, because it helps us to find answers and make decisions
- The return value of a comparison is either `1` or `0`, which means **true** (1) or **false** (0).
```
int x = 5;  
int y = 3;  
cout << (x > y); // returns 1 (true) because 5 is greater than 3
```
- All Comparisons
![[Pasted image 20250831183506.png]]

- As with [comparison operators](https://www.w3schools.com/cpp/cpp_operators_comparison.asp), you can also test for **true** (`1`) or **false** (`0`) values with **logical operators**
- Logical Operators
![[Pasted image 20250826025419.png]]
![[Pasted image 20250831183543.png]]
- **Note:** String indexes start with 0: [0] is the first character. [1] is the second character, etc.
``` cpp
string myString = "Hello";  
cout << myString[0];  
// Outputs H
```

- Change String
``` cpp
string myString = "Hello";  
myString[0] = 'J';  
cout << myString;  
// Outputs Jello instead of Hello

==================================================================

string myString = "Hello";  
cout << myString; // Outputs Hello  
  
cout << myString.at(0);  // First character  
cout << myString.at(1);  // Second character  
cout << myString.at(myString.length() - 1);  // Last character  
  
myString.at(0) = 'J';  
cout << myString;  // Outputs Jello
```

- `cin` considers a space (whitespace, tabs, etc) as a terminating character, which means that it can only store a single word (even if you type many words)
- That's why, when working with strings, we often use the `getline()` function to read a line of text. It takes `cin` as the first parameter, and the string variable as second
``` cpp
string fullName;  
cout << "Type your full name: ";  
getline (cin, fullName);  
cout << "Your name is: " << fullName;  
  
// Type your full name: Maki Uwu  
// Your name is: Maki Uwu
```

- In a switch case, a break can save a lot of execution time because it "ignores" the execution of all the rest of the code in the switch block.
- difference of 3 loops
- for loop = used when the number of iterations is clear (i know how much stuff i need to loop)
``` cpp
Syntax umum:
for (inisialisasi; kondisi; update) {
    // kode yang diulang
}

contoh:
#include <iostream>
using namespace std;

int main() {
    for (int i = 1; i <= 5; i++) {
        cout << "Perulangan ke-" << i << endl;
    }
    return 0;
}

hasil output:
Perulangan ke-1
Perulangan ke-2
Perulangan ke-3
Perulangan ke-4
Perulangan ke-5

```
- while loop = used when we want repeat as long as the certain condition is still valid/being met
``` cpp
Syntax umum:
while (kondisi) {
    // kode diulang selama kondisi true
}

Contoh:
#include <iostream>
using namespace std;

int main() {
    int i = 1;
    while (i <= 5) {
        cout << "Perulangan ke-" << i << endl;
        i++;
    }
    return 0;
}

Output:
Perulangan ke-1
Perulangan ke-2
Perulangan ke-3
Perulangan ke-4
Perulangan ke-5

```
- do while loop = similar to while, but executed at least once first, then the condition is checked
```cpp
Syntax umum:
do {
    // kode diulang minimal sekali
} while (kondisi);

Contoh:
#include <iostream>
using namespace std;

int main() {
    int i = 1;
    do {
        cout << "Perulangan ke-" << i << endl;
        i++;
    } while (i <= 5);
    return 0;
}

Output:
Perulangan ke-1
Perulangan ke-2
Perulangan ke-3
Perulangan ke-4
Perulangan ke-5

```

- Example of infinite loop
```cpp
while (true) {
    cout << "Ini akan jalan terus tanpa henti" << endl;
}

```

- nested loop = the "inner loop" will be executed one time for each iteration of the "outer loop"
- Intinya loop luar itu mengendalikan berapa kali loop dalam dijalankan
- loop dalam itu dijalankan setiap kali loop luar berjalan sekali
```cpp
Contoh:
#include <iostream>
using namespace std;

int main() {
    for (int i = 1; i <= 5; i++) {        // baris
        for (int j = 1; j <= i; j++) {    // kolom
            cout << "* ";
        }
        cout << endl; // pindah baris
    }
    return 0;
}

Ooutput:
* 
* * 
* * * 
* * * * 
* * * * * 
```

- for each loop = used to loop through elements in an [array](https://www.w3schools.com/cpp/cpp_arrays.asp)
```cpp
Contoh:
#include <iostream>
using namespace std;

int main() {
  // Create an array of integers
  int myNumbers[5] = {10, 20, 30, 40, 50};
  
  // Loop through integers
  for (int i : myNumbers) {
    cout << i << "\n";
  }
  return 0;
}

Output:
10  
20  
30  
40  
50
```
- difference between break and continue
- break = it will stop something once that condition is being met
```cpp
Contoh:
#include <iostream>
using namespace std;

int main() {
  for (int i = 0; i < 10; i++) {
    if (i == 5) {
      break;
    }
    cout << i << "\n";
  } 
  return 0;
}

Output:
0
1
2
3
4
```
- continue = it will continue once the condition is being met but just skip the result of that certain condition
```cpp
Contoh:
#include <iostream>
using namespace std;

int main() {
  for (int i = 0; i < 10; i++) {
    if (i == 4) {
      continue;
    }
    cout << i << "\n";
  }   
  return 0;
}

Output:
0  
1  
2  
3  
5  
6  
7  
8  
9
```

- array = used to store multiple values in a single variable, instead of declaring separate variables for each value. To declare an array, define the variable type, specify the name of the array followed by **square brackets** and specify the number of elements it should store using curly brackets
```
contoh:
string cars[4] = {"Honda", "BMW", "Yamaha", "Tesla"};  
cout << cars[0];  
// Outputs Honda
```

- array in C++ is fixed, meaning you **cannot** **add** or **remove** elements after it is created.
``` cpp
// An array with 3 elements  
string cars[3] = {"Volvo", "BMW", "Ford"};  
  
// Trying to add another element (a fourth element) to the cars array will result in an error  
cars[3] = "Tesla";

// It will result as an error
```

- Structs (also called structs) = are a way to group several related variables into one place. Each variable in the structure is known as a **member** of the structure. Unlike an [array](https://www.w3schools.com/cpp/cpp_arrays.asp), a structure can contain many different data types: `int`, `string`, `bool`, etc

```cpp
// Create a structure variable called myStructure  
struct {  
  int myNum;  
  string myString;  
} myStructure;  
  
// Assign values to members of myStructure  
myStructure.myNum = 1;  
myStructure.myString = "Hello World!";  
  
// Print members of myStructure  
cout << myStructure.myNum << "\n";  
cout << myStructure.myString << "\n";

Output:
1  
Hello World!
```

```cpp
#include <iostream>
#include <string>
using namespace std;

Contoh 2:
// Declare a structure named "car"
struct car {
  string brand;
  string model;
  int year;
};

int main() {
  // Create a car structure and store it in myCar1;
  car myCar1;
  myCar1.brand = "BMW";
  myCar1.model = "X5";
  myCar1.year = 1999;

  // Create another car structure and store it in myCar2;
  car myCar2;
  myCar2.brand = "Ford";
  myCar2.model = "Mustang";
  myCar2.year = 1969;
 
  // Print the structure members
  cout << myCar1.brand << " " << myCar1.model << " " << myCar1.year << "\n";
  cout << myCar2.brand << " " << myCar2.model << " " << myCar2.year << "\n";
 
  return 0;
}

Output:
BMW X5 1999  
Ford Mustang 1969
```