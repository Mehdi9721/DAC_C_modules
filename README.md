# DAC_C_modules
# C++
## d-155
stating with conditional operators and many more
#### msys2 compiler for c++
c++ installed in vs studio 
## 27-09-2023
loop completed <br>
for(;;); <br>
## D-147
## 4-10-23
### function pointer
##### int (*fun)(int,int);

#include <iostream>
using namespace std;
//function pointer
int (*fun)(int,int);
int sum(int,int);
int sum(int,int,int);
int main(){
int a=10,b=15,c=50;
fun=sum;
cout<<fun(a,b)<<" with fun pointer\n";
cout<<"\n"<<sum(a,b,c)<<"  with direct 3 argument on calling sum\n";
fun=sum;
cout<<"\n"<<fun(a,b,c)<<"\n";
return 0;
}
int sum(int a,int b){
return a+b;
}
int sum(int a,int b,int c){
return a+b+c;
}
<br>
///////////////////////////////////////////////////////////////////////////
### assignment 04-10-23
find sum... using function pointer <br>
int (*fun)(int,int); <br>
#include<iostream>
using namespace std;
int (*fun)(int,int);
int sum(int,int);
int sub(int,int);
int mul(int,int);
int main(){
//using function pointer doing sum mul
int a=40,b=30;
fun=sum;
cout<<"\n sum :="<<fun(a,b);
fun=sub;
cout<<"\n sub :="<<fun(a,b);
fun=mul;
cout<<"\n mul :="<<fun(a,b);


}
int sum(int a,int b){
return a+b;
}
int sub(int a,int b){
return a-b;
}
int mul(int a,int b){
return a*b;
}

/////////////////////////////////////////////
using switch for choice on sum,sum <br>
#include<iostream>
using namespace std;
int (*fun)(int,int);
int sum(int,int);
int sub(int,int);
int mul(int,int);
int main(){
//using function pointer doing sum mul
int a=40,b=30,x=0;
cout<<"enter choice \n";
cin>>x;
switch(x){
case 1:
fun=sum;
cout<<"\n sum :="<<fun(a,b);
break;
case 2:
fun=sub;
cout<<"\n sub :="<<fun(a,b);
break;
case 3:
fun=mul;
cout<<"\n mul :="<<fun(a,b);
break;
default: cout<<"enter right choice";
}




}
int sum(int a,int b){
return a+b;
}
int sub(int a,int b){
return a-b;
}
int mul(int a,int b){
return a*b;
}
///////////////////////////////////////////////////////////////////////////////////
same upper question now by using reference variable <br>
##### int sum(int &a,int &b);
for function syntax <br>
for declaration on top === int sum(int &,int &);

