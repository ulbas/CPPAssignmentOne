# Assignment1 
###Ulrich Baskerud 	S236421

##Problem one

Write a C program that prompts a user to input `6` *integers* and print the *largest*.

code:
```c++
#include <stdio.h>
		//creating an array to store the numbers in
int numbers[6]={0,0,0,0,0,0};
		//declaring the largest value, set value = 0
int largest =0;
		//setting up main
int main(void){
		//printing to console, asking for six number
	printf("Enter your six integers. \n");
		//for loop scaning 6 numbers for my array
	for (int i=0; i<6; ++i)
	{
		scanf("%d", &numbers[i]);

	}
		//printing the numbers from last scanf
	printf("You entered the following numbers: ");
	for (int i=0; i<6; ++i)
	{
		printf("%d,", numbers[i]);
	}
/		/picking the biggest number from the array
	for (int i =0; i<6; ++i)
	{
		if (numbers[i]> largest)
		{
			largest=numbers[i];
		}
	}

	printf(" \n The largest number is %d\n", &largest);
	return 0;
}
```
##Problem two
Write a C program that converts a *temperature* from *Celsius* to *Fahrenheit* and vice versa.

code:
```c++
#include <stdio.h>

float temperatur;
float temp;
int valg=0;
int main(void){

	printf("Convert from Celsius to farenheit, visa versa!\n pick 1 for Celsius to farenheit.\n or 2 for farenheit to celsius.\n");
	
	scanf("%d", &valg);
	
	if (valg==1){
		printf("Write celsius temperatur you want to convert til farenheit : ");
		scanf("%f", &temp);
		
		temperatur= (temp*(9.0/5)+32);
		printf("You have choosed %.1f and that is in farenheit %.1f degrees",temp, temperatur);
		
	}
	else if (valg==2){
		printf("Write the farenheit temperatur you want to convert to celsius : ");
		scanf("%f", &temp);
		temperatur= (((temp-32)*5)/9.0);
		
		printf("You have choosed %.1f farenheit, and that is in celsius %.1f degrees",temp, temperatur);
		
	}
	else if(valg>=3){
		printf("type in celsius or farenheit");
	}
	
	return 0;
}
```
##Problem three
Write a C program that counts the number of *blank spaces*, *new lines* and *tabs* of an input. 
For example: 
if the input is Effective Programming in C and C++ - the output should be            
 
 Words	  -	value     
 New Lines       = 1      
 Blank Spaces    = 5       
 Tabs            = 0     


code:
```c++
#include <stdio.h>

int main(void){
	//declearing c, nl, ns, nt as int
	int c, nl, ns, nt;
	// giving them 0 as starting value
	nl=0;
	ns=0;
	nt=0;
	// starting a while loop so my program reads when i type the different keys.
	while((c = getchar()) != EOF && c != 'q')	{
	// reading the typings
		if (c == '\n')
			++nl;
		if(c == '\t')
			++nt;
		if(c == ' ')
			++ns;
	}
		//printing out a sentence and the count value for Newline, Space and Tab
		printf("Blanks: %d, Newlines: %d, Tabs: %d", ns, nl, nt);

		return 0;
	}
```

##Problem four
Write a C or C++ program that counts the *number of words* in a given sentence.

code:
```c++
#include <stdio.h>
#include <string.h>



		// setting up my main
	int main(void){
		// declaring char s and int count,i
	char s[200];
	int count = 0; 
	int i;
		//Starting my program with a text sentence so user know hos to use program
	printf("Enter the text string\n");
		//scanning for words typed
	scanf("%[^\n]s",s);
		// for loop for counting words
	for (i = 0; s[i] != '\0';i++)
	{
	if (s[i] == ' ')
	count++;
	}
		//printing out last sentence with number of words typed
	printf("Number of words in given text string are : %d\n", count + 1);

		  }
```

##Problem five
Write a program in either C or C++ that prints the following *pattern*.
 `1`
 `1` `2`
 `1` `2` `3`
 `1` `2` `3` `4`
 `1` `2` `3` `4` `5`

code:
```c++

#include <iostream>
#include <conio.h>
 // Using namespace so i dont have to use std>>,std<< in my programming code
using namespace std;
//declaring and setting up main
int main()
{

	//declaring integer i,j and rader
	int i,j,rader;
	//writing out to console
	cout<<"how many rows with numbers do you want? \n";
	//reading from the console, readed value goes to rader
	cin>>rader;
	//setting up two for loops so it counts and starts a new line with more numbers
	for(i=0;i<=rader;++i)
		{ for (j=0;j<=i;++j)
			{
				
				cout<<j<<" ";
			}

			cout<<"\n";
		}
		//returning value
		return 0;
	}
```
##Problem six
Write a C++ function which takes a *single integer* parameter, and returns the boolean *”True”* if the given
number is even and *”False”* otherwise.


