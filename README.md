#Assignment 2

##Problem 1
####Write a C++ program to sort an array of numbers in an ascending order and descending order based on user’s choice and display them.

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
###Write a C++ program to sort string (name) in an alphabetical order. For example if a user enters a string "bye", then the 
###output of the program will be "bey".

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

##a)
###Declare and implement a function CreateArray(...) that returns a pointer to an array of n integers.
```
int* createArray(int n){
	int* tom = new int[n];
	return tom;
}
```
##b)
###Declare and implement a function DeleteArray(...) that takes and deletes an array of integers.
```
void deleteArray(int* array)
{
	delete[] array;

}
```
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
```
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
```c++

```
##b)
###To test the DisplayPointerInfo(...)function, declare two integer pointers a and b to dynamically allocate arrays of integers for n elements (n should be an input from the user).
###Array a will be filled with even numbers, and array b will be filled with odd numbers.

##Problem 5
###Define an int* pointer variable a. Then:
##a)
###Use new to make a point to a dynamic array of 5 cells of type int.
##b)
###Write a loop to fill a with values 5, 7, 16, 12, 15.
##c)
###Using Hex, print the pointer address stored in a.
##d)
###Write a loop to print the values in a with one cell per line.
##e)
###Delete the dynamic memory allocated to a using delete [ ].

##Problem 6
###Define a struct named Date to keep track of dates. Provide functions that read dates from an input and finally display dates as an output.

##Problem 7
###Write a C++ program with a class having two private variables and one member function which will return the area of a triangle.

##Problem 8
###Write a C++ program with a class that takes 10 input integers in the main function and pass them to the default constructor of the class. 
Finally, your program should return (display)the sum of the 10 input numbers.

##Problem 9
###Perform addition operation on complex data using class and object. 
###The program should ask for real and imaginary part of two complex numbers, and display the real and imaginary parts of their sum.
##Problem 10
###Write the definition for a class called Distance that has data member feet as integer and inches as float. The class has the following member functions:
###void set(int, float) to give value to object void disp() to display distance in feet and inches Distance add(distance) to sum two distances & return distance
###Write a main function to create three distance objects. Set the value in two objects and call add() to calculate sum and assign it in the third object. 
###Finally, display all distances.
