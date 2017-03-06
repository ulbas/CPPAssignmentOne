#Assignment 2

##Problem 1
####Write a C++ program to sort an array of numbers in an ascending order and descending order based on user’s choice and display them.

Here I use array[10] to store ten values, then I check the values that are typed in using for loop to put them in the right order, and at last I used **for loop** to display the values in right order **(acsending and descending)**.

What i got in cmder:
```
 Enter the number of elements: 6


 Enter the 1th element: 7

 Enter the 2th element: 4

 Enter the 3th element: 5

 Enter the 4th element: 8

 Enter the 5th element: 15

 Enter the 6th element: 18

 Ascending order: 4 5 7 8 15 18
 Descending order: 18 15 8 7 5 4

```
The code:
```c++

#include <iostream>
using namespace std;

int main(void)
{
	int array[10], i=0, j=0, n, t;

	cout<< "\n Enter the number of elements: ";
	cin>>n;
	cout<<"\n ";

	for (i = 0; i <n; i++)
	{
		cout<<"\n Enter the "<<i+1<<"th element: ";
		cin>>array[i];
	}

	for (j=0 ; j<(n-1) ; j++)
	{
		for (i=0 ; i<(n-1) ; i++)
		{
			if (array[i+1] < array[i])
			{
				t = array[i];
				array[i] = array[i + 1];
				array[i + 1] = t;
			}
		}
	}

	cout<<"\n Ascending order: ";
	for (i=0 ; i<n ; i++)
	{
		cout<<array[i]<<" ";
	
	}

	cout<<"\n Descending order: ";
	for (i=n ; i>0 ; i--)
	{
		cout<<array[i-1]<<" ";
	}

      
      return 0;
}


```
##Problem 2
###Write a C++ program to sort string (name) in an alphabetical order. For example if a user enters a string `"bye"`, then the output of the program will be `"bey"`.

I choosed to use string and algorithm libraries, so I hade the tools **getline** and **sort** to sort the string the user types in in console.

What i got in cmder:
```
Please enter a string text: right
You wrote: right
Sorted in right order: ghirt
```
The code:
```c++
#include <iostream>
#include <string>
#include <algorithm>
using namespace std;

int main(){
	string text;
	cout<<"Please enter a string text: ";
	getline(cin, text);
	cout<<"You wrote: "<<text<<endl;
	sort(text.begin(), text.end());
	cout<<"Sorted in right order: "<<text<<endl;

	return 0;
}

```
##Problem 3
###Allocation and deallocation of mono-dimensional and bi-dimensional arrays represented by pointers.
I separated Exercise 3 in two parts problem a and b as one code and c,d and e on another code since the problem was to write to a bigger array than in a.

Im letting the user type in the size of the array, then the program types out the adress of the element.

What i got in cmder in the first code:
```
please enter number of rows for array:
4
your adress is: 0x1001db8
```
What i got in cmder in the second code:
```
Enter value of rows and columns:
4
4
The value of the first element is: 0x761da8


0x761dc0 0x761dc4 0x761dc8 0x761dcc
0x761dd8 0x761ddc 0x761de0 0x761de4
0x761df0 0x761df4 0x761df8 0x761dfc
0x7619b0 0x7619b4 0x7619b8 0x7619bc
```
##a)
###Declare and implement a function CreateArray(...) that returns a pointer to an array of n integers.
Problem a I solved by setting up a function like the one under, letting the function make a array with **n** integers.
```
int* createArray(int n){
	int* tom = new int[n];
	return tom;
}
```
##b)
###Declare and implement a function DeleteArray(...) that takes and deletes an array of integers.
Here I solved it by creating an **void deleteArray** since it dont return values, **delete[] array** will clear the space inside the array.
```
void deleteArray(int* array)
{
	delete[] array;

}
```
The code for a and b:
```c++
#include <iostream>
int* createArray(int n);
void deleteArray(int* array);
int main(int argc, char const *argv[])
{
	int n;
	int* peker;
	std::cout<<"please enter number of rows for array: "<<std::endl;
	std::cin>>n;
	createArray(n);
	peker= createArray(n);
	std::cout<<"your adress is: "<<peker<<std::endl;
	deleteArray(peker);

	return 0;
}
int* createArray(int n){
	int* tom = new int[n];
	return tom;
}
void deleteArray(int* array)
{
	delete[] array;

}
```
##c)
###Declare and implement a function CreateMatrix(...) that returns a pointer to an array of arrays of n × m floats.
Here I did almost the same as in *a*, i made an function **float createMatrix** with two int's c and r to use in the for loops so i can make **array c x r**.
Returning the value of matrixP to use in **main**.

