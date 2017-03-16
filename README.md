##Exercise 1  
###Write a C++ program that calculates n^n by declaring your own function. Note: n is an input from the user.

This exercise was easy to solve, I just let the user type in value n, value n was then sent to function calculate where i used a for loop to find `n^n`.

Input and Output i cmder:
```
Type in a value n to calculate the n^n value
5
The value is: 3125
```
The code:
```c++
#include <iostream>

using namespace std;
int calculate(int t);
int main()
{
	int n,number;
	cout<<"Type in a value n to calculate the n^n value"<<endl;
	cin>>n;
	number=calculate(n);
	cout<<"The value is: "<<number<<endl;
	return 0;
}
int calculate (int t){
	int P=t;
	for (int i = 1; i < t; ++i)
	{
		P*=t;
	}
	return P;
}

```
##Exercise 2  
###Write a C++ program that sorts strings in alphabetical order (from a to z).

Here I used algorithm and string library, so it was easier to take a string and sort it from a-z. The reason I get the "S" before "aekt" is that the "S" is typed in as a uppercase.

What I got in cmder
```
Please enter a sentence:  
Stake                     
                          
The sentence is now: Saekt

```
The code:
```c++
#include <iostream>
#include <algorithm>
#include <string>

using namespace std;

int main()
{
	string n;
	cout<<"Please enter a sentence: "<<endl;
	cin>>n;
	sort(n.begin(),n.end());
	cout<<"\nThe sentence is now: "<<n;
	return 0;
}

```
##Exercise  3  
###Write a C++ program using an array that can hold twenty integers which should be input from the user. Display those input values on the screen, and then prompt the user for an element to be searched in this array.  
Finally, count the number of times the input element is foundin the array.

Here I'm giving the user the choice to pick the size of the array and what number to look for. I'm using two for loop, one to write the values to the array and one to print them in console, I also use an if statement in the first for loop to count every time the value we look for is typed.

What i got in the cmder:
```
Type in how many numbers you want to store:
5
What number do you want to look for?
4
You want to store, 5 numbers.
Now type in the numbers
2
3
4
5
4
You typed in the values:
2 3 4 5 4 You wanted to look for the number '4' this number is stored 2 times in the array.
```
The code:
```c++
#include <iostream>
#include <vector>

using namespace std;

int main()
{
	//vector<int> values;

	int n,r,u=0; 
	//int input;
	cout<<"Type in how many numbers you want to store: "<<endl;
	cin>>n;
	cout<<"What number do you want to look for?"<<endl;
	cin>>r;
	int *P= new int[n];
	cout<<"You want to store, "<<n<<" numbers.\nNow type in the numbers"<<endl;
	for (int i = 0; i < n; ++i)
	{			
		//cin>>input; 
		//values.push_back(input);
		cin>>P[i];
		if (P[i]==r){
			u++;

		}
		
	}
	cout<<"You typed in the values:"<<endl;
	for (int j = 0; j < n; ++j)
	{
		cout<<P[j]<<" ";
	}
	delete[] P;
	cout<<"You wanted to look for the number '"<<r<<"' this number is stored "<<u<<" times in the array."<<endl;
	return 0;
}
```
##Exercise 4  
###Write a C++ program that creates a vector of 15 integer elements. Using an iterator, assign each element a value that is three times of its current value.

Here i created a vector that holds 15 integers by using a for loop to give it values from 1-15. These numbers are used to give new values three times the size of the original value. I also used for loop for displaying the values for the user in cmder.

What i got in cmder:
```
You hav now stored the numbers:
1 2 3 4 5 6 7 8 9 10 11 12 13 14 15
Now the integers is three times its original size, and the value is now:
3 6 9 12 15 18 21 24 27 30 33 36 39 42 45
```
The code:
```c++
#include <iostream>
#include <vector>

using namespace std;

int main()
{
	vector<int> elements;

	for (int i = 1; i < 16; ++i)
	{
		
		elements.push_back(i);

	}
	cout<<"You hav now stored the numbers: "<<endl;
	for (int i = 0; i < 15; ++i)
	{   

		cout<<elements[i]<<" ";
	}


	for (int i = 0; i < 15; ++i)
	{

		elements[i]=elements[i]*3;
	}
	cout<<"\nNow the integers is three times its original size, and the value is now: "<<endl;
	for (int i = 0; i < 15; ++i)
	{
		cout<<elements[i]<<" ";
	}

	return 0;
}

```
##Exercise 5  
###Write a C++ program that accepts five integer values from the user using pointers.

