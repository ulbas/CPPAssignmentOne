##Problem 1
###Write a class to contain the following information about towns: the name (a sequence of characters); the population (an integer); and a Boolean value (i.e. true or false) which 
indicates whether the town has an airport or not. Make the three data members private. Include a constructor that initialises the data members.

The code:
```c++
#include <iostream>
#include <string>

using namespace std;

class Town
{
private:
	int popul;
	bool airport;
	string name;

public:
	Town(string n, int p, bool a);
	
};
Town::Town(string n,int p, bool a){

	name= n;
	popul=p;
	airport=a;

}

int main()
{
	Town townone("Oslo",542416,true);
	return 0;
}
```
##Problem 2
###Now add three new member functions to the towns class that assign values to the three data members. Also add a member function to print out all the information about a town. The 
member functions should all be publicly accessible. Write a main()function which declares three town objects and assigns the following values to them:

What i get in console:
```
Oslo    1019000 TRUE
Bergen  275100  TRUE
Lillestrøm      14000   FALSE
```
The code:
```c++
#include <iostream>
#include <string>

using namespace std;

class Town
{
private:
	int popul;
	bool airport;
	string name;

public:
	Town(string n, int p, bool a);
	void setName(string n);
	void setPop(int p);
	void setAir(bool a);
	void displaytown();
	
};
Town::Town(string n,int p,bool a){

	name= n;
	popul=p;
	airport=a;
	
}
void Town::setName(string n)
{
	name=n;
	
}
void Town::setPop(int p){
	
	popul=p;
}
void Town::setAir(bool a){
	airport=a;
}
void Town::displaytown()
{

	cout<<name<<"\t"<<popul<<"\t";
	if (airport==1)
		cout<<"TRUE"<<endl;

	else if(airport==0)
		cout<<"FALSE"<<endl;
	
}

int main()
{	
	Town tone("",0,0);
	Town ttwo("",0,0);
	Town tthree("",0,0);
	tone.setName("Oslo");
	ttwo.setName("Bergen");
	tthree.setName("Lillestr\233m");
	tone.setPop(1019000);
	ttwo.setPop(275100);
	tthree.setPop(14000);
	tone.setAir(1);
	ttwo.setAir(1);
	tthree.setAir(0);
	tone.displaytown();
	ttwo.displaytown();
	tthree.displaytown();

	return 0;
}
```
##Problem 3
###Write a class called Point. The class should have two private float data members x and y. Write two constructors: one default constructor that initialises the data members to 0, and one that takes two arguments and uses them to initialise the two data members. Also write the following member functions:void SetXY (float, float) assigns the two arguments to the two data members float GetX () returns the value of the x data member float GetY ()returns the value of the 
y data member void Move (float, float) moves the point by the specified amount void Display () displays the values of the arguments Write a main function that allows  the  user  to  enter  the x and y coordinates of two Point objects and then calculates  and  prints  the  equation  of  the  straight  line  that  joins  the  two 
points. A straight line is defined by the equation y = mx + c, so the values of m and c can be calculated as follows:
m = (y2–y1) / (x2–x1)
c = y1-mx1
```
```
```c++
#include <iostream>

using namespace std;

class Point
{
private:
	float x,y;
public:
	Point();
	Point(float a,float b);
	void SetXY(float a,float b);
	float GetX();
	float GetY();
	void Move(float a,float b);
	void Display();
	
};
Point::Point(void){
	x=0;
	y=0;
}
Point::Point(float a, float b){
	x=a;
	y=b;
}
void Point::SetXY(float a,float b){
	x=a;
	y=b;
}
float Point::GetX(){
	return x;
}
float Point::GetY(){
	return y;
}
void Point::Move(float a, float b){
	x = x+a;
	y = y+b;
}
void Point::Display(){

	cout<<"X = "<<x<<" and Y = "<<y<<endl;
}
int main()
{
	float e,f;
	float m,c;
	cout<<"For the first point."<<endl;
	cout<<"Enter the x-value."<<endl;
	cin>>e;
	cout<<"Enter the y-value."<<endl;
	cin>>f;
	Point point1(e,f);
	cout<<"For the second point."<<endl;
	cout<<"Enter the x-value."<<endl;
	cin>>e;
	cout<<"Enter the y-value."<<endl;
	cin>>f;
	Point point2(e,f);
	
	m = (point2.GetY()-point1.GetY())/(point2.GetX()-point1.GetX());
	c = m*point1.GetX();
	cout<<"y = "<<m<<"x + "<<c<<endl;
	return 0;
}
```
##Problem 4
###Now write a new class called Triangle. A triangle consists of 3 points. The Triangle class should have one default constructor and another constructor that initialises the three points  
of the triangle. It should also have a member function that calculates the area of the triangle according to the formula where a, b and c are the lengths of the three sides, and s is half of the sum of the three sides.  
Write a main function that inputs three points from the user, and prints out the area of the triangle they form.