///
#include<iostream>
using namespace std;
int sum(int &,int &);
int sub(int &,int &);
int mul(int &,int &);
int main(){
//using function pointer doing sum mul
int a=40,b=30,x=0;
cout<<"enter choice \n";
cin>>x;
switch(x){
case 1:
cout<<"\n sum :="<<sum(a,b);
break;
case 2:
cout<<"\n sub :="<<sub(a,b);
break;
case 3:
cout<<"\n mul :="<<mul(a,b);
break;
default: cout<<"enter right choice";
}
//////////////////////////////////////////////////////

## assigment on class constructor

1=> write a data class along with constructor <br>
class std{
int a;
public:
std(int a){
this->a=a
}
};
int main(){
std a(10);
}
/////////////////////////////////////////////////////////
## operator overloading
operator overloading is a amazing functionality provided by the c++ which is not available in java,<br>
By the help of operator overloading we can add two objects also by using + operator, + operator is limited for arethmetic operations but by using operator overloading we can maximise the power of any operator.
////
class A { 
    statements; 
}; 
  
int main() 
{ 
    A a1, a2, a3; 
  
    a3 = a1 + a2; 
  
    return 0; 
}
in above code we are addin <br>
### operator overloading for adding two objects
#include<iostream>
using namespace std;
class Date{
int dd,mm,yy;
public:
Date(){
}
Date(int dd,int mm,int yy){
this->dd=dd;
this->mm=mm;
this->yy=yy;
}
void display(){
cout<<dd<<"-"<<mm<<"-"<<yy<<"\n";
}
//operator overloading
Date operator+(Date c){
Date date;
date.dd=dd+c.dd;
date.mm=mm+c.mm;
date.yy=yy+c.yy;
return date;
}


~Date(){}
};
int main(){
//date before update
Date d(05,10,2023),e(1,1,1),f;
d.display();
//date after update
f=d+e;
f.display();
}
### using getter setter om date for updating class values (asss- on point)
#include<iostream>
using namespace std;
class Point{
int x,y;
public:
Point(){
}
Point(int x,int y){
this->x=x;
this->y=y;
}
void setx(int x){
this->x=x;
}
void display(){
cout<<"("<<x<<","<<y<<")"<<"\n";
}
~Point(){}
};
int main(){
Point p(10,12);
p.display();
p.setx(99);
p.display();
}

## day-144
Integer class with copy constructor and operator overloading
///
#include<iostream>
using namespace std;
class Integer{
int a,b;
public:
Integer (){a=2;b=2;}
Integer (int aa,int bb){
a=aa;
b=bb;
}
// copy constructor
Integer(Integer const &m){
a=m.a;
b=m.b;
}
// operator overloading
Integer operator+(Integer const &ob){
Integer res;
res.a=a+ob.a;
res.b=b+ob.b;
return res;
}
//+= operator
Integer operator+=(Integer const &ob){
Integer res;
res.a=a+ob.a;
res.b=b+ob.b;
return res;
}
// bool == operator
bool operator==(Integer const &ob){
if(a==ob.a && b==ob.b) return true;

}
void display(){
cout<<a<<" " <<b<<"\n";
}
 
};
int main(){
Integer a,b(10,11),c(55,55),d(10,11);
a.display();
b.display();
a=b;
c=c+b;
c.display();
c+=b;
c.display();
if(c==d){cout<<"ok";}
return 0;
}
///
## 2D  matrix using pointer
// creating 2-D array with pointer
#include <iostream>
#include <Math.h>
using namespace std;

class Matrix{
int row,col;
int **mat;
//default constructor
public:
Matrix(){
row=2;
col=2;
// creating address spaces in mat
mat=new int *[row];
// creating colums value
for(int i=0;i<row;i++)
mat[i]=new int[col];
// filling array to 0
for(int i=0;i<row;i++){
for(int j=0;j<col;j++)
mat[i][j]=0;
}
}

Matrix(int r,int c){
row=r;
col=c;
mat=new int *[row];
}
// getting values of matrix from user
void input(){
for(int i=0;i<row;i++){
cout<<"enter matrix value \n";
for(int j=0;j<col;j++)
{
//cout<<"enter matrix value \n";
cin>>mat[i][j];
}
}
}

//for displaying matrix
void display(){
cout<<"our matrix will be \n";
for(int i=0;i<row;i++){
for(int j=0;j<col;j++)
cout<<mat[i][j]<<" ";
cout<<"\n";
}
}

// for copying matrix
Matrix (Matrix const &m){
row=m.row;
col=m.col;
mat=new int*[m.row];
for(int i=0;i<row;i++)
mat[i]=new int[col];

for(int i=0;i<row;i++){
for(int j=0;j<col;j++)
mat[i][j]=m.mat[i][j];
}

}


//destructor
~Matrix(){
for(int i=0;i<row;i++){
delete[] mat[i];
}
delete [] mat;
}
};
int main(){
Matrix a; 
a.input();
a.display();
Matrix b(a);
b.display();
return 0;
}
/////////////////////////////////////////
## program for String including strcpy for getting string
# include<iostream>
# include<string.h>
using namespace std;
class StringX{
int len;
char *str;
//creating public type
public:
// creating constructor
StringX(){
len=2;
str=new char[len];
strcpy(str,"\0");
}
//taking length 
StringX(int l){
len=l;
str=new char[len];
}
//talking string by base address of input string
StringX(char *p){
len=strlen(p);
str=new char[len];
strcpy(str,p);
}
// displaying string
void display(){
cout<<"string is => "<<str<<"\n";
}
// for copy constructor
StringX(StringX const & s){
len=s.len;
str=new char[len];
strcpy(str,s.str);
}

//operator overloading
StringX operator=(StringX const &o){

len=o.len;
str=new char[len];
strcpy(str,o.str);
return *this;
}
// for destructor
~StringX(){delete [] str;
str=NULL;}
};

int main(){
//StringX a(4);
StringX a("hell");
a.display();
StringX m(a),p;
m.display();
p=m;

p.display();
return 0;
}
////////////////////////////////////////////////////////////////////////////////////////////
# D-143      07-10-23
## polymorphsim and inheritance
inheritance in c++ can achive when child class is derived from parent class. "child:public parent{}",this will create a child class. <br>
A diamond problem will arise when the child class "D" is derived from calss "B" and "C" and the B C is also derived from "A", in this situation the methods in class A will also pass to B and C both on calling this function from class D the ambiguty will arrise.
To sole this ambiguty we will use "virtual" keyword after ":" during extension of parent class in child class.
//
class A{
};
class B:virtual public A{
};
class C:virtual public A{
};
class D:public B,public C{
};
//
### polymorphism
The parent class or base class can hold the address of its derived class or child class. <br>
A pure virtual function can be written to achive this.
#### pure virtual function
A vitual function is called virtual when it has no any methods written inside it "exp = virtual float A() =0;









