```
float** createMatrix(int c, int r)
{
	float** matrixP = new float*[c];
	for (int i = 0; i < c; ++i)
	{
		matrixP[i] = new float[r]; 
	}
	return matrixP;
}
```
##d)
###Declare and implement a function Deletematrix(...) that takes and deletes this kind of matrix.
Using for loops to delete the arrays, just like I created them. Since im not returning any values I use Void in the function:
```
void deleteMatrix (float** fjern, int c)
{
	
	for (int i = 0; i < c; ++i)
	{
		delete[] fjern[i];
	}

	delete[] fjern;
}
```
##e)
###Declare and implement  a  function  DisplayMatrix(...)  that  displays  the  address  of  the matrix of floats in the memory and all its elements.

Here I had to do almost the same as in c and d. But I had to use cout to make it display every element of the c x r array, since it's not returning any value, just text i can use void to declare my **displayMatrix** function
```
void displayMatrix(float** matrise, int p, int o)
{
	for (int i = 0; i < p; ++i)
	{
		cout<<endl;

		for (int j = 0; j < o; ++j)
		{
			cout<<&matrise[i][j]<<" ";
		}
	}
	
}
```
The code for c,d and e:
```c++
#include <iostream>
float** createMatrix(int c, int r);
void deleteMatrix (float** fjern, int c);
void displayMatrix (float** matrise, int p, int o);
int main()
{
	int a,b;
	float** arrayP;
	std::cout<<"Enter value of rows and columns: "<<std::endl;
	std::cin>>a>>b;
	arrayP=createMatrix(a,b);
	std::cout<<arrayP<<std::endl;
	displayMatrix(arrayP,a,b);
	deleteMatrix(arrayP,a);
	
	return 0;
}
float** createMatrix(int c, int r)
{
	float** matrixP = new float*[c];
	for (int i = 0; i < c; ++i)
	{
		matrixP[i] = new float[r]; 
	}
	return matrixP;
}
void deleteMatrix (float** fjern, int c)
{
	
	for (int i = 0; i < c; ++i)
	{
		delete[] fjern[i];
	}

	delete[] fjern;
}
void displayMatrix(float** matrise, int p, int o)
{
	for (int i = 0; i < p; ++i)
	{
		std::cout<<std::endl;

		for (int j = 0; j < o; ++j)
		{
			std::cout<<&matrise[i][j]<<" ";
		}
	}
	
}
```
##Problem 4
##a)
###Declare and implement a function DisplayPointerInfo(...) which displays on screen the address of the first element of an array represented by a pointer. If multiple elements of the array exist, then display the address of all the values represented by a pointer.

Here I used one function to set up an array with **n** elements, displaying them by including the function **displayPointerInfo** letting the pointer A and n determine the size of the array in function.

The code for a:
```c++
#include <iostream>

using namespace std;
void displayPointerInfo(int* array,int y);
int main()
{
	int n;
	int* A;
	cout<<"Write the size of the array: ";
	cin>>n;
	A = new int[n];
	displayPointerInfo(A,n);

	return 0;

}


void displayPointerInfo(int* array,int y)
{	
	cout<<"The pointer adress of the first array element are: "<<&array[0]<<endl;
	if(y>1){
		int rest= y-1;
	cout<<"\nThere is more than one element, here are the address of the last "<<rest<<" elements: \n";
	for (int i = 1; i < y; ++i)
	{
		cout<<&array[y]<<endl;
	}
	}
}
```
##b)
###To test the DisplayPointerInfo(...)function, declare two integer pointers a and b to dynamically allocate arrays of integers for n elements (n should be an input from the user).
###Array a will be filled with even numbers, and array b will be filled with odd numbers.

I give my code a couple of functions to do the task, **displayPointerInfo** and **displayElementValue** these two functions let me se that the dynamically allocate of array is fullfilled, I can now se that my two arrays have been filled, one with **even** and one with **odd**, the user chooses have many slots there are in the arrays with value **n**.