I set up an array with the room for 5 integers, the I set up the possibility to write to this array with an pointer form a for loop, then I use those same pointers to print the values that I have stored in the array.

What i get in cmder:
```
Please enter your five values:
6
8
3
4
1
Your numbers are:
6 8 3 4 1
```
The code:
```c++
#include <iostream>

using namespace std;

int main(int argc, char const *argv[])
{
	int arr[5];
	int *p=arr;

	cout<<"Please enter your five values: "<<endl;
	
	for (int i = 0; i < 5; ++i)
	{
		cin>>*(p+i);
	}
	
	
	cout<<"Your numbers are: "<<endl;
	
	for (int i = 0; i < 5; ++i)
	{
		cout<<*(p+i)<<" ";
	}
	return 0;
}

```
##Exercise 6  
###Write a C++ program that prints the elements of an array in a reverse order using pointers.

In this code I gave the user possibility to choose the size of the array, and to type in the values to store. Then I use an new for loop to read the values in revers order and displaying them in console.

What I get in cmder:
```
Enter the size of the array:
5                           
                            
The size is chosen to be 5. 
Now type in your integers:  
8                           
4                           
5                           
2                           
3                           
                            
                            
3 2 5 4 8                   
```
The code:
```c++
#include <iostream>

using namespace std;

int main()
{
	int n;
	cout<<"Enter the size of the array: "<<endl;
	cin>>n;
	int *p=new int[n];
	cout<<"\nThe size is chosen to be "<<n<<".\nNow type in your integers: "<<endl;
	for (int i = 0; i < n; ++i)
	{
		cin>>p[i];
	}
	cout<<"\n"<<endl;
	for (int j=n-1; j >= 0 ; j--)
	{
		cout<<p[j]<<" ";
	}
	return 0;
}

```
##Exercise 7  
###Write a C++ program that finds the maximum of an integral data set.   
The program will first ask the user to input the number of data values in the set and   
finally should display a pointer that points to the maximum value of the data set. 

I used a function to find the highest value typed in by the user. This value I displayed again in console, and I used this values to let med print its adress using a pointer.

What I get in cmder:
```
Enter number of data values:
4
Enter value 1'th: 4
Enter value 2'th: 9
Enter value 3'th: 4
Enter value 4'th: 1
The highest value is: 9
The the adress is: 0xf31f28
```
The code:
```c++
#include <iostream> 

using namespace std;

int *findMax(int arr[],int n);

int main(){    
	int n,i,*p;    
	cout<<"Enter number of data values:"<<endl;    
	cin>>n;    
	int *t =new int[n];        
	for(i=0;i<n;i++)    
	{      
		cout<<"Enter value "<<i+1<<"'th: ";      
		cin>>t[i];            
	}          
	p=findMax(t,n);    

	cout<<"The highest value is: "<<*p<<"\nThe the adress is: "<<p;    
	    
	return 0;
}  

int *findMax(int data[],int n){    
	int *max=data;    
	int i;    
	for(i=1;i<n;i++){           
		if(*max<*(max+i)) *max=*(max+i);                             
	}    
	return max;
}

```
##Exercise 8  
###Write a C++ class having private variables and two member functions which will return the area of a rectangle and a triangle.

Setting up a class Area where I store both the height and the width of my triangle and rectangle. I give my class two member functions where I do the math to find the size of the area and returning the value to use. In main I let the user type in the width and height of the triangle and the rectangle.

