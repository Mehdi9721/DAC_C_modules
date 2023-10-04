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






