What I get in cmder:
```
Write the size of the array: 4                                               
The value of the first array                                                 
                                                                             
The number of the first array element are: 2                                 
                                                                             
There is more than one element, here are the numbers of the last 3 elements: 
4 6 8                                                                        
The pointer adress of the first element of the array are: 0x7019b0           
                                                                             
There is more than one element, here are the address of the last 3 elements: 
0x7019c0                                                                     
0x7019c0                                                                     
0x7019c0                                                                     
The value of the second array                                                
                                                                             
The number of the first array element are: 1                                 
                                                                             
There is more than one element, here are the numbers of the last 3 elements: 
3 5 7                                                                        
The pointer adress of the first element of the array are: 0x7019c8           
                                                                             
There is more than one element, here are the address of the last 3 elements: 
0x7019d8                                                                     
0x7019d8                                                                     
0x7019d8                                                                     
```

The code:
```c++
#include <iostream>

using namespace std;

void displayPointerInfo(int* array,int y);
void displayElementValue(int* arra,int x);
int* createArray(int t);

int main()
{
	int n;
	
	cout<<"Write the size of the array: ";
	cin>>n;
	int *Aeven = createArray(n);
	int *Bodd = createArray(n);
	
	for (int i = 0; i < n; ++i)
	{
		Bodd[i] = 2*i+1;
		Aeven[i] = 2*i+2;
	}


	cout<<"The value of the first array"<<endl;
	displayElementValue(Aeven,n);
	displayPointerInfo(Aeven,n);
	cout<<"The value of the second array"<<endl;
	displayElementValue(Bodd,n);
	displayPointerInfo(Bodd,n);
	return 0;
}

int* createArray(int t){
	int* tom = new int[t];
	return tom;
}
void displayPointerInfo(int* array,int y)
{	
	cout<<"\nThe pointer adress of the first element of the array are: "<<&array[0]<<endl;
	if(y>1){
		int rest= y-1;
	cout<<"\nThere is more than one element, here are the address of the last "<<rest<<" elements: \n";
	for (int i = 1; i < y; i++)
	{
		cout<<&array[y]<<endl;
	}	
	}
}
void displayElementValue(int* arra,int x)
{	
	cout<<"\nThe number of the first array element are: "<<arra[0]<<endl;
	if(x>1){
		int rest= x-1;
	cout<<"\nThere is more than one element, here are the numbers of the last "<<rest<<" elements: \n";
	for (int j = 1; j < x; j++)
	{		
		cout<<arra[j]<<" ";
	}	
	}
}

```
##Problem 5
###Define an int* pointer variable a. Then:
##a)
###Use new to make a point to a dynamic array of 5 cells of type int.

What I got in cmder:
```
Type in 5 values to the array:
5
7
16
12
15
the numbers you have written is: 5 7 16 12 15
0xe61da0 0xe61da4 0xe61da8 0xe61dac 0xe61db0
```

Here I have made a integer pointer to a new 5 integer array.
```
int* a= new int[5];
```
##b)
###Write a loop to fill a with values 5, 7, 16, 12, 15.
Letting the user type in the 5 values to store in the array. Using a for loop to make the user type in the right way.
```
cout<<"Type in 5 values to the array: "<<endl;
	for (int i = 0; i < 5; ++i)
	{
		
		cin>>a[i];
	}
```
##c)
###Using Hex, print the pointer address stored in a.
##d)
###Write a loop to print the values in a with one cell per line.
Using for loop to print the values, I also use a **&** in front of my array to print the hex values.
```
cout<<"the numbers you have written is:\n";
	for (int i = 0; i < 5; ++i)
	{
		cout<<&a[i]<<"\n";
	}
```
##e)
###Delete the dynamic memory allocated to a using delete [ ].
Deleting array a when the program have runned through using **delete[] a**
```
delete[] a;
```

The code:
```c++
#include <iostream>

using namespace std;

int main()
{
	int* a= new int[5];

	cout<<"Type in 5 values to the array: "<<endl;
	for (int i = 0; i < 5; ++i)
	{
		
		cin>>a[i];
	}
	cout<<"the numbers you have written is:\n";
	for (int i = 0; i < 5; ++i)
	{
		cout<<&a[i]<<"\n";
	}
	delete[] a;
	return 0;
}
```
##Problem 6
###Define a struct named Date to keep track of dates. Provide functions that read dates from an input and finally display dates as an output.

