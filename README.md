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








