What i get in cmder:
```
Set the Height and Width for the area of the rectangle and the triangle:

Height: 8

Width: 10

The size of the 'Rectangle' is: 80, and the size of the 'Triangle' is: 40
```
The code:
```c++
#include <iostream>

using namespace std;

class Area{
	float height,width;

public:
	void set_values(int,int);
	float areatri(){
		float area1=(height*width)/2;
		return area1;
	}
	float arearec(){
		return height*width;
	}	

};
void Area::set_values(int x, int y){
	width = x;
	height = y;
}

int main()
{	
	float a,b;
	cout<<"Set the Height and Width for the area of the rectangle and the triangle: "<<endl;
	cout<<"\nHeight: ";
	cin>>a;
	cout<<"\nWidth: ";
	
	cin>>b;
	Area figure;
	figure.set_values(a,b);	

	cout<<"\nThe size of the 'Rectangle' is: "<<figure.arearec()<<", and the size of the 'Triangle' is: "<<figure.areatri()<<endl;
	return 0;
}

```
##Exercise 9  
###Write a C++ program that takes an input of two integers in the main function and pass them to a default constructor of the class. Finally, display the result of an addition, subtraction, multiplication and division of the input integers.

Setting up a class to store the values the user types in, here I also sett up 4 funtions in public where I take this two values and do the tasks the exercise asks for(addition, substraction, multiplication and division). I also give the class Kalk a constructor so I can impliment more objects, without making any syntax errors. 

What I get in cmder:
```
Type in two integers so the code can find the addition, substraction, multiplication and the division of the two numbers.

Type in the first number: 8
and now the second: 6

Here are the values of 8 and 6
8 + 6 = 14
8 - 6 = 2
8 x 6 = 48
8 / 6 = 1.33333

```
The code:
```c++
#include <iostream>

using namespace std;
class Kalk{
	int one,two;
public:
	Kalk(int x,int y);
	int addition(){
		return one+two;
	}
	int substr(){
		return one-two;
	}
	int multipli(){
		return one*two;
	}
	float divis(){
		
		return 1.0*one/two;
	}


};
Kalk::Kalk(int x,int y){
	one = x;
	two = y;
	cout<<"\nHere are the values of "<<one<<" and "<<two<<endl;
}
int main()
{
	int a,b;
	cout<<"Type in two integers so the code can find the addition, substraction, multiplication and the division of the two numbers.\n\nType in the first number: ";
	cin>>a;
	cout<<"and now the second: ";
	cin>>b;

	Kalk first(a,b);
	
	
	cout<<a<<" + "<<b<<" = "<<first.addition()<<endl;
	cout<<a<<" - "<<b<<" = "<<first.substr()<<endl;
	cout<<a<<" x "<<b<<" = "<<first.multipli()<<endl;
	if (first.divis()<=0)
		cout<<a<<" / "<<b<<" = "<<"Not possible!"<<endl;
	else	
		cout<<a<<" / "<<b<<" = "<<first.divis()<<endl;
	return 0;
}

```
##Exercise 10  
###Write a C++ class named point that has three coordinates x,y, and z, where the coordinates are private.  
Create a function which is external to the class that computes the dot product between the coordinates.  
(Note: How do we access private members? Refer to the lecture slides on classes. Hint: friend functions)  
Note: In mathematics, the dot product or scalar product is an algebraic operation that takes two equal-length  
sequences of numbers (usually coordinate vectors) and returns a single number.
\*Example: The dot product of vectors [1, 3, -5] and [4, -2, -1] is: (1)(4) + (3)(-2) + (-5)(-1) =3*\

Creater a class Point, here i store the values of the x,y and z. In the public area i include the friend member function *int dot* where I have my two vectors. In the int dot I multiply the x,y and z from the two vectors so I end up with just one `x,y,z` her called `a,b,c` so I can find the product easier. In main I give the object dot the new name dotProduct so I can use it in my cout so I dont have to type in the value all the time.

What I get in cmder:
```
The dotProduct is :3
```
The code:
```c++
#include <iostream>
using namespace std;

class Point {

private:
int p_x,p_y,p_z;

public:
	Point(int x,int y, int z) : p_x(x),p_y(y),p_z(z){
	}
 	friend int dot(Point p1, Point p2);
};

int dot(Point p1, Point p2){
    int a,b,c,sum;
    a=p1.p_x*p2.p_x;
    b=p1.p_y*p2.p_y;
    c=p1.p_z*p2.p_z;
    sum=a+b+c;
    return sum;
}


int main() {
	
    Point p1(1,3,-5);
    Point p2(4,-2,-1);

    int dotProduct = dot(p1,p2);
 	cout<<"The dotProduct is :"<<dotProduct<<endl;
    return 0;
}




```