What i get in console:
```
For the first point. 
Enter the x-value.   
5                    
Enter the y-value.   
5                    
For the second point.
Enter the x-value.   
10                   
Enter the y-value.   
8                    
y = 0.6x + 3         
                     
```
The code:
```c++
#include <iostream>

using namespace std;
class Triangle
{
private:
	float x,y,z;
public:
	Triangle();
	Triangle(float a,float b, float c);
	
	
};
Triangle::Triangle(void){

}
Triangle::Triangle(float a, float b, float c){
	a=Point.setX;
	b=Point.setY;
	c=Point.setZ;
}
float Triangle::setSum(){
 float s=
}
class Point
{
private:
	float x,y;
public:
	Point();
	Point(float t,float r);
	setX(float t,float r);
	setY(float t,float r);
	setZ(float t,float r);
};
Point::Point(float t,float r){
	x=t;
	y=r;
}
float Point::setX(float t, float r){
	float g=(t,r);
	return g;
}
float Point::setY(float t, float r){
	float h=(t,r);
	return h;
}
float Point::setZ(float t, float r){
	float j=(t,r);
	return j;
}

int main()
{
	Point.setX(1,2);
	Point.setY(4,6);
	Point.setZ(3,1);

	return 0;
}
```
##Problem 5
###A video shop needs to store information about the films it stocks. It has two types of film: 
video-cassettes and DVDs. Create a Film class that has two public data members title (a char*) and length (an int). Next create two classes called Cassette and   
DVD that are both derived from Film. The Cassette class should contain an extra public data member called condition (an enum type that can take the values perfect,  
good, average or poor). The DVD class should contain an extra public data member called region (an int). Both Cassette and DVD should have an extra public member function called  
Print that displays all data members. Write a short main function that creates objects to store information about two films and then displays the information to the screen:  
“Titanic” (a DVD, 180 minutes long, region 1) and “Kezkaza Welafen” (a video cassette, 100 minutes long, good condition).

What i get in console:
```
Kezkaza Welafen is a video cassette, 100 minutes long, the condition is Good  
                                                                              
Titanic is a DVD, 180 minutes long, region 1                                  
```
The code:
```c++
#include <iostream>

using namespace std;
class Film
{
public:
	
	char* title;
	int length;
	
	
};
class DVD:public Film
{
public:
	int region;
	
	void print(void);
	
};
void DVD::print(void){
	cout<<"\n"<<this->title;
	cout<<" is a DVD, "<<this->length<<" minutes long, region "<<this->region<<endl;
}
class Cassette:public Film
{
public:
	enum condition {Perfect,Good,Avarage,Poor};	
	
	void print(void);
	condition cond;	
	
};
void Cassette::print(void){
	cout<<this->title;
	cout<<" is a video cassette, "<<this->length<<" minutes long, the condition is ";
	switch (cond){
		case 0: cout<<"Perfect"<<endl; break;
		case 1: cout<<"Good"<<endl; break;
		case 2: cout<<"Avarage"<<endl; break;
		case 3: cout<<"Poor"<<endl; break;
	}
}

int main(int argc, char const *argv[])
{	
	char name1[100]= "Kezkaza Welafen";
	char name2[100]= "Titanic";
	Cassette film1;
	DVD film2;
	
	film1.title=name1;
	film1.length =100;
	film1.cond = film1.Good;
	//film1;
	
	film2.title=name2;
	film2.length =180;
	film2.region=1;
	film1.print();
	film2.print();
	return 0;
}
```
##Problem 6
###Create the ZooAnimal inheritance hierarchy shown below. Every animal in the hierarchy should have a char* data member called name. Every Bear,  
Koala or Panda should have an int data member called gestationPeriod. Every Fish or Shark should have a float data member called speed.  
Every  animal  in  the  hierarchy  should  include  a  function  called feedingTime() that prints out details of when an animal should be fed. The actual feeding time will be different  
for each animal but every animal should have a feeding time. Every type of bear should include a function called makenoise() that prints out the noise made by the animal. The  
actual noise made will be different for each type of bear. Fish do not make any noise.
```
```
```c++
#include <iostream>
#include <cstdlib>
using namespace std;
class ZooAnimal
{
public:
	char* name;
	name=n;
	void feedingTime(int a);	
};
void ZooAnimal::feedingTime(int a){
	cout<<"The animal should be fed at: "<<a<<". O'clock."<<endl;
}

class Bear:public ZooAnimal
{
public:	
	int gestationPeriod;
	void makenoise(char* n){
cout<<"The bear make the following noise: "<<n<<"\n"<<endl;
}
};

class Fish:public ZooAnimal
{
public:
	float speed;	
};
class Shark:public Fish
{
public:
};
class Koala:public Bear
{
public:
	char noise[50]="wakkaaaah";
	char* n=noise;
};
class Panda:public Bear
{
public:	
	char noise[50]="raaaawrrr";	
	char* n=noise;
};

int main()
{
	char name[50];"Pamba";
	Panda bear1;
	bear1.n =name;
	bear1.gestationPeriod =9;
	cout<<"This bear is named: "<<bear1.n<<"."<<endl;
	bear1.makenoise(bear1.n);
	cout<<bear1.n<<"\'s gestation period is: "<<bear1.gestationPeriod<<" months."<<endl;
	bear1.feedingTime(5);
	
	return 0;
}
```
##Problem7
###Write a C++ program to create two files named abc.txt which contains the text I love C++  Programming and def.txt which contains the text I love Java Programming.  
Now, copy the contents of these two files to a new file named xyz.txt. Finally, display the appropriate message on successful completion of the task, for exmaple:  
“the contents of file abc.txt and def.txt are successfully copied to xyz.txt”.

What i get in console:
```
The contents of file abc.txt and def.txt are successfully copied to xyz.txt
```
The code:
```c++
#include <iostream>
#include <fstream>

using namespace std;

int main()
{
	char ch;
	ofstream file1;
	ifstream file2;
	ofstream file3;
	file3.open("xyz.txt");

	file1.open("abc.txt");
	file1 << "I love C++ Programming"<<endl;
	file1.close();
	file1.open("def.txt");
	file1 << "I love Java Programming"<<endl;
	file1.close();

	file2.open("abc.txt");
	while(!file2.eof())
	{
		file2.get(ch);
		file3<<ch;
	}
	file2.close();
	file2.open("def.txt");
	while(!file2.eof())
	{
		file2.get(ch);
		file3<<ch;
	}
	file3.close();
	cout<<"The contents of file abc.txt and def.txt are successfully copied to xyz.txt"<<endl;
	return 0;
}
```