Setting up my struct with **day**, **month** and **year**. Letting the user type in the date in **(dd.mm.yyyy)** format, and transform the month from number to string text with month name. Giving the code a couple of while loop so the user is made to type in a valid day and month, so we dont get more days then there is in the particular month.

What I got in cmder:
```
Type in the date:
14
Type in month:
5
Type in year:
1991
You typed in :
14. May. 1991
```
The code:
```c++
#include <iostream>
#include <string>

using namespace std;

 struct _Date {
int day;
string month;
int year;
}date;

void readDate (_Date Date);
int main()
{ 
	int mo,days;
	string m[12]={"January","February","March","April","May","June","July","August","September","October","November","December"};
	int d[12]={31,28,31,30,31,30,31,31,30,31,30,31};

	cout<<"Type in the date:"<<endl;
	cin>>days;
	cout<<"Type in month:\n";
	cin>>mo;
	cout<<"Type in year:\n";
	cin>>date.year;

	while(mo>12){	
		cout<<"There are not more than 12 months!\n Try again"<<endl;
		cout<<"Type in month:\n";
		cin>>mo;
		break;
	}

	while(days>=d[mo-1]){
		cout<<"There are not "<<days<<" in this month"<<endl;		
		cout<<"Type in the date:"<<endl;
		cin>>days;
		break;
	}
			
	date.day = days;
	date.month=m[mo-1];
	
	cout<<"You typed in :"<<endl;
	readDate (date);

	return 0;
}
void readDate (_Date Date)
{
	cout<<Date.day<<". "<<Date.month<<". "<<Date.year<<endl;
	
}
```
##Problem 7
###Write a C++ program with a class having two private variables and one member function which will return the area of a triangle.

Creating a class Triangle giving it two private floats, **height** and **width**. Then I made an float inside the class public to find the area of the triangle with the values it recieves from set_values. The user is the one choosing the height and width of the triangle.

What i got in cmder:
```
This program will find the area of an Triangle.
Type in the height: 5

Type in the width: 7

The height the triangle is: 5 and the width is: 7
The area of the Triangle is then: 17.5
```
The code:
```c++
#include <iostream>

using namespace std;

class Triangle{
	float height, width;
public:
	void set_values (int,int);
	float area() {return (width*height)/2;}	

};
void Triangle::set_values(int x, int y){
	width = x;
	height = y;
	
}
int main()
{
	cout<<"This program will find the area of an Triangle. "<<endl;
	float Height, Width;
	cout<<"Type in the height: ";
	cin>>Height;
	cout<<"\nType in the width: ";
	cin>>Width;

	Triangle triangle;
	triangle.set_values(Width,Height);
	cout<<"\nThe area of the Triangle is: "<<triangle.area()<<endl;
	
	return 0;
}
```
##Problem 8
###Write a C++ program with a class that takes 10 input integers in the main function and pass them to the default constructor of the class. 
Finally, your program should return (display) the sum of the 10 input numbers.

Letting the user type in 10 integers that is stored in an array in the class data. Here i also use sum_num to make a for loop to add togheter the ten integers to a final sum, returning the sum to write it out in main.

What I get in cmder:
```
Enter ten integers:
421
512
421
3412
5
15123
43124
32152
123
415
The addition result from numbers:
421 + 512 + 421 + 3412 + 5 + 15123 + 43124 + 32152 + 123 + 415 = 95708
```

The code:
```c++
#include <iostream>
using namespace std;

class data{
private:
	int* m_array;
	int m_N;
public:
	
	data (int* arrayP, int N)
	{
	 m_array = arrayP;	
	 m_N = N;
	}
	int sum_num(){
		int sum = 0;
		for(int i=0; i<m_N; i++){
			sum+= m_array[i];
		}
		return sum;
	}	
};
int main (){

	int num[10];
	cout<<"Enter ten integers: \n";
	for (int i = 0; i < 10; ++i)
	{
		cin>>num[i];
	}	

	data su_num(num, 10); 

	cout << "The addition result from numbers: "<<endl;
	for (int i = 0; i < 10; ++i)
	 {	
	 	if(i<9){
	 	cout<<num[i]<<" + ";
	 }
	 else
	 cout<<num[i]<<" = ";
	 } 
	cout<<su_num.sum_num()<<"\n";
	
	return 0;
}
```
##Problem 9
###Perform addition operation on complex data using class and object. 
###The program should ask for real and imaginary part of two complex numbers, and display the real and imaginary parts of their sum.

