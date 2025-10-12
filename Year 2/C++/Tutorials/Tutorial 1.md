![[image-69.png|552x265]]

```c++
// take in users age  
int age;  
cin >> age;  
  
// output result based on age  
if (age < 18) {  
    cout << "user is too young";  
} else if (age > 30) {  
    cout << "user is too old";  
} else {  
    cout << "user is the right age";  
}  
  
return 0;

```


![[image-70.png]]

```c++
#include <iostream>  
using namespace std;  
  
int main() {  
  
  
   // request users name  
   cout << "Enter your name: ";  
   string name;  
   cin >> name;  
   cout << "Hello, " << name << endl;  
  
}
```

Q3)

The program below is a simple guessing game. 

```c++
#include <iostream>
#include <cstdlib>
#include <ctime>

using namespace std;

int main() {

	srand(time(nullptr));
	int n = 10;
	int secret = rand()%n + 1;
	cout << "Guess a number between 1 and " << n << ": ";
	int guess;
	cin >> guess;
	
	while (guess != secret) {
	cout << "Wrong! Guess again: ";
	cin >> guess;
	}
	
	cout << "Correct!\n";
	return 0;
}
```

Explanation:
- `strand(time(nullptr))` initialises the systems pseudo-random number-generator