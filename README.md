# Ninjas-Recursion-1
#include <iostream>

using namespace std;
int factorial(int n){
    if(n==0){
        return 1; //Return used to stop code otherwise it would've gone till -(infinite)
    }
    int smalloutput=factorial(n-1);
    return n*smalloutput;
}
int Nth_Fibonacci(int n){
    if(n==1){
        return 0;
    }
    if(n==2){
        return 1;
    }
    int output= Nth_Fibonacci(n-1)+ Nth_Fibonacci(n-2);
    return output;
}
bool Arraysortedornot(int arr[], int n){
    if(n==0 || n==1){
        return true;
    }
    if(arr[0]>arr[1]){
        return false;
    }
    bool IssmallerArraysorted= Arraysortedornot(arr+1,n-1);
       return IssmallerArraysorted;
}
int Power(int m, int n){
   if(n==1){
    return m;
   }
    int pow=m*Power(m,n-1);
    return pow;

}
void Printnums(int n){
    if(n==1){
        cout<<n<<endl;
        return;
    }
    Printnums(n-1);
    cout<<n<<endl;
}
int Arrsum(int a[], int n){
    if(n==0){
        return 0;
    }

    return a[0] + Arrsum(a+1,n-1);


}
bool Numberinarrayornot(int a[], int n,int x){
    if(n==0){
        return false;
    }
    else if(a[0]==x){
        return true;
    }
    return Numberinarrayornot(a+1,n-1, x);
}

int main()
{
    //Factorial
    int n;
    cin>>n;
    int output= factorial(n);
    cout<<output<<endl;
    //Recursion is based on principle of mathematical induction
    //That is proving the fact for x=0 or x=1 for f(x)
    //Then assume that f(k) is true
    //Final induction step===> Using the fact that f(k) is true prove that f(k+1) is true
    //Recursion funda:
    //1) First make the base case (for example we made fact(0)=1;)
    //2) Now make the case for f(n) and assume that it works for f(n-1).
    //3) Zyada dimaag na lagao recursion mein




    //Write the program to print fibonacci numbers:
    cout<<"Which number term of Fibonacci do you need?"<<endl;
    int m;
    cin>>m;
    int Nthfibo=Nth_Fibonacci(m);
    cout<<Nthfibo<<endl;

    //Write a program to check whether the given array is sorted or not by using recursion
    int arr[100];
    cout<<"The size of arrays should be: "<<endl;
    int k;
    cin>>k;
    for(int i=0;i<k;i++){
        cin>>arr[i];
    }
    bool sort=Arraysortedornot(arr,k);
    if(sort){
        cout<<"Sorted array"<<endl;
    }
    else{
        cout<<"Unsorted array"<<endl;
    }
    //Write a program to get nth power of integer m
    cout<<"Type in the base and exponent"<<endl;
    int y,u;
    cin>>y>>u;
    int out= Power(y,u);
    cout<<out<<endl;
    //Print numbers from 1 to n recursively
    cout<<"Upto how many numbers you have to print?"<<endl;
    int b;
    cin>>b;
    Printnums(b);
    //Write a recursion code to print the sum of digits of an array
    int arrr[10];
    cout<<"The size of arrays should be: "<<endl;
    int c;
    cin>>c;
    for(int i=0;i<c;i++){
        cin>>arrr[i];
    }
    int ourput=Arrsum(arrr,c);
    cout<<ourput<<endl;
    //Write a program to check whether a number occur in the given array or not
      int ar[100];
    cout<<"The size of arrays should be: "<<endl;
    int x;
    cin>>x;
    for(int i=0;i<x;i++){
        cin>>ar[i];
    }
    cout<<"Type in the number you want to search for"<<endl;
    int f;
    cin>>f;
    bool Presornot= Numberinarrayornot(ar,x,f);
    if(Presornot){
        cout<<"Yes it is present in array"<<endl;
    }
    else{
        cout<<"No it is not present in array"<<endl;
    }





    return 0;
}