In my code I made a class Imaginary to store det values, did most off mye code in the main. Used a double to create and store the real values and made som simple addition variables to put the values togheter to a final sum.

What I got in cmder console:
```
First number.
Enter the real part:4
Now enter the imaginary part:7
Second number.
Enter the real part:4
Now enter the imaginary part:2
 real: 8 Imaginary: 11
```

The code:
```c++
#include <iostream>
using namespace std;

class Imaginary{
public:

	double x,y;
	Imaginary(double nx, double ny){
		x=nx;y=ny;
	}
};

int main(){
	
	double a,b;	
	cout<<"First number. \n" << "Enter the real part:";
	cin>> a;
	cout<< "Now enter the imaginary part:";
	cin>> b;
	Imaginary number1(a,b);
	
	double c,d;
	cout<<"Second number. \n"<< "Enter the real part:";
	cin>> c;
	cout<< "Now enter the imaginary part:";
	cin>> d;
	
	Imaginary number2(c,d);
	Imaginary number3(0,0);
	double real;

	real = number1.x +number2.x;

	double imaginary;

	imaginary = number2.x + number1.y;

	number3.x = real;
	number3.y = imaginary;
	
	cout<<" real: "<<number3.x<<" Imaginary: "<<number3.y;

	return 0;
}

```
##Problem 10
###Write the definition for a class called Distance that has data member feet as integer and inches as float. The class has the following member functions:
###void set(int, float) to give value to object void disp() to display distance in feet and inches Distance add(distance) to sum two distances & return distance
###Write a main function to create three distance objects. Set the value in two objects and call add() to calculate sum and assign it in the third object. 
###Finally, display all distances.

Here I used class Distance to set int feet and float inches private, then I gave the class a public with setdist to recieve feet and inches values from cin in main. Then I made a couple of functions to define members outside the class itself, one that adds togheter inches and feet, and one to display the values in console when they're added togheter. In main I give the user the possibility to type inn two inches values, and two feet values. I made default constructors distance1, distance2 and distance3 so the users typed values can be used in class, and so main can write out the values again in console.

What i get in cmder:
```
Type in the first feet value: 15

Type in the first inch value: 6

Type in the second feet value: 17

Type in the second inch value: 32

 distance 1 = 15' 6"
 distance 2 = 17' 32"
 distance 3 = 33' 26"
```
The code:
````c++
#include <iostream>

using namespace std;
class Distance
{
	int feet;
	float inches;
public:
	void setdist(int ft,float in)
	{
		feet=ft;
		inches=in;
	}
	Distance add(Distance);
	void disp();
};
Distance Distance::add(Distance D)
{
	Distance t;
	t.inches=inches + D.inches;
	t.feet=0;
	if(t.inches>=12.0)
	{
		t.inches-=12.0;
		t.feet++;
	}
	t.feet +=feet+ D.feet;
	return t;

}
void Distance::disp()
{
	cout<<feet<<"\' "<<inches<<"\"";
}

int main()
{	
	int fet1,fet2;
	float inc1,inc2;
	cout<<"Type in the first feet value: ";
	cin>>fet1;
	cout<<"\nType in the first inch value: ";
	cin>>inc1;
	cout<<"\nType in the second feet value: ";
	cin>>fet2;	
	cout<<"\nType in the second inch value: ";
	cin>>inc2;
	Distance distance1,distance2,distance3;
	distance1.setdist(fet1,inc1);
	distance2.setdist(fet2,inc2);
	distance3=distance1.add(distance2);

	cout<<"\n distance 1 = ";
	distance1.disp();
	cout<<"\n distance 2 = ";
	distance2.disp();
	cout<<"\n distance 3 = ";
	distance3.disp();

	
	return 0;
}
```