code:
```c++
#include <iostream>
#include <iomanip>
// using namespace std so i dont have to use std<<, std>> in code.
using namespace std;
//getting the function IsEven.
void IsEven(int num);

int main()
{//declaring num as integer
	int num;
 //writing to console, asking for user to type in number to check.
	cout<<"Please enter a number."<<endl;
	//Reading typed number from console.
	cin >>num;
// checking if number is "Even"
	IsEven(num);
	// if sentence to choose if it true or false
	if(numIsEven = true)
		cout << num << " is an even number."<< endl;
	else
		cout << num << " is an odd number. " <<endl;
//returning value
	return 0;
}
//IsEven function
void IsEven(int num)
{
	bool numIsEven = false;
}
```
##Problem seven
In number theory, a *perfect number* is a positive integer that is equal to the sum of its proper positive
divisors, that is, the sum of its positive divisors excluding the number itself.  The *smallest* perfect number
is `6`, which is the sum of `1`, `2`, and `3`.  Other perfect numbers are `28`, `496`, and `8,128`.  Write a program in
either C or C++ to print all *perfect numbers* in given range using a function.

code:
```c++
#include <iostream>

using namespace std;

int main()
{
int n,i;
int k=0;
cout<< "Enter a number: ";
cin>>n;

for(i=1;i<n;i++)
{
	if(n%i==0)
		k=k+i;
}
if(k==n)
{
	cout<<n<<" is a perfect number";
}
else
{
	cout<<n<<" is not a perfect number";
}
	return 0;
}
```

##Problem eight
In mathematics, a *triangle* is a polygon with *three edges and three vertices*.  
Triangles can be classified according to the lengths of their sides.

• An ***equilateral** triangle has all sides the same length.
• An **isosceles** triangle has two sides of equal length.
• A **scalene** triangle has all its sides of different lengths.

Write a program either in C or C++ that checks whether a given triangle is
`equilateral`, `isosceles` or `scalene`.

code:

```c++
#include <iostream>
//using namespace std so i dont have to use it in the rest of the code
using namespace std;
// setting up main
int main()
{
	//declaring a,b and c as integer
int a,b,c;
	// Asking the user to choose the three sides
cout<<"Enter the sides of a triangle"<<endl;
	//reading the three values form console
cin>>a>>b>>c;

	//writing a if sentence to look for 2 sides that alike

if((a==b) && (b==c))
	{
		cout<<"\n The triangle is isosceles"<<endl;
}
	//writing an else if all three sides are the same
else if((a==c) || (b==c) || (a==b)){
	cout<<"The triangle is equilateral"<<endl;
}

else
	//if all sides are of different length
	cout<<"The triangle is scalene"<<endl;


return 0;


}
```
##Problem nine
In mathematics, the *Fibonacci numbers* are the sequence of numbers **{Fn}8n=1** defined by the linear
recurrence equation **Fn=Fn-1+Fn-2** with **F1 = F2 = 1**, and conventionally defining F0 = 0.  
The first few *Fibonacci numbers* are *1, 1, 2, 3, 5, 8,13, 21,...etc*.  
Implement a C++ function to compute and display the first *n numbers* of the *Fibonacci list*,
where n is provided as an input by the user.


code:

```c++
#include <iostream>

using namespace std;

int main()
{
	int t1=1, t2 =1, nextTerm = 0, n;
	cout << "Enter a positive number: ";
	cin >> n;

	cout << "Fibonacci Series: " << t1 <<"," << t2 <<",";
	nextTerm = t1 + t2;
	while(nextTerm <= n)
	{
		cout << nextTerm << ", ";
		t1 = t2;
		t2 = nextTerm;
		nextTerm = t1 + t2;
	}
	return 0;
}
```
##Problem 10
Implement two C++ functions called **swap_1(int, int)** and **swap_2(int&, int&)** that are supposed to *swap* two values.   
Display the final values just before the end of each function, and display the results from the main function 
before and after the call. 
What do you make of these two functions?

code:
```c++
#include <iostream>
//using namespace, so i dont have to use std in rest of the code
using namespace std;
//creating functions swap_1 and swap_2, one without references
void swap_1(int a,int b);
void swap_2(int &a, int &b);
//creating main to run code in
int main()
{
	//giving int a and b values so they can swap. choose different values!
	int a =10;
	int b = 50;
	//writing to console the original value of a and b
	cout << "Value before swap a:" << a <<endl;
	cout << "Value before swap b:" << b <<endl;
	swap_1(a,b);
	cout << "Value after swap a:" << a <<endl;
	cout << "Value after swap b:" << b <<endl;
	//giving console a seperation text so i can see det difference easier
	cout << "New value"<<endl;
	cout << "Value before swap a:" << a <<endl;
	cout << "Value before swap b:" << b <<endl;
	//using swap_2 to switch the a and b value
	swap_2(a,b);
	//writing new switched values to console
	cout << "Value after swap a:" << a <<endl;
	cout << "Value after swap b:" << b <<endl;
	//returning the values
	return 0;
}
//swap_1 function that store int temp,a and b
void swap_1(int a, int b){
	int temp = a;
	a=b;
	b=temp;
}
//swap_2 function that also store a int temp, a and b value
void swap_2(int &a, int &b){
	int temp = a;
	a = b;
	b=temp;
}
```
